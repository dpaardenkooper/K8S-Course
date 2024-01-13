#  Clean up

## 1. Removing the apps

Use the following commands to delete the Demo-apps

```bash
cd ./K8S-Course/Day01/Demo-Apps
kubectl delete -f ./hello-world --force
kubectl delete -f ./azure-votingapp --force
kubectl delete -f ./Ingress-app --force
```

## 2. Removing the helm chart of ingress.

```bash
az group delete --resource-group rg-k8s-course -y
```
