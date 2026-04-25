<h1>Internet Protocols - Public and Private IP addresses</h1>

<h3> In this lab, summarizes and investigates a customer scenario, analyze the differences between private and public IP addresses, develop a solution to the customer’s issue, and summarize their findings through a group activity.
</h3>

</br>

<h3>TASK 1: Investigate the customer's environment </h3>
</br>

<div align="center">
<img src="pictures/networking/console.png" alt="AWS Lab Credentials" width="350">
<img src="pictures/networking/ec2.png" alt="AWS Lab Credentials" width="350">
</div>

<p>1. I first opened AWS Management Console, and opened EC2 service once the management console had opened. </p>

</br> </br>

<div align="center">
<img src="pictures/networking/instance1.png" alt="AWS Lab Credentials" width="350">
<img src="pictures/networking/instance2.png" alt="AWS Lab Credentials" width="350">
</div>

<p> 2. On the EC2 Dashboard from the left navigation pane, I selected Instances. Where there was two instances running. </p>


</br> </br>

<div align="center">
<img src="pictures/networking/instance A.png" alt="AWS Lab Credentials" width="350">
<img src="pictures/networking/instance B.png" alt="AWS Lab Credentials" width="350">
</div>

<p> 3. I copy the names and IP addresses of both EC2 instances into a text editor for future reference. I select <b>Instance A</b>, open the <b>Networking</b> tab, and record its public and private IPv4 addresses, along with the VPC and subnet details. I then repeat the same process for <b>Instance B</b> and compare the information to identify any differences between the two instances. </p>

</br>

<h3>TASK 2: Use SSH to connect to an Amazon Linux EC2 instance </h3>
</br>

<div align="center">
<img src="pictures/compute/credentials.png" alt="AWS Lab Credentials" width="350">
</div>

<p>1. I selected the Details dropdown and clicked Show. Downloaded the labsuser.ppk file. And noted the Public IP Address. </p>

</br> </br>

<div align="center">
<img src="pictures/networking/putty.png" alt="AWS Lab Credentials" width="350">
</div>

<p> 2. I download <b>PuTTY</b> to use SSH for connecting to the Amazon EC2 instance, then open <b>putty.exe</b> to begin the connection setup. </p>


</br> </br>

<div align="center">
<img src="pictures/networking/putty config.png" alt="AWS Lab Credentials" width="350">
<img src="pictures/networking/putty config 2.png" alt="AWS Lab Credentials" width="350">

</div>

<p>3. I configured my Putty to connect to my Linux instance. I entered: <b>Host Name: ec2-user@Public-IP-of-Instance-B</b> and <b>Port: 22 </b> Then I went to: <b>Connection > SSH > Auth </b> and browsed for the labsuser.ppk key file. </p>


</br> </br>

<div align="center">
<img src="pictures/networking/B.png" alt="AWS Lab Credentials" width="350">
</div>

<p>4. To connect to Instance B. </p>
<p>login as: ec2-user
Authenticating with public key
Last login: ...
[ec2-user@ip-10-0-1-20 ~]$</p>


</br> </br>

<div align="center">
<img src="pictures/networking/A.png" alt="AWS Lab Credentials" width="350">
</div>

<p>5. Attempt Connection to Instance A </p>
<p> I attempted SSH to Instance A. But conuldnt connect. Instance A only has a private IP address, which cannot be reached from outside the VPC. </p>
