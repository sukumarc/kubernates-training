
# ReplicaSet

####  1. What are the differences file-wise?

      Referencing the below two files,

      https://github.com/ashishrpandey/kubernetes-training/blob/master/04-controllers/kubia-rc.yaml
      https://github.com/ashishrpandey/kubernetes-training/blob/master/05-services/kubia-replicaset.yaml
      
      In kubia-rc, 
       --> it support only equality-based selector, only one label properties can be checked(selector: app: kubia). It replicates the app based on lable "app:kubia" 
       --> containerPort:8080 is added, so that we can reach the app from outside of the container using 8080 port.(it is not mandatory to mention)
       
       In kubia-replicaset, 
       --> it support set based selector, in this file there is only one key value is checked(selector: matchLabels: app: kubia). It is also replicates the app based on lable "app:kubia". But we can add multiple properties under matchlabels and matchexpressions.
       --> containerPort:8080 is not mentioned here, but still app can be accessed or reached from the defaul port 8080.
           
           
#### 2. Run the kubia-replicaset.yaml
        
 
<img width="935" alt="rs" src="https://user-images.githubusercontent.com/9497448/171045670-34bfd2fe-090e-426f-800a-b17d0e3ffa89.PNG">


#### 3.Identify what commands can be run after "kubectl apply...."

       kubectl apply -f kubia-replicaset.yaml
       
#### 4. Make a service over these pods (kubia-replicaset) and see if the service picks up the web-service within the pod ("You have hit....." message)

<img width="931" alt="svc" src="https://user-images.githubusercontent.com/9497448/171047621-179ff5f3-d9a7-4fb5-9282-d53f801bfeb2.PNG">

#### 5. Negative Testing : change the labels of the pod and see if the service is still applied on those pods

<img width="571" alt="rs-label-test" src="https://user-images.githubusercontent.com/9497448/171048068-9c77a2ba-e38e-49a3-9c53-168ac1689642.PNG">


