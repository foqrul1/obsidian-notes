Podman is the container engine used in RHEL 9 (instead of Docker).
	#sudo yum install -y podman
install podman in your device

1. Check Podman Version
	. podman --version
2. Check podman is working or not
	. podman info
3. Run a simple Container using alpine image
	. podman run --rm alpine echo "Hello, Container World!."
	This will:
	- Pull the Alpine image (lightweight Linux)
	- Run it and print "Hello..."
	- Remove the container after it exits
4. Run a Persistant Container 
	. podman run -dit --name mycontainer alpine
		This will:
	- `-d` run in detached mode
	- `-i` keep STDIN open
	- `-t` allocate a pseudo-TTY
	- `--name` gives it a name
	- Then Enter it:
			podman exec -it mycontainer sh
	- exit with #"exit"
5. List of Running Container
	. podman ps

6. useradd alth
7. passwd alth
8. ssh-keygen
9. enter-> enter
10. ssh-copy-id-i  /root/ .ssh/id_rsa-pub alth@localhost
11. enter
12. enter enter
13. vim containerfile
14.  FROM docker.io/nginx
	   RUN mkdir -p /action/incoming /action/outgoing
15. podman build -t monitor .
16. podman images
17. yum install podman* -y
18. podman start podman.service
19. podman start podman.socket
20. podman enable podman.service podman.socket
21. mkdir /opt/files /opt/outprocess
22. mkdir /opt/process
23. chown alth:alth /opt/files
24. chown alth:alth /opt/process
25. ssh alth@localhost
26. make sure you your image must be on under normal user not in root user
27. podman run -dit --name asciipdf -v /opt/files://opt/incoming:Z -v /opt/processed:/opt/outgoing:Z monitor
28. podman ps
29. mkdir -p .config/systemd/user
30. cd ~/.config/systemd/user
31. podman generate systemd --name asciipdf --new --files
32. systemctl --user daemon-reload
33. systemctl --user start container-asciipdf.service
34. systemctl --user enable container-asciipdf.service
35. systemctl --user status container-asciipdf.service
36. loginctl enable-linger
37. loginctl show-user alth
38. 
	