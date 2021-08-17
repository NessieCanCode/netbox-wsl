# netbox-wsl

This repository is intended to facilitate installation of the popular NetBox DCIM/IPAM on Windows 10 using WSL (Ubuntu 20.04 LTS)

1. sudo nano /etc/redis/redis.conf
2. Find "supervised no" line and change to supervised systemd
3. sudo service redis-server start
4. sudo chmod +x netbox-rq.service netbox.service
5. sudo update-rc.d netbox-rq.service defaults && sudo update-rc.d netbox.service defaults
6. sudo touch /var/tmp/netbox-rq.pid && sudo chown netbox:netbox /var/tmp/netbox-rq.pid
7. sudo touch /var/log/netbox-rq.log && sudo chown netbox:netbox /var/log/netbox-rq.log
8. sudo touch /var/tmp/netbox.pid && sudo chown netbox:netbox /var/tmp/netbox.pid
7. sudo touch /var/log/netbox.log && sudo chown netbox:netbox /var/log/netbox.log
8. sudo chown -R netbox:netbox /opt/netbox/
