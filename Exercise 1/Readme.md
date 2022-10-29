Exercise 1

Customize your Vagrantfile as necessary with private_network set to dhcp
Once the machine is up, run ifconfig and share the output in your submission along with your Vagrantfile in a folder for this exercise.

Solution:
<br> - Install Vagrant and VirtualBox from the links provided in the course.
<br> - Navigate to the folder where you want to create the Vagrantfile and install the box using the command "vagrant init ubuntu/focal64"
<br> - Open the Vagrantfile and add the following lines: config.vm.network "private_network", type: "dhcp"
<br> - Run the command "vagrant up" to start the virtual machine.
<br> - Run the command "vagrant ssh" to connect to the virtual machine.
<br> - Install the net-tools package using the command "sudo apt-get install net-tools"
<br> - Run the command "ifconfig" to get the IP address of the virtual machine.

![ifconfig-Output](Screenshot%202022-08-15%20152257.png)