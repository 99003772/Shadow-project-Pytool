# Shadow-project-Pytool

# Aim 
Using Pytool we need to do Vm creation, deletion, network creation, NAT, so that we can display number of VM, network status.

# Individual Contribution
| Work Assigned | Team Members  |
| ------------- | ------------- |
| Creation and Installation of Virtual Machine  | Karisma Kiran  |
| Integration of Code  | Yandapalli Priya Manasa  |
| NAT Execution  |  Akshansh Mishra  |
| Manual Code   |  Jasleen Kaur Sethi  |
| Code Template-Menu Driven Program  |  Md. Danish Alam  |
|Network Creation for Virtual Machine  | Sayani Basak  |

# Challenges Faced 
There are some challenges faced during the project. They are:
· Deploying the ISO Image to Virtual Machine.
· Finding differences between ISO and qcow2.
· Adding network XML fil to code.
· While connecting to the portal Network connecting issues for connecting to serial console.
· All the issues were solved by searching in internet and with references.

# Summary
In this project, we'll see how to create a VM, delete a VM, shutdown a VM, pinging the VM, network creation, creation of NAT, so that we can display number of Virtual machines, network status. Here, we're creating a Virtual machine in which we're using a KVM guest that is built into Linux. KVM lets us turn Linux into a hypervisor that allows a host machine to run multiple Virtual machines. We're using libvirt package that provides the server and host side libraries for interacting with hypervisors and host system. For communicating with libvirt, we use a command line tool called virsh. After creating a KVM Guest, we'll install Centos8 O.S. To create a centos8 Virtual machine, we're required the centos8 ISO file on our KVM virtualization host. So, we'll create the VM by using the qcow2 image. We've added a network in the command line as a part of creation. We've also added the commands for creation of VM to python code.

So first we'll create a network file where we'll define the name, mask, subnet mask etc, and a NAT network is created. We'll check if all the networks have been established or not. Then we'll create a VM by mentioning the name, path & the network, and the installation process begins. We'll change the time zone, select the software, define the destination of VM, enable kdump option, define network configuration, and give a new root password. And according to this the installation will begin and the VM starts running. We can also shut down and delete the VM by mentioning the name and path.

Now to check if the VM has been created and is able to communicate with the host machine or not we'll first check all the network connections. As we have made virtual bridge in the network connection, we can check the IP address of it to ping the VM. After pinging we will see that the packets are transmitted and there is no loss which means that the IP is reachable and is able to ping the host machine.
