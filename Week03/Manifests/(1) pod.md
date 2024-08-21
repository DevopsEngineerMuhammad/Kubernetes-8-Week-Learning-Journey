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

### Troubleshooting Minikube
If you encounter an error while applying a command from the above list, it may indicate that Minikube has stopped. Follow these steps to resolve the issue

1. Check the Minikube status:
```sh
  minikube status
```

2. If Minikube is stopped, start it:
```sh
  minikube start
```

3. Verify the Minikube status again:
```sh
  minikube status
```

4. Once Minikube is running, reapply the command that caused the error

# Note
Once you've successfully completed the above commands, click on pod2.yml.md and apply the manifest along with all related commands. Similarly, practice with pod3.yml.md and pod4.yml.md. You are now in Week 03. After finishing these tasks, you can move on to Week 04. Thanks!
