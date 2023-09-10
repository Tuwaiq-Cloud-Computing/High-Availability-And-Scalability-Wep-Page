# High-Availability-And-Scalability-Wep-Page

## Setup:
Create ESC Instance using centos 7.9 image and use the commands below in User Data field:
```
#!/bin/bash
yum install httpd -y
systemctl enable httpd
systemctl start httpd

ZONE=$(curl -s http://100.100.100.200/latest/meta-data/zone-id)
HOSTNAME=$(curl -s http://100.100.100.200/latest/meta-data/hostname)

echo "Zone: $ZONE" > /var/www/html/index.html
echo "Hostname: $HOSTNAME" >> /var/www/html/index.html
```
#### After running these commands create scaling configuration from that instance and use it with your scaling group.

<br />

![Riyadh Regin](https://user-images.githubusercontent.com/80869015/216392405-dfe0a3cb-7b91-4c06-bc46-3df50c2d9ad8.png)
