# Reference
Playbook for installation of Jitsi Meet - a video conferencing service, and an associated STUN server.

# Requirements
- One domain name, e.g. jitsi.chadg.net
- One public IP address.
- Ports 80, 443 open on any firewalls (or security groups).

# Deploy
```
# Locally
ansible-playbook jitsi.yml --extra-vars="target=localhost my_domain=chadg.net my_host=jitsi"
```

# Post-Installation Tasks
- TODO

# See Also
https://github.com/jitsi/docker-jitsi-meet
