

```
sudo apt-get update
sudo apt-get install apache2
sudo apt-get install php5 libapache2-mod-php5 php5-mcrypt
sudo systemctl enable apache2.service
sudo systemctl start apache2.service

echo "<?php phpinfo(); ?>" /var/www/html/info.php
```

```
sudo yum install httpd -y
sudo systemctl enable httpd.service
sudo systemctl start httpd.service
sudo yum install php php-mysql php-fpm -y

echo "<?php phpinfo(); ?>" /var/www/html/info.php