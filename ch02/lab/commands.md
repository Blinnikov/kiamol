``` shell
➜  lab git:(master) kubectl apply -f deployment.yaml
deployment.apps/whoami-1 created
➜  lab git:(master) ✗ kubectl get all
NAME                            READY   STATUS              RESTARTS   AGE
pod/whoami-1-54bcf9956d-ljs9d   0/1     ContainerCreating   0          4s

NAME                 TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
service/kubernetes   ClusterIP   10.96.0.1    <none>        443/TCP   69d

NAME                       READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/whoami-1   0/1     1            0           4s

NAME                                  DESIRED   CURRENT   READY   AGE
replicaset.apps/whoami-1-54bcf9956d   1         1         0       4s
➜  lab git:(master) ✗ kubectl get pods -o custom-columns=NAME:metadata.name,LABELS:metadata.labels
NAME                        LABELS
whoami-1-54bcf9956d-ljs9d   map[app:whoami-1 pod-template-hash:54bcf9956d]
➜  lab git:(master) ✗ kubectl get pods -o custom-columns=NAME:metadata.name,POD_IP:status.podIP
NAME                        POD_IP
whoami-1-54bcf9956d-ljs9d   10.1.0.71
➜  lab git:(master) ✗ kubectl port-forward deploy/whoami-1 8080:80
Forwarding from 127.0.0.1:8080 -> 80
Forwarding from [::1]:8080 -> 80
Handling connection for 8080
Handling connection for 8080
Handling connection for 8080
^C%
➜  lab git:(master) ✗ kubectl exec -it deploy/whoami-1 -- sh -c 'hostname'
whoami-1-54bcf9956d-ljs9d
```

Browser output: 
```
"I'm whoami-1-54bcf9956d-ljs9d running on Linux 5.10.104-linuxkit #1 SMP PREEMPT Wed Mar 9 19:01:25 UTC 2022"
```