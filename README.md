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
15. After reboot check kernel version using "uname -a", the kernel version is updated in my case it is updated to "5.14.3".
16. Modify the cpuid.c file in "linux-5.14.3/arch/x86/kvm/" folder.
17. Modify the vmx.c file in "linux-5.14.3/arch/x86/kvm/vmx/" folder.
18. Follow steps 10-14 again. (new changes will added to kernel)
19. Install virtual manager using command "sudo apt-get install virt-manager".
20. I have setup Desktop for GCP instance, follow link to install Desktop server https://cloud.google.com/architecture/chrome-desktop-remote-on-compute-engine
21. After installation connect to instance using chrome remote desktop https://remotedesktop.google.com/access/
22. Download an ubunut ISO file from website, I downloaded ubuntu 20.04 ISO file
23. Open Virtual Machine Manager.
24. Create VM using downloaded ISO file.
25. After creating VM, boot into VM.
26. Install CPUID package using "sudo apt install cpuid"
27. Create a test C file by putting required instructions.
28. Install C compiler using "sudo apt install gcc".
29. Complie  C file. Ex: gcc test.c
30. Execute C file. Ex: ./a.out
31. The exits and time spent is displayed.

Screenshots
1. Intial screenshot is taken eight after creating VM
<img width="797" alt="Initial_output" src="https://user-images.githubusercontent.com/99615170/205765189-6dda7958-a8aa-42f4-bd52-e99c4fa2f623.png">

2. This screenshot is taken after keeping VM on for some hours
<img width="1440" alt="output2" src="https://user-images.githubusercontent.com/99615170/205765277-39b2bee5-5be9-40d7-83dc-0ab4bbab6294.png">


# Assignment 3

1.For each member in your team, provide 1 paragraph detailing what parts of the lab that member implemented / researched.

I have done it alone.
Screenshots are present in Assignment 3 directory.

2. Steps

1.Take the assignment 2 setup VM

2. modify cpuid.c and vmx.c as per assignment 3 requirements

3. Fire command "make -j 8 modules", (8 is number of CPU's, I have 8 in my VM. Find CPU's using "nproc" command)

4. After above step,fire command "make -j 8".

5. After above step, fire command "sudo make INSTALL_MOD_STRIP=1 modules_install".

6. Reboot VM using "sudo reboot"

7. Open the VM created using virtual manager.

8. Crate test.c file and run it to get required output.


3.Comment on the frequency of exits – does the number of exits increase at a stable rate? Or are there 
more exits performed during certain VM operations? Approximately how many exits does a full VM 
boot entail?

 Approximately 21648929. Number of exits are not stable and keeps changing. It depends on the activities performed on VM.
 
4.Of the exit types defined in the SDM, which are the most frequent? Least?

Exit 48:EPT Violation, Exit 1: External Interrupt, Exit 30: IO Interrupt, Exit 32:WRMSR -> Most Frequently occuring.
Exit 29: MOV DR, Exit 46: Access to IDTR, Exit 55 XSETBV -> Least Frequently occuring.
