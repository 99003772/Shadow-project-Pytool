# Shadow-project-Pytool

# Aim 
Using Pytool We should create a virtual machine, Deletion of virtual machine, Network creation, NAT, so that we can display number of Virtual Machine, Network Status and also create a Python Menu-Driven Code for run these commands.
# Individual Contribution
| Work Assigned | Team Members  |
| ------------- | ------------- |
| Creation and Installation of Virtual Machine  | Karisma Kiran  |
| Integration of Code  | Yandapalli Priya Manasa  |
| Network Creation  |  Akshansh Mishra  |
| Manual Code   |  Jasleen Kaur Sethi  |
| Code Template-Menu Driven Program  |  Md. Danish Alam  |
| Creation and Installation of Virtual Machine  | Sayani Basak  |

# Summary of the Project
In this project, we'll see how to 
1. create a VM
2. delete a VM
3. shutdown a VM
4. ping the VM
5. network creation
6. creation of NAT

We thus display number of Virtual machines and the network status. Here, we're creating a Virtual machine in which we're using a KVM guest that is built into Linux. KVM lets us turn Linux into a hypervisor that allows a host machine to run multiple Virtual machines. We're using libvirt package that provides the server and the host side libraries for interacting with hypervisors and host system. For communicating with libvirt, we use a command line tool called virsh. After creating a KVM Guest, we'll install Centos8 Operating System. To create a centos8 Virtual machine, we're required the centos8 ISO file on our KVM virtualization host. So, we'll create the VM by creating the qcow2 image for the disk path. We've added a network in the command line as a part of creation. We've also added the commands for creation, deletion and display of VM to python code.

So first we'll create a network file where we'll define the name, mask, subnet mask etc, and a NAT network is created. We'll check if the network has been established or not. Then we'll create a VM by mentioning the name, disk path & the network, and the installation process begins. We'll change the time zone, select the software, define the destination of VM, enable kdump option, define the network configuration, and give a new root password. And according to this, the installation will begin and the VM starts running. We can also shut down and delete the VM by mentioning the name and the disk path.

Now to check if the VM has been created and is able to communicate with the host machine or not we'll first check all the network connections. As there is a virtual bridge that is defined to the network, we can check the IP address of it to ping the VM. After pinging we will see that the packets are transmitted and there is no loss which means that the IP is reachable and is able to ping the host machine. We also see, that the host machine can ping the virtual machine while the VM cannot ping the host machine's public address while it is able to ping its private address. This implies that the established network is a NAT network.

# 4W1H
What: 
1. We are establishing a network and displaying the network status.
2. We're creating, deleting and displaying a Virtual machine in which we're using a KVM guest that is built into linux. 
3. We're using libvirt package that provides the server and host side libraries for interacting with hypervisors and host system.  
4. For communicating with libvirt, we use a command line tool called virsh.  

When:
1. When we need multiple machines working simultaneously with different OS, or functionalities. 

Why:
1.  We're creating a VM by mentioning the name, path & the network, so that the installation process will begin.
2.  To check if the VM has been created and is able to communicate with the host machine or not we'll first check all the network connections. 

Where:
1. We are using the Microsoft azure Virtual environment for creating, deleting the Virtual machine.

How:

Input: We need to give the choice between 1-11. 

Output: We will be able to create a VM, display all VM, run the VM, shutdown the VM, delete the VM, display the network connections, Ping the VM, creation of a network, display all networks, delete a network, exit the program.

# Challenges Faced 
There are some challenges faced during the project. They are:


1. Deploying the ISO Image to the Virtual Machine.

2. Finding differences between ISO and qcow2.

3. Adding network XML file to the python code.

4. While connecting to the portal Network connecting issues for connecting to serial console.

5. All the issues were solved by searching on internet and with references.
