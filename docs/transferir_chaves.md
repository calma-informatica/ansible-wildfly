### Transferência das chaves SSH entre o bastion (*máquina que executará os comandos ansible*) e os servidores {docsify-ignore}

1. Verificar os IPs e nome das máquinas no arquivo 01-playbook-copy-id.yml
1. Após ajustar e garantir que os IPs estão devidamente configurados executar o comando abaixo:
```
ansible-playbook 01-playbook-copy-id.yml -vv
```
