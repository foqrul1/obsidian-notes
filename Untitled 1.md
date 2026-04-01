dnf install httpd
   99  httpd -v
  100  systemctl status httpd.service 
  101  systemctl enable --now httpd.service 
  102  systemctl status httpd.service 
  103  dnf install epel-release -y
  104  dnf install https://dev.mysql.com/get/mysql84-community-release-el9-1.noarch.rpm
  105  vim /etc/environment 
  106  source /etc/environment 
  107  subscription-manager register 
  108  dnf install https://dev.mysql.com/get/mysql84-community-release-el9-1.noarch.rpm
  109  vi /etc/yum.repos.d/mysql-community.repo
  110  dnf clean all
  111  rm -rf /var/cache/dnf
  112  dnf makecache
  113  dnf repolist
  114  dnf install mysql-community-server
  115  mysql- V
  116  mysql -V
  117  php -v
  118  dnf install https://rpms.remirepo.net/enterprise/remi-release-9.rpm
  119  dnf module reset php -y
  120  dnf module enable php:remi-8.3 -y
  121  ls /etc/yum.repos.d/ | grep epel
  122  rm -f /etc/yum.repos.d/epel*.repo
  123  dnf install epel-release -y
  124  ls /etc/yum.repos.d/ | grep epel
  125  vim /etc/environment 
  126  source /etc/environment 
  127  ls /etc/yum.repos.d/ | grep epel
  128  dnf remove remi-release -y
  129  rm -f /etc/yum.repos.d/remi*.repo
  130  dnf install https://rpms.remirepo.net/enterprise/remi-release-9.rpm -y
  131  vi /etc/yum.repos.d/remi*.repo
  132  dnf clean all
  133  rm -rf /var/cache/dnf/*
  134  dnf makecache
  135  dnf config-manager --set-disabled remi-safe
  136  dnf clean all
  137  dnf makecache
  138  dnf module reset php
  139  dnf module enable php:remi-8.3
  140  dnf install php php-cli php-fpm php-mysqlnd -y
  141  php -v
  142  mysqld -V
  143  httpd -v