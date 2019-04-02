### Interface de administração Web {docsify-ignore}

Ao acessar a URL http://10.1.124.10:9990 para visualizar a console web
![](/images/fig01.png)
**Observar a URL. No exemplo foi usado o IP 10.1.124.10, verifique o IP configurado para o Domain Master e faça a devida alteração**

O Playbook cria três usuários de gerenciamento;
- wildflyAdmin
  - Super usuário com privilégios totais
  - senha: *password*
- wildflyMonitor
  - Usuário com perfíl de monitoramento. Pode ver logs e estado das aplicações
  - senha: *passwordMonitor*
- wildflyDeployer
  - Usuário com perfil de operação. Gerencia deploy de aplicações e ciclo de vida dos servidores
  - senha: *passwordDeployer*
