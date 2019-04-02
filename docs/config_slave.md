### Configurar os nodes slaves {docsify-ignore}

O playbook cria uma quantidade pré configurada de nodes que serão os slaves do master domain. São estes nodes que criam servidores virtuais e executam as aplicações.

1. Execute o playbook abaixo para configurar o domain slave
```
ansible-playbook -i hosts 05-slaves.yml -vv
```
