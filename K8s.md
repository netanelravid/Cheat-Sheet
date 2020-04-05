# K8s

### Kubectl

**cheatsheet**

https://kubernetes.io/docs/reference/kubectl/cheatsheet/ 

**Resources to getting started w/ k8s** 

https://vsupalov.com/getting-started-with-kubernetes/ 

<u>Execute command in specific container:</u> 

```shel
kubectl exec -it __POD_NAME__ –n __NAMESPACE__ -c __CONTAINER_NAME__ __COMMAND__ 
```

Copy file from host to container 

```shell
kubectl cp <some-namespace>/<some-pod>:/tmp/foo /tmp/bar -c <container-name> 
```

Get description about pods in namespace 

```
shell kubectl describe pod -n netanel
```

Get pod logs 

```sh
kubectl logs -n __NAMESPACE__ __POD__ > /tmp/logs.txt 
```

Port forwarding 

```sh
kubectl port-forward __POD__ __LOCAL_PORT__:__REMOTE_PORT__ -n __NAMESPACE --context __CONTEXT__ 
```

Get kubeconfig

```shell
kubectl config view
```

### Helm

Install helm package

```sh
helm install --kube-context __CONTEXT__ --namespace __NAMESPACE__ --name __POD__ __HELM_CHART_PATH__
```

Upgrade helm package

```sh
helm upgrade --kube-context __CONTEXT__ --namespace __NAMESPACE__ __POD__ __HELM_CHART_PATH__
```

Remove pod

```sh
helm delete --purge __POD__
```

