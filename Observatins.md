# kubernetesTraining

 commands:
 login as: ec2-user
Authenticating with public key "imported-openssh-key"
Last login: Wed Jun  1 11:11:43 2022 from 182.74.120.34

       __|  __|_  )
       _|  (     /   Amazon Linux 2 AMI
      ___|\___|___|

https://aws.amazon.com/amazon-linux-2/
2 package(s) needed for security, out of 9 available
Run "sudo yum update" to apply all updates.
[ec2-user@ip-172-31-21-49 ~]$ sudo su
[root@ip-172-31-21-49 ec2-user]# ls
kubernetes-training
[root@ip-172-31-21-49 ec2-user]# cd /root
[root@ip-172-31-21-49 ~]# git clone  https://github.com/ashishrpandey/example-
Cloning into 'example-voting-app'...
remote: Enumerating objects: 494, done.
remote: Total 494 (delta 0), reused 0 (delta 0), pack-reused 494
Receiving objects: 100% (494/494), 236.17 KiB | 1020.00 KiB/s, done.
Resolving deltas: 100% (179/179), done.
[root@ip-172-31-21-49 ~]# cd /root/example-voting-app/k8s-specifications
[root@ip-172-31-21-49 k8s-specifications]# kubectl apply -f .

[root@ip-172-31-21-49 k8s-specifications]# kubectl get po
NAME                      READY   STATUS    RESTARTS   AGE
db-b54cd94f4-flb2r        1/1     Running   0          8m16s
redis-868d64d78-nxbv7     1/1     Running   0          8m15s
result-5d57b59f4b-cfqj8   1/1     Running   0          8m15s
vote-94849dc97-vsbhb      1/1     Running   0          8m15s
worker-dd46d7584-ncl82    1/1     Running   0          8m15s

db-deployment.yaml  redis-deployment.yaml  result-deployment.yaml  vote-deploy
db-service.yaml     redis-service.yaml     result-service.yaml     vote-servic
[root@ip-172-31-21-49 k8s-specifications]# cat result-
[root@ip-172-31-21-49 k8s-specifications]# kubectl get svc
NAME         TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
db           ClusterIP   10.110.193.145   <none>        5432/TCP         14m
kubernetes   ClusterIP   10.96.0.1        <none>        443/TCP          10d
redis        ClusterIP   10.103.120.240   <none>        6379/TCP         14m
result       NodePort    10.106.66.38     <none>        5001:31001/TCP   14m
vote         NodePort    10.104.220.63    <none>        5000:31000/TCP   14m
[root@ip-172-31-21-49 k8s-specifications]# LS
bash: LS: command not found
[root@ip-172-31-21-49 k8s-specifications]# ls
db-deployment.yaml  redis-deployment.yaml  result-deployment.yaml  vote-deploy
db-service.yaml     redis-service.yaml     result-service.yaml     vote-servic
[root@ip-172-31-21-49 k8s-specifications]# vi result-service.yaml
[root@ip-172-31-21-49 k8s-specifications]# kubectl get svc
NAME         TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
db           ClusterIP   10.110.193.145   <none>        5432/TCP         23m
kubernetes   ClusterIP   10.96.0.1        <none>        443/TCP          10d
redis        ClusterIP   10.103.120.240   <none>        6379/TCP         23m
result       NodePort    10.106.66.38     <none>        5001:31001/TCP   23m
vote         NodePort    10.104.220.63    <none>        5000:31000/TCP   23m
[root@ip-172-31-21-49 k8s-specifications]# kubectl get po
NAME                      READY   STATUS    RESTARTS   AGE
db-b54cd94f4-flb2r        1/1     Running   0          23m
redis-868d64d78-nxbv7     1/1     Running   0          23m
result-5d57b59f4b-cfqj8   1/1     Running   0          23m
vote-94849dc97-vsbhb      1/1     Running   0          23m
worker-dd46d7584-ncl82    1/1     Running   0          23m
[root@ip-172-31-21-49 k8s-specifications]# vi result-service.yaml
[root@ip-172-31-21-49 k8s-specifications]#
[root@ip-172-31-21-49 k8s-specifications]# vi result-service.yaml
[root@ip-172-31-21-49 k8s-specifications]# delete po
bash: delete: command not found
[root@ip-172-31-21-49 k8s-specifications]# delete po ^C
[root@ip-172-31-21-49 k8s-specifications]# delete po vote-94849dc97-vsbhb
bash: delete: command not found
[root@ip-172-31-21-49 k8s-specifications]# kubectl delete po vote-94849dc97-vs
pod "vote-94849dc97-vsbhb" deleted
[root@ip-172-31-21-49 k8s-specifications]# ls
db-deployment.yaml  redis-deployment.yaml  result-deployment.yaml  vote-deploy
db-service.yaml     redis-service.yaml     result-service.yaml     vote-servic
[root@ip-172-31-21-49 k8s-specifications]# kubectl get svc
NAME         TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
db           ClusterIP   10.110.193.145   <none>        5432/TCP         41m
kubernetes   ClusterIP   10.96.0.1        <none>        443/TCP          10d
redis        ClusterIP   10.103.120.240   <none>        6379/TCP         41m
result       NodePort    10.106.66.38     <none>        5001:31001/TCP   41m
vote         NodePort    10.104.220.63    <none>        5000:31000/TCP   41m
[root@ip-172-31-21-49 k8s-specifications]# kubectl get po
NAME                      READY   STATUS    RESTARTS   AGE
db-b54cd94f4-flb2r        1/1     Running   0          41m
redis-868d64d78-nxbv7     1/1     Running   0          41m
result-5d57b59f4b-cfqj8   1/1     Running   0          41m
vote-94849dc97-qsfhr      1/1     Running   0          43s
worker-dd46d7584-ncl82    1/1     Running   0          41m

[root@ip-172-31-21-49 k8s-specifications]# kubectl get po
NAME                      READY   STATUS        RESTARTS   AGE
db-b54cd94f4-flb2r        1/1     Running       0          46m
redis-868d64d78-nxbv7     1/1     Running       0          46m
result-5d57b59f4b-cfqj8   1/1     Running       0          46m
vote-94849dc97-6nvwx      1/1     Running       0          3m42s
worker-dd46d7584-8g429    1/1     Running       0          18s
worker-dd46d7584-ncl82    1/1     Terminating   0          46m
[root@ip-172-31-21-49 k8s-specifications]# kubectl get po
NAME                      READY   STATUS        RESTARTS   AGE
db-b54cd94f4-flb2r        1/1     Running       0          46m
redis-868d64d78-nxbv7     1/1     Running       0          46m
result-5d57b59f4b-cfqj8   1/1     Running       0          46m
vote-94849dc97-6nvwx      1/1     Running       0          3m53s
worker-dd46d7584-8g429    1/1     Running       0          29s
worker-dd46d7584-ncl82    1/1     Terminating   0          46m
[root@ip-172-31-21-49 k8s-specifications]# kubectl get po
NAME                      READY   STATUS    RESTARTS   AGE
db-b54cd94f4-flb2r        1/1     Running   0          46m
redis-868d64d78-nxbv7     1/1     Running   0          46m
result-5d57b59f4b-cfqj8   1/1     Running   0          46m
vote-94849dc97-6nvwx      1/1     Running   0          4m12s
worker-dd46d7584-8g429    1/1     Running   0          48s
[root@ip-172-31-21-49 k8s-specifications]# kubectl delete po db-b54cd94f4-l5zl
pod "db-b54cd94f4-l5zlg" deleted
y
[root@ip-172-31-21-49 k8s-specifications]# y
bash: y: command not found
[root@ip-172-31-21-49 k8s-specifications]# kubectl get po
NAME                      READY   STATUS    RESTARTS   AGE
db-b54cd94f4-mwmb7        1/1     Running   0          41s
redis-868d64d78-nxbv7     1/1     Running   0          53m
result-5d57b59f4b-cfqj8   1/1     Running   0          53m
vote-94849dc97-6nvwx      1/1     Running   0          11m
worker-dd46d7584-4plvw    1/1     Running   1          3m38s
[root@ip-172-31-21-49 k8s-specifications]# kubectl get svc
NAME         TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
db           ClusterIP   10.110.193.145   <none>        5432/TCP         54m
kubernetes   ClusterIP   10.96.0.1        <none>        443/TCP          11d
redis        ClusterIP   10.103.120.240   <none>        6379/TCP         54m
result       NodePort    10.106.66.38     <none>        5001:31001/TCP   54m
vote         NodePort    10.104.220.63    <none>        5000:31000/TCP   54m
[root@ip-172-31-21-49 k8s-specifications]# ^C
[root@ip-172-31-21-49 k8s-specifications]# kubectl get po
NAME                      READY   STATUS    RESTARTS   AGE
db-b54cd94f4-mwmb7        1/1     Running   0          29m
redis-868d64d78-nxbv7     1/1     Running   0          82m
result-5d57b59f4b-r6gxl   1/1     Running   0          25m
vote-94849dc97-6nvwx      1/1     Running   0          40m
worker-dd46d7584-4plvw    1/1     Running   1          32m
[root@ip-172-31-21-49 k8s-specifications]# kubectl delete po result-5d57b59f4b-r6gxl
pod "result-5d57b59f4b-r6gxl" deleted

  

 \\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
  
  
  <------Obeservations----------->

    
 ~kubectl get svc
it gives all running services including result and vote app which is runnung on public ip

~kubectl get po
 it gives all pods including Vote and Result POD
 
 Now Vote and Result app is runnung on port 31000 and 31001 resp. on public ip instance
 Result app shows exact result as voting is done one by one
 
 Now deleted Voting POD
 it will create new voting POD i.e it copies Voting POD from replica set and run
 
 Now deleted Result POD
 it will create new Result POD i.e it copies Result POD from replica set and run
 
  Now deleted Database POD
 it will create new Database POD i.e it copies Database POD from replica set and run
 
 Now, After voting in Voting app the result app will not show exact resuls because it is expecting from old DBs.
 For exact Result we have to delete Result POD , so that, Result POD will create again from replica set, and it will craete new Connection to the DBS
 
 
 
 
 
 
 
