### Criar usuários administrativos {docsify-ignore}

1. Verificar os IPs e nome das máquinas no arquivo hosts
1. Executar o playbook abaixo:
```
ansible-playbook -i hosts 02-playbook-users.yml -vv
```
