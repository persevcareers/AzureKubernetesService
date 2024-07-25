# Installation of NGINX Ingress Controller on Azure Kubernetes Service

## Creating a Resource group ,
```bash
az group create --name dev-env --location centralindia
```
## Creating a AKS cluster ,
```bash
az aks create 
 --resource-group dev-env
  --name dev-env 
  --node-count 2 
  --enable-addons monitoring 
 --generate-ssh-keys
```
## Connecting to AKS cluster
```bash
az aks get-credentials --resource-group dev-env --name aks-dev-env
```
## To install the NGINX Ingress Controller on your Kubernetes cluster, follow these steps:

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.10.0/deploy/static/provider/cloud/deploy.yaml
```
## It creates all different required resources in ingress-nginx namespace.

## Deployment of application , 
  kubectl apply of deployment-v1.yml and deployment-v2.yml two different paths with two different versions of a product.
 
 Deploy your application with manifest which have deployment and svc as well.
 
 Post which , we can now deploy ingress resources which will be deploy gets external ip of the load balancer deployed during nginx ingress controller installation.
