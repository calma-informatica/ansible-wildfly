### Preparação das máquinas com pré requisitos para execução do wildfly {docsify-ignore}

1. Verificar os IPs, nome das máquinas e demais parâmetros do arquivo playbook-vars.yml
1. Executar o playbook abaixo
```
ansible-playbook -i hosts 03-prepare.yml -vv
```
