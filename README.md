# argo-aks
Helping guide to setting up Argo Workflow in Azure Kubernetes Service

## 1. Create an Argo namespace in Kubernetes

`kubectl create ns argo`

## 2. Install Argo Workflow
`kubectl apply -n argo ./install.yaml`

## 3. Configure Service Account & RBAC

`kubectl apply -n argo -f ./argo-service-rbac.yaml`

## 4. Run Argo Workflow

This is an example workflow. The major thing to note is that the service account to use is detailed as part of the workflow (serviceAccountName: workflow)

`argo submit -n argo --watch ./argo-workflow.yaml`
