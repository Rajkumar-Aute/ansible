### deploying jar app file on ubuntu using ansible
linux commends to install jar app
```
sudo apt update
sudo apt install openjdk-11-jdk -y
wget https://rajshared.s3.amazonaws.com/spring-petclinic.jar
sudo cp spring-petclinic.jar /usr/share/springpetclinic/
sudo adduser springbootuser
sudo chown springbootuser:springbootuser /usr/share/springpetclinic/spring-petclinic.jar
sudo chmod 500 /usr/share/springpetclinic/spring-petclinic.jar
sudo vi /etc/systemd/system/springpetclinic.service
sudo systemctl enable springpetclinic.service
sudo systemctl start springpetclinic.service
sudo systemctl status springpetclinic.service