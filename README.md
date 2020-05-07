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

# Post Installation
- User admin is created with a randomly generated password (see /opt/jitsi/admin_pass)
- Create additional users via:
```
sudo docker exec -it jitsi_prosody_1 prosodyctl --config /config/prosody.cfg.lua register someuser1 meet.jitsi SomeSecurePass1
```
- Post-installation changes to the .env file require:
 - removing the .jitsi-meet-config directory
 - restarting the containers

# See Also
https://github.com/jitsi/docker-jitsi-meet
