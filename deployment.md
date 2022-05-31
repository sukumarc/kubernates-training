
# Deployment

#### Deployment file

Adding the minReadySeconds will help for zero downtime for the application
   
    vi kubia-deployment-v3.yaml

<img width="626" alt="deployment-1" src="https://user-images.githubusercontent.com/9497448/171136527-b9eda29e-4666-4b18-9f65-1d5ba818606f.PNG">

#### Deploy the deployment file

    kubectl apply -f kubia-deployment-v3.yaml
    
 <img width="619" alt="deployment-2" src="https://user-images.githubusercontent.com/9497448/171136866-5c01819a-5cae-4e74-bb73-a64521f8bb9f.PNG">


#### Updating the containers image

     kubectl set image deployment kubia nodejs=luksa/kubia:v3
  
We can able to see this below image, the old pod is terminating only after the 10 seconds of the pod started.
     
<img width="945" alt="deployment-3" src="https://user-images.githubusercontent.com/9497448/171138062-9e7758ed-dd50-4082-ab17-384b34d3ecae.PNG">

With help the below command, we can able to check the status of recent rollout deployment.

     kubectl rollout status deployment kubia
     
<img width="616" alt="deployment-4" src="https://user-images.githubusercontent.com/9497448/171139101-66603406-3377-48ca-a3bf-ac5c547d2c5a.PNG">
