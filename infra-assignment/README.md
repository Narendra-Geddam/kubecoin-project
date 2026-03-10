# Infra Assignment

This folder contains a Jenkins + Kubernetes setup for:
- Building backend and frontend images with Kaniko.
- Pushing images to Docker Hub using `dockerhub-creds`.
- Deploying infrastructure services (PostgreSQL) in `infra` namespace.
- Deploying application services (backend, frontend) in `app` namespace.

## Structure

- `Jenkinsfile`: Pipeline to build/push images and deploy manifests.
- `k8s/00-namespaces.yaml`: Namespace definitions.
- `k8s/infra/`: Infra resources (DB).
- `k8s/app/`: Application resources.

## Deploy Manually

```bash
kubectl apply -f infra-assignment/k8s/00-namespaces.yaml
kubectl apply -f infra-assignment/k8s/infra/
kubectl apply -f infra-assignment/k8s/app/
```

## Jenkins RBAC (One-Time)

```bash
kubectl apply -f infra-assignment/k8s/rbac/jenkins-helm-deployer-rbac.yaml
```

## Notes

- Update image repository values in `k8s/app/*deployment.yaml` to your Docker Hub repo.
