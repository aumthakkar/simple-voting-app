# simple-voting-app

This is a Helm Chart to deploy the simple voting app which implements the Voting app and the result app using NodePort type Kubernetes services so you can test
this on your own PC using the IP address of any node of your cluster followed by :30001 to get the Voting app page and port :30002 to get the Result App

Please note that this is just a test to check the deployment of the entire Simple Voting application using Helm Charts. (it uses dockersamples container images). 

Installing this chart deploys all 5 deployments (Voting app deployment, Result app deployment, In memory Redis deployment, the Postgres DB deployment and the Worker app deployment) Also, it deploys all the 4 services in order to be reached by other pods. Please note that the worker deployment does not need any service to be implemented.  
