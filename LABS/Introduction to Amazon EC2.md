<h1 align="center"> Introduction to Amazon EC2 </h1> 

<h3> This lab provides a basic overview of launching, resizing, managing, and monitoring an Amazon EC2 instance </h3>

</br>

<h3><b>TASK 1: Launching your EC2 instance </b></h3>
</br>

<div align="center">
<img src="pictures/compute/launch 1.png" alt="AWS Lab Credentials" width="350">
</div>

<p>1. I opened the AWS Management Console and Select EC2 services where I selected LAUNCH INSTANCE and named my Instance "Web Server"</p>
</br>
</br>

<div align="center">
<img src="pictures/compute/ami.png" alt="AWS Lab Credentials" width="400">
</div>

<p>2. This is where I was choosing an AMI (Amazon Machine Image), an AMI provides the information required to launch an instance, which is a virtual server in the cloud. </p>
<p> Under AMI Machine Image (AMI), I kept it to Amazon Linux 2023* image.</p>

</br> 
</br>

<div align="center">
<img src="pictures/compute/instance type.png" alt="AWS Lab Credentials" width="400">
</div>
<p>3. This is where I was choosing an instance type. I selected t3.micro instance  </p>

</br>
</br>

<div align="center">
<img src="pictures/compute/key pair.png" alt="AWS Lab Credentials" width="400">
</div>

<p>4. Configuring a key pair: Selected proceed without </p>

</br>
</br>

<div align="center">
<img src="pictures/compute/vpc.png" alt="AWS Lab Credentials" width="400">
</div>

<p>5. Configuring the network settings: for VPC I selected Lab VPC</p>

</br>
</br>

<div align="center">
<img src="pictures/compute/sec grp.png" alt="AWS Lab Credentials" width="400">
</div>

<p> Security Group name : Web Security Group</p>
<p>Description: Security Group for my web server</p>
<p> A security group acts as a virtual firewall that controls the traffic for one or more instances. When you launch an instance, you associate one or more security groups with the instance. </p>

</br>
</br>

<div align="center">
<img src="pictures/compute/storage.png" alt="AWS Lab Credentials" width="400">
</div>

<p>6. Adding Storage: Amazon EC2 stores data on a network-attached virtual disk called Amazon Elastic Block Store (Amazon EBS). EC2 instance is a default 8 GiB disk volume</p>


</br>
</br>

<div align="center">
<img src="pictures/compute/user data.png" alt="AWS Lab Credentials" width="400">
</div>

<p> 7. Configuring Advance details:This is where I enabled Termination Protection and entered the commands to the user data text box </p>
<p>The script does the following: Install an Apache web server (httpd) , Configure the web server to automatically start on boot , Activate the Web server, Create a simple web page</p>


</br>
</br>

<div align="center">
<img src="pictures/compute/launch 2.png" alt="AWS Lab Credentials" width="400">
<img src="pictures/compute/launch 3.png" alt="AWS Lab Credentials" width="400">
<img src="pictures/compute/launch 4.png" alt="AWS Lab Credentials" width="400">
</div>

<p> 8. This is where I launched my EC2 Instance. I launched my EC2 instance by clicking <b>Launch instance</b> and then view it in the instances list. The instance first shows as <b>Pending</b>, then changes to <b>Running</b> once it starts. After a short wait, it becomes accessible and gets a <b>public DNS name</b> for internet access. I waited until its status shows <b>Running</b> with <b>2/2 checks passed</b> to confirm it’s fully ready.
</p>

</br>
</br>
<h3><b>TASK 2: Monitor your Instance </b></h3>
</br>


<div align="center">
<img src="pictures/compute/status.png" alt="AWS Lab Credentials" width="400">
</div>

<p> 1. I monitor my EC2 instance to ensure it is reliable, available, and performing well. I select the instance and check the <b>Status checks</b> tab to see its condition. This helps me quickly identify any hardware or software issues. I confirm that both the <b>system reachability</b> and <b>instance reachability</b> checks have passed, meaning my instance is running properly.
</p>


</br></br>

<div align="center">
<img src="pictures/compute/monitor.png" alt="AWS Lab Credentials" width="400">
</div>

<p> 2. I select the <b>Monitoring</b> tab to view metrics from Amazon CloudWatch for my EC2 instance. Since the instance is new, there are only a few metrics available, but I can click on a graph to see more details. I understand that Amazon EC2 sends basic monitoring data every five minutes by default, and I can enable detailed one-minute monitoring if needed. I also use the <b>Monitor and troubleshoot</b> option to get an instance screenshot, which shows what the instance console looks like as if a screen were connected.
</p>

</br></br>
<h3><b>TASK 3: Update Your Security Group and Access the Web Server </b></h3>
</br>

<div align="center">
<img src="pictures/compute/security g1.png" alt="AWS Lab Credentials" width="400">
</div>
<p> 1. In the EC2 Management Console tab, in the left navigation pane, I selected Security Groups located under Network & Security. And I selected the Web Server security group.</p>


</br></br>
<div align="center">
<img src="pictures/compute/security g2.png" alt="AWS Lab Credentials" width="400">
</div>
<p> 2. I selected the Inbound rules tab <b>The security group currently has no rules</b>. I then added a rule. </p>



</br></br>
<div align="center">
<img src="pictures/compute/security g3.png" alt="AWS Lab Credentials" width="400">
</div>
<p> 3. I edit the inbound rules, add a new rule with <b>HTTP</b> as the type and <b>Anywhere-IPv4</b> as the source, and then save the rules. </p>

</br></br>
<h3><b>Task 4: Resize Your Instance: Instance Type and EBS Volume</b></h3>
</br>

<div align="center">
<img src="pictures/compute/stop instance.png" alt="AWS Lab Credentials" width="400">
<img src="pictures/compute/stop instance 2.png" alt="AWS Lab Credentials" width="400">
</div>
<p> 1. <b>STOP THE INSTANCE:</b> I stop my EC2 instance before resizing it. When I stop it, the instance shuts down and I’m not charged for the instance itself, but I still pay for the attached storage (EBS volumes). In the EC2 console, I select the instance, choose <b> Instance state > Stop instance</b>, and confirm. I then wait until the instance status shows <b>stopped</b>.
</p>

</br></br>
<div align="center">
<img src="pictures/compute/type.png" alt="AWS Lab Credentials" width="400">
</div>
<p>2.<b>CHANGE THE INSTANCE TYPE:</b>  I go to the <b>Actions</b> menu, select <b>Instance Settings > Change Instance Type</b>, and set the instance type to <b>t3.small</b>, then confirm the change. When I start the instance again, it will run as a <b>t3.small</b>, which has twice the memory of a <b>t3.micro</b> (noting that other instance types may be restricted in the lab).
</p>

</br></br>
<div align="center">
<img src="pictures/compute/volume 1.png" alt="AWS Lab Credentials" width="400">
<img src="pictures/compute/volume 2.png" alt="AWS Lab Credentials" width="400">

</div>
<p> 3.  <b>RESIZE THE EBS VOLUME: </b> I resize my EBS volume by going to <b>Volumes</b> under Elastic Block Store, selecting the volume, and choosing <b>Actions > Modify Volume</b>. I increase the size from <b>8 GiB to 10 GiB</b>, then confirm the change by selecting <b>Modify</b> again.
</p>

<p> 4. I start my resized EC2 instance by selecting it and choosing <b>Instance state > Start instance</b>. Once it starts, it now has more memory and increased disk space. I successfully changed the instance type from <b>t3.micro to t3.small</b> and expanded the disk from <b>8 GiB to 10 GiB</b>.
</p>

</br></br>
<h3><b>Task 5: Test Termination Protection </b></h3>
</br>

<div align="center">
<img src="pictures/compute/terminate.png" alt="AWS Lab Credentials" width="400">
</div>
<p> I go to the <b>Instances</b> page and try to terminate my Web Server instance by selecting <b>Instance state > Terminate (delete) instance</b>, but it fails because termination protection is enabled. I then go to <b>Actions > Instance settings > Change termination protection</b>, uncheck <b>Enable</b>, and save the change. After that, I successfully terminate the instance by selecting <b>Instance state > Terminate instance</b> and confirming.
</p>


