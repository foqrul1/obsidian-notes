
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
