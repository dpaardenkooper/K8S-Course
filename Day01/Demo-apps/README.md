# Create your first app in Kubernetes

On this page you will deploy your first apps. In the previous step, you have deployed an AKS Cluster.
Before we can deploy apps, list first arrange the prerequirements. If you use the Cloudshell you can skip the next step. 

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

## First app deployment - hello-world

Lets install the first demo app "Hello-World" (via kubectl)

```bash
cd ./K8S-Course/Day01/Demo-apps/hello-world
kubectl apply -f hello-world.yaml
```

## Second app deployment - Azure Voting app

Lets install the second demo app "Azure Voting app" (via kubectl)

```bash
cd ./K8S-Course/Day01/Demo-apps/hello-world
kubectl apply -f hello-world.yaml
```

## Third app deployment - Nginx via Ingress

Lets install the second demo app "Azure Voting app" (via kubectl). To do this, we first need an ingress controller.

```bash
helm install ingress-nginx --version 4.3.0 ingress-nginx/ingress-nginx --namespace ingress-nginx --create-namespace --set controller.service.annotations."service\.beta\.kubernetes\.io/azure-load-balancer-health-probe-request-path"=/healthz
cd ./K8S-Course/Day01/Demo-apps/hello-world
kubectl apply -f hello-world.yaml
```
