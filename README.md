# Passo a passo para a criação do ambiente.

Projeto com playbooks de [Ansible](https://www.ansible.com) para automação da criação de ambientes Wildfly.

*Clique <a href="https://calma-informatica.github.io/ansible-wildfly/" target="_blank">aqui</a> para acessar a documentação*

Os playbooks criam e configuram ambientes wildfly no modo domínio ilustrado conforme imagem abaixo:
![](/docs/images/wildfly-diagram.svg)

Os seguintes passos são automatizados pelo playbook:
* Configuração para usuário Linux
* Transferência de chaves SSH entre os servidores
* Instalação de pacotes essenciais
* Ajustes de data e hora com timezone local
* Atualização de pacotes e kernel
* Instalação da Open JDK (versão community) 1.8
* Instalação e configuração de servidor Apache HTTP 2.4 configurado com mod_cluster
* Instalação e configuração do servidor de aplicação Wildfly versão 16.0.0 em modo domínio com balanceamento de carga e cluster com replicação de sessão HTTP.
* Configuração de usuários e grupos no modelo RBAC no Wildfly
* Habilitação de métricas para conexão com o banco de dados
* Limite de tempo para execução de comandos SQL
* Configuração de DataSource para banco Oracle e Postgres
* Criação de grupos de aplicação para exemplos
* Criação de virtual servers para hospedar aplicações de exemplo
* Disponibiliza duas aplicações para testar o ambiente:
  * counter
    * para acessar: http://[CLUSTER_IP]/counter
  * cluster-app
    * para acessar: http://[CLUSTER_IP]/cluster-app
