# Huawei Network Role
Esta role faz backup e gerencia ACLs em switches Huawei via Ansible.

## Variáveis
- `backup_path`: Caminho para armazenar backups.
- `switch_username`, `switch_password`, `switch_enable_password`: Credenciais do switch.
- `acl_rules`: Lista de ACLs a configurar.

## Uso
```yaml
- hosts: huawei
  roles:
    - huawei_network_role
```
