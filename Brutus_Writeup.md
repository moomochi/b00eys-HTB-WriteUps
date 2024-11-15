# B00ey's writeup for HTB Brutus.

Howdy! My name is b00ey and welcome to my first ever writeup of many writeups I will be doing.  I finally decided to start doing writeups to document the steps/thought process for the HTB machines I pwded. _(plus it gives me 
pratice to git and the writing part of cyber not alot of people talk about..)_


I will mention the resources I used, and steps I done to tackle each of the boxes :) . 

## Overview of Brutus. 
According to HTB, Brutus allows the player to

**_"Familiarize yourself with Unix auth.log and wtmp logs. We'll explore a scenario where a Confluence server was brute-forced via its SSH service.
After gaining access to the server, the attacker performed additional activities, which we can track using auth.log. Although auth.log is 
primarily used for brute-force analysis, we will delve into the full potential of this artifact in our investigation, including aspects of privilege escalation, persistence, and even some visibility into command execution."_**

Meaning that we will be dealing with both the auth.log and wtmp log that is provided with the machine. 

# Diving in first. Pre-introduction. 
When I first downloaded both the Brutus files, I strugged for a min or so to extract the file in order to read the contents. If you try extract the file, without any data compresssion or decompression tool like 7-Zip or Win-RAR
it will give you this error. 

<img width="830" alt="Raw_Extract_Error" src="https://github.com/user-attachments/assets/149674a3-7e1f-4b0b-a2ff-e9636cdf5010">

By typing in "Error 0x80004005" into a search engine, you can find many resources  

But I used [this article by IONOS ](https://www.ionos.com/digitalguide/server/configuration/0x80004005-error/) to solve my issue, quoting

_"Resolving Error “0x80004005” When Unpacking Files
If you want to unpack zipped files with the standard Windows tool and are confronted with the error code “0x80004005”, 
this usually means that the archive has been compressed with an algorithm that’s not supported. A second possible cause is that the ZIP file is password protected. After all, 
the Windows program only supports ZIPCrypto and AES 128, while encrypted archive files are often based on AES 256. An easy solution is to use third-party tools like WinZip or the freely licensed 7-Zip. 
These programs support far more compression and encryption methods than the integrated Windows service, significantly increasing your chances of being able to open the file."_


This made sense as Brutus was a password protected file , however downloading a data compression tool like 7-Zip fixed the issue right away and I was able to open up the file.

# Trying to Solve Brutus.
So Brutus has 8 tasks in total to complete. This ranges from identifying the IP address used by the attacker to which command they used in sudo. 


_TASK 1_
_Analyzing the auth.log, can you identify the IP address used by the attacker to carry out a brute force attack?_



_TASK 2_
_The brute force attempts were successful, and the attacker gained access to an account on the server. What is the username of this account?_



_TASK 3_
_SSH login sessions are tracked and assigned a session number upon login. What is the session number assigned to the attacker's session for the user account from Question 2?_



_TASK 4_
_SSH login sessions are tracked and assigned a session number upon login. What is the session number assigned to the attacker's session for the user account from Question 2?_








