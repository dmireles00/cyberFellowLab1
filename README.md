# cyberFellowLab1


## Blue

Vulnerability: SQL Injection

<img src='SQLI-blue.gif' title='Session Hijacking/Fixation' width='' alt='' />

In the salesperson page, a salesperson is selected to retrieve the individuals information from the database.  We can then add
```'OR SLEEP(5)=0--;'``` to the end of the URL, which causes a  database inquiry error.  This causes the database to reset to Daron Burke's page, which indicates an SQL injection vulnerablitity.



Vulnerability: Session Hijacking/Fixation

<img src='SESSION1-blue.gif' title='Session Hijacking/Fixation' width='' alt='' />
<img src='SESSION2-blue.gif' title='Session Hijacking/Fixation' width='' alt='' />

Two different browsers need to be opened for this vulnerability to work.  One browser in the blue website is logged into using the pperson credentials.  The SESSIONID for the logged in browser is then copied using the ```/public/hacktools/change_session_id.php``` script, and pasted into the other broswer using the change session tool.  After the session ID is copied, the second browser login is refreshed, and the user is allowed into the website using the copied session ID.


## Green

Vulnerability: Username Enumeration

<img src='EU-green.gif' title='Username Enumeration' width='' alt='' />
Using the known usernames of pperon and jmonroe99, with a random password, we can see that the message "log in was unsuccessful" is printed in bold text.  When the username of admin is used, the message "log in was unsuccessful" is not printed in bold.  The bold text indicates that the username is valid in the green site.

Vulnerability: Cross-Site Scripting

<img src='XSS-green.gif' title='Cross-Site Scripting' width='' alt='' />

In the Contact page, the name and email boxes were filled out out, and the script ```<script>alert("Dan was here");</script>``` was entered into the feedback section.  By navigating to the feedback section through the login page, several XSS scripts appear, including the one ```Dan was here```.


## Red

Vulnerability: Insecure Direct Object Reference

<img src='IDOR-red.gif' title='Insecure Direct Object Reference' width='' alt='' />

In the Find a Salesperson page, the first salesman David Burke is selected which gives the URL. ```https://35.184.234.47/red/public/salesperson.php?id=1```.  The id can be changed to 10 and 11, which give two pages that are not visible in the blue or green websites.  The blue and green websites prevent the information from being revealed by limiting the number of id's that are visible to the user.

Vulnerability: Cross-Site Request Forgery

<img src='CSRF-red.gif' title='Cross-Site Request Forgery' width='' alt='' />
<img src='CSRF-blue.gif' title='Cross-Site Request Forgery' width='' alt='' />
When I trying to edit the information after changing the value of csrftoken, red section is still able to make a change, while the other two websites show "Error: invalid request" after I changed its csrftoken. 


## Bonus 2:

<img src='XSSBONUS-green.gif' title='Cross-Site Scripting' width='' alt='' />

In green section, the script ```<script>document.location="https://www.msn.com"</script>``` is input into the feedback section.  By navigating thorugh the login page to the feedback section, the script activates and takes us to the ```www.msn.com``` webpage. 



