
Linux File System Security:

Linux File System Security restricts user to access the files and directories. User
require permissions to access files or directories. “ls -l” or “ll” command can be used to check security
of any file or directory. Above command will display contents from directory along with its security
details.

1. File type.
2. Owner Permissions.
3. Group Permissions.
4. Other User Permission.
5. Link Count.
6. Owner of file/directory.
7. Group Owner of File or Directory.
8. File Size.
9. Creation Date and Time.
10. File/Directory Name.

Regular File: The regular file is a most common file type found on the Linux system. It governs all
different files such us text files, images, binary files, shared libraries, etc.
Directory: Directory is second most common file type found in Linux. Directory can be created with
the mkdir command
Character Device File: Character and block device files allow users and programs to communicate with
hardware peripheral devices.
Block Device File: Block devices are similar to character devices. They mostly govern hardware as hard
drives, memory, etc.
Local Domain Socket: Local domain sockets are used for communication between processes.
Generally, they are used by services such as X windows, syslog and etc.
Named piped: Similarly, as Local sockets, named pipes allow communication between two local
processes. They can be created by the mknod command and removed with the rm command.
Symbolic Link: With symbolic links an administrator can assign a file or directory multiple identities.
Symbolic link can be thought of as a pointer to an original file.



Link Count: Also called as reference count. It shows count of links of file/directory that has
been created.
Default link count of directory is 2 whereas default link count of file is 1. Whenever
new directory is created, link count of its just parent directory will increase by 1.
There are two types of symbolic link,
a. Hard Link
b. Soft Link


User and group ownership: Basically, by default, user who creates the file/directory is
the owner and his primary group acquires group ownerships of that file/directory. User
owner and group owner of file will be shown in 6th and 7th field as shown in the figure.
“chown” command is use to change owner and group where as using “chgrp” we can change
group ownership.
Syntax,
# chown <user_name>:<group_name> <file/dir_name>
# chgrp <group_name> <file/dir_name>


Managing Permissions: Field 2nd, 3rd and 4th represents permissions for owner, group
owner and other users. Each of that field contain three basic permissions which allow user
to read, write, and executes files. The effect of these permissions differ when applied to file
or directory. If applied to a file, the read permission gives user the right to open file for
reading. Therefore, user can read it’s contain. “chmod” command is use to change these
basic permissions.

<img width="611" height="203" alt="Screenshot 2026-08-05 at 1 08 23 AM" src="https://github.com/user-attachments/assets/1a037283-b37f-4dba-b8f2-e736b33deba2" />

Change permission using letters -
Syntax,
# chmod <u,g,o><+,-,=><r,w,x> <file_name>
                               (Symbols used in syntax are explained in below table)

<img width="608" height="81" alt="Screenshot 2026-08-05 at 1 09 12 AM" src="https://github.com/user-attachments/assets/7215863b-932f-434d-ad6c-a4013b68e7ef" />

Default Permission: When a user creates a file as a regular user, it’s given permission rw-
rw-r-- (664) by default. A directory is given the permission rwxrwxr-x (775). For the root

user, file and directory permission are rw-r--r-- (644) and rwxr-xr-x (755), respectively. These
default values are determined by the value of umask. Type umask to see what your umask
value is.

If you ignore the leading zero for the moment, the umask value masks what is
considered to be fully opened permissions for a file 666 or a directory 777. The umask value
of 002 results in permission for a directory of 775 (rwxrwxr-x). That same umask results in a
file permission of 644 (rw-rw-r--).

<img width="616" height="81" alt="Screenshot 2026-08-05 at 1 09 57 AM" src="https://github.com/user-attachments/assets/c515c276-6241-4cbe-aab8-f88668373d2d" />


<img width="615" height="107" alt="Screenshot 2026-08-05 at 1 10 27 AM" src="https://github.com/user-attachments/assets/32b9a310-33b4-44d0-af2e-4143a4b210f9" />

## ACL 
- https://medium.com/@mukundeotale9860/acl-access-control-list-e2ed72244ce3
- https://medium.com/@mukundeotale9860/acl-access-control-list-9ab165d00fe2





