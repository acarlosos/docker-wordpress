#
## Como executar o Docker Wordpress com Docker Compose
## Passo 1 — Fazendo download do Projeto

Primeiramente, verifique se você está no seu diretório home e faça uma cópia da versão mais recente do Projeto:

    $ git clone git@github.com:acarlosos/docker-wordpress.git wordpress

Vá até o diretório wordpress:

    $ cd wordpress

Vamos fazer uma cópia do arquivo .env.example para .env e inserir as configurações do banco de dados:

    $ cp .env.example .env

Adicionando as configurações
Nome do projeto pode ser definido na variável COMPOSE_PROJECT_NAME.
Para o banco de dados você pode definir um nome para seu banco de dados em DB_DATABASE, um usuário em DB_USERNAME e uma senha para seu usuário em DB_PASSWORD é importante também definir uma porta para seu banco de dados em DB_PORT
Na variável WEBSERVER_PORT você defini onde seu wordpress vai estar disponível.

```.env```
```
COMPOSE_PROJECT_NAME=wordpress
DB_DATABASE=wordpress
DB_USERNAME=wordpress
DB_PASSWORD=secret
DB_PORT=3399
WEBSERVER_PORT=8099
```

Hora de levantar os containers:

    $ docker-compose up -d

## Passo 2 - Acessando seu Wordpress

Com tudo configurado você pode acessar seu wordpress visitando http://localhost:8099 no seu navegador.
lembre que a porta deve ser igual a configurada em WEBSERVER_PORT que no nosso exemplo é 8099