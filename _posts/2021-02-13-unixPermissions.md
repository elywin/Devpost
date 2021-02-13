---
layout: post
title: Unix/Linux Permissions
---

**Deep Dive Into Linux Permissions**<br>
Every file and folder on the system has a set of permissions that specifies who is allowed to do what with that particular file or folder.<br>
Each may belong to three user based permission groups (UGO):
- User/Owner permissions (U) − The owner's permissions determine what actions the owner of the file can perform on the file, they will not impact the actions of other users.(eg. Root, elywin, michael)
- Group permissions (G)− The group's permissions determine what actions a user, who is a member of the group that a file belongs to, can perform on the file, they will not effect the actions of other users.(e.g. sudo, admin, docker)
- Other (world) permissions (O)− The permissions for others indicate what action all other users can perform on the file.(e.g. non-owner and non-group members)

There are three types of permissions:<br>
- read(r)
- write(w)
- execute(x)

Read permission<br>
A read permission on a file enables a user to read the contents of the file.

Write permission<br>
A write permission allows a user to modify or delete the file. 

Execute permission<br>
 execute permission allows a user to run the file as a script or an executable.

You can view the permissions of a file or directory by using the ls -l command.<br>

```
$ls -l 
-rw-r--r--  1 elywin elywin       48 Oct  4 03:01  add.tcl
drwxrwxr-x  3 elywin elywin     4096 Jul 22  2020  data
```

The first character indicates whether the item is a file or a directory. A dash “ - “ means that the item is a file, whereas a “d” means it’s a directory. 

> drwxrwxr-x  3 elywin elywin     4096 Jul 22  2020  data

- “data” is a folder
- “add.tcl” is a file

The next three characters are the permissions of the file’s owner. The owner is usually the user who created the file and has the most control over it. 

> drwxrwxr-x  3 elywin elywin     4096 Jul 22  2020  data

U	G	O
rwx	rwx	r-x

User/Owner can read(r), write(w) and execute(x).

The next three characters are the permissions of the owner’s group.

> drwxrwxr-x  3 elywin elywin     4096 Jul 22  2020  data

U	G	O
rwx	rw-	rw-

Group can read(r), and write(w).

The final three are the permissions for everyone else.

> drwxrwxr-x  3 elywin elywin     4096 Jul 22  2020  data

U	G	O
rwx	rwx	r-x

Others can read(r), and execute(x).


> `R indicates read, w indicates write, and X indicates execute. And a dash indicates the lack of that permission except for the first dash that indicates a file or directory/folder.`

Changing Permissions
To change the file or the directory permissions, you use the chmod (change mode) command,  there are two ways to use chmod command, the symbolic mode and the absolute mode(use binary references/ numbers ).

Using chmod in Symbolic Mode
 With symbolic permissions you can add, delete, or specify the permission set you want by using the operators “ +, - , = ”.

+ : Adds the designated permission(s) to a file or directory.

- : Removes the designated permission(s) from a file or directory.

= : Sets the designated permission(s).

Here's an example using add.tck. Running ls -1 on the add.tcl file shows that the file's permissions are as follows:

```
$ls -l add.tcl
-rw-r--r-x  1 elywin elywin       48 Oct  4 03:01  add.tcl
```

Then each example chmod command run on the add.tcl, followed by ls –l, so you can see the permission changes:

```
$chmod u+x add.tcl
$ls -l add.tcl
-rwxr--r-x  1 elywin elywin       48 Oct  4 03:01  add.tcl

$chmod o-x add.tcl
$ls -l add.tcl
-rwxr--r--  1 elywin elywin       48 Oct  4 03:01  add.tcl

$chmod g = wx add.tcl
$ls -l add.tcl
-rwxrwxr--  1 elywin elywin       48 Oct  4 03:01  add.tcl
```

You can combine these commands on a single line:

```
$chmod g-wx,u-x,o = wx add.tcl
$ls -l add.tcl
-rw-r--rwx  1 elywin elywin       48 Oct  4 03:01  add.tcl
```

**Using chmod with Absolute Permissions(integers/binary reference)**

The second way to modify permissions with the chmod command is to use a number to specify each set of permissions for the file. Each permission is assigned a value, and the total of each set of permissions provides a number for that set.

0 : no permission  ---
1 : execute  permission  --x
2 : write  permission  -w-
3 : execute and write permission: 1(x) + 2(w) = 3  -wx
4 : read permission  r--
5 : read and execute permission: 4(r) + 1(x) = 5  r-x
6: read and write permission: 4(r) + 2(w) = 6 rw-
7: all permissions (4)read + write(w) + execute(x) = 7 rwx

Here's an example using add.tcl file. Running ls -1 on the add.tcl file shows that the file's permissions are as follows:

```
$ls -l add.tcl
-rw-r--r-x  1 elywin elywin       48 Oct  4 03:01  add.tcl
```

Then each example chmod command run on the add.tcl, followed by ls –l, so you can see the permission changes:

```
$ chmod 755 add.tcl
$ls -l add.tcl
-rwxr-xr-x  1 elywin elywin       48 Oct  4 03:01  add.tcl

$chmod 743 testfile
$ls -l add.tcl
-rwxr---wx  1  elywin elywin       48 Oct  4 03:01  add.tcl

$chmod 043 add.tclk
$ls -l add.tcl
----r---wx  1  elywin elywin       48 Oct  4 03:01  add.tcl
```

**Changing Owners and Groups**


