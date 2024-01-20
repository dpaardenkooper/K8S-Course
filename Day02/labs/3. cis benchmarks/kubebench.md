# Using CIS Benchmark to review your Kubernetes cluster

The purpose of this lab is to get an overview of the hardeing of your Kubernetes Master or Worker.

## Required for this course

A Kubernetes environment, where you can log in into the Kubernetes Worker or Master node. 
Check for the correct CIS benchmark, at their site: https://www.cisecurity.org/benchmark/kubernetes.

## Opening the location of the certificate path
Open the github page of kubebench: https://github.com/aquasecurity/kube-bench/blob/main/docs/running.md

```bash
docker run --pid=host -v /etc:/etc:ro -v /var:/var:ro -t docker.io/aquasec/kube-bench:latest --version 1.18
```

Version could be changed. Always check the GitHub page, for the latest version.