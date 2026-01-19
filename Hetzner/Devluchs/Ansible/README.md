# Devluchs Hetzner Cloud Ansible

Ansible repo for Hetzner Cloud servers (Ubuntu 24.04.3 LTS).

## Inventory
- Production inventory: `inventories/production/hosts.yml`
- Host vars: `host_vars/*.yml`

## Playbooks
- `playbooks/bind9.yml`
- `playbooks/cockpit.yml`
- `playbooks/apache.yml`
- `playbooks/certbot.yml`
- `playbooks/requirements.yml`
- `playbooks/hcloud-firewall.yml`
- `playbooks/site.yml`

## Usage
```
ansible-playbook playbooks/site.yml
```

Limit to a host or group:
```
ansible-playbook playbooks/bind9.yml -l server01.devluchs.de
```

## OS Notes
- Target OS: Ubuntu 24.04.3 LTS.
- Network role installs `netplan.io` and applies `/etc/netplan/01-ansible.yaml`.

## Collections
```
ansible-galaxy collection install -r collections/requirements.yml
```

## HCloud Firewall
```
HCLOUD_TOKEN=... ansible-playbook playbooks/hcloud-firewall.yml
```
