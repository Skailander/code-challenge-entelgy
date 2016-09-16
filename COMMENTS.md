#Coment�rios#

Nas se��es a seguir, irei descrever as decis�es mais relevantes do ponto de vista t�cnico.

## Spring Boot, Data e REST ##

Nunca havia utilizado esses m�dulos do Spring juntos, mas fiquei bastante impressionado com a organiza��o e facilidades que ele proporciona. 
Al�m disso, pude utilizar uma arquitetura que se assemelha em muitos aspectos com o MEAN (MongoDB, [ExpressJS](https://github.com/expressjs/express), AngularJS e Node.js), uma abordagem emergente atualmente. 
Em termos praticos o Node.js deu lugar ao Java e o ExpressJS ao Spring.

## MongoDB ##

Com rela��o ao banco de dados, optei por um NoSQL pois o dom�nio da aplica��o n�o exigia relacionamentos fortes entre as entidades. 
Com isso, pude obter um ganho consider�vel de performance, mesmo utilizando uma inst�ncia free no [mLab](https://mlab.com).
Caso queira utilizar o MongoDB localmente, basta alterar a constante `MONGODB_CLIENT_URI` no arquivo `MongoConfig.java`.

## CORS Filter ##

Devido � estrutura atual dos projeto, tive de permitir acesso aos m�todos GET e PATH em meu CORS Filter na classe `RestConfig.java`. 
Assim, as aplica��es (backend e frontend) podems e comunicar mesmo em dom�nios diferentes.

## AngularJS e Angular Material ##

Tais escolhas para o frontend se devem a duas coisas:

1. O Angulat Material � uma implementa��o de refer�ncia do Google Material Design, talves um dos padr�es mais difundidos atualmente. Al�m disso, � totalmente responsivo e aderente ao conceito de Mobile First;
2. J� o Angular utilizei porque tenho boa familiaridade com o framework e isso me ajudou em termos de produtividade.

## Ecolu��es ##

#### Make file ####