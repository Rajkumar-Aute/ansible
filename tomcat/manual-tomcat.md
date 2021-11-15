

sudo apt update
sudo apt install openjdk-11-jdk

sudo groupadd tomcat
sudo useradd -s /bin/false -g tomcat -d /opt/tomcat tomcat

cd /tmp/
curl -O https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.54/bin/apache-tomcat-9.0.54.tar.gz

sudo mkdir /opt/tomcat

sudo tar xzvf apache-tomcat-*tar.gz -C /opt/tomcat --strip-components=1


cd /opt/tomcat/
sudo chgrp -R tomcat /opt/tomcat
sudo chmod -R g+r conf g+x conf
sudo chown -R tomcat webapps/ work/ temp/ logs/
sudo update-java-alternatives -l
sudo nano /etc/systemd/system/tomcat.service
sudo systemctl daemon-reload
sudo systemctl start tomcat
sudo systemctl enable tomcat
sudo systemctl status tomcat





