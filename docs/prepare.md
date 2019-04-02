### Preparação das máquinas com pré requisitos para execução do wildfly {docsify-ignore}

1. Verificar os IPs, nome das máquinas e demais parâmetros do arquivo playbook-vars.yml
1. Executar o playbook abaixo
```
ansible-playbook -i hosts 03-prepare.yml -vv
```

**Antes de prosseguir faça o download do wildfly no link https://download.jboss.org/wildfly/16.0.0.Final/wildfly-16.0.0.Final.zip e ponha na pasta binary.**

O playbook procurará por um arquivo com nome wildfly-16.0.0.Final.zip dentro da pasta binary. Certifique-se de que haja um arquivo válido com este nome representando a versão 16.0.0.Final do Wildfly.
