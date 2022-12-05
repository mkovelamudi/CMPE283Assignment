# Assignment-1

Steps For Assignment-1

1. Create New Instance(VM)/Take a Linux Machine with "Nested Virtualization" enabled.
2. Install Git and clone the repository into the Machine.
3. Install "gcc" and "make" on the machine. Example "sudo apt install gcc make" (For ubuntu)
4. Install "Linux Headers" with username on the machine. Example "sudo apt install linux-headers-$(uname -r)
5. Update the cmpe283-1.c file to accomodate new controls.
6. Run "make" command (Makefile should be in same folder).
7. This will create new files.
8. Insert module by running "sudo insmod cmpe283-1.ko" (sudo permission is required)
9. Run "sudo dmesg" command to see the output printed by kernel module.
10. Commit the changes and push the changes to git repository using "git commit" and "git push" commands.

11. For Sample output check below
Following line suggests start of module "CMPE 283 Assignment 1 Module Start"
Following line suggests end of module "CMPE 283 Assignment 1 Module Exits"
 
12. <img width="468" alt="image" src="https://user-images.githubusercontent.com/99615170/199652543-666566c2-7938-4844-bca0-d1228dbdb084.png">
 
# Note
Tertiary Processor Based controls cannot be added, as the Can Set Flag is No in primary processor controls.


# Assignment -2

1. Take a VM with ubunut 18.04 version
2. Boot into VM
3. Clone or get linux kernel repo, I used using "wget https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-5.14.3.tar.xz"
4. Install dependency packages "sudo apt-get install git fakeroot build-essential ncurses-dev xz-utils libssl-dev bc flex libelf-dev bison"
5. extract zip file "tar xvf linux-5.14.3.tar.xz"
6. change directory into linux "cd linux-5.14.3"
7. Copy existing config file to current folder "cp /boot/config-$(uname -r) .config"
8. fire command "make oldconfig" to copy from existing config file, press enter to keep default operations
9. Fire command "make prepare" 
10. Fire command "make -j 8 modules", (8 is number of CPU's, I have 8 in my VM. Find CPU's using "nproc" command)
11. After above step,fire command "make -j 8".
12. After above step, fire command "sudo make INSTALL_MOD_STRIP=1 modules_install".
13. After above step, fire "uname -a" to check the version of kernel.
14. Reboot VM using "sudo reboot"
15. After reboot check kernel version using "uname -a", the kernel version is updated in my case 5.14.3.
16. Install virtual manager using command "sudo apt-get install virt-manager".
17. I have setup Desktop for GCP instance, follow link to install Desktop server https://cloud.google.com/architecture/chrome-desktop-remote-on-compute-engine
18. After installation connect to instance using chrome remote desktop https://remotedesktop.google.com/access/
19. Download an ubunut ISO file from website, I downloaded ubuntu 20.04 ISO file
20. Open Virtual Machine Manager.
21. Create VM using downloaded ISO file.
22. After creating VM, boot into VM.
23. Install CPUID package using "sudo apt install cpuid"
24. Create a test C file by putting required instructions.
25. Install C compiler using "sudo apt install gcc".
26. Complie  C file. Ex: gcc test.c
27. Execute C file. Ex: ./a.out
28. The exits and time spent is displayed.
