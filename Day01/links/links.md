Internet links mentioned in the Presentation Course-day01:

<br>

Deployments:
- Kubernetes
    - Pods: https://kubernetes.io/docs/concepts/workloads/pods/
    - Deployment: https://kubernetes.io/docs/concepts/workloads/controllers/deployment/
    - Deployment - Statefull: https://kubernetes.io/docs/tutorials/stateful-application/basic-stateful-set/
    - Deployment - Stateless: https://kubernetes.io/docs/tutorials/stateless-application/expose-external-ip-address/
    - Service: https://kubernetes.io/docs/concepts/services-networking/service/
    - ingress: https://kubernetes.io/docs/concepts/services-networking/ingress/
    - Replicaset: https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/
    - jobs: https://kubernetes.io/docs/concepts/workloads/controllers/job/
    - cronjobs: https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/
    - daemonset: https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/

CNI:
- kubernetes
    - https://kubernetes.io/docs/concepts/extend-kubernetes/compute-storage-net/network-plugins/
- calico
    - https://docs.tigera.io/calico/latest/getting-started/kubernetes/managed-public-cloud/aks
    - https://academy.tigera.io/course/certified-calico-operator-level-1/
    - https://academy.tigera.io/course/certified-calico-operator-azure-expert/
- Azure:
    - https://learn.microsoft.com/en-us/azure/aks/concepts-network
    - https://learn.microsoft.com/nl-nl/azure/aks/azure-cni-powered-by-cilium
    - https://learn.microsoft.com/nl-nl/azure/aks/use-byo-cni?tabs=azure-cli
    - https://learn.microsoft.com/nl-nl/azure/aks/azure-cni-overlay?tabs=kubectl
    - https://learn.microsoft.com/nl-nl/azure/aks/azure-cni-powered-by-cilium
    - https://learn.microsoft.com/nl-nl/azure/aks/configure-kubenet
- Cilium:
    - https://isovalent.com/blog/post/isovalent-aks/
    - https://cilium.io/labs/
- Other:
    - https://medium.com/@amitmavgupta/cilium-pod-sandboxing-in-aks-and-azure-cni-powered-by-cilium-b6586e831c64


DNS:
- Kubernetes
    - https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/

Storage:
- Kubernetes
    - Persistent volume: https://kubernetes.io/docs/concepts/storage/persistent-volumes/#persistent-volumes
    - Persistent volume access modes: https://kubernetes.io/docs/concepts/storage/persistent-volumes/#access-modes
    - Persistent volume claim: https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/#create-a-persistentvolumeclaim
    - create pod with PVC: https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/#create-a-pod
    - Peristent volume types: https://kubernetes.io/docs/concepts/storage/persistent-volumes/#types-of-persistent-volumes
    - Volume snapshot: https://kubernetes.io/docs/concepts/storage/persistent-volumes/#volume-snapshot-and-restore-volume-from-snapshot-support
    - Storage class: https://kubernetes.io/docs/concepts/storage/storage-classes/#storageclass-objects
- azure:
    - storage: https://learn.microsoft.com/en-us/azure/aks/concepts-storage
    - csi: https://learn.microsoft.com/nl-nl/azure/aks/csi-storage-drivers
    - Azure Blob storage: https://learn.microsoft.com/en-us/azure/aks/azure-blob-csi?tabs=NFS
    - Azure File storage: https://learn.microsoft.com/en-us/azure/aks/azure-files-csi


Scaling:
- Kubernetes
    - https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/
    - https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale-walkthrough/
    - https://github.com/kubernetes/autoscaler/tree/master/vertical-pod-autoscaler
- Microsoft:
    - https://learn.microsoft.com/en-us/azure/aks/vertical-pod-autoscaler
    - https://learn.microsoft.com/en-us/azure/aks/keda-about
    - https://learn.microsoft.com/en-us/azure/aks/concepts-scale
    - https://learn.microsoft.com/en-us/azure/aks/concepts-scale#horizontal-pod-autoscaler
- Keda:
    - https://keda.sh/docs/2.12/concepts/
    - https://keda.sh/docs/2.12/concepts/scaling-deployments/


Servicesmesh:
- Comparison: https://servicemesh.es/


ebpf:
- ebpf:
    - https://ebpf.io/what-is-ebpf/
- calico:
    - https://academy.tigera.io/course/certified-calico-operator-ebpf/
- cilium:
    - https://isovalent.com/labs/security-observability-with-ebpf-and-cilium-tetragon/


Exam
- Linuxfoundation:
    - LFS158 - Introduction to Kubernetes (free)   
      https://training.linuxfoundation.org/training/introduction-to-kubernetes/
    - CKA - Certified Kubernetes Administrator (595 dollar incl. exam)   
      https://training.linuxfoundation.org/certification/certified-kubernetes-administrator-cka/
    - CKAD -  Certified Kubernetes Application Developer (595 dollar incl. exam)   
      https://training.linuxfoundation.org/certification/certified-kubernetes-application-developer-ckad/
    - KCNA - Kubernetes and Cloud Native Associate (299 dollar incl. exam)   `
      https://training.linuxfoundation.org/certification/kubernetes-cloud-native-associate/
- Udemy:
    - Kubernetes CKA (Administrators)
      https://www.udemy.com/course/certified-kubernetes-administrator-with-practice-tests/
    - Kubernetes CKAD (Developers)
      https://www.udemy.com/course/certified-kubernetes-application-developer/
    - Kubernetes CKS (Security)
      https://www.udemy.com/course/certified-kubernetes-security-specialist/
- CNCF – Cloud Native Training Courses:
    - Courses
      https://www.cncf.io/training/courses/
    - Certifications
      https://www.cncf.io/training/certification/
    - Certificate path
      https://www.cncf.io/training/
- Other:
    - Medium “Exam tips and tricks”:
      https://blog.itlogic.io/how-i-passed-kubernetes-kcna-ckad-cka-and-cks-exams-my-experience-exam-tips-and-tricks-5a82819eb49c
    - Kubernetes.io “Cheatsheet”
      https://kubernetes.io/docs/reference/kubectl/quick-reference/
