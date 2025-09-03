
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



