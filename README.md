# Project 8 - Pentesting Live Targets

Time spent: 3 hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQL Injection (SQLi)  
The website has the vulnerability of SQL Injection. As shown below, instead of inputing intended number for "id", ' OR SLEEP(5)=0--' is put in to stall the site.
![Gif 1](https://github.com/jiayiw6/Week-8-CodePath-Web-Security/blob/master/gif_8_1.gif)

Vulnerability #2: Session Hijacking/Fixation  
The website's session ID can be obtained and set to another session ID.
![Gif 2](https://github.com/jiayiw6/Week-8-CodePath-Web-Security/blob/master/gif_8_2.gif)

## Green

Vulnerability #1: Username Enumeration  
The website's usernames can be obtained by entering an user name to see if the "span" class failed or failure. It shows as failed if the user does not exist and it shows as failure if the user does exist but the password is incorrect. 
![Gif 3](https://github.com/jiayiw6/Week-8-CodePath-Web-Security/blob/master/gif_8_3.gif)

Vulnerability #2: Cross-Site Scripting (XSS)  
The website is vulnerable to XSS attack. By inserting a script (for example, <script>alert(1);</script>) in the "feedback"tab which is not log-in required, the attack will deliver when a user opens the log-in required "feedback" tab. 
![Gif 4](https://github.com/jiayiw6/Week-8-CodePath-Web-Security/blob/master/gif_8_4.gif)

## Red

Vulnerability #1: Insecure Direct Object Reference (IDOR)  
The website is vulnerable to Insecure Direct Object Reference. By Accessing https://35.184.88.145/red/public/staff/salespeople/show.php?id=10, a page that's not suppose to be public is shown up. 
![Gif 5](https://github.com/jiayiw6/Week-8-CodePath-Web-Security/blob/master/gif_8_5.gif)

Vulnerability #2: Cross-Site Request Forgery (CSRF)  
The website allows log-in user to edit other user profiles. When inspecting the element, it is possible to change the csfr token which leads to unintended information changing. 
![Gif 6](https://github.com/jiayiw6/Week-8-CodePath-Web-Security/blob/master/gif_8_6.gif)

## Notes
The CSRF vulerability was the hardest one to find for me. 
