#### Random commands
* List all through argo cli
  * argo list --verbose --loglevel debug --all-namespaces
* Submit a workflow
  * argo submit -n argo workflow2.yaml
* Get all workflows
  * kubectl get workflows -n argo
* Get workflow details
  * kubectl describe workflows k8s-jobs-nv7n9 -n argo
* Submit workflow with namespace and service account
  * argo submit --serviceaccount=workflow --namespace argo workflow2.yaml

#### Argo authentication 
* Get all argo role bindings 
  * kubectl get rolebinding  -n argo
* Get all argo roles
  * kubectl get role  -n argo
* Get argo service account yaml
  * kubectl get sa argo -n argo -o yaml
* Create service account
  * kubectl create serviceaccount workflow -n argo
* Create role binding with exist argo-role
  * kubectl create rolebinding workflow --role=argo-role --serviceaccount=argo:workflow
* Create K8 RBAC ClusterRole across namespace
  * https://medium.com/faun/kubernetes-rbac-use-one-role-in-multiple-namespaces-d1d08bb08286
