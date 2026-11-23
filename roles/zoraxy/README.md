# plopoyop.personal_network_gateway.zoraxy

Install & configure Zoraxy reverse proxy

## Table of contents

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [zoraxy_admin_password](#zoraxy_admin_password)
  - [zoraxy_admin_user](#zoraxy_admin_user)
  - [zoraxy_disable_auth](#zoraxy_disable_auth)
  - [zoraxy_listen_port](#zoraxy_listen_port)
  - [zoraxy_service_enabled](#zoraxy_service_enabled)
  - [zoraxy_service_state](#zoraxy_service_state)
  - [zoraxy_system_group](#zoraxy_system_group)
  - [zoraxy_system_user](#zoraxy_system_user)
  - [zoraxy_version](#zoraxy_version)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.1`

## Default Variables

### zoraxy_admin_password

Admin password

**_Type:_** string<br />

#### Default value

```YAML
zoraxy_admin_password: admin
```

### zoraxy_admin_user

Admin username to create

**_Type:_** string<br />

#### Default value

```YAML
zoraxy_admin_user: admin
```

### zoraxy_disable_auth

Disable administration auth

**_Type:_** boolean<br />

#### Default value

```YAML
zoraxy_disable_auth: false
```

### zoraxy_listen_port

Zoraxy administration port

**_Type:_** string<br />

#### Default value

```YAML
zoraxy_listen_port: 8000
```

### zoraxy_service_enabled

#### Default value

```YAML
zoraxy_service_enabled: true
```

### zoraxy_service_state

Zoraxy service state

**_Type:_** string<br />

#### Default value

```YAML
zoraxy_service_state: started
```

### zoraxy_system_group

System group name to create

**_Type:_** string<br />

#### Default value

```YAML
zoraxy_system_group: zoraxy
```

### zoraxy_system_user

Enable zoraxy service on boot

**_Type:_** boolean<br />

#### Default value

```YAML
zoraxy_system_user: zoraxy
```

### zoraxy_version

Zoraxy version to install

**_Type:_** string<br />

#### Default value

```YAML
zoraxy_version: 3.3.4
```

## Dependencies

None.

## License

MPL-2.0

## Author

Clément Hubert
