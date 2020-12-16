Add additional roles for API group helmrelease to Argo role

$ kubectl get role argo-role  -n argo -o yaml > argo_role.yaml

Add the API group helm.fluxcd.io
====
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  annotations:
  name: argo-role
  namespace: argo
  selfLink: /apis/rbac.authorization.k8s.io/v1/namespaces/argo/roles/argo-role
rules:
- apiGroups:
  - ""
  resources:
  - pods
  - pods/exec
  verbs:
  - create
  - get
  - list
  - watch
  - update
  - patch
  - delete
- apiGroups:
  - "helm.fluxcd.io"
  resources:
  - helmreleases
  verbs:
  - create
  - get
  - watch
  - list
  - update
  - delete
  - patch
- apiGroups:
  - ""
  resources:
  - configmaps
  verbs:
  - get
  - watch
  - list
- apiGroups:
  - ""
  resources:
  - persistentvolumeclaims
  verbs:
  - create
  - delete
- apiGroups:
  - argoproj.io
  resources:
  - workflows
  - workflows/finalizers
  verbs:
  - get
  - list
  - watch
  - update
  - patch
  - delete
  - create
- apiGroups:
  - argoproj.io
  resources:
  - workflowtemplates
  - workflowtemplates/finalizers
  verbs:
  - get
  - list
  - watch
- apiGroups:
  - ""
  resources:
  - serviceaccounts
  verbs:
  - get
  - list
- apiGroups:
  - ""
  resources:
  - secrets
  verbs:
  - get
- apiGroups:
  - argoproj.io
  resources:
  - cronworkflows
  - cronworkflows/finalizers
  verbs:
  - get
  - list
  - watch
  - update
  - patch
  - delete
- apiGroups:
  - ""
  resources:
  - events
  verbs:
  - create
  - patch
- apiGroups:
  - policy
  resources:
  - poddisruptionbudgets
  verbs:
  - create
  - get
  - delete
=====

kubectl apply -f  argo_role.yaml
