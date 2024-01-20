# Falco - Block Syscalls and protect the Kernal 
The purpose of this lab is to get an understanding how to visualize syscalls at the host or containerlevel and an short overview how to act with rules.

## Required for this course
A Running Kubernetes environment.
Log in into a worker or master node.

## Installing it standalone (could also be via helm chart) on your workernode
For demo purposes, it was choosen to install it standalone, to give you a view how the tool is working.
To the following steps on your worker node:

```bash
curl -s https://falco.org/repo/falcosecurity-packages.asc | apt-key add -
echo "deb https://download.falco.org/packages/deb stable main" | tee -a /etc/apt/sources.list.d/falcosecurity.list
apt-get update -y
apt-get install -y linux-headers-$(uname -r)
apt-get install -y falco
```

To verify if it is running correctly:

```bash
service falco status
service falco start
```

## Investigating Falco files
Open de install directory to see the falco files:

```bash
cd /etc/falco
```

## Look into the configuration file of falco
Open the falco.yaml file to see the configuration of falco.

```bash
vim falco.yaml
```

## What does Falco currently detect
With the following command, you can see that falco realtime detects.

```bash
tail -f /var/logs/syslog | grep falco
echo user >> /etc/passwd
apt-get update
tail -f /var/logs/syslog | grep falco
```

## Make on your master node a pod to see how Falco will respond
Lets first make a pod and get inside the pod

```bash
kubectl apply -f apache.yaml
kubectl exec -it apache -- bash
cat /etc/passwd
echo user >> /etc/passwd
apt-get update
```

## Switch back to the worker node
Lets see what message falco has given you.

Response1: Notice A Shell was spawned in a container with attached terminal
Response2: Error File below /etc opened for writing.
Response3: Error package management process launched in container.


## See the default falco Rules
Lets dive into the falco rules to understand which messages it gives you.
Open your workernode

```bash
cd /etc/falco
ls
vim falco_rules.yaml
## search on /was spawned
vim k8s_audit_rules.yaml
## search on /etc
```