# CLuster Creation using az cli
# Create a RG ,
az group create --name dev-cluster --location centralindia
# Create cluster using az cli,
az aks create 
 --resource-group dev-cluster 
  --name dev-env 
  --node-count 2 
  --enable-addons monitoring 
 --generate-ssh-keys
 # Get AKS credentails,
az aks get-credentials --resource-group dev-cluster --name dev-env

# List Kubernetes Worker Nodes
kubectl get nodes 
kubectl get nodes -o wide
