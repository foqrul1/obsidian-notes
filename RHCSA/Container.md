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
	- Pull the Alpine image (lightweight
	- Linux)
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
16. sudo podman build -t pdfconvert -f Containerfile .
17. podman images
18. yum install podman* -y
19. podman start podman.service
20. podman start podman.socket
21. podman enable podman.service podman.socket
22. mkdir /opt/files /opt/outprocess
23. mkdir /opt/process
24. chown alth:alth /opt/files
25. chown alth:alth /opt/process
26. ssh alth@localhost
27. make sure you your image must be on under normal user not in root user
28. podman run -dit --name asciipdf -v /opt/files://opt/incoming:Z -v /opt/processed:/opt/outgoing:Z monitor
29. podman run -dit --name asciipdf_v2 \
	  -v /opt/input/:/action/incoming:Z \
	  -v /opt/processed/:/action/outgoing/:Z \
	  pdfconvert
30. podman --runtime /usr/bin/runc run -dit \
	  --name ascii2pdf \
	  -v /opt/input/:/action/incoming:Z \
	  -v /opt/processed/:/action/outgoing:Z \
	  pdfconvert


31. podman ps
32. mkdir -p .config/systemd/user
33. cd ~/.config/systemd/user
34. podman generate systemd --name asciipdf --new --files
35. systemctl --user daemon-reload
36. systemctl --user start container-asciipdf.service
37. systemctl --user enable container-asciipdf.service
38. systemctl --user status container-asciipdf.service
39. loginctl enable-linger
40. loginctl show-user alth
41. 

mkdir /demo
cd /demo
vim Containerfile
FROM nginx:alpine

# Install bash and rsync

# Create working directories
RUN mkdir -p /action/incoming /action/outgoing

# Add the rsync script
COPY rsync_handler.sh /usr/local/bin/rsync_handler.sh
RUN chmod +x /usr/local/bin/rsync_handler.sh

Run rsync handler in background and start nginx
CMD ["/bin/sh", "-c", "/usr/local/bin/rsync_handler.sh & nginx -g 'daemon off;'"]
