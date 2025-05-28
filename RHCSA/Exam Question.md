1. Configure IP address in servers and ensure that mentioned DNS server IP will be permanent not be updated if any change on DNS IP.
	Setup an ip address for [ servera ] virtual machine
	Password: redhat
	IP: 172.25.250.10/24
	GW: 172.25.250.254
	DNS: 172.25.250.220
	NB: All partition should be created on /dev/vdb
	Ans-> 






setfacl -m d:u:appadmin:rw- /var/www/html/