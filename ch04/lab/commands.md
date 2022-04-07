➜  ch04 git:(master) ✗ cd lab
➜  lab git:(master) ✗ kubectl apply -f postgres
secret/ch04-lab-db-secret created
service/ch04-lab-db created
deployment.apps/ch04-lab-db created
➜  lab git:(master) ✗ kubectl apply -f adminer.yaml
service/adminer-web created
deployment.apps/adminer-web created
➜  lab git:(master) ✗ kubectl get svc
NAME          TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
adminer-web   LoadBalancer   10.100.161.152   localhost     8082:31706/TCP   18s
ch04-lab-db   ClusterIP      10.101.102.65    <none>        5432/TCP         33s
kubernetes    ClusterIP      10.96.0.1        <none>        443/TCP          3m8s
➜  lab git:(master) ✗ kubectl apply -f adminer.yaml
secret/adminer-web-secret created
service/adminer-web unchanged
deployment.apps/adminer-web configured
➜  lab git:(master) ✗ kubectl apply -f adminer.yaml
secret/adminer-web-secret configured
service/adminer-web unchanged
deployment.apps/adminer-web unchanged
➜  lab git:(master) ✗ kubectl apply -f adminer.yaml
secret/adminer-web-secret configured
service/adminer-web unchanged
deployment.apps/adminer-web configured
➜  lab git:(master) ✗ kubectl apply -f adminer.yaml
secret/adminer-web-secret configured
service/adminer-web unchanged
deployment.apps/adminer-web configured
➜  lab git:(master) ✗ kubectl apply -f adminer.yaml
secret/adminer-web-secret configured
configmap/adminer-web-config created
service/adminer-web unchanged
deployment.apps/adminer-web configured
➜  lab git:(master) ✗ kubectl apply -f adminer.yaml
secret/adminer-web-secret configured
configmap/adminer-web-config unchanged
service/adminer-web unchanged
deployment.apps/adminer-web configured
➜  lab git:(master) ✗