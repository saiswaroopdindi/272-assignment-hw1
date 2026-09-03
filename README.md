# SJSU Ansible Webserver Assignment

This project configures two Ubuntu VMs with Apache web servers on port 8080.

## Hosts
- VM1 / web1: 192.168.1.148
- VM2 / web2: 192.168.1.151

## Required files
- `inventory` - Ansible inventory
- `deploy.yml` - deployment playbook

## Run
```bash
ansible -i inventory webservers -m ping -k
ansible-playbook -i inventory deploy.yml --syntax-check
ansible-playbook -i inventory deploy.yml -k -K
```

## Verify
```bash
curl http://192.168.1.148:8080
curl http://192.168.1.151:8080
```

Expected:
- `Hello World from SJSU-1`
- `Hello World from SJSU-2`

Do not commit passwords, SSH private keys, or other secrets.
