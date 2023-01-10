# Deploy an application with Helm

## Setup

- Helm 3
- Docker
- Access to a Kubernetes cluster or a tool to create a local cluster e.g.
  - kind
  - minikube
  - K3s
  - k3d
  - MicroK8s
- Deploy an ingress controller

---

## Deliverables

- Create a Helm chart that deploys two instances of the `http-echo` application
- Both instances:
  - run the image `hashicorp/http-echo:0.2.3`
  - use the argument `--text=hello`
- One instance:
  - should be a `Deployment`
  - the other a `StatefulSet`
- One instance:
  - listens on port `8080`
  - the other on `8081`
- Helm chart must include the following resources at minimum:
  - Ingress
  - Deployment

---

## Validation

- `helm lint` should pass
- `curl http://localhost:8080` and `curl http://localhost:8081` must return `hello`
