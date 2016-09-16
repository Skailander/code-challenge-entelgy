# Backend #

Primeiramente, clone o repositório do projeto via Git e acesse o diretório de `backend`:

#### SSH ####
```
git clone git@bitbucket.org:falvojr/entelgy-challenge.git && cd backend
```
#### HTTPS ####
```
git clone https://falvojr@bitbucket.org/falvojr/entelgy-challenge.git && cd backend
```

## Estrutura ##

Em termos estruturais, o frontend foi estruturado da seguinte maneira:

```
src/               --> todo o código-fonte da aplicação.
  main/java        --> classes responsáveis pelos endpoints RESTful, banco de dados (MongoDB) e configurações de segurança.
  test/java        --> classes responsáveis pelos testes unitários da aplicação.
build.gradle       --> descreve o projeto, provendo um poderoso mecanismo de build e gestão de dependências.
```

## Pré-Requisitos ##

#### Java 8+ ####

#### Gradle: ####

```
curl -s https://get.sdkman.io | bash
sdk install gradle 3.0
```

## Execução ##

Com o Gradle devidamente instalado, basta executar o comando a seguir, ele irá baixar as dependências necessárias e subir a aplicação na porta 8080:

```
gradle bootRun
```

*O comando acima irá subir nossa API REST e com o isso o frontend poderá consumí-la.*  
*Nota: no Ubuntu 16.04 o script em questão é finalizado com sucesso, mas o terminal apresenta `> Building 80% > :bootRun`. Entretanto, isso não impacta no acesso à API, que já estará disponível.*

## Testes ##

A classe `CandidateTests` encapsula os testes dos principais enpoints da API.
Nesse sentido, foi utilizada a implementação `SpringRunner`, que funciona em conjunto com o JUnit 4 e o Mock MVC.
Para rodar os testes unitários basta executar o seguinte comando:

```
gradle build
```

* ATENÇÃO: a classe de testes está configurada para excluir todo o banco de dados após a sua execução. Por isso, caso queira mantê-los, basta comentar a linha abaixo do **TODO** *