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
 
12. <img width="468" alt="image" src="https://user-images.githubusercontent.com/99615170/199652543-666566c2-7938-4844-bca0-d1228dbdb084.png">
 
