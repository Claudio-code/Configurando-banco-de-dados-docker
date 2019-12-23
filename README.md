# :whale: Configurando o banco de dados no docker

## Objetivo
O objetivo aqui é mostrar como configurar bancos de dados relacionais e não relacionais usando o docker, montaremos um container com o postgres de banco relacional e o mongoDb para ter um NoSql e configuraremos um banco de cache de chave e valor e para isso usaremos o Redis.

### Pré-requsitos 

Para proseguir com esse guia você precisa ter o docker instalado no seu sistema, ele felizmente esta disponivel para todos os sistemas operacionais, para isso basta seguir o guia de instalação no site da documentação.

Guia de instalacao - [Docker](https://docs.docker.com/install/) - **https://docs.docker.com**.


### Iniciando 

1. Faremos o download da imagem do postgres usando o docker execulte esse comando no terminal.
```sh
  docker pull postgres
```
> Para poder checar se a imagem foi baixada você pode execultar esse comando.
```sh
  docker image list
```
  
 2. Vamos instanciar o banco.
 ```sh
    docker run --name postgresDb -e POSTGRES_PASSWORD=IloveLinux -p 5432:5432 -d postgres
  ```
- para checar se o banco esta sendo execultado digite que todas as instancias serão listadas inclusive as que não estao sendo execultadas no momento.

```sh
  docker ps -a
```
 
 3. Agora vamos iniciar o postgres digitando.
 
 ```sh
  docker start postgresDb
```
- pronto agora o banco pode ser usado por sua aplicação. 

### MongoDb

4. Vamos instalar o mongoDb.

```sh
  docker run --name mongoDb -p 27017:27017 -d -t mongo
```
- para execultar ele execulte o mesmo comando a cima.

```sh
  docker start mongoDb
```

### Redis

5. Agora vamos instalar o redis 
```sh
  docker run --name redisDb -p 6379:6379 -d -t redis:alpine
  
  docker start redisDb
```

### :smiley: Pronto agora você tem um banco relacional um banco não relacional e um banco de cache Agora partiu codar.
