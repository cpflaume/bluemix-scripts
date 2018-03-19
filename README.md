# bluemix-scripts
Example Scripts for bluemix container deployment.

Requirements:
- you have an account with bluemix
- you have uploaded an image to your private ibm image registry
- kubectl is installed
- bluemix cli is installed

1. Deploy a container

Note: YAML files are indentation sensitive! Don't mix spaces and tabulators in yaml files.
```
kubectl create --save-config -f my_jenkins_server.yaml
```
Tip: --save-config allows you do apply changes later with ``kubectl apply -f my_jenkins_server.yaml``

Check if the container is running.
```
kubectl proxy
```

2. Deploy a servic, which mapps the container port to external reachable ports
```
kubectl create --save-config -f my_jenkins_service.yaml
```
Note: You can only assign public ports in the range of 30000-32767

Now lookup the external IP address of your Node (you can find it at the bluemix dashboard).
