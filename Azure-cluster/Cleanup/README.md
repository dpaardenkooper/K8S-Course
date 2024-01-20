#  Clean up

## 1. Removing the AKS Cluster

```bash
az aks delete --name aks-course-weu-01 --resource-group rg-k8s-course -y 
```
> Note: It might take 3-6 minutes to delete the cluster


## 2. Removing the Azure Resource Group

```bash
az group delete --resource-group rg-k8s-course -y
```

## 3. Removing the AKS Kubeconfig Entries

```bash
kubectl config delete-cluster aks-course-weu-01
kubectl config delete-context aks-course-weu-01
kubectl config delete-user clusterUser_rg-k8s-course_aks-course-weu-01
```

## 4. Deleting the Cloud Shell Instance

```bash
clouddrive unmount
```
> You will be prompted to confirm twice.

>WARN: Removing a file share from Cloud Shell will terminate your current session.
Do you want to continue(y/n): y

> WARN: You will be prompted to create and mount a new file share on your next session.
Do you want to continue(y/n): y