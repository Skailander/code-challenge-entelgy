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
2. J� o Angular utilizei porque tenho boa familiaridade com o framework e isso me ajudou em termos de produtividade. Apesar da vers�o 2 j� estar dispon�vel a algum tempo, a migra��o � significativamente complexa. De qualquer forma, todo c�digo implementado seguiu os guidelines de [John Papa](https://github.com/johnpapa/angular-styleguide/blob/master/a1/README.md).

## TODO ##

Como evolu��es futuras, pensei nos seguintes itens:

* **Makefile**: arquivo com scripts organizados de modo a facilitar os testes e implanta��o do projeto; 
* **ECS6**: migrar todo o frontend para o ECMAScript 6, mesmo que para isso fosse necess�rio utilizar um compilador/tradutor como o [Babel](https://github.com/babel/babel/). Pois a nova vers�o dessa especifica��o traz melhorias fant�sticas para o JavaScript;
* **i18n**: criar um mecanismo de internacionaliza��o no front e tamb�m banckend.