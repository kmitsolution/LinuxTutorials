# Links in Linux
### Hard links
<ul>
  <li>The link is between the filename and the actual data stored on the filesystem.</li>
  <li>Each hard linked file is assigned the same Inode value as the original, therefore they reference the same physical file location.</li>
  <li>Removing any link, just reduces the link count, but doesn’t affect other links.</li>
  <li><b>ls -l</b> Commands shows the number of hardlinks for a file</li>
  <li>Hardlinks cannot be created for directories, it is only applicable for files.</li>
  <li>Size of hardlink files remains same all the time </li>
  <li> Hard link can not be created across the partition </li>
</ul>  

#### Example


  ##### Let's create a file called origfile
    $ touch origfile
  ##### Run ls -l command for origfile
    $ ls -l origfile
  ##### Output will be something like below. Here 1 means there is no hardlink get created for this file  
    -rw-r--r--. 1 root root 0 Jul 14 10:30 origfile
  ##### Find the inode number of origfile.
    $ ls -i origfile
  ##### Output ( in this case the inode number is 15336  but it can be different in your case)
    15336 origfile
  ##### Create a directory called linkdir (it is user defined directory you can give any name)
    $ mkdir linkdir
  ##### Create a hard link of origfile. Below command will create a copy of origfile under linkdir with same content as well as inode number of origfile
    $ ln origfile linkdir/
  ##### check the inode number of linkdir/origfile it should be same as origfile inode number
    $ ls -i linkdir/origfile
    15336 origfile
  ##### list origfile, Now it will show 2 hardlinks  
    $ ls -l origfile
    -rw-r--r--. 2 root root 0 Jul 14 10:30 origfile  
  ##### add some data in any of hard link files 
    $ echo "Hard link" >> origfile
  ##### read the content of other hard link file, it should show the same content because both are refering to same file location.
    $ cat linkdir/origfile
    Hard link
  ##### remove origfile and verify the linkdir/origfile exists and it should have same content 
     $ rm origfile
     $ ls -li linkdir/origfile

### Soft Links
<ul>
  <li>It is same as windows shortcut feature.</li>
  <li>Each soft linked file contains a separate Inode value that points to the original file.</li>
  <li>Size of original file is differnt from soft link file </li>
  <li>Soft Link contains the path for original file and not the contents.</li>
  <li>A soft link can link to a directory</li>
  <li>If the soft link is deleted then there is no impact of original file</li>
  <li>If original file is deleted then there is no use of soft link</li>
  <li>Changing the name of original file makes soft link as useless</li>
  <li> unlink <<soft link file>> unlink the soft link of the file </li>
  <li>A Soft link can be created across the partitions</li>
  </ul>  

#### Example

##### Create a file call origfile 
    $ echo "Soft link example" >> origfile
##### Create a directory
    $ mkdir softlinkdir
##### Create a soft link file
    $ ln -s origfile softlinkdir/
##### Check the inode number and size of origfile
    $ ls -li origfile
##### Check the inode number and size of softlinkdir/origfile ( it should be different from origfile)
    $ ls -li softlinkdir/origfile
    15338 lrwxrwxrwx. 1 root root 8 Jul 14 11:40 origfile -> origfile
##### Delete softlinkdir/origfile and read the content of origfile, there will not be any impact of origfile
    $ rm softlinkdir/origfile
    $ cat origfile
    
   
  




