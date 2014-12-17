# Ansible Role: opendkim

A base opendkim config

## Requirements



## Role Variables
To set the domains which opendkim should sign pass you can pass in a list. 
```yml
opendkim_domains:
  - name: example.org
    selector: default
    private_key: "" # optional
    public_key:  "" # optional
```
- `name` should be the base domain
- `selector` is the DNS selector you would like to use.
- If you would like you can pass in the value of a predetermined `private_key`. If the value is not set or blank a new key will be generated.
- `public_key` is optional and informational only.

You can also choose to make a backup of your keys by setting `opendkim_save_keys_locally: true`. The default save location is `{{ inventory_dir }}/../_private/keys`, but may be overridden by setting `opendkim_local_keys_path`.


## Dependencies

MatthewMi11er.postfix

## Example Playbook

```yml
    - hosts: servers
      roles:
         - MatthewMi11er.opendkim
```

## License

MIT

## Author Information
