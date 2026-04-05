#                                       Aws-high-availability-auto-scaling-project
Highly Available and Scalable Web Application on AWS using Auto Scaling and Load Balancer

## Architecture Diagram
![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/main%20Architecture.png)

![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/archiflow.png)

                          ** THE Aim of this project is to design a highly available and scalable web application using AWS services.
    In this project, I focused on ensuring that the application remains available even if one server fails and can automatically scale based on user traffic. **

  🛠️ Services Used
- Amazon EC2
- AMI (Golden Image)
- Launch Template
- Auto Scaling Group
- Application Load Balancer (ALB)
- Target Group
- SNS (Simple Notification Service)

⚙️ Step-by-Step Implementation <br>

🔹 Step 1: Create EC2 Instance
<br>

Firstly, I created an EC2 instance and installed a web server (Apache).

Then I added a simple HTML page to display instance details like hostname.
<br>

![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/FINALL%20alb%20enpoint%20to%20show%20result.png)

<br>
🔹 Step 2: Create AMI (Golden Image) <br>

After configuring the EC2 instance, I created an AMI (Golden Image).
<br>

This AMI helps to launch multiple identical instances with pre-installed configurations.
<br>
![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/AMI.png)
<br>

Step 3: Create Launch Template <br>

Next, I created a Launch Template using the AMI.<br>
This template defines instance configuration like instance type, security group, and user data script.
<br>

![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/LAUNCH%20TEMPLATE.png)

<br>
🔹 Step 4: Create Target Group <br>

Then I created a Target Group to register EC2 instances.
<br>

It helps the load balancer to route traffic to healthy instance <br>

![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/TARGET%20GROUP.png)

<br>

🔹 Step 5: Create Application Load Balancer (ALB) <br>

After that, I created an Application Load Balancer.
<br>

It distributes incoming traffic across multiple EC2 instances in different Availability Zones. <br>

![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/LB.png) 

<br>

![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/ALB.png)

<br>
🔹 Step 6: Configure Auto Scaling Group <br>

Then I created an Auto Scaling Group using the Launch Template.
<br>

I configured:
- Minimum capacity = 1
- Desired capacity = 2
- Maximum capacity = 4
<br>
This ensures high availability and automatic scaling.
<br>

![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/target-traking%20policy.png)

<br>

![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/multiple%20AZ%20and%20subnets.png)

<br>

🔹 Step 7: Configure SNS Notifications <br>
Finally, I configured SNS to receive notifications when instances are launched or terminated.
<br>
This helps in monitoring Auto Scaling activities.
<br>
![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/SNS.png)

<br>
 ** for subscriber like -> email ,sqs sms
![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/SNS%20SUB.png)

<br>

 ** step 8 : 🧪 Testing <br>
To test the system, I used a stress command on EC2 instances. <br>
As CPU usage increased, Auto Scaling automatically launched new instances. <br>
The Load Balancer distributed traffic across all instances. <br>

![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/STRESS%20CMD%20TO%20SHOW%20RESULT.png)

<br>

** monitoring of the cpu load  to used Top command **
<br>

![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/MONITORING%20BY%20YU%3DUSING%20TIPOP%20CMD.png)

<br>

// this is the final result to 
- Achieved high availability using multiple AZs
- Achieved scalability using Auto Scaling
- Load was evenly distributed using ALB
- Automated infrastructure behavior
<br>

🔹 step 9 : finally Autoscaling is worked and maintained desired state and maximum number of the instances,
<br>

![image alt](https://github.com/kailasadhav126/aws-high-availability-auto-scaling-project/blob/2d2cf67b1b732d6ea63d9a6564edaa6fb9413e68/images/EC2-INSTANCES.png)



