# Linux - date command

This command is used to display the current date and time of your local system.You can use this command to change the current date and time( you must be login with root or super user.

#### NOTE:- Output will be in the format as mentioned in each output but the value could be different depends upon your system current datetime

### 1. Display current date and time with TimeZone
<b>Command</b>
```
   $ date
```
<b>Output</b>
```
Sun Jul 11 21:00:55 IST 2021
```
### 2. Display the time in GMT(Greenwich Mean Time)/ UTC( Cordinated universal time)
<b>Command</b>
```
  $ date -u
```
<b>Output</b>
```
Sun Jul 11 15:37:17 UTC 2021
```

### 3. Display specified date time in string format ( you can use --date or -d options alternatively)

<table>
  <th> <td><b>Command</b> </td><td><b>Output</b></td><td><b>Remarks</b></td></th>
  <tr><td>1</td><td> date --date="08/28/1975"</td><td>Thu Aug 28 00:00:00 IST 1975 </td></tr>
  <tr><td>2</td><td> date --date="08/28/1975"</td><td>Thu Aug 28 00:00:00 IST 1975 </td></tr>
  <tr><td>3</td><td> date --date="Aug 28 1975 12:35:00"</td><td>Thu Aug 28 12:35:00 IST 1975 </td></tr>
  <tr><td>4</td><td> date --date="Ag 28 1975 12:35:00"</td><td>date: invalid date ‘Ag 28 1975 12:35:00’</td></tr>
  <tr><td>5</td><td> date --date "3 years ago"</td><td>Wed Jul 11 21:29:51 IST 2018</td><td> It prints 3 years ago date and time</tr>
  <tr><td>6</td><td> date -d "yesterday"</td><td>Sat Jul 10 21:34:34 IST 2021</td><td> It 1 day ago date and time</tr>
  <tr><td>7</td><td> date -d "1 hour ago"</td><td>Sun Jul 11 20:35:54 IST 2021</td><td> It prints 1 hour ago date and time</tr>
  <tr><td>8</td><td> date -d "1 min ago"</td><td>Sun Jul 11 21:34:54 IST 2021</td><td> It prints 1 min ago date and time</tr>
  <tr><td>9</td><td> date -d "5 day"</td><td>Fri Jul 16 21:34:54 IST 2021</td><td> It prints date and time after 5 days</tr>
  <tr><td>10</td><td> date -d "2 year"</td><td>Tue Jul 11 21:39:53 IST 2023/td><td> It prints date and time after 2 years</tr>
  <tr><td>11</td><td> date -d "next wed"</td><td>Wed Jul 14 00:00:00 IST 2021/td><td> It prints date and time for next wednesday</tr>
  
</table>  

### 4. Set system's date and time by using -s or --set option

<b>Command</b>
```
$ date --set="08/20/2021"
```
<b>Output</b>
```
Fri Aug 20 00:00:00 IST 2021
```

### 5. Display the date and time by reading each line of the file ( use -f or --file option)
Consider datefile.txt contains following lines </br>
01/05/2021

01/11/2020

<b>Command</b>
```
    $ date -f datefile.txt
```
<b>Output</b>
```
Tue Jan  5 00:00:00 IST 2021
Sat Jan 11 00:00:00 IST 2020
```
### 6. Display the last modified date and time of a function ( use -r option)
<b>Command </b>
```
date -r datefile.txt
```
<b>Output </b>
```
Sun Jul 11 21:59:44 IST 2021
```
### 7. Display date and time with different formats (date +[Format])
```
%D: Display date as mm/dd/yy.   
%F: Display full date in (yyyy-mm-dd format)
%d: Display the day of the month (01 to 31).       
%a: Displays the abbreviated name for weekdays (Sun to Sat).
%A: Displays full weekdays (Sunday to Saturday).
%h: Displays abbreviated month name (Jan to Dec).
%b: Displays abbreviated month name (Jan to Dec).
%B: Displays full month name(January to December).
%m: Displays the month of year (01 to 12).
%y: Displays last two digits of the year(00 to 99).
%Y: Display four-digit year. 
%T: Display the time in 24 hour format as HH:MM:SS.
%H: Display the hour.
%M: Display the minute.
%S: Display the seconds.
```
<b>Examples </b>
```
date +%d-%M-%Y
```
<b>Output</b>
```
11-10-2021
```
<b> Create a file with filename with date 
```
   touch file_`date +%d-%M-%Y`
   # it will create a file with name file_11-14-2021
```
  
  
  
  
