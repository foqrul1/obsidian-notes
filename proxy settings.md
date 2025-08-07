
vim /etc/environment

export http_proxy="http://192.168.195.64:443"
export https_proxy="http://192.168.195.64:443"
export ftp_proxy="http://192.168.195.64:443"
export no_proxy="localhost,127.0.0.1"

source /etc/environment