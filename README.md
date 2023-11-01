in cmd:
minikube start
terraform init
terraform plan
terraform apply


kubectl get pods -n argocd
kubectl port-forward svc/argocd-server -n argocd 8080:80

in browser goto: 
localhost:8080  -> should see argocd homepage

username: admin
get password:
kubectl get secrets argocd-initial-admin-secret -o yaml -n 

**decrypt password**
linux:
echo "copied_password_here" | base64 -d

Windows:
$file = "C:\password\input.txt"
$data = Get-Content $file
[System.Text.Encoding]::ASCII.GetString([System.Convert]::FromBase64String($data)) > out.html