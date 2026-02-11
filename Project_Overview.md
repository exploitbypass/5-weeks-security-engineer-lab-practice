# 5 weeks Security Engineer Training --Begineer Friendly


## Overview 

### This repository documents my hands-on cybersecurity training which i mainly focused to get hands on experience and be job-ready in offensive secuirty and penetration testing.

### The goal of this 5-week routing is to build:

- Practical enumeration skills
- Learning Exploitation Methodology
- Linux privilege awarness
- Post-exploitation workflow
- Automation Mindset
- Reporting Habits


## All work is performed in secure way in virtualbox.



## Setting Lab Environment 

###** Attacker Machine **
- Kali Linux 

### ** Target Machine **
- Metasploitable2 (vulnerable ubuntu vm)

### ** Network Setup ** 
- Virtual Box
- Adapter1 : Nat 
- Adapter2 : Internal Network


#Network trouble shooting commands
> On kali vm
''' sudo nmcli device connect eth0 up
	sudo ip addr add 192.168.56.0/24 dev eth0
	sudo ip link set eth0 up'''

> Metasploitable IP assigning
'''bash sudo ifconfig eth0 192.168.56.10 netmask 255.255.255.0 up'''



5-weeks-security-engineer-training/
|
|--- week1/
|		  |
|		  |--week1_notes.md
|		  |--auto_enumeration.py
|		  |--Screenshots/
|
|---week2/
