#### Random commands
* argo list --verbose --loglevel debug --all-namespaces
* argo submit -n argo workflow2.yaml

#### Argo authentication 
Get all argo role bindings 
* kubectl get rolebinding  -n argo
Get all argo roles
* kubectl get role  -n argo
Get argo service account yaml
* kubectl get sa argo -n argo -o yaml
Create service account
* kubectl create serviceaccount workflow -n argo
Create role binding with exist argo-role
* kubectl create rolebinding workflow --role=argo-role --serviceaccount=argo:workflow
