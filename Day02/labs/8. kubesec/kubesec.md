# Kubesec - Static analysis on Kubernetes Manifest files 
The purpose of this lab is to get an understanding how to statically scan your Kubernetes Manifest files.

## Required for this course
A Running Kubernetes environment.

## Create a simple pod
In this example we create a pod.

```bash
kubectl run nginx --image=nginx -oyaml --dry-run=client > pod.yaml
cat pod.yaml
```

# Verify with Kubesec
Lets see what is wrong confirm Kubesec.

Open the documentation and get the line of code: https://kubesec.io/#docker-usage.
Change at the end of the code, the pod name to the correct manifest file.


```bash
docker run -i kubesec/kubesec:512c5e0 scan /dev/stdin < pod.yaml
```

Result: it returns a json file with things it observed from the Kubernetes manifest file.
