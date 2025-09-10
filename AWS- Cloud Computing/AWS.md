
#Cloud Computing 
on demand delivery of computes power, database, storage, applications, and other IT resources through a cloud service.

Cloud computing provides a simple way to access servers, storage, database,

		Virtualization                                    Cloud
Webserver->
			1. Create VM
				->CPU+Memory+Disk+NET
			2. ISO >> rhel9
			3.  Boot
			4. OS- Instalation
				-Manually
				'--Windows>> UnattendInstaller
				--Linux >> KS >Kickstart >> abc.ks
									>>OS >> partition
									>>Network
									>>Package
									>>GUI /CLI
									>>ROOT
			5. Package Installation(Web server)
			6.  service >> start/enable
			7. firewall config
	Now For CLoud:
		1.  Creae Instance/ Server
			-PRDN
		2. Instance will not install via ISO
		3. Cloud image - RHEL 9 cloud image 
		4. we will launch cloud image not install. --> rhel cloud image


##Types of Cloud - Based on Service
IAAS - infrastructure as a service.  EC2(Elastic Compute Cloud).  

PAAS- Platform as a service. 

SAAS - Software as a Service



	#Keybase Authentication:
	keypair: >> (tala+chabi)
				- Private Key(chabi)
				- Pulic Key(tala)

ssh-keygen

VPC design always set by private IP not by public IP.
==Elastic IP==
Fixed IP address. instance delete korar por o Elastic IP theke jabe. Elastic IP release korar ag porjonto Elastic IP theke jabe


EC2> instance
## CloudTrail events (1)
Track Log

==**Virtual Private Cloud(VPC)**==
VPC is a Virtual Networking Environment(VNE) in AWS Cloud. VPC provide security group. VPC provide NAC .

private/public subnet:
using browser we can use the web server through a network but cannot access database server but web server can access their database server. that web server we can access through network called public Subnet and through which network we can access database server called private Subnet
In short, which subnet internet facing is called public subnet, which subnet facing intranet facing called private subnet.

**==SDN==**
Software Define Network. Software based Network Service. Programmatic Router.

*A single instance can manage 5 different Security Group
*A single VPC can attach to one IGW same as single IGW can attach to a single VPC.
*NACL is a subnet level firewall and SG is a instance level firewall


Security Group is a stateful.
stateful/stateless->  If instance sends request to go another instance, its also allowed to get back/return request to that instance. called statefull.
Stateless- if instance sends request to another instance then NACL should allow again when its return to get back request.

Default Security Group cannot be deleted.

Windows ICS: Windows Internet Connection Sharing er moddhe internet connection enable kora jay

IP forwarding- if i want to use a linux machine as a router i have to enable IP forwarding. by defaults it's disabled. Because when a request come to this machine it's need to forwarding that ip. If i use a OS as a router called NAT instance.

NAT Gateway/Router

for public IP it's need to Internet Gateway to access internet and for Private IP's its need to NAT to get internet.




NAT Gateway/Router
Steps to deploy NAT instance/Gateway
-NAT instance:
		-Create Security Group and allow all inbound and outbound Traffic.
		-Create NAT instance/Gateway in Public Subnet with Newly created SG.
		-Assign Public/EIP in instance/Gateway
		-Enable IP forwarding 
		- Configure NAT/MASQUERADE
		- add defaults route via NAT instance
		- disable source and Destination check in Instance

When i ping 8.8.8.8 from any private server it's not pass or get ping because:
	1. not enable IP forwarding
	2. Not enabled Masquerade
	3. Source and destination check not disabled.

1. Check not enable IP forwarding: cat /proc/sys/net/ipv4/ip_forward
		if result is 0 then enabled it.
		echo 1 >/proc/sys/net/ipv4/ip_forward
2. Not enabled Masquerade:
   ## What is Masquerade?
- **Masquerade** is a type of **NAT (Network Address Translation)**.
- It’s often called **Source NAT (SNAT)** where the **private IP of a device** is replaced (masqueraded) by the **public IP of the gateway/router** when going out to the internet.
In Linux, this is usually done with **iptables/nftables** using the `MASQUERADE` target.

---

## 🔹 How it Works

Imagine you have a private subnet `192.168.1.0/24` with a Linux router that has a public IP `203.0.113.10`.

1. A private host `192.168.1.100` sends traffic to the internet (say Google)
2. The router rewrites the source IP from **192.168.1.100 → 203.0.113.10**.
3. Google replies to `203.0.113.10`.    
4. The router remembers the connection and translates the reply back to `192.168.1.100`.
So, **many private machines can share one public IP**.


		Private                     Public
-------------------------------------------------
	DB1                                                         WEB
	(anyInstanceofPrivateSubnet)                NAT-Instance

Production:

-Subnet
	 - Public Subnet                                               >>Web Server
	 - Private Subnet with Internet                         >>DB
	 - Private Subnet without No Internet              >> Financial Server
 