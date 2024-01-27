Internet links mentioned in the Presentation Day03:

<br>

Deployment - the manual way:
- Docker 
    - Docker file: https://docs.docker.com/engine/reference/builder/
    - docker build: https://docs.docker.com/build/guide/intro/
    - docker builder: https://docs.docker.com/engine/reference/builder/
- Dockercompose (docker environment)
    - docker compose: https://docs.docker.com/compose/
    - docker compose works.
- Convert docker compose to kubernetes:
    - Kompose: https://kompose.io/
    - Kubernetes: https://kubernetes.io/docs/tasks/configure-pod-container/translate-compose-kubernetes/
- kustomize
    - general: https://kustomize.io/
    - intro: https://kubectl.docs.kubernetes.io/guides/introduction/kustomize/
    - kubernetes configuration that can be changed: https://kubectl.docs.kubernetes.io/guides/config_management/
    - helm
    - general: https://helm.sh/
    - install: https://helm.sh/docs/intro/install/
    - chart guide: https://helm.sh/docs/chart_template_guide/getting_started/

Deployment - the automated way
- CI/CD:
    - Github
        - Marketplace GitHub actions - kubernetes deployment: https://github.com/marketplace/actions/deploy-to-kubernetes-cluster
        - Marketplace GitHub actions - azure: https://github.com/marketplace?category=&type=actions&verification=&query=azure
    - Azure
        - Docs Azure github actions: https://learn.microsoft.com/en-us/azure/aks/kubernetes-action
        - Azure DevOps
            - Kubectl task: https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/reference/kubernetes-v1?view=azure-pipelines
            - KubernetesManifests task: https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/reference/kubernetes-v1?view=azure-pipelines
            - HelmInstaller task: https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/reference/helm-installer-v1?view=azure-pipelines
            - Helm deploy task:https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/reference/helm-deploy-v0?view=azure-pipelines
            - Azure DevOps pipeline:
                - https://learn.microsoft.com/en-us/azure/aks/devops-pipeline?tabs=cli&pivots=pipelines-yaml
                - https://learn.microsoft.com/en-us/azure/aks/devops-pipeline?tabs=cli&pivots=pipelines-yaml

<br>

Deployment - the next level:
- Gitops
    - Azure:
        - https://learn.microsoft.com/en-us/azure/architecture/guide/aks/aks-cicd-github-actions-and-gitops
        - Github: https://learn.microsoft.com/nl-nl/azure/architecture/guide/aks/aks-cicd-github-actions-and-gitops
        - Azure devops: https://learn.microsoft.com/nl-nl/azure/architecture/example-scenario/gitops-aks/gitops-blueprint-aks
    - Flux:
        - general: https://fluxcd.io/flux/
        - roadmap: https://fluxcd.io/roadmap/
        - github: https://github.com/fluxcd/flux2
        - releases: https://github.com/fluxcd/flux2/releases
        - walktrough: https://www.youtube.com/watch?v=X5W_706-jSY
    - ArgoCD:
        - general: https://argo-cd.readthedocs.io/en/stable/
        - roadmap: https://github.com/orgs/argoproj/projects/25/views/14
        - github: https://github.com/argoproj/argo-cd
        - releases: https://github.com/argoproj/argo-cd/releases
        - learn: https://learning.codefresh.io/start
        - walkthrough: https://www.youtube.com/watch?v=Yb3_4PZX0B0
