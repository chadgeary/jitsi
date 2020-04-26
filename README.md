# Reference
Playbook for installation of Jitsi Meet - a self-hosted video conferencing service.

# Requirements
- One domain name, e.g. jitsi.chadg.net
- One public IP address.
- Ports 80, 443, 3478, and UDP 30000 through 39999 open on any firewalls (or security groups).

# Deploy
```
# Local example - assuming domain is jitsi.chadg.net
ansible-playbook jitsi.yml --extra-vars="target=localhost my_domain=chadg.net my_host=jitsi"
```

# Post-Installation Tasks
- TODO

# See Also
https://github.com/jitsi/docker-jitsi-meet
