# dina101
Walkthrough for boot2root vulnhub vm


## netdiscover

Get the IP for the VM, 192.168.56.106

![Alt text](./netdis.png?raw=true)


## nmap

Nmap shows just port 80 open

![Alt text](./nmap.png?raw=true)


## dirb

dirb gives us some hits and the 'secure' and 'nothing' directories are of note

![Alt text](./dirb.png?raw=true)


View the source of the page in the 'nothing' directory for compromised credentials

![Alt text](./nothing.png?raw=true)


Download and analyze the zip file in the 'secure' directory

Try each compromised password. First try is lucky, we are in with 'freedom' to unzip the file

![Alt text](./unzip.png?raw=true)


It is not an audio file, 'cat' the contents to compromise a username

![Alt text](./new_url.png?raw=true)


## browser

Brute force the login in to the webapp with compromised login info, trying each password

user: touhid

password: diana

![Alt text](./login.png?raw=true)


## fu

Find a PlaySMS exploit POC with the Google

![Alt text](./edb.png?raw=true)


## msfvenom

Create a reverse shell payload

![Alt text](./venom.png?raw=true)


## Exploit DB PoC

Create the malicious filename, use encoding to bypass restriction on front slash in the filename

![Alt text](./poc.png?raw=true)


## netcat

Start your listener and get a low-level shell

![Alt text](./lowshell.png?raw=true)


## priv esc

The OS is setup to balk at gcc use, pre-compiled kernel exploits like overlayfs failed. Other red-herrings like the DB password in config.php were of no use. Finally the 'sudo -l' command proves helpful.

![Alt text](./perl.png?raw=true)


## root

<pre>
\(*_*)
  ( (>
  /  \
</pre>

![Alt text](./root.png?raw=true)


## ctf

Get the flag

![Alt text](./ctf.png?raw=true)


## thanks

Thanks to Touhid Shaikh for the vm
