<h1>Snort IDS/IPS Implementation on Ubuntu</h1>


<h2>Description:</h2>
Implemented Snort IDS/IPS on an Ubuntu machine, showcasing adept technical skills in intrusion detection and prevention systems. Conducted thorough testing, including attacks from a Kali Linux system, to assess effectiveness. Developed custom rules and documented the installation, configuration, and test results for clear insights into the project's outcomes.
<br />


<h2>The tools used in this project include:</h2>

- <b>Ubuntu: Operating system for hosting the Snort IDS/IPS.</b>
- <b>Snort: Intrusion Detection and Prevention System (IDS/IPS) software.</b>
- <b>Kali Linux: Used as an attacking system to test the effectiveness of Snort.</b>


<h2>Program walk-through:</h2>

<h3>To install the Snort IDS/IPS follow the below steps:</h3>

<p align="left">
Installing snort in ubuntu: <br/>
<img src="https://i.imgur.com/ErwM37F.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
Give the IP range and click ok. To check this range, open another terminal and give command: ip a s  <br/>
<img src="https://i.imgur.com/7tO6EAn.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
ip a s: <br/>
<img src="https://i.imgur.com/z3GKl8v.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
To check snort is installed:  <br/>
<img src="https://i.imgur.com/3QkqDtr.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
To turn on promisc mode:  <br/>
<img src="https://i.imgur.com/STO7Van.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
Below is the dir where everything will be stored:  <br/>
<img src="https://i.imgur.com/W93dcmZ.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
We need to make some changes in snort.conf file:  <br/>
<img src="https://i.imgur.com/S0CnMku.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
Click i to insert > give your ip range:
click esc+:wq! to write the file and save it  <br/>
<img src="https://i.imgur.com/C7YbzGl.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
To validate the conf:  <br/>
<img src="https://i.imgur.com/wAlFqyJ.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
To get the line number in files:  sudo vim /root/.vimrc:  <br/>
<img src="https://i.imgur.com/fRqvR9I.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
Open the snort.conf and comment-out the rules with below command:
:598,718s/^/#
<br />
Now, we will write local rules
We can also visit http://snorpy.cyb3rs3c.net/ to write the rules

sudo vim /etc/snort/rules/local.rules > type the below rule > save the file:  <br/>
<img src="https://i.imgur.com/4avDUzu.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
Now, we will run the snort
sudo snort -q -l /var/log/snort -i ens33 A console -c /etc/snort/snort.conf <br/>
<img src="https://i.imgur.com/Gs8Bgxt.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
Now, ping the ubuntu system from kali linux system:  <br/>
<img src="https://i.imgur.com/teKq9IR.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
You can see snort is showing the msg ICMP ping detected:  <br/>
<img src="https://i.imgur.com/Yn5VRlP.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
Now, uncomment the rules you have commented earlier
sudo vim /etc/snort/snort.conf <br />
Open the file > press ctrl+v (this will enable visual block) > press j (this will select the line below) > press x (this will delete the #) > save the file

Now, we will validate the snort.conf file
sudo snort -T -i ens33 -c /etc/snort/snort.conf  <br/>
<img src="https://i.imgur.com/KvHHRtl.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
Now, we will run the snort
<br />
<br />
Open kali linux terminal and give the command: nmap -Pn 192.168.137.129:  <br/>
<img src="https://i.imgur.com/q1KD72v.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
Snort has identified the intrusion:  <br/>
<img src="https://i.imgur.com/jkdMYiH.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
Now, open legion tool (information gathering tool in kali linux)
Give the ubuntu ip and run the service:  <br/>
<img src="https://i.imgur.com/r0vNJda.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
You can see snort has detected the intrusion :  <br/>
<img src="https://i.imgur.com/1AVTfOx.png" height="80%" width="90%" alt="Snort IDS/IPS-Ubuntu"/>
<br />
<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
