# Huawei Network Role
Esta role faz backup e gerencia ACLs em switches Huawei via Ansible.

## Variáveis
As seguintes variáveis devem ser definidas nos formulários do Red Hat Ansible Automation Platform (AAP) para a correta utilização da role:

- `backup_path`: Caminho para armazenar backups. *(Exemplo: `/var/backups/huawei`)*
- `switch_username`: Nome de usuário para acessar o switch. *(Exemplo: `admin`)*
- `switch_password`: Senha do usuário do switch. *(Exemplo: `password`)*
- `switch_enable_password`: Senha para modo privilegiado do switch. *(Exemplo: `enable_password`)*
- `switch_ip`: Endereço IP do switch. *(Exemplo: `192.168.1.1`)*
- `acl_rules`: Lista de ACLs a configurar. *(Formato JSON/YAML: ver exemplo abaixo)*
- `backup_retention`: Número máximo de backups a serem mantidos. *(Padrão: 5)*

### Exemplo de ACL Rules:
```yaml
acl_rules:
  - id: 3000
    rules:
      - number: 10
        protocol: tcp
        src: any
        dst: 192.168.1.100 80
```

## Uso
```yaml
- hosts: huawei
  roles:
    - huawei_network_role
```