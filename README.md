# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:

<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## program
~~~
Server.py
import socket
from pythonping import ping
s = socket.socket()
# Bind to localhost and port
s.bind(('localhost', 8000))
# Listen for connections
s.listen(5)
print("Ping Server started... Waiting for connection")
# Accept connection
c, addr = s.accept()
print("Connected to:", addr)
while True:
    hostname = c.recv(1024).decode()
    if not hostname:
        break
    try:
        result = ping(hostname, count=4, verbose=False)
        c.send(str(result).encode())
    except:
        c.send("Host Not Found".encode())
c.close()

Client.py
import socket
# Create socket
s = socket.socket()
# Connect to server
s.connect(('localhost', 8000))
while True:
    website = input("Enter the website you want to ping: ")
    if website.lower() == "exit":
        break
    s.send(website.encode())
    result = s.recv(1024).decode()
    print("\nPing Result:\n", result)
s.close()

Traceroute.py
import os
print("Running Traceroute...\n")
os.system("C:\\Windows\\System32\\tracert.exe google.com")
~~~
## Output
1)ping

<img width="844" height="353" alt="image" src="https://github.com/user-attachments/assets/bf7f3d24-5894-48b5-b559-84df69812a15" />

2)Tracert

<img width="1046" height="561" alt="image" src="https://github.com/user-attachments/assets/7061c83e-e452-4b62-b890-6a17b5e05e21" />

3)ipconfig

<img width="984" height="719" alt="image" src="https://github.com/user-attachments/assets/2fb6184e-7d40-4536-9073-f765f6d0d3ce" />

4)netstat

<img width="886" height="909" alt="image" src="https://github.com/user-attachments/assets/a73b0cff-1051-4dcf-a6e9-224c18029453" />

5)nslookup

<img width="799" height="555" alt="image" src="https://github.com/user-attachments/assets/726dbb72-27c1-4cfa-b578-c2cd4cad4765" />

6)getmac

<img width="956" height="171" alt="image" src="https://github.com/user-attachments/assets/f9e318e3-7a04-4076-996f-346338aca3df" />

7)nbtstat

<img width="1105" height="600" alt="image" src="https://github.com/user-attachments/assets/49ba2dd2-f53d-4418-80c1-670035772ff3" />

8)arp

<img width="958" height="789" alt="image" src="https://github.com/user-attachments/assets/cc7a4ab5-4ac7-4b0b-a1cc-695162076223" />

9)systeminfo

<img width="705" height="964" alt="image" src="https://github.com/user-attachments/assets/af7a145e-14dc-42a9-93fc-210f6e2bdcb6" />

## Result
Thus Execution of Network commands Performed 
