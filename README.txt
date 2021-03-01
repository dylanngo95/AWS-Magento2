# Install magento 2 on Amazon Linux 2

# Comfirm amazon-linux-extras is exists

which amazon-linux-extras

# If not exists

sudo yum install -y amazon-linux-extras

# Check php7.x is available 

sudo  amazon-linux-extras | grep php

sudo amazon-linux-extras enable php7.4

# Install php7.x

sudo yum clean metadata
sudo yum install php php-{pear,cgi,common,curl,mbstring,gd,mysqlnd,gettext,bcmath,json,xml,fpm,intl,zip,imap}

# Install another php version

sudo amazon-linux-extras disable php7.4
sudo amazon-linux-extras enable php7.2
sudo yum install php php-{pear,cgi,common,curl,mbstring,gd,mysqlnd,gettext,bcmath,json,xml,fpm,intl,zip,imap}

# Fix composer out of memory

sudo /bin/dd if=/dev/zero of=/var/swap.1 bs=1M count=1024
sudo /sbin/mkswap /var/swap.1
sudo /sbin/swapon /var/swap.1

# Use redmi

sudo yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
sudo yum install https://rpms.remirepo.net/enterprise/remi-release-7.rpm
sudo yum-config-manager --enable remi-php7.2

sudo yum install php72-php-fpm php72-php-gd php72-php-json php72-php-mbstring php72-php-mysqlnd php72-php-xml php72-php-xmlrpc php72-php-opcache

sudo yum install --disablerepo="*" --enablerepo="remi,remi-php72" php7.2-{pear,cgi,common,curl,mbstring,gd,mysqlnd,gettext,bcmath,json,xml,fpm,intl,zip,imap}
