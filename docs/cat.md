# Linux-cat (concatenate) Command
This command is mainly used to read a file but you can perform other operations like write,append and concatenate the file(s).

### 1. To Read or display the content of a file
```
    $ cat <<filename>>
    ## To read file1
    $ cat file1
```
### 2. To Read or display the content of multiple files
```
    # To print content of file1 then file2
    $ cat file1 file2
    # To print content of all txt files
    $ cat *.txt
```
### 3. To view the file content with line number
```
    $ cat -n file1
```
### 4. To create a new file ( after finishing writing in file press Enter and then CTRL + C)
```
    $ cat > file1
```
### 5. To Copy the content of a file to another file
```
    # to copy content of file1 to file2
    $ cat file1 > file2
    # To merge content of multiple files file1,file2.file3 into file4
    $ cat file1 file2 file3 > file4
```
### 6. To Append the content of a file to another file
```
     # to append the content of file1 to file2
    $ cat file1 >> file2  
```
### 7. To Append new content to a file ( after finishing writing in file press Enter and then CTRL + C)
```
      
    $ cat >> file1 
```
### 8. To supress repeated empty lines of a file
```
     $ cat -s file1
```
### 9. To display $ at end of each line
```
    $ cat -E file1
```
### 10. To  display number nonempty output lines, overrides -n
```
    # it will not display number in front of empty lines whereas -n option prints the number for empty lines as well.
    $ cat -b file1
```
