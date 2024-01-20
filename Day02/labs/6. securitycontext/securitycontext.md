# Short demo concerning securitycontext
The purpose of this lab is to see what you can do at the securitycontext.

## Required for this course
A Running Kubernetes environment.

## Scenario 1 - Run the pod as a User.
You will change the securityContext so the container does not run as Root.

### Create a simple pod
In this example we create a pod based on busybox container.

```bash
kubectl run pod --image=busybox --command -oyaml --dry-run=client > pod.yaml -- sh -c 'sleep 1d'
kubectl get pod
```

### See the current user and group
First verify the current user and group.

```bash
kubectl exec -it pod -- sh
id
```

Verify if you can make a file

```bash
touch test
ls -lh test
```


### change the user and group
Lets change the user and group in the pod.

Open the documentation and reuse some code located at: https://kubernetes.io/docs/tasks/configure-pod-container/security-context/#set-the-security-context-for-a-pod.

Open the current pod.yaml
If the code is pasted in, it should look like this:

```bash
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: pod
  name: pod
spec:
  securityContext:
    runAsUser: 1000
    runAsGroup: 3000
  containers:
  - command:
    - sh
    - -c
    - sleep 1d
    image: busybox
    name: pod
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```

### Update the pod
Lets see the new changes. Delete the pod and recreate it.

```bash
kubectl delete -f pod.yaml --force --grace-period 0
kubectl apply -f pod.yaml
```


### See the current user and group from the pod
Recheck the current user and group.

```bash
kubectl exec -it pod -- sh
id
```

Verify if you can make a file

```bash
touch test
ls -lh test
```

Result should be "Permission denied".
If someone is trying to break out, they don't have root or write permissions.


## Scenario 2 - RunasNonRoot the container as a User.
You will change the securityContext so the container does not run as Root.

### Change the pod
You will change the pod.

Open the current pod.yaml. At at container level the securityContext. It look like this:

```bash
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: pod
  name: pod
spec:
  securityContext:
    runAsUser: 1000
    runAsGroup: 3000
  containers:
  - command:
    - sh
    - -c
    - sleep 1d
    image: busybox
    name: pod
    resources: {}
    securityContext:
      runAsNonRoot: true
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```

### Update the pod
Lets see the new changes. Delete the pod and recreate it.

```bash
kubectl delete -f pod.yaml --force --grace-period 0
kubectl apply -f pod.yaml
```

The pod should run. This is because we have on top level, the securitycontext placed that it runs as user.
Lets remove this part. 


### Change the pod again
Change the pod.yaml file and comment the SecurityContext.

Open the current pod.yaml. At at container level the securityContext. It look like this:

```bash
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: pod
  name: pod
spec:
#  securityContext:
#    runAsUser: 1000
#    runAsGroup: 3000
  containers:
  - command:
    - sh
    - -c
    - sleep 1d
    image: busybox
    name: pod
    resources: {}
    securityContext:
      runAsNonRoot: true
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```

### See the changes
Lets see the new changes. Delete the pod and recreate it.

```bash
kubectl delete -f pod.yaml --force --grace-period 0
kubectl apply -f pod.yaml
kubectl get pod
```

Result should be "CreateContainerConfigError".
To get the reason, do the following:

```bash
kubectl describe pod pod
```

Result should be "Error: container has runAsNonRoot and inage will run as Root".
