# ansible-role-registartor

Ansible playbook to automate installing and maintaining
[Consul Registrator](http://github.com/gliderlabs/registrator).

## Requirements

This role currently requires a working VMware Photon server with enabled Docker
environment.

## Role Variables

```yaml
# Container memory limit -- Use 512MB, type string, or 0 for unlimited
memory_limit: 0MB

# The docker systemd unit file to modify if necessary.
docker_service_unit: /lib/systemd/system/docker.service

# Name server hosts the container should use.
docker_dns_hosts:
  - "{{ inventory_hostname }}"
  
# The Consule service endpoint to use for registering.
consul_service_uri: consul://consul.service.consul:8500
```

## Example playbook

```
---
- hosts: registrator
  sudo: True
  roles:
    - registrator
  vars:
    - ... forthcoming
```

# License and Copyright
 
Copyright 2015 VMware, Inc.  All rights reserved.

SPDX-License-Identifier: Apache-2.0 OR GPL-3.0-only

This code is Dual Licensed Apache-2.0 or GPLv3

