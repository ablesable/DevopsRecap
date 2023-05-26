## Changing shells
` grep newuser /etc/passwd` \
` usermod --shell /bin/bash newuser`\
` grep newuser /etc/passwd` (new shell added after restart)

## Permissions
- d on the beginning is sign that this is a directory.
- next three letters are permission of a user.
- second three letters are permission of a group.
- last three letters are permissions for EVERYONE ELSE which are not a user or a group.
- After ls -lsah will see . directory which is a directory of a current folder.
- .. directory that current directory appears to be in.

## Changing permissions
`$ sudo chown newuser:newuser /specific-directory` (changes OWNERSHIP to newuser user and newuser group for /specific-directory). \
`$ sudo chmod u=rw, g=rw, o=rw specificfile` (changes permissions to read and write for user, group and others) \
`$ sudo chmod u=rwx, g=rwx, o=rwx specificdirectory` (changes permissions to read and write and execute for user, group and others. For directories we need to add execute permissions BECAUSE YOU CANNOT USE CHANGE DIRECTORY COMMAND!) 

<b> We can change chmod by numbers, just google it :) </b>
Each number means user, group and then others. 
- 4 number is for read
- 2 number is for write
- 1 number is for execute 
- Adding them up together will give us total permission, 7 is a permission for read, write and execute.