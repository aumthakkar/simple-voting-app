# simple-voting-app

This is a Helm Chart to deploy the simple voting app which implements the Voting app and the result app using NodePort type Kubernetes services so you can test
this on your own PC using the IP address of any node of your cluster followed by :30001 to get the Voting app page and port :30002 to get the Result App

Please note that this is just a test to check the deployment of the entire Simple Voting application using Helm Charts. (it uses dockersamples container images). 

Installing this chart deploys all the objects as shown below: It install all 5 deployments (Voting app deployment, Result app deployment, In memory Redis deployment, the Postgres DB deployment and the Worker app deployment) Also, it deploys all the 4 services in order to be reached by other pods

***************************************************************************************
NAME                                       READY   STATUS             RESTARTS   AGE
pod/postgres-deployment-554644bb97-vk9vt   1/1     Running            0          35s
pod/redis-deploy-5d7988b4bb-5vzs6          1/1     Running            0          35s
pod/result-app-deploy-7cdc94dfcd-tpf6k     1/1     Running            0          35s
pod/voting-app-deploy-678c67fc7-v8xm8      1/1     Running            0          35s
pod/worker-app-deploy-6bbc9cf7c8-gbn59     0/1     CrashLoopBackOff   1          35s

NAME                 TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
service/db-svc       ClusterIP   10.100.255.50    <none>        5432/TCP       36s
service/kubernetes   ClusterIP   10.96.0.1        <none>        443/TCP        2d15h
service/redis-svc    ClusterIP   10.101.35.224    <none>        6379/TCP       37s
service/result-svc   NodePort    10.105.173.117   <none>        80:30002/TCP   37s
service/voting-svc   NodePort    10.111.148.106   <none>        80:30001/TCP   36s

NAME                                  READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/postgres-deployment   1/1     1            1           36s
deployment.apps/redis-deploy          1/1     1            1           36s
deployment.apps/result-app-deploy     1/1     1            1           36s
deployment.apps/voting-app-deploy     1/1     1            1           36s
deployment.apps/worker-app-deploy     0/1     1            0           36s

NAME                                             DESIRED   CURRENT   READY   AGE
replicaset.apps/postgres-deployment-554644bb97   1         1         1       36s
replicaset.apps/redis-deploy-5d7988b4bb          1         1         1       36s
replicaset.apps/result-app-deploy-7cdc94dfcd     1         1         1       36s
replicaset.apps/voting-app-deploy-678c67fc7      1         1         1       36s
replicaset.apps/worker-app-deploy-6bbc9cf7c8     1         1         0       36s

****************************************************************************************
