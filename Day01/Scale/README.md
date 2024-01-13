# Manual scale an application

Here is a short demo how to manual scale an applicaton in kubernetes.


## Required for this Course 

Some prerequirements are needed. In this case only kubectl is required. 
Helm is already installed by setting up the AKS cluster.

```bash
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
sudo az aks install-cli
```

## Clone the repository

Clone the Repo, so you have access to the Kubernetes Manifest files of the demo apps.

```bash
git clone https://github.com/dpaardenkooper/K8S-Course.git
```
## deploy the Azure Voting app

Lets install the "Azure Voting app" (via kubectl)

```bash
cd ./K8S-Course/Day01/Demo-apps/hello-world
kubectl apply -f hello-world.yaml
```

## Manual scale

Lets manual scale the deployment from 1 to 50

```bash
kubectl get deploy
kubectl scale deploy azure-vote-front --replicas=50
kubectl get pod -w
```
