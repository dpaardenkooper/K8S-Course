# Viewing the Kubernetes Cert locations

The purpose of this lab is to get an understanding where Kubernetes stores it's certificates.

## Required for this course

A Kubernetes environment, where you can log in into the Kubernetes Worker or Master node. 

## Opening the location of the certificate path
Log into your master or worker node.

```bash
cd /etc/kubernetes/pki
ll
```

Depending on which node you are, you will see all the certificates which are used in Kubernetes.