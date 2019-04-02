### Explorando as aplicações de exemplo {docsify-ignore}

O playbook disponibiliza duas aplicações por padrão para validar o ambiente:
- [cluster-app](https://github.com/calma-informatica/cluster_app)
- [counter](https://github.com/calma-informatica/ansible-wildfly/raw/master/binary/counter.war)

São aplicações básicas que servem para demonstrar as aplicações em funcionamento no cluster.

#### Counter.war
Para acessar navegue até a URL http://10.1.124.10/counter.</br>
![](/images/fig05.png)

**Observação: Verifique o IP do seu ambiente e faça o devido ajuste, lembrando que o mod_cluster faz o balance automático e não é necessário incluir a porta (8080 por exemplo) na URL.**

Trata-se de uma aplicação que acumula a quantidade de acessos e põe este valor na sessão HTTP. O objetivo é garantir que caso o servidor que atualmente atende as requisições da página fique inoperante o segundo servidor no cluster seja capaz de manter a sessão ativa sem a perda de dados para o usuário final.

#### cluster-app.war
Para acessar navegue até a URL http://10.1.124.10/cluster-app.</br>
![](/images/fig06.png)

**Observação: Verifique o IP do seu ambiente e faça o devido ajuste, lembrando que o mod_cluster faz o balance automático e não é necessário incluir a porta (8080 por exemplo) na URL.**

Trata-se de uma aplicação que guarda as informações das requisições que atende. Informações como o IP de origem da requisição, a data da requisição e qual os IPs do servidor que atendeu àquela requisição. Trás também informações a respeito da sessão como o código da sessão e a data da criação.

A aplicação disponibiliza uma URL para guardar valores na sessão do usuário a fim de garantir que mesmo que a sessão troque de servidor os dados serão mantidos. Para incluir um parâmetro por exemplo que guarde a chave *foo* e o valor *bar* utilize a URL http://10.1.124.10/cluster-app/add?name=foo&value=bar

![](/images/fig07.png)</br>
Observe que no exemplo acima as requisições desta páginas estão sendo tratadas pelo servidor 10.1.124.30.</br>
Analisando o console web do wildfly é possível identificar qual o node que está atendendo as requisições.
![](/images/fig08.png)</br>

Através do console web é possível forçar uma parada do servidor remoto simulando um possível erro.
![](/images/fig09.png)</br>

É possível visualizar através do console web que o servidor foi parado e não está mais atendendo requisições.
![](/images/fig10.png)</br>

Basta fazer novas requisições na URL http://10.1.124.10/cluster-app e verificar que a partir de agora o IP que está tratando as requisições é o 10.1.124.20 e os dados da sessão do usuário permanecem.
![](/images/fig11.png)</br>
