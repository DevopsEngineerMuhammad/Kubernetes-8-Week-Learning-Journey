```sh
vi pod1.yml
```

```sh
kind: Pod
apiVersion: v1
metadata:
 name: testpod
spec:
 containers:
  - name: coo
    image: ubuntu
    command: ["/bin/bash", "-c", "while true; do echo DevopsEngineerMuhammad; sleep 5 ; done"]
```

```sh
kubectl apply -f pod1.yml
```

```sh
kubectl get pods
```

```sh
kubectl get pods -o wide
```

```sh
kubectl describe pod testpod
```
or
```sh
kubectl describe pod/testpod
```

```sh
kubectl logs -f testpod
```
or
```sh
kubectl logs -f testpod -c coo
```

```sh
kubectl delete pod testpod
```
or
```sh
kubectl delete -f pod1.yml
```
