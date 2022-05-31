
# Service

You have deployed an application, that is listening at port 8000. You used a replica-set to deploy it and created a NodePort service to make it accessible. But when you test it, somehow the application is not reachable at the port. Write down your approach and sequentially all the steps that you will take to find out the issue.

####  ReplicaSet creation 

     kubectl apply -f kubia-replicaset.yaml

<img width="916" alt="replicaset" src="https://user-images.githubusercontent.com/9497448/171126574-cd7575d5-ea5b-4f40-8add-6e20e04432a0.PNG">

#### Node Port creation

##### Exposing the nodeport 8000

     kubectl apply -f kubia-svc-nodeport-onlylocal.yaml
      
<img width="946" alt="node-port" src="https://user-images.githubusercontent.com/9497448/171127104-223bf3e1-7554-4e9c-a6da-4af7c2059a60.PNG">

We canot expose the nodeport in 8000, the port should be in the range between 30000 to 32767

##### Exposing the nodeport 30124

     kubectl apply -f kubia-svc-nodeport-onlylocal.yaml 
     
<img width="576" alt="node-port-30124" src="https://user-images.githubusercontent.com/9497448/171128070-81ea4708-bbab-43ac-b42c-a4bb5dbbfe11.PNG">

After editig the nodeport to 30124, service deployed successfully and we are able to reach the application using public ip with port 30124

<img width="425" alt="node-port-web" src="https://user-images.githubusercontent.com/9497448/171128426-d365cdad-43e9-48f3-9cfc-155a07141977.PNG">



