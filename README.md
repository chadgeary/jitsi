# Reference
Playbook for installation of Jitsi Meet - a self-hosted video conferencing service.

# Requirements
- One domain name, e.g. jitsi.chadg.net
- One public IP address.
- Ports 80, 443 open on any firewalls (or security groups). See official docker page for more port information.

# Deploy
```
# Local example with LetsEncrypt
sudo ansible-playbook jitsi.yml --extra-vars="target=localhost le_enable=True le_domain=meet.chadg.net le_email=chad@chadg.net"

# No LetsEncrypt
sudo ansible-playbook jitsi.yml --extra-vars="target=localhost le_enable=False"
```

# Post-Installation Tasks
- TODO

# See Also
https://github.com/jitsi/docker-jitsi-meet
