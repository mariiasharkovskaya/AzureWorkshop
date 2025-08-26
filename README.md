az aks get-credentials --resource-group atom-demo --name atom-demo
kubectl get namespaces
kubectl create namespace mariia-shark-argocd
kubectl config set-context argocd --cluster=atom-demo --user=clusterUser_atom-demo_atom-demo --namespace=mariia-shark-argocd
kubectl apply -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
kubectl get all
kubectl get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode; echo
kubectl port-forward svc/argocd-server 8080:443 &
localhost:8080 -> [ArgoCD] username:admin; password:password
brew install argocd
argocd login localhost:8080 --username admin --password vRKqjnDUIamLwehh  --insecure
argocd app list
ps aux | grep kubectl
killall -9 kubectl
argocd logout localhost:8080
