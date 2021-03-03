# PERMISSIONS

**User:** 
A user is the one who created the file. By default, whosoever, creates the file becomes the owner of the file. A user can create, delete, or modify the file.

**Group:**
A group can contain multiple users. All the users belonging to a group have same access permission for a file.

**Other:**
Any one who has access to the file other than user and group comes in the category of other. Other has neither created the file nor is a group member.

- Users and groups can be locally managed in /etc/psswd or /etc/group.

> cut -d: -f1 /etc/passwd | column => to show all user accounts.    
> chgrp *newGroup fileName* => change group of file.             
> chgrp -R *group folder* => change group of folder and subfolders             
> sudo chgrp -R --reference=*ref.txt Newdirectory*  => change according to refernce                
> chown *newOwner fileName* => change owner of the file         
> chown *newOwner:newGroup fileName* => change owner and group simultaneously. 

read = r
write = w
execute = x

user = u 
group = g
others = o 
all = a

+ add permission
- remove permission 

**chmod** :=> modifiy permissions
> chmod u=rw,go=rw '*.txt'        
> chmod o+w '*.txt'          
> chmod 777 '*.txt'  => r w x  = 4 2 1  for octal            
> chmod +t  'myfile.txt' => enable sticky bit         
> chmod -t  'myfile.txt; => disable sticky bit           
The **sticky bit** is a user ownership access right flag that can be assigned to 
files and directories on Unix-like systems. 

**Linux Inodes**
An Inode number is a uniquely existing number for all the files in Linux 
and all Unix type systems.When a file is created on a system, a file name 
and Inode number is assigned to it.Generally, to access a file, a user 
uses the file name but internally file name is first mapped with respective 
Inode number stored in a table.The Inode table contains all the Inodes and is
created when file system is created. The df -i command can be used to check how 
many inodes are free and left unused in the filesystem                
> df -i  => list all inode numbers.

**Links**
> ln file hardlink => creates hard link          
> ln -s file softlink => creates soft link    
- links are file and can be removed with *rm* command