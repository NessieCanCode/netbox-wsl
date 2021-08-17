# netbox-wsl

This repository is intended to facilitate installation of the popular NetBox DCIM/IPAM on Windows 10 using WSL (Ubuntu 20.04 LTS).

These are the extra steps taken:

1. sudo nano /etc/redis/redis.conf
2. Find "supervised no" line and change to supervised systemd
3. sudo service redis-server start
4. Copy /etc/init.d/ content from this github to WSL instance using '\\wsl$\{Distro}\home\{username}'
5. sudo cp ~\netbox-rq.service /etc/init.d/
6. sudo cp ~\netbox.service /etc/init.d/
7. sudo chmod +x netbox-rq.service netbox.service
8. sudo update-rc.d netbox-rq.service defaults && sudo update-rc.d netbox.service defaults
9. sudo touch /var/tmp/netbox-rq.pid && sudo chown netbox:netbox /var/tmp/netbox-rq.pid
10. sudo touch /var/log/netbox-rq.log && sudo chown netbox:netbox /var/log/netbox-rq.log
11. sudo touch /var/tmp/netbox.pid && sudo chown netbox:netbox /var/tmp/netbox.pid
12. sudo touch /var/log/netbox.log && sudo chown netbox:netbox /var/log/netbox.log
13. sudo chown -R netbox:netbox /opt/netbox/
