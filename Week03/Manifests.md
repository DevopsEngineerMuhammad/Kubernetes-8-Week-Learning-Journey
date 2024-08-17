vi pod1.yml
kind: Pod
apiVersion: v1
metadata:
 name: testpod
spec:
 containers:
  - name: coo
    image: ubuntu
    command: ["/bin/bash", "-c", "while true; do echo DevopsEngineerMuhammad; sleep 5 ; done"]
kubectl apply -f pod1.yml
kubectl get pods
kubectl pods -o wide
kubectl describe pod testpod
or
kubectl describe pod/testpod
kubectl logs -f testpod
or
kubectl logs -f testpod -c coo
kubectl delete pod testpod
or
kubectl delete -f pod1.yml
