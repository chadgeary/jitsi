# Reference
Playbook for installation of Jitsi Meet - a self-hosted video conferencing service. Tested with EL7 (CentOS/RHEL 7).

# Requirements
- Ports 80 and 443 open (LetsEncrypt), and domain name/email address.
- Ports 8000 and 8443 (No HTTP encryption)
- /opt available for install
# Deploy
```
# Local example with LetsEncrypt
sudo ansible-playbook jitsi.yml --extra-vars="target=localhost le_enable=True le_domain=meet.chadg.net le_email=chad@chadg.net"

# Local example (No HTTP encryption)
sudo ansible-playbook jitsi.yml --extra-vars="target=localhost le_enable=False"
```

# Post Installation
- User admin is created with a randomly generated password (see /opt/jitsi/admin_pass)
- Create additional users via:
```
sudo docker exec -it jitsi_prosody_1 prosodyctl --config /config/prosody.cfg.lua register someuser1 meet.jitsi SomeSecurePass1
```
- Post-installation changes to the .env file require:

   1. Removing the .jitsi-meet-config directory
   2. Restarting the containers

# See Also
https://github.com/jitsi/docker-jitsi-meet
