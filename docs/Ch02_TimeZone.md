## Linux :- Change TimeZone -CentOs 7 or Red Hat 7

Execute below command as an <b>Administrator</b> or <b>root user</b>
1. Find all the timezones available, timedatectl command is used to query on system clock settings
 ```
    timedatectl list-timezones 
  # if you want to store these timezones in a file
    timedatectl list-timezones > timezones.txt
  # Read this file to display all the timezones
    cat timezones.txt
 ```

2.  <b>tzselect</b> command is used to set the timezone for your system
  ```
   # To change the timezone run below command 
      tzselect
   
   # After running above command it will ask certain number of question like select the location, and then select the country 
     and at the end you need to confirm to change the timezone.
   # Next run below command to set the datetime format as per the timezone ( eg if selected timezone is Asia/kolkata)
   
      timedatectl set-timezone Asia/Kolkata
  ```
3. Verify the <b>status</b> of the system timezone.

```
   #Run below command to check the datetime status w.r.t. timezone
       timedatectl status
   # You can also run date command to check the current date and time
       date
```
   
  
  


