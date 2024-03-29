# demo-terraform-aks
AKS deployment AKS with Mysql Service and wordpress app with HPA and peering to azureVM


Manual Deployment
```bash
az login
az account list
az account set --subscription <id>
cd aks-sql-vm/
terraform init
terraform plan
terraform apply
az aks get-credentials --resource-group demo-terraform-aks --name dev-demo
```

## Create Public and Private load balancers

```bash
kubectl apply -f kubernetes/public-private-lb
kubectl get svc

```

## Auto-Scaling

```bash
kubectl get nodes
kubectl apply -f kubernetes/autoscaling
kubectl get pods
kubectl describe pods {{ podname }}
kubectl get pods
kubectl get nodes
```

## Create an Ingress using Nginx Ingress with Secure TLS & Cert-manage

```bash
kubectl get svc -n ingress
kubectl apply -f kubernetes/wordpress
kubectl get pods
kubectl get ing

kubectl get Certificate
kubectl describe Certificate
kubectl describe CertificateRequest
kubectl describe Order
kubectl describe Challenge

kubectl get ing
kubectl get Certificate
kubectl get ing
```

## Setup Horizontal Pod Autoscaler

```bash
kubectl apply -f kubernetes/hpa
kubectl get pods 
kubectl describe pods <podname>
```


## Setup peering vm to aks

```bash
by default we dont need peering since we place the vm to subnet2 under the same VNet
```