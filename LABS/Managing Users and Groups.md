<h1>Managing Users and Groups</h1>

<h3> In this lab, users create new user accounts with a default password, set up groups, and assign the appropriate users to those groups. They also log in as different users to verify and test the configurations. </h3>

</br>

<h3>TASK 1: Using SSH to Connect </h3>
</br>

<div align="center">
<img src="pictures/compute/credentials.png" alt="AWS Lab Credentials" width="350">
</div>

<p> I open the <b>Details</b> drop-down menu and select <b>Show</b> to access the credentials window. I download the <b>labsuser.ppk</b> file and save it, usually in my Downloads folder. I also note the <b>Public IP address</b> and close the details panel. I then download and open <b>PuTTY</b>, and configure it using the provided instructions to connect to my Amazon EC2 Linux instance via SSH. Windows users can skip ahead to the next task.
</p>

</br>

<h3>TASK 2: Create Users </h3>
</br>

<div align="center">
<img src="pictures/compute/pwd.png" alt="AWS Lab Credentials" width="350">
</div>

<p> 1. I validate that I am in the home directory of my current user by using the `pwd` command, which displays the path `/home/ec2-user`. </p>

</br></br>

<div align="center">
<img src="pictures/compute/arosalez.png" alt="AWS Lab Credentials" width="350">
</div>

<p> 2. I create the first user, <b>arosalez</b>, by using the `sudo useradd` command. I then set a password for the account with `sudo passwd arosalez`, entering the password twice to confirm it. While typing the password, nothing appears on the screen, so I type it carefully and press Enter.
</p>

</br></br>

<div align="center">
<img src="pictures/compute/sudo.png" alt="AWS Lab Credentials" width="350">
</div>
