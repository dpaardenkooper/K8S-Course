# Working with helm

The purpose of this lab is to understand how helm works.
To experience this, we will work with the helm chart of nginx.

## Required for this course

An running Kubernetes environment.
On your client the installation of Helm, which you can find at [this link](/Day01/Helm/).


## installing a helm chart.
To install a Helm chart, you first have to add the repo.
Then you have to update the cache of helm.

```bash
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
```

After that you can install it:

```bash
helm install ingress-nginx --version 4.3.0 ingress-nginx/ingress-nginx --namespace ingress-nginx   
```

## Upgrading a helm chart.
Overtime, new versions of the helm chart will come out, since they work on specific Kubernetes versions. 
Alwasy check the documentation for the correct version. In our case, it will be nginx 4.9.0: https://github.com/kubernetes/ingress-nginx

Use the following command to upgrade your chart.

```bash
helm repo update
helm upgrade ingress-nginx --version 4.9.0 ingress-nginx/ingress-nginx --namespace ingress-nginx  
```

> **Remark**
> It is always best practice not to use the "latest" tag. In the latest tags there could be some bugs not being fixed or elements not working properly. Always check the docs!


## Rolling back a helm chart.
If the upgrade didn't work as planed, you can mostly revert back to the old edition.

> **Remark**
> Mostly means if the charts aren't to big of a difference and that they both support the Kubernetes version they should run. Always check the docs!

Use the following command to upgrade your chart.

```bash
helm rollback ingress-nginx --version 4.3.0 ingress-nginx/ingress-nginx --namespace ingress-nginx   
```


## Uninstall back a helm chart.
If want to remove the helm chart, you can use the following command.

```bash
helm uninstall ingress-nginx --version 4.3.0 ingress-nginx/ingress-nginx --namespace ingress-nginx 
```