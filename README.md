# First-time-on-VPS
Noobie Information how to login and protect virtual private server
ssh root@your-ip-address
apt update
apt upgrade
apt install fail2ban
echo "sshd_backend = systemd" >> /etc/fail2ban/paths-debian.conf
nano /etc/fail2ban/jail.local

copy and paste this commands to file with right button click (in windows cmd) then ctrl + o to save (probably use enter to save file), 

[sshd]
backend=systemd
enabled = true
port = ssh
filter = sshd
logpath = /var/log/auth.log
maxretry = 3

 ctrl + x to exit 

 if you want more hard protection and you have stable ip, use this:
 nano /etc/hosts.allow
 sshd: your-ip-address: allow (you can add more same lines with different ip)
 nano /etc/hosts.deny
 sshd: ALL
