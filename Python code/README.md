import os
import re
import xml.dom.minidom
def NAT_network():
        doc = xml.dom.minidom.parse("nat223.xml")
        os.system('virsh net-define nat223.xml')
        os.system('virsh net-start nat223')
        os.system('virsh net-autostart nat223')
def display_network():
        os.system('virsh net-list --all')
def delete_NAT_network():
        os.system('virsh net-destroy nat223')
        os.system('virsh net-undefine nat223')
def create_vm(name,path,netw):
        os.system('sudo virt-install \
        --name '+ name+' \
        --description "Test VM with CentOS 8" \
        --ram=1024 \
        --vcpus=1 \
        --os-type=Linux \
        --os-variant=rhel7 \
        --disk path=/var/lib/libvirt/images/'+path+',bus=virtio,size=10 \
        --graphics none \
        --location /var/lib/libvirt/images/CentOS-8.3.2011-x86_64-minimal.iso \
        --network network='+netw+' \
        --console pty,target_type=serial -x \'console=ttyS0,115200n8 serial\'')
def networks():
        os.system('ifconfig')
def display_vm():
        print "Printing all active and inactive domains\n"
        os.system('virsh list --all')
        print "Printing all active domains\n"
        os.system('virsh list')
def PingIp():
        ipaddr = raw_input('Enter the IP address:')
def PingIp():
        ipaddr = raw_input('Enter the IP address:')
        stream = os.popen('ping -c 4 {}'.format(ipaddr))
        output = stream.read()
        if '0 received' in output:
                print "IP unreachable"
        else:
                print "IP reachable"
                print output
def shutdown_vm(name):
        shut = 'virsh shutdown '+name
        print shut
        os.system(shut)
def run_vm(name):
        run = 'virsh start '+name
        os.system(run)
def delete_vm(name,path):
        destroy = 'virsh destroy '+name+' 2> /dev/null'
        os.system(destroy)
        delete = 'virsh undefine '+name
        os.system(delete)
        os.system('virsh pool-refresh images')
        remove = 'virsh vol-delete --pool images '+path
        os.system(remove)


print "Project: Creating and managing Virtual Machines\nTeam Members:\n1.Akshansh Mishra\n2.Md. Danish Alam\n3.Jasleen Kaur Sethi\n4.Karishma Kiran\n5.an\n5.Sayani Basak\n6.Yandapalli Priya Manasa\n\n\n"
while True:
        choice = int(input("Enter your choice:\n1.Create a virtual machine\n2.Displaying all virtual machine\n3.Running the virtual machine\n4.Shut down the virtual machine\n5.Delete the virtual machine\n6.Display the network connections\n7.Ping the virtual machine\n8.Create a NAT network\n9.Display all networks\n10.Delete a network\n11.Exit Program "))
        if choice == 1:
                check = 1
                name = raw_input("Enter VM name to create: ")
                while check == 1:
                        path = raw_input("Enter path(in the format of name.qcow2")

                        check_path = re.search("\.qcow2$", path)
                        if(check_path):
                                check = 2
                                continue
                        else:
                                print "Enter valid path format"
                netw = raw_input("Enter the network to add the Virtual Machine")
                create_vm(name,path,netw)
        elif choice == 2:
                display_vm()
        elif choice == 4:
                name = raw_input("Enter VM name to shut down: ")
                shutdown_vm(name)
        elif choice == 3:
                name = raw_input("Enter VM name to start running: ")
                run_vm(name)
        elif choice == 5:
                name = raw_input("Enter VM name: ")
                path = raw_input("Enter path(in the format of name.qcow2): ")
                delete_vm(name,path)
        elif choice == 6:
                networks()
        elif choice == 7:
                PingIp()
        elif choice == 8:
                NAT_network()
        elif choice == 9:
                display_network()
        elif choice == 10:
                delete_NAT_network()
        elif choice == 11:
                quit()
        else:
                print "Enter valid choice"
