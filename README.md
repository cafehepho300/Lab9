# Lab9
Kiểm tra: iptables -L

Cho phép/cấm ICMP (ping)
sudo iptables -A INPUT -p icmp --icmp-type echo-request -j ACCEPT

Cấm
sudo iptables -A INPUT -p icmp --icmp-type echo-request -j DROP
