# Create the schedule for the start/stop AWS EC2 instances using the lambda function.

## Introduction: 

In today's dynamic cloud computing landscape, optimizing costs is paramount. For businesses relying on Amazon Web Services (AWS), effective cost management involves more than just monitoring usage—it requires proactive strategies. One such strategy involves intelligently scheduling the operation of AWS EC2 instances. By stopping instances during non-operational hours and starting them when needed, significant cost savings can be achieved without compromising operational efficiency.
we will explore the key steps to design a customized schedule tailored to your organization’s specific requirements. By the end of this discussion, you will have a clear understanding of how to implement an automated and efficient system that maximizes cost savings while maintaining the agility and flexibility that AWS is renowned for.




### Step-1 : Login into Aws Console With Admin Access.

<img width="1300" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/02f97f1b-8f39-4ab7-8eb5-e962a485ad85">

### Step-2 : Create an EC2 Instance.
- Go to Ec2 Console, Click on Launch Instance and Provice the required details.
 <img width="1300" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/104b6ffe-d4af-4ed6-b511-99465f28ba19">

- Here our instance is ready.
 <img width="1300" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/e803058d-a17d-4eef-ab7e-68bc394cf811">


### Step-3 : Create an IAM Policy to START and STOP the instance.

- Go to the AWS IAM Console.
  <img width="1300" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/edf05632-d020-450e-a6b0-4edfc03b08ed">

- Click on Policy & then Click on Create policy.
  <img width="1300" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/81f36f2f-47ae-47c1-bd1e-384a7e35cd9f">
  <img width="1342" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/a2d40288-b0be-4521-ac4e-cd5ddb36ca1d">

- Select the Ec2 Service and Click on Next
  <img width="1342" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/bad2efa9-b149-4886-9631-c7f871c25416">
  <img width="1342" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/ec3e3d68-5f0f-46b6-ab12-1ac83866ea95">

- Select the Start and Stop policy.
  <img width="1003" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/7d7060eb-f2d8-4fe0-9bf6-12a4c6ce11b7">

- Provide the Policy Name and Create it.
  <img width="1003" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/a432c722-bf4a-49ef-ad44-ed80e11fb048">

### Step-4 : Create an IAM Role for Lambda Function.

- Go to the AWS IAM Console.
  <img width="1300" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/edf05632-d020-450e-a6b0-4edfc03b08ed">

- Click on "Roles" and then Create Role.
  <img width="1300" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/28811d2e-7164-4f7b-9e75-2c9d94afc90c">
  <img width="1300" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/7c7815a0-a8eb-4154-a98f-9d63d5f9e005">

- Select the Start and Stop Policy role and click on next.
  <img width="1007" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/2f20f98a-8645-4a40-a768-32699a92d575">

- Provide the Role Name and Click on Create Role.
  <img width="1019" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/82236509-ed6b-4a82-9000-a8655c969d4f">
  <img width="1019" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/40661f8e-e968-4556-af38-19cf3af826fc">



  
### Step-5 : Create the Lambda Fucntion to Start and Stop the EC2.
- Go to the AWS LAMBDA Console and Click on Create Function.
  <img width="1019" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/159b6c6d-be83-444f-80c4-18b6d0472409">

- Provide the details, attach the Role & create it.
  <img width="1318" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/42488c03-3135-408f-977a-30e3b75a2d32">
  <img width="1318" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/e4de8d1f-fd62-40b2-87ee-73e1305315fd">

- Write the below code inside the lambda function in Python format for STOPING instance.
  <img width="1322" alt="Screenshot 2023-10-09 at 7 05 15 PM" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/66a07fb8-92ad-4656-8bfa-fc8e4d34e1cb">

### Now lets TURN-OFF the Instance.

- Next configure the Test event for stop and provide the details then deploy it.
  <img width="822" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/d8a44438-c47c-4f24-aa49-ada25d16bcde">

- Now lets test the Function, Click on Test.
  <img width="1322" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/180880b7-05f1-489f-a804-db2892a828e7">
  <img width="1283" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/864f3834-f987-4fbc-9dc9-adb9a3f0023f">

- Wow, Server has been Stoped.
 <img width="1193" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/b92e5b74-f955-4d15-9c8c-4b1491bdfff4">


### Now lets TURN-ON the Stoped Instance.
- Create the function for Start instance as shown in above and Write the below code inside the lambda function in Python Format for STARTING instance.
<img width="1320" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/b17e8a1d-650a-4b97-88eb-387e727b2a60">

- Next configure the Test event for start and provide the details then deploy it.
  <img width="822" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/e7df4ff0-adee-47a3-9fed-42a71bf21933">

- Now TURN-ON the Server using Lambda Function by Clicking on Test.
  <img width="1117" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/63559e2b-39f1-486f-b0c4-48e55c8a0c59">

- Wow, Instance has been Started and Runnning Successfully.
  <img width="1193" alt="image" src="https://github.com/Vedvilas/Task-Repo/assets/113783616/a5c0cfca-d09e-40fc-9680-946f2bc03a0b">

### Conclusion.

Managing AWS EC2 instances efficiently is crucial for optimizing costs and ensuring the effective use of resources. By creating a well-defined schedule for starting and stopping instances based on specific time frames, businesses can significantly reduce unnecessary expenses associated with idle resources. In this journey, we explored the process of automating this scheduling task using AWS Lambda function, IAM Roles and IAM policies.

