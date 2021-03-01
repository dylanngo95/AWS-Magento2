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
