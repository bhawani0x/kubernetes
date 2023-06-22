## Nodes

- Get all nodes: 
```kubectl get nodes```
- Get detailed information about nodes: 
```kubectl describe node```
- Get nodes with extended information: 
`kubectl get nodes -o wide`
- Get nodes in YAML format:
`kubectl get nodes -o yaml`
- Get nodes based on label selection:
`kubectl get node --selector=[label_name]`
- Get external IP addresses of nodes in JSON format: 
`kubectl get nodes -o jsonpath='{.items[*].status.addresses[?(@.type=="ExternalIP")].address}'`
- Get resource utilization of a specific node: 
`kubectl top node [node_name]`

## Pods

- Get all pods: 
`kubectl get pods`
- Get pods with extended information: 
`kubectl get pods -o wide`
- Get detailed information about a pod: 
`kubectl describe pod [pod_name]`
- Show labels for pods: 
`kubectl get pods --show-labels`
- Get pods filtered by label: 
`kubectl get pods -l app=nginx`
- Get pods in YAML format: 
`kubectl get pods -o yaml`
- Export pod details in YAML format: 
`kubectl get pod [pod_name] -o yaml --export`
- Export pod details in YAML format and save to a file: 
`kubectl get pod [pod_name] -o yaml --export > nameoffile.yaml`
- Get pods in the "Running" phase: 
`kubectl get pods --field-selector status.phase=Running`

## Namespaces

- Get all namespaces: 
`kubectl get namespaces`
- Get namespaces in YAML format: 
`kubectl get namespaces -o yaml`
- Get detailed information about a namespace: 
`kubectl describe namespace [namespace_name]`

## Deployments

- Get all deployments: 
`kubectl get deployments`
- Get detailed information about a deployment: 
`kubectl describe deployment [deployment_name]`
- Get deployments with extended information: 
`kubectl get deployments -o wide`
- Get deployments in YAML format: 
`kubectl get deployments -o yaml`

## Services

- Get all services: 
`kubectl get services`
- Get detailed information about a service: 
`kubectl describe service [service_name]`
- Get services with extended information: 
`kubectl get services -o wide`
- Get services in YAML format: 
`kubectl get services -o yaml`
- Show labels for services: 
`kubectl get services --show-labels`

## DaemonSets

- Get all DaemonSets: 
`kubectl get daemonsets`
- Get all DaemonSets in all namespaces: 
`kubectl get daemonsets --all-namespaces`
- Get detailed information about a DaemonSet: 
`kubectl describe daemonset [daemonset_name] -n [namespace_name]`
- Get DaemonSet details in YAML format:
`kubectl get daemonset [ds_name] -n [ns_name] -o yaml`

## Events

- Get all events: 
`kubectl get events`
- Get events in the "kube-system" namespace: 
`kubectl get events -n kube-system`
- Get events and watch for new events: 
`kubectl get events -w`

## Logs

- Fetch logs of a pod: 
`kubectl logs [pod_name]`
- Fetch logs of a pod since the last hour: 
`kubectl logs --since=1h [pod_name]`
- Fetch the last 20 lines of logs from a pod: 
`kubectl logs --tail=20 [pod_name]`
- Fetch logs of a specific container within a pod: 
`kubectl logs -f -c [container_name] [pod_name]`
- Save logs of a pod to a file:
`kubectl logs [pod_name] > pod.log`

## Service Accounts

- Get all service accounts: 
`kubectl get

 serviceaccounts`
- Get service accounts in YAML format: 
`kubectl get serviceaccounts -o yaml`
- Export a service account to a file: 
`kubectl get serviceaccounts default -o yaml > ./sa.yaml`
- Replace a service account with a file: 
`kubectl replace serviceaccount default -f ./sa.yaml`
