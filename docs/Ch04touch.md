# Linux- touch command
With the help of touch command you can create an empty file as well as change the modification or access time of a file.

### 1. Create an empty file (test.txt)
```
  touch test.txt
```
### 2. Create multiple empty files ( test1.txt, test2.txt, test3.txt)
```
  touch test1.txt test2.txt test3.txt
```

### 3. Create a set of files with a range (say an example test1 to test20)
```
touch test{1..20}.txt
```
### 4. To change the access and modification time of a file
```
  touch -a test1.txt
```
### 5. To change the modification time only of the file
```
  touch -m test1.txt
```
### 6. To update time of one file with reference to another file
```
# To change the date and time of datefile.txt same as file1.txt file
touch -r file1.txt datefile.txt
```
### 7. To modify the time by specified time instead of default time. touch -t YYYYMMDDhhmm.ss [filename]
```
# To change the date time of file1 year2020 month01 day01 hr10 and min00
touch -t  202001011000 file1
```
### 8. DONOT create a file if it does not exist and if the file exist then update its modify and access time
```
  touch -c file1
```

