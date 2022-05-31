
# Sample Voting App

#### 1. go to root (cd /root/ ) . (both Master and Worker can perform this in their instances)

<img width="428" alt="root" src="https://user-images.githubusercontent.com/9497448/171115205-d05077b7-c670-4698-9eed-7d55af306230.PNG">


#### 2. git clone https://github.com/ashishrpandey/example-voting-app


<img width="621" alt="git" src="https://user-images.githubusercontent.com/9497448/171115370-78d9651b-0b09-4835-a267-bda3f2bd4a01.PNG">


#### 3. go to /root/example-voting-app/k8s-specifications

<img width="537" alt="cd" src="https://user-images.githubusercontent.com/9497448/171115533-1834d5be-de7b-4722-b8e1-0df00cfa00ca.PNG">

#### 4. [root@ip-172-31-7-102 k8s-specifications]# kubectl apply -f .

<img width="476" alt="kube apply" src="https://user-images.githubusercontent.com/9497448/171115791-06f4bf64-2d9f-44cd-a95f-f7474f9a7b2f.PNG">

#### 5. for voting and result pods, Observe that NodePort is assigned.

Node Port is assigned to voting and result pods, refere below image (higlighted yellow)

<img width="904" alt="nodeport" src="https://user-images.githubusercontent.com/9497448/171116382-5b9d2007-6aa9-4bef-95a8-1801edbbacd0.PNG">

#### 6. take your publicIP (your instance IP) : NodePort ► open 2 browsers , one for VOTING and one for Results, 7 try voting and see the results paralelly in results page.

<img width="960" alt="browser" src="https://user-images.githubusercontent.com/9497448/171117373-9d1dfdeb-4b0e-45a3-9b16-4b2e4e8b8924.PNG">

#### 8. Now try to delete the Pods one by one (first voting Pod, then worker pod, then db pod) and see what happens to the voting and result app after deleting, 9. Write your observations in a text file, 10. what happens after db pod deletion. 

##### **Vote pod delete Case:**

Automatically vote pod recreated.
All the services are running in the kubernates
Both result and voting application working fine, able to access from the browser successfully.

<img width="718" alt="vote delete" src="https://user-images.githubusercontent.com/9497448/171118318-e7d649be-627d-4d03-a924-d94eca717908.PNG">

##### **Worker pod delete Case:**

Automatically worker pod recreated.
All the services are running in the kubernates.
Both result and voting application working fine, able to access from the browser successfully.

<img width="658" alt="worker delete" src="https://user-images.githubusercontent.com/9497448/171119253-5dabd556-0a51-48fc-827e-ec604a31ec20.PNG">

##### **DB pod delete Case:**

Automatically db pod recreated.
All the services are running in the kubernates.
Voting application working fine, able to access from the browser and able to vote.
We are able to reach result app from browser, but not able to see the voting result count.

<img width="697" alt="db delete" src="https://user-images.githubusercontent.com/9497448/171119787-eb75be0e-cfbd-4bc3-b76c-57385095c3bc.PNG">

#### 11. complete the assignment by making the result pod work. (if you delete db pod, results would not be captured.So repeat what we did in the class in order to make the result pod work), 12. Write in the text file, what you did in order to make the result pod work.

     1. After checking the result pod logs socket connection is terminates, so it is not able to make a connection to db.
     2. For foxing this issue, need to delete the result pod
     3. After deleting the result pod, it will automatically recreates the result pod.
     4. Now able to see the voting count in the result web page.

<img width="897" alt="logs and restart" src="https://user-images.githubusercontent.com/9497448/171121496-862b25e4-9310-482c-aacb-61594e2f02fe.PNG">





