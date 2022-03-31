``` shell
➜  lab git:(master) kubectl apply -f deployments.yaml
deployment.apps/lab-numbers-api created
deployment.apps/lab-numbers-web created
deployment.apps/lab-numbers-web-v2 created
➜  lab git:(master) kubectl get po
NAME                                  READY   STATUS    RESTARTS   AGE
lab-numbers-api-d6c7586-vttxj         1/1     Running   0          15s
lab-numbers-web-685b55c664-2zdb6      1/1     Running   0          15s
lab-numbers-web-v2-7679fbc76c-x4pnv   1/1     Running   0          15s
➜  lab git:(master) kubectl get svc
NAME         TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
kubernetes   ClusterIP   10.96.0.1    <none>        443/TCP   2m59s
➜  lab git:(master) ✗ kubectl apply -f api-service.yaml
service/numbers-api created
➜  lab git:(master) ✗ kubectl get svc
NAME          TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)   AGE
kubernetes    ClusterIP   10.96.0.1        <none>        443/TCP   3m8s
numbers-api   ClusterIP   10.101.140.212   <none>        80/TCP    2s
➜  lab git:(master) ✗ kubectl apply -f api-service.yaml
service/numbers-api configured
➜  lab git:(master) ✗ kubectl apply -f web-service.yaml
service/numbers-web created
```