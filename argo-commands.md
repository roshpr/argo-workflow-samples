#### Random commands
List all through argo cli
* argo list --verbose --loglevel debug --all-namespaces
Submit a workflow
* argo submit -n argo workflow2.yaml
Get all workflows
* kubectl get workflows -n argo

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
