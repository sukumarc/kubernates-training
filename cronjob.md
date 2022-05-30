
# CronJob

#### 1. Go to cronjob.yaml (/root/kubernetes-training/04-controllers, 2.Open the file and change the 1st line to (apiVersion: batch/v1beta1), 3.Run this file

<img width="502" alt="cron" src="https://user-images.githubusercontent.com/9497448/171050333-22c6dc3b-01e7-4b48-8c94-fdc8cd36c01d.PNG">

#### 4. Find out what is the command to "get" the running jobs, 5.Observe and if possible, paste the results from your practicals.

      kubectl get cronjob

<img width="624" alt="cron1" src="https://user-images.githubusercontent.com/9497448/171052681-ffadf037-e55b-405f-81e4-b14c22df9bcb.PNG">

#### 6.Also identify how you would "permanently arrest" the jobs from running

      kubectl delete cronjob --all

<img width="590" alt="cron-delete" src="https://user-images.githubusercontent.com/9497448/171052868-37a9c040-f348-4ea5-8065-9d8740e09e7e.PNG">

#### 7. What is the change from normal Jobs (jobs v/s cronJobs) - Your observation in one sentence.

      1. Normal Job
      --> Job is used to perform some desired task. 
      --> If pod deleted or failed it will automatically creates another pod to to complete its task.
      
<img width="941" alt="batch-job" src="https://user-images.githubusercontent.com/9497448/171054381-4d31d574-98fb-40ac-843a-fa59a7fb7075.PNG">

      2. Cron Job
      --> Cron job is used for scheduling the any task or we can use this cron job to start the batch job.
      --> This is more offen like a timer for trigger some task.
 
<img width="941" alt="cron-all" src="https://user-images.githubusercontent.com/9497448/171057049-9ff47e8d-0db4-47f6-95fe-59891c492075.PNG">

