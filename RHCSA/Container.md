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
	
	