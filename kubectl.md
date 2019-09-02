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
| List contexts  | ```kubectl config get-contexts``` |
| Switch context  | ```kubectl config use-context <context-name>```  |
| Add a new cluster(cy) to your kubeconfig that supports basic auth  | ```kubectl config set-credentials kubeuser/cy.kuberenetes.com --username=kubeuser --password=kubepassword```  |
| Set a context(cy) utilizing a specific username and Namespace  | ```kubectl config set-context cy --user=cluster-admin --namespace=cyns && kubectl config use-context cyns```  |
### Network Operations
| Description   | Command  |
|---|---|
| Temporarily add a port-forwarding   | ```kubectl port-forward <podname> <portnumber>```  |
| Add port-forwarding for deployment  | ```kubectl port-forward deployment <deployname> <port>:<port>``` |
| Add port-forwarding for service   | ```kubectl port-forward svc <svcname> <port>:<port>```  |
| Get NetworkPolicy  | ```kubectl get NetworkPolicy```  |
| Create a service object that exposes the deployment  | ```kubectl expose deployment <deployname> --type=<service-type> --name=<svc-name>``` |
### Delete Operations
| Description   | Command  |
|---|---|
| Delete Pod forcefully  | ```kubectl delete pod grace-test --force --grace-period=0```   |
| Delete a pod using the type and name specified in pod.json  | ```kubectl delete -f ./pod.json```  |
| Delete pods and services with names "bar" and "foo"  | ```kubectl delete pod,svc bar foo```  |
| Delete pods and services with label 'name=label'   | ```kubectl delete pods,services -l name=label```  |
| Delete pods and services running with label 'name=label' also including unintialized ones | ```kubectl delete pods,services -l name=label --include=unintializedones``` |
| Delete all pods inclusing unintializedones, in namespace my-ns  | ```kubectl -n my-ns delete po --all```  |
### Configmaps & Secrets
| Description   | Command  |
|---|---|
| Create config map from both configuration file and variable  | ```kubectl create cm <configmapname> --from-file=<file-name> --from-literal=app=frontend```  |
| Create secret to store TLS key and certificate  | ```kubectl create secret generic <secretname> --from-file=ca.crt --from-file=ca.key```  |
| Create image pull secret for docker registry | ```kubectl create secret docker-registry myregistrykey --docker-server=$DOCKER_REGISTRY_SERVER --docker--username=$DOCKER_USER --docker-password=$DOCKER_PASSWORD --docker-email=$DOCKER_EMAIL```  |
### Labels & Annotations
| Description   | Command  |
|---|---|
| Filter pods by label  | ```kubectl get pods -l app=run```  |
| Manually add label to a pod  | ```kubectl label pods <podname> app=run```  |
| remove label  | ```kubectl label pods <podname> app-```  |
| Manually add annotation to a pod  | ```kubectl annotate pods <podname> my-url=https://<url>```  |
### API Extensions
| Description   | Command  |
|---|---|
| List API extesnions  |  ```kubectl api-versions``` |
| List all CRD  | ```kubectl get crd```  |
| List al supported resources  | ```kubectl api-resources```  |
### Volume Operations
| Description   | Command  |
|---|---|
| List storage class  | ```kubectl get sc```  |
| Check persistent volume  | ```kubectl decribe pv <pv-name>```  |
| Check persistent volume claim | ```kubectl describe pvc <pvc-name>```  |
| Copy local file to pod  | ```kubectl cp </path/to/file> <ns-name>/<po-name>:/tmp/data```  |
| Copy pod file to local |  ```kubectl cp <ns-name>/<po-name>:/tmp/data /tmp/mydata```|




