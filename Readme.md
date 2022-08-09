## Cloud Watch
You will create a Cloud Watch event to notify via an SNS topic when an EC2 instance is created.  

### Prerequisites:  
AWS account
SNS Topic

### By the end of this lab, you will be able to:
Create Cloud Watch event to react to the creation of an Amazon EC2 instance
Send SNS notification via Cloud Watch when an event occurs  

## Steps:
Create CloudWatch Rule  
Navigate to the Amazon EventBridge.  
On the left-hand menu, under Events, select Rules.  
Click on the Create rule button.  
Define rule detail: Rule with an event pattern, supply Name
For Service Name, select EC2.  
![watch1](watch1.png?raw=true "watch1")
![watch2](watch2.png?raw=true "watch2")

For the Event Type, select EC2 Instance State-change Notification.  
Select the Specific state(s) radio button. Select running from the drop-down box.  
![watch3](watch3.png?raw=true "watch3")
![watch4](watch4.png?raw=true "watch4")

`Note: This configures the rule to trigger whenever an Amazon EC2 instance changes to the running state, which happens when an instance is launched or started.`   

Tn the Target section, add a target by clicking on Add target.  
In the drop-down, select SNS topic.  
For the Topic, select the topic you created in the SNS hands-on exercise.  

Configure tags - optional    
Review and create  
![watch5](watch5.png?raw=true "watch5")


## 2. Test CloudWatch Rule
Go and create EC2 instances  
Once the Instance state changes to Running, check your email client for an email alert from the SNS Topic.  

![watch6](watch6.png?raw=true "watch6")

## 3. Cleanup & Disable EC2 Instance and Cloud Watch Rule


