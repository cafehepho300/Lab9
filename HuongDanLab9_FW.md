# Lab9
---------Kiểm tra: iptables -L

Cho phép/cấm ICMP (ping)
Cho phép: 
```bash
sudo iptables -A INPUT -p icmp --icmp-type echo-request -j ACCEPT
```

Cấm: 
```bash
sudo iptables -A INPUT -p icmp --icmp-type echo-request -j DROP
```

Cho phép/cấm HTTP (web):
Cho phép: 
```bash
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
```

Cấm: 
```bash
sudo iptables -A INPUT -p tcp --dport 80 -j DROP
```

Cho phép/cấm FTP:
Cho phép:
```bash
sudo iptables -A INPUT -p tcp --dport 21 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 20 -j ACCEPT
```
Cấm:
```bash
sudo iptables -A INPUT -p tcp --dport 21 -j DROP
sudo iptables -A INPUT -p tcp --dport 20 -j DROP
```
Cho phép/cấm telnet:
Cho phép:
```bash
sudo iptables -A INPUT -p tcp --dport 23 -j ACCEPT
```
Cấm:
```bash
sudo iptables -A INPUT -p tcp --dport 23 -j DROP
```
