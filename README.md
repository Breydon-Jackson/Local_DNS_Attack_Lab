# Local_DNS_Attack_Lab
<a href="https://seedsecuritylabs.org/Labs_20.04/Networking/DNS/DNS_Local/">SEED Labs Local DNS Attack Lab</a>
## Objective
The objective of this lab was to get first hand experience with attacks on the Domain Name System (DNS). The domain name system translates IP addresses into domain names and vice versa. After setting up the DNS, the lab focused on several
different DNS pharming attack techniques on a DNS in the same local network in a lab environment.

## Tools Used
- Seed Ubuntu Virtual Machine

## Tasks
### Task 1
<img width="975" height="673" alt="image" src="https://github.com/user-attachments/assets/fb94d2b4-6f5f-495d-8113-1de1c80f871a" />
Command: 
sudo gedit /etc/resolvconf/resolv.conf.d/head

I added the IP address of our DNS Server 10.0.2.15

### Task 2

<img width="742" height="636" alt="image" src="https://github.com/user-attachments/assets/7bea90b8-a251-47f9-89e3-dd2153111b95" />

Commands:
- Sudo rndc dumpdb -cache
- Sudo rndc flush
- Sudo apt install bind9
Here I dumped the DNS cache to a file the flushed it to install bind9

<img width="975" height="1036" alt="image" src="https://github.com/user-attachments/assets/0e479767-3829-4837-8d47-897a948686f0" />

Command:

Cat/etc/bind/named.conf.options

### Task 3

<img width="975" height="848" alt="image" src="https://github.com/user-attachments/assets/88dc30fc-54b6-452d-8c67-af182a524621" />

Command:

Sudo gedit /etc/named.conf

Here I added the zones for bank32.com

<img width="975" height="837" alt="image" src="https://github.com/user-attachments/assets/d2943c00-1e63-4759-aafb-862611440de4" />

Command:
dig www.bank32.com 

I downloaded bank32 and performed a reverse lookup on 192.168.0.10
