# What if you had acces to the workernode
The purpose of this lab is to see info which is available on the worker node.

## Required for this course
A Running Kubernetes environment with access to a workernode.

## Create a simple pod
In this example we create a pod with a secret in it.

```bash
kubectl run inspect --image=nginx -oyaml --dry-run=client > inspect.yaml
```

To add a secret in a variable, we can reuse some code located at: https://kubernetes.io/docs/tasks/inject-data-application/define-environment-variable-container/#using-environment-variables-inside-of-your-config.

If the code is pasted in, it should look like this:

```bash
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: inspect
  name: inspect
spec:
  containers:
  - image: nginx
    name: inspect
    resources: {}
    env:
    - name: USERNAME
      value: "demo-admin"
    - name: PASSWORD
      value: "demo-password"
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```

> **Warning**
> The example above is not a best practices. This is just an example, to show you what is readable if you would have access to the workernode. 


## Run the pod
Deploy the yaml file.

```bash
kubectl apply -f ./inspect.yaml
kubectl get pod
```

## Log in into the pod
Deploy the yaml file.

```bash
kubectl exec -ti  inspect -- bash
env
exit
```

## Now from the worker node view
Log in onto a workernode if this is possible. In this demo, this is done an a GKE Kubernetes cluster for demonstrating purposes.
Use crictl (like docker), to view all the containers.

```bash
crictl ps
crictl inspect <containerid>
crictl inspect <containerid> | vim -
crictl inspect <containerid> | cat PASSWORD
crictl inspect <containerid> | grep PASSWORD
ps aux | grep <PIDnr>
```

### Check the /PROC directory based on the containerid it's PID
When the PID is known, you can go and do the following:

```bash
find /proc/<PIDnr>/root/etc
```