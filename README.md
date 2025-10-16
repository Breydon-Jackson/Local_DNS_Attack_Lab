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
dig ww<span>w.bank32.c<span>om 

I downloaded bank32 and performed a reverse lookup on 192.168.0.10

<img width="888" height="610" alt="image" src="https://github.com/user-attachments/assets/a8292688-d549-42ec-b492-d69b64f40060" />

Commands:
- sudo python dns_spoof.py
- sudo python dns_server.py
- dig www.example.net

### Task 4

<img width="975" height="837" alt="image" src="https://github.com/user-attachments/assets/c749a991-0513-4fa3-87aa-f7473eb04320" />

Command: sudo service bind9 restart

Here I restart bind9

### Tasks 5 and 6

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/19a1fc94-c33d-454c-82e5-85bc20299daf" />

Commands: 
- sudo python dns spoof
- sudo python dns_server

Here I used dns_spoof to set up the dig command to return the ip address of our attack machine rather than the legitimate DNS server

### Task 6 and 7

<img width="975" height="827" alt="image" src="https://github.com/user-attachments/assets/6e73d2e6-fac4-4f33-a4bf-ddae0c120509" />

Command:  cat dns__as_spoof.py

Here I used dns_as_spoof to poison the DNS server's cache and have it return my attacker as the authority

### Task 8

<img width="888" height="610" alt="image" src="https://github.com/user-attachments/assets/7bcd5c29-2f44-42d0-aed4-07b5c8357eb7" />

Commands:
- sudo dns_as_spoof.py
- dig ww<span>w.example.n<span>et

Here we see that when I run the dig command on ww<span>w.example.n<span>et the command goes to the attacking machine's IP address rather than the legitimate server

### Task 9

<img width="841" height="712" alt="image" src="https://github.com/user-attachments/assets/2c4d91b7-1e6d-4444-b253-3a3499ac87ce" />

Commands:

cat dns_as_spoof.py

<img width="788" height="671" alt="image" src="https://github.com/user-attachments/assets/9864eb92-1f58-4422-bffa-3bdc1cd76063" />

<img width="813" height="566" alt="image" src="https://github.com/user-attachments/assets/21348a80-6202-4e0a-83eb-f278e57149a0" />

Commands:

sudo python dns_as_spoof.py

Here I used the dns_spoof.py to add an additional section which would further poison the cache by essentially saying heres the answer and here is where you can find google even if you didnt request that yet.
