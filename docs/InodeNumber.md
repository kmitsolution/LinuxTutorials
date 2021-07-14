# Inode
Inode is a data structure that stores metadata about file(s). It stores the information USERID, GROUPID, DEVICEID, FILESIZE, DATEOFCREATION, PERMISSION, OWNER, FILE PROTECTION FLAG, LINK COUNTER TO DETERMINE NUMBER OF HARDLINKS

<ul>
  <li>Each inode is identified by an integer number.</li>
  <li>An inode is assigned to a file when it is created.</li>
  <li>When FileSystem is created then it creates the Inode Table which contains all Inodes.</li>
  <li><b>df -i</b> Command is used to list how many inodes are free and used.</li>
  <li><b>ls -i</b> Command is used to display the inode number of file(s).</li>
  <li><b>ls -di</b> Command is used to display the inode number of directory(ies).</li>
  <li><b>ls -ai</b> Command is used to display the inode number of file(s) including hidden files.</li>
  <li><b>ls -li | wc -l </b> Command will display total number of inodes in the current directory</li>
</ul>  

### Inode and find command
You can search a file on the basis of inode number.
```
   # To find the file with given inode number(in below example I used inodenumber 5380912) under root directory(/)
   find / -inum 5380912
```
### Inode with cp and mv command
When you copy a file then source and destination files will have differnt inode number whereas in move command when the source file is moved to destination then its inode number does not get changed.
<b>cp file example</b>
```
# Create a file called cpfile
  touch cpfile
# Check its inode number 
  ls -i cpfile
# copy file cpfile to newcpfile
  cp cpfile newcpfile
# Now compare the inode number of both the files it should be different
  ls -li cpfile newcpfile
```

<b>mv file example</b>
```
# rename the file cpfile with mvfile
   mv cpfile mvfile
# Check the inode number of mvfile ( it should be same as it was for cpfile)
   ls -li mvfile
```
