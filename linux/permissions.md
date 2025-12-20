# Linux Permissions

Linux is a multi-user operating system. Permissions control who can read, modify, and execute files. In a cybersecurity context, misconfigured permissions can lead to data leaks, writable file systems, etc.

## Permission Strutcture

Each file has three permission sets:
- User (File Owner)
- Group (Users in the same group)
- Others (Everyone else)

These sets has the permissions to read, write, and execute. Permission strings (accessible by doing **ls -l** in the terminal) will showcase something like:
- -rwxr-xr--

The first set of characters, excluding the beginning - which represents that it is a file, showcases user permissions. User can read, wirte, and execute. The second set of three characters showcases the group permissions. He can read and execute, but not write. The final set of three characters represents the permissions for others. They can only read.

Permissions can also be indicated by numerics. The numbers added up indicate the permissions wanted.
- r = 4
- w = 2
- x = 1

When we have rwx, that adds up to 7. R and x adds to 5. This becomes important with chmod.

**Files are not automatically executable**. To allow execution, we utilize chmod (change mode) to either make it executable, or to change permissions (which can also allow execution).
- chmod +x script.sh --> Allows script execution
- chmod -x script.sh --> Remove execution permission
- chmod 755 script.sh --> Users = rwx. Groups = r-x. Other = r-x.
-chmod 000 script.sh --> No one has any permissions to do anything.

To see who the current user operating is, the command is:
- whoami

To view user & group info, the command is:
- id

To switch user, the command is:
- su user

A command that escalates privileges is **sudo**. You will often do this when installing packages or when you need to run commands from the root system itself. 
- sudo apt install package --> Installs packages from the root.
