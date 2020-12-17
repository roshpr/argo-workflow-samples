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
