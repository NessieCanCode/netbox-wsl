# netbox-wsl

NetBox is an infrastructure resource modeling (IRM) tool designed to empower network automation. Initially conceived by the network engineering team at DigitalOcean, NetBox was developed specifically to address the needs of network and infrastructure engineers. It is intended to function as a domain-specific source of truth for network operations.

NetBox runs as a web application atop the Django Python framework with a PostgreSQL database. The code is available on GitHub.

The complete documentation for NetBox can be found at Read the Docs. A public demo instance is available at https://demo.netbox.dev.

netbox-wsl, are modifications and documented setting changes to allow netbox to run on on (Ubuntu 20.04 LTS) WSL

1. sudo nano /etc/redis/redis.conf
2. Find supervised no line and change to supervised systemd
3. sudo service redis-server start
4. sudo chmod +x netbox-rq.service netbox.service
5. sudo update-rc.d netbox-rq.service defaults && sudo update-rc.d netbox.service defaults
6. sudo touch /var/tmp/netbox-rq.pid && sudo chown netbox:netbox /var/tmp/netbox-rq.pid
7. sudo touch /var/log/netbox-rq.log && sudo chown netbox:netbox /var/log/netbox-rq.log
8. sudo touch /var/tmp/netbox.pid && sudo chown netbox:netbox /var/tmp/netbox.pid
7. sudo touch /var/log/netbox.log && sudo chown netbox:netbox /var/log/netbox.log
8. sudo chown -R netbox:netbox /opt/netbox/
