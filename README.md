# Safra Partners 

![Badge em Desenvolvimento](http://img.shields.io/static/v1?label=STATUS&message=EM%20DESENVOLVIMENTO&color=GREEN&style=for-the-badge)

## Motivação 
De acordo com uma pesquisa da PWC em 2019, no Brasil 95% das compras on-line utilizam marketplace.

Em termos de faturamento via e-commerce as plataformas de marketplace possuem uma representação de 78% do valor total faturado equivalente a R$ 81 bilhões de reais no ano de 2020

---

O Safra Partners surge dessa oportunidade, através da disponibilização de seus dados através do Open Banking entregamos a você cliente um marketplace com serviços que você não encontra com facilidade no mercado. 

Você como empresa parceira, acessa a plataforma e oferece seus produtos e serviços de forma online, contando com o Safra para virtualizar pagamentos e oferecer maior segurança a você e ao nossos clientes. 

---

## Stacks
* [Figma](https://www.figma.com/) - Design UX-UI.
* [Ruby on Rails](https://rubyonrails.org/) - Framework da linguagem Ruby utilizado no desenvolvimento Back-end 
* [Flutter](https://vuejs.org/) - Framework da linguagem Dart utilizado no desenvolvimento Mobile
* [MySQL](https://www.mysql.com/) - Sistema de gerenciamento de banco de dados, que utiliza a linguagem SQL como interface, usado no desenvolvimento. 
* [Postgress](https://www.postgresql.org/) - Sistema de gerenciamento de banco de dados, que utiliza a linguagem SQL como interface, usado na aplicação. 

# Arquitetura da aplicação

<div align="center">
<img src="https://raw.githubusercontent.com/matgermano/Hackaton_Safra2022/main/arquitetura.JPG" width="600">
</div>    


# BackEnd

O back-end cria a interface com a API open-bank Safra e com o banco de dados Safra Partners.
---

Esta API foi desenvolvida com a intenção de trabalhar de forma conjunta com o app Safra Partners, funcionando de backend da aplicação. Este então oferece o controle de usuários, tanto clientes do banco quanto parceiros e administradores do sistema, manejando dados do OpenBanking e oferecendo o controle de ofertas e contratos entre usuários e parceiros.

---
	
Uso (para teste) No diretório raiz:

	1- Criar e fazer migration da base de dados:
		rake db:migrate

    2- Iniciar o Rails
        rails s
	

### Endpoints da API

[Clique aqui para acessar os endpoints desta API](https://app.getpostman.com/join-team?invite_code=07290794c7e168fef1e5c2dafe30c9a6&target_code=d4579371b43ad35fef8eb87f20a710d4)

Gems instaladas (além das padrão do Rails)

	- pg 
        somente para ambiente de produção
	
	- devise
        para controle de usuários
	
	- simple_token_authentication 
        para login e requisições através de token

Versão:

1.0b A versão atual suporta o controle de usuários e o uso de token para acesso aos dados, porém os dados obtidos através dos endpoins do openbanking retornam
informações padrão, obtidas através da documentação do OpenBanking Brasil, pois apenas as instituições financeiras podem obter acesso aos dados de clientes reais,     após autorização.
    
[Também é possível acessar a API clicando aqui](https://safrapartners-backend-producti.herokuapp.com/)
    
# Front-end

O Front-end do aplicativo oferece uma experiência amigável ao usuário do Safra Partners em plataforma mobile. 

## Interface

- Login:

<div>
<img src="https://raw.githubusercontent.com/matgermano/Hackaton_Safra2022/main/login.png" width="250">
</div>    

---

- Solicitação do uso do Open Banking:
<div>
<img src="https://raw.githubusercontent.com/matgermano/Hackaton_Safra2022/main/opbank.png" width="250">
</div>    

---

## Uso (para teste):
	1- Instalar o framework Flutter e o Android Studio (para uso do SDK).
	2- Abrir o projeto pelo Android Studio.
	3- Conectar ao computador um smatphone em modo depuração ou utilizar o emulador embutido na plataforma.
	4- Executar o projeto no aparelho conectado.
	
## Telas / Fluxo:
	1- Auth page:
		- Autenticação do usuário;
		- Recuperação de senha;
	2- Intro page:
		- Introdução ao usuário sobre a plataforma;
		- Esclarecimento e confirmação dos dados a serem disponibilzados pelo usuário (Open Banking);
		- Mostrada apenas na primeira utilização do aplicativo;
	3- Home page:
		- Visualização dos serviços contratados e serviços aguardando propostas;
		- Solicitação de novos serviços;
	4- Contract page:
		- Timeline com as etapas necessárias para a contratação do serviço:
			- Apresentação do serviço escolhido;
			- Informações necessárias para contratação;
			- Visualização de propostas;
			- Detalhamento da proposta e finalização da contratação;
