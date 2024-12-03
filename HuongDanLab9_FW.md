# Lab9
Xem danh sách quy tắc đã cài vào: 
```bash
iptables -L
```
Liệt kê tất cả:
```bash
sudo iptables -L -n -v --line-number
```
xóa quy tất cả quy tắc đã thêm:
```bash
iptables -F
```
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
iptables -A OUTPUT -p tcp --dport 443 -j DROP
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

cài đặt snort:
```bash
sudo apt install snort -y
```

tải rules snort 
```bash
wget https://www.snort.org/rules/community -O ~/commynity.tar.gz
```

giải nén:
```bash
sudo tar -xvf ~/commynity.tar.gz -C ~/
```

```bash
sudo cp ~/community-rules/* /etc/snort/rules
```

```bash
sudo snort -T -c /etc/snort/snort.conf
```

```bash
alert icmp any nay -> $HOME_NET any (msg:"Hello Bi Ping";sid:10000001; rev:001;)
```
                                                    
