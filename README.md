# Ansible Role: Iptables

- Master branch: [![Build Status](https://travis-ci.org/insspb/ansible-role-iptables.svg?branch=master)](https://travis-ci.org/insspb/ansible-role-iptables)
- Developer branch: [![Build Status](https://travis-ci.org/insspb/ansible-role-iptables.svg?branch=develop)](https://travis-ci.org/insspb/ansible-role-iptables)

## Description

Role to install and configure iptables firewall on different systems.
Supports multiinterfaces configuration. 

## Requirements

No requiments yet.

## Role Variables

| Name                            | Default                                                                       | Description                                        |
|---------------------------------|-------------------------------------------------------------------------------|----------------------------------------------------|
| iptables_input_policy           | "DROP"                                                                        | Default input policy                               |
| iptables_forward_policy         | "DROP"                                                                        | Default forward policy                             |
| iptables_output_policy          | "ACCEPT"                                                                      | Default output policy                              |
| iptables_icmp_enabled           | True                                                                          | Enable/disable ICMP for all interfaces             |
| iptables_logging                | True                                                                          | Enable/disable droped packages logging             |
| iptables_rules                  | [{protocol: tcp, source_addresses: 0.0.0.0/0, port: 22, comment: "OpenSSH" }] | Array of firewall rules represented as hashes      |
| iptables_unprotected_interfaces | []                                                                            | Array of interfaces where ALLOW ALL applied (list) |
| iptables_port_forward_rules     | []                                                                            | Array of port forward rules represented as hashes  |


## Dependencies
No dependencies for this role. 

## Example Playbook
```yaml
- hosts: all
  roles:
    - insspb.iptables
```
## Development information
This role is developed with community help. 
Process of development follows this rule: 

- You are free to add any pool request to develop branch. All request will be answered in timely manner. 
- If you want to made any contribution, but do not know where to start - check issues.
- Master branch updated just after significant changes in develop.
- Please include documentation for new features. 
- Please use variables.
- Please do not forget to set defaults.
- Please do your best to keep backward compatibility if possible.
- Please use packet installation as default software installation method. Source installation must be optional anywhere if possible.
- Please use official software developers repositories instead of general Debian/Ubuntu/Centos etc for main application. 
- Do you best to keep role independent from any other roles. User must have the way to choose what roles to use.

## License

MIT

## Author Information

This role is contributed and maintained by [Andrey Shpak](http://www.ashpak.ru). I am always available for [hire](https://www.upwork.com/o/profiles/users/_~01a780866aa29e4429/).
