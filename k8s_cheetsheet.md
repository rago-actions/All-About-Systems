  ### CONFIG
  1. Displays the current-context
  ```
  kubectl config current-context
  ```
  2. Delete the specified cluster from the kubeconfig
  ```
  kubectl config delete-cluster cluster-name
  ```
  3. Delete the specified context from the kubeconfig
  ```
  kubectl config delete-context context-name
  ```
  4. Display clusters defined in the kubeconfig
  ```
  kubectl config get-clusters
  ```
  5. Describe one or many contexts
  ```
  kubectl config get-contexts
  ```
  6. Renames a context from the kubeconfig file.
  ```
  kubectl config rename-context old-name new-name
  ```
  7. set             Sets an individual value in a kubeconfig file
  ```
  kubectl config set property_name property_value
  kubectl config set clusters.my-cluster.server https://1.2.3.4
  kubectl config set contexts.my-context.cluster my-cluster
  kubectl config set clusters.my-cluster.certificate-authority-data $(echo "cert_data_here" | base64 -i -)
  kubectl config set users.cluster-admin.client-key-data cert_data_here --set-raw-bytes=true
  ```
  8. Sets a cluster entry in kubeconfig
  ```
  kubectl config set-cluster NAME 
  kubectl config set-cluster e2e --server=https://1.2.3.4
  kubectl config set-cluster e2e --certificate-authority=~/.kube/e2e/kubernetes.ca.crt
  kubectl config set-cluster e2e --insecure-skip-tls-verify=true
  ```
  9. Sets a context entry in kubeconfig
  ```
  kubectl config set-context NAME
  kubectl config set-context --current=true 
  kubectl config set-context NAME --cluster=cluster_nickname
  kubectl config set-context NAME --user=user_nickname
  kubectl config set-context NAME --namespace=namespace
  ```
  10. set-credentials Sets a user entry in kubeconfig  
  ```
  kubectl config set-credentials NAME
  kubectl config set-credentials cluster-admin --client-key=~/.kube/admin.key
  kubectl config set-credentials cluster-admin --username=admin --password=uXFGweU9l35qcif
  kubectl config set-credentials cluster-admin --client-certificate=~/.kube/admin.crt --embed-certs=true
  kubectl config set-credentials cluster-admin --auth-provider=gcp
  kubectl config set-credentials cluster-admin --auth-provider=oidc --auth-provider-arg=client-id=foo
--auth-provider-arg=client-secret=bar
kubectl config set-credentials cluster-admin --auth-provider=oidc --auth-provider-arg=client-secret-
```
  11. Unsets an individual value in a kubeconfig file 
  ```
  kubectl config unset PROPERTY_NAME
  kubectl config unset current-context
  kubectl config unset contexts.foo.namespace
  ```
  12. Sets the current-context in a kubeconfig file
  ```
  kubectl config use-context context-name
  ```         
  13. Display merged kubeconfig settings or a specified kubeconfigfile
  ```
  kubectl config view
  ```
