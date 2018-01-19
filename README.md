# Dell_OS10_Ansible_Lab
##Using Ansible with Dell OS10

### Copy the following files from the Syncplicity share folder;
#### NOS-VM-Template.ova
#### PKGS_OS10-Enterprise-10.4.0E.R1.56-installer-x86_64.bin
#### os10_virtualization_guide_10192016.pdf (optional)
### Open “NOS-VM-Template.ova” with VirtualBox and import the VM
#### Give the VM a name and choose the location to store the VM locally
#### Edit the Virtual Disk Image file name for the VMDK if you want it to match the VM name (optional)
#### Select the checkbox to ‘Reinitialize the MAC address of all network cards’
#### Import and then go into settings --> network --> change the ‘Attached to:’ setting to NAT
#### Start the VM
### The VM will boot into a pre-install linux kernel called ONIE (Open Network Install Environment)
#### Press enter and type ‘onie-discovery-stop’ (this stops the auto discovery boot process)
#### Type ‘ifconfig’ and record the IP address that was assigned by the DHCP server
### Use WinSCP to connect to the above IP with the username root (no password)
#### Upload the file ‘PKGS_OS10-Enterprise-10.4.0E.R1.56-installer-x86_64.bin’ from your local copy into the remote VM directory ‘/root’
### Run the following command on the VM console ‘onie-nos-install /root/PKGS_OS10-Enterprise-10.4.0E.R1.56-installer-x86_64.bin’
### OS10 should install itself, then reboot into a login prompt
#### You will now be able to login to OS10 with username admin and password admin
#### Or if you want to gain access to the linux shell that powers OS10, login as user linuxadmin and password linuxadmin
