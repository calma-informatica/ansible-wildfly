### Fazer deploy de aplicação de referência {docsify-ignore}

Para fazer deploy da aplicação de referência é preciso garantir alguns pré requisitos como:
  1. Garantir que o DataSource do oracle esteja devidamente funcional. Acessar a console web e garantir que o teste no datasource esteja deviamente funcional.
  1. Criar os objetos de banco conforme scripts abaixo:
  ```sql
  CREATE USER demouser IDENTIFIED BY passwduser;

  alter user SYSTEM quota unlimited on SYSTEM;
  alter user SYSTEM quota unlimited on SYSTEM;

  GRANT create session TO demouser;
  GRANT create table TO demouser;
  GRANT create view TO demouser;
  GRANT create any trigger TO demouser;
  GRANT create any procedure TO demouser;
  GRANT create sequence TO demouser;
  GRANT create synonym TO demouser;

  alter user demouser quota unlimited on SYSTEM;
  alter user demouser quota unlimited on SYSTEM;

  create sequence demouser.request_seq start with 1 increment by  1;
  create sequence demouser.visitor_seq start with 1 increment by  1;
  create table demouser.tb_requests (id number(19,0) not null, data timestamp, origin varchar2(255 char), server varchar2(255 char), virsitor_id number(19,0), primary key (id));
  create table demouser.tb_visitor (id number(19,0) not null, ip varchar2(255 char), primary key (id));
  alter table demouser.tb_requests add constraint FK9flybfu2nbohe68rwde52n1vg foreign key (virsitor_id) references demouser.tb_visitor;
  ```
**A aplicação foi testada utilizando um banco de dados Oracle 11G e está devidamente configurada para o Oracle**

Executar o playbook abaixo
```
ansible-playbook -i hosts 06-deploy-cluster-db-app.yml -vv
```

Acesse a URL http://10.1.124.10/cluster-db-app/swagger-ui.html (_Observe o IP do seu cluster e faça a devida alteração_)
![](/images/fig03.png)

A partir da janela do swagger é possível testar todos os métodos disponíveis na API.
![](/images/fig04.png)
