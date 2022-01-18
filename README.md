# Hack The Box Driver
![image]("https://user-images.githubusercontent.com/67650329/149863392-0cb492c9-4759-49c1-ae48-8c678311d918.png" width="385px" align="center")
This is my first pentest, here I will pentest HTB Driver. Why I use HTB (Hack the box) because my opinion HTB it’s the best platform to pentest and have so many machine to practice. So I'm having trouble with the exploit flag, but after I tried and searched many times, I finally found the exploit flag.


# Service and Web Enumeration
I used NMAP to scan the target.
Target IP  : 10.10.11.106
Machine IP : 10.10.14.37
![image](https://user-images.githubusercontent.com/67650329/149864550-9e1a7894-eb73-414b-98ad-a899c01c01f4.png width="385px" align="center")

NMAP Command I use :
•	- sC : Performs a script scan using default scripts available in NMAP.
•	- sV : Performs version detection for the services.
NMAP scan found port and services :
•	Port 80 : Apache
•	Port 135 : Transmission Control Protocol
•	Port 445 : Direct TCP/IP MS Networking access





I search the IP and I got the login username and password
 
In this target I try first use common password for admin:
Admin : admin
Admin : admin123
Admin : password
Admin : password123
Admin : qwert
Admin : qwert123
And I got the password for admin its admin.





 
And this it’s the website target 10.10.11.106.
 
I got the upload website, maybe I can input script in here.



Authenticate With the Cracked Password
Make the script first
 
 
This it’s the script and save it @PoC.scf
And run the listener I use responder to listen the script.
 

And I got the hash user tony.
 
After I got the hash user tony, I must crack the hash use hashcat.
 
I got liltony maybe this it’s the password user tony.
Lets go access to target 10.10.11.106
I use evil-wirnm to access the target.
 
Now I am inside the machine target.
 
I got the user.txt on C:\Users\tony\Desktop.







Privilege Escalation
After I got user.txt now I search the flag.
I use reverseshell to execute the flag.
 
Download the exploit first from github:
https://raw.githubusercontent.com/cube0x0/CVE-2021-1675/main/CVE-2021-1675.py.
 
Run smb for run reverseshell.
 

Run listerner.
 
Run the exploit download on github.
 
And baam!
 
I am inside the target machine.


 
And I got the root or flag.txt
On C:\Users\Administrator\Desktop\root.txt.
