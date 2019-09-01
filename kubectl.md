## kubectl cheatsheet
### Abbreviated Alias
| Resourcetype   | Alias  |
|---|---|
| componentstatuses | cs |
| configmaps | cm |
| daemonsets | ds |
| deployments | deploy |
| endpoints | ep |
| event | ev |
| horizandpodautoscalers | hpa |
| ingresses | ing |
| limitranges | limits |
| namespaces | ns |
| nodes | no |
| statefulsets | sts |
| persistentvolumeclaims | pvc |
| persistentvolumes | pv |
| pods | po |
| podsecuritypolicies | psp |
| replicasets | rs |
| replicationcontrollers | rc |
| serviceaccount | sa |
| services | svc |
| storageclasses | sc | 
### Cluster Operation
| Description   | Command  |
|---|---|
| Get component status  | ```kubectl get componentstatus```  |
| Mark node as unschedulable  | ```kubectl cordon <nodename>```  |
| Drain node for maintenance  | ```kubectl drain <nodename>```  |
| Mark node as schedulable  |  ```kubectl uncordon <nodename>``` |
| Show metrics for a given node | ```kubectl top node <nodename>```  |
| Display addresses of the Master and services  | ```kubectl cluster-info```  |
| Dump current clsuter state to stdout  | ```kubectl cluster-info dump```   |
| Add a label to a node instance | ```kubectl label node/worker disk=ssd```  |

### Listing
| Description   | Command  |
|---|---|
| List everything present in cluster | ```kubectl get all --all-namespaces``` |
| List nodes with labels | ```kubectl get nodes --show-labels``` |
| List pods with labels | ```kubectl get pods --show-labels``` |
| List pods with additional information | ```kubectl get pods -o wide``` |
| Get the YAML manifest of the pod | ```kubectl get pods/<podname> -o yaml``` |
| Get the JSON manifest of the pod |  ```kubectl get pods/<podname> -o json``` |
| Explain resources | ```kubectl explain <resourcename>``` |
| List all services | ```kubectl get services``` |
| List all pods | ```kubectl get pods``` |
| List pods sorted by restart count | ```kubectl get pods --sort-by=.status.ContainerStatuses[0].restartCount``` |
| Get Statefulsets | ```kubectl get sts``` |
| List service endpoints | ```kubectl get endpoints``` |
| Describe pod | ``` kubectl describe pod <podname>``` |
### Object Operations
<comingup-soon>
### Context Operations
<comingup-soon>
### Network Operations
<comingup-soon>
### Delete Operations
<comingup-soon>
### Configmaps & Secrets
<comingup-soon>
### Labels & Annotations
<comingup-soon>
### API Extensions
<comingup-soon>
### Volume Operations
<comingup-soon>



