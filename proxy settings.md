
vim /etc/environment

export http_proxy="http://192.168.195.64:443"
export https_proxy="http://192.168.195.64:443"
export ftp_proxy="http://192.168.195.64:443"
export no_proxy="localhost,127.0.0.1"

source /etc/environment


nc -zv 10.124.9.238 9002 for checking port is allow or not in firewall(from linux server)
tnc 10.124.9.238 -p 9002 or checking port is allow or not in firewall(from Windows server)



