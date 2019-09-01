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
| Description   | Command  |
|---|---|
| Validate YAML file with dry run |  ```kubectl create --dry-run --validate -f pod.yaml``` |
| Open a shell terminal in a pod with single container  | ```kubectl exec -it <podname> sh```  |
| Scaling the deployment to 3 replicas  | ```kubectl scale --replicas=3 deploy/<deploymentname>```  |
| Set the resource limit |  ```kubectl set resources deployment nginx -c=nginx --limits=cpu=200m,memory=512Mi``` |
| Updating the image, rollingupdate "wwww" containers of "frontend" deployment  | ```kubectl set image deploy/frontend www=image:V2```  |
| Rollback to the previous deployment  | ```kubectl rollout undo deploy/<deploymentname>```  |
| Watch rolling update status of "frontend" deployment until completion  | ```kubectl rollout status -w deploy/frontend```  |
| force, replace, delete and the recreate the resource  | ```kubectl kubectl replace --force -f pod.yaml```  |
| Start a temporary pod for testing  | ```kubectl run --rm -i -t  --image=alpine test --sh```  |
| Dump pod logs  | ```kubectl logs pods/<podname>```  |
| Dump pod container logs | ```kubectl logs po/<podname> -c <containername/id>```  |
| Stream pod logs  | ```kubectl logs -f po/<podname>```  |
| Stream pod container logs  |  ```kubectl logs -f po/<podname> -c <containername/id>``` |
| Show metrics for a given pod and its containers  | ```kubectl top pod <podname> --containers``` |
### Context Operations
| Description   | Command  |
|---|---|
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
### Network Operations
| Description   | Command  |
|---|---|
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
### Delete Operations
| Description   | Command  |
|---|---|
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
### Configmaps & Secrets
| Description   | Command  |
|---|---|
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
### Labels & Annotations
| Description   | Command  |
|---|---|
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
### API Extensions
| Description   | Command  |
|---|---|
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
### Volume Operations
| Description   | Command  |
|---|---|
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |



