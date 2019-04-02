### Configurar o Domain Admin {docsify-ignore}

O passo abaixo configura um host com:
- Apache HTTP Server com mod_cluster
- Wildfly 16.0.0 como Domain Admin.

**Obs: Nenhum servidor virtual é executado no host Domain Admin, este host tem a finalidade de administração do ambiente**

1. Execute o playbook abaixo para configurar o domain admin
```
ansible-playbook -i hosts 04-domain.yml -vv
```
