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

## Program :
### Client :
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
### Server :
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
### Traceroute Command :
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output :
### Client :
![Screenshot 2024-04-16 154824](https://github.com/Rogith08/4.Execution_of_NetworkCommends/assets/162728044/d1339e44-c59c-4bb7-b8ea-b637a891d297)

### Server :
![Screenshot 2024-04-16 154848](https://github.com/Rogith08/4.Execution_of_NetworkCommends/assets/162728044/23636298-03c1-440c-b3e2-96f152b87f3e)

### Traceroute :
![Screenshot 2024-04-16 154910](https://github.com/Rogith08/4.Execution_of_NetworkCommends/assets/162728044/b563986a-0db3-49d6-aa0e-fa4e7e87fb88)

## Result :
Thus Execution of Network commands Performed 
