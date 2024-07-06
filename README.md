# Cluster Creation using az cli
## Create a RG ,
```t
az group create --name dev-cluster --location centralindia
```
## Create cluster using az cli,
```t
az aks create 
  --resource-group dev-cluster \
  --name dev-env \
  --node-count 2 \
  --enable-addons monitoring \
  --generate-ssh-keys
```
## Get AKS credentails,
```t
az aks get-credentials --resource-group dev-cluster --name dev-env
```
## List Kubernetes Worker Nodes
```t
kubectl get nodes 
```
