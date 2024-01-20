# strace - Visualize the Syscalls
The purpose of this lab is to get an understanding how to visualize the syscalls that are happening at host or container level.

## Required for this course
A Running Kubernetes environment.
Log in into a worker or master node.

## Scenario 1 - how does strace work - simple test
In this example you will experience how strace works.
Log in into a worker or master node.

```bash
ls
strace ls /
strace -cw ls /
echo hello > test
cat test
strace cat test
```

## Scenario 2 - strace in acction on the masternode
In this example you will see the syscalls being made to ETCD.
Log in into a worker or master node.

### Grabbing the PID of ETCD
Lets first grep the PID of ETCD.

```bash
list syscalls
crictl ps | grep etcd
ps aux | grep etcd
strace -p <pid>
strace -p <pid> -f -cw (see how many syscalls it made)
```

### Looking for open files of ETCD pod
Reuse the PID and see if there are files open in the ETCD container.

```bash
strace -p <pid>
cd /proc/<pid>
ls
```

### Looking for executable files of ETCD pod
Reuse the PID and see if there are executables in the ETCD container.

```bash
ls -lh exe >>> see the executable
cd fd
cd ls -lh
cat environ
```