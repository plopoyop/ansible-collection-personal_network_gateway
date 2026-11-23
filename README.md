# Ansible Collection - plopoyop.personal_network_gateway

Roles to build a personal network gateway (home or small office): DNS
filtering, intrusion prevention and reverse proxy.

## Roles

| Role | Description |
| ---- | ----------- |
| [`plopoyop.personal_network_gateway.adguardhome`](roles/adguardhome/README.md) | Install & configure AdGuard Home DNS server |
| [`plopoyop.personal_network_gateway.crowdsec`](roles/crowdsec/README.md) | Install & configure CrowdSec and its firewall bouncer from the official repository |
| [`plopoyop.personal_network_gateway.zoraxy`](roles/zoraxy/README.md) | Install & configure Zoraxy reverse proxy |

Each role is independent: use only the ones you need.

## Installation

```shell
ansible-galaxy collection install plopoyop.personal_network_gateway
```

Or in `requirements.yml`:

```yaml
collections:
  - name: "plopoyop.personal_network_gateway"
    version: "0.1.0"
```

## Usage

```yaml
- name: "Gateway"
  hosts: "gateway"
  become: true
  roles:
    - role: "plopoyop.personal_network_gateway.adguardhome"
    - role: "plopoyop.personal_network_gateway.crowdsec"
```

### Site playbook

`plopoyop.personal_network_gateway.site` applies every role to the
`personal_network_gateway` group:

```shell
ansible-playbook plopoyop.personal_network_gateway.site
```

| Variable | Default | Description |
| -------- | ------- | ----------- |
| `personal_network_gateway_hosts` | `personal_network_gateway` | Hosts or group to target |
| `personal_network_gateway_adguardhome_enabled` | `true` | Apply the `adguardhome` role |
| `personal_network_gateway_zoraxy_enabled` | `true` | Apply the `zoraxy` role |
| `personal_network_gateway_crowdsec_enabled` | `true` | Apply the `crowdsec` role |

Each role has a tag of the same name (`--tags crowdsec`).

## Migrating from the standalone roles

The roles were previously published as `plopoyop.adguardhome`,
`plopoyop.crowdsec` and `plopoyop.zoraxy`. Their variables are unchanged:
install the collection and replace the role name with its fully qualified
name, e.g. `plopoyop.adguardhome` → `plopoyop.personal_network_gateway.adguardhome`.

## Development

Tooling is provided by [devbox](https://www.jetify.com/devbox) and
[Task](https://taskfile.dev):

```shell
devbox shell
task lint                    # yamllint + ansible-lint
task test:role:adguardhome   # molecule tests of one role
task test:roles:all          # molecule tests of every role
task gen-doc:roles:all       # regenerate role READMEs (ansible-doctor)
```

## License

MPL-2.0
