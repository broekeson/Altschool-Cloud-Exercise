Exercise: 3

Create 3 groups – admin, support & engineering and add the admin group to sudoers. 
Create a user in each of the groups. 
Generate SSH keys for the user in the admin group

Instruction:

Submit the contents of /etc/passwd, /etc/group, /etc/sudoers

Solution:
<br> - Create the groups using the command "sudo groupadd admin", "sudo groupadd support" and "sudo groupadd engineering".
<br> - Create the users using the command "sudo useradd -m -G admin,engineering -s /bin/bash broekeson", "sudo useradd -m -G support -s /bin/bash godwin" and "sudo useradd -m -G engineering -s /bin/bash user3".
<br> - Add the user "broekeson" to the sudoers using the command "sudo usermod -aG sudo broekeson".
<br> - Generate the SSH keys for the user "broekeson" using the command "ssh-keygen" and follow the instructions.

<br> 1. The contents of /etc/passwd are:
<br> ![passwd Output](passwd.png)

<br> 2. The contents of /etc/group are:
<br> ![group Output](groups.png)

<br> 3. The contents of /etc/sudoers are:
<br> ![sudoers Output](sudoers.png)
