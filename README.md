# Clonando o repositório

```console
git clone https://github.com/rafaelperazzo/strapi
```

## Iniciando o strapi

```console
cd strapi
cd mobile
docker-compose up -d
``` 

## Acessando o painel admin

* No Chrome/Firefox digite a URL: http://localhost:1337/admin
* Crie o usuário admin

## Exportando o banco de dados (mariadb/mysql) do container

```console
docker-compose exec strapiDB bash
mysqldump -u mobile -pmobile --add-drop-database --add-drop-table --databases mobile > /export/mobile.sql
```

* Onde usuário = mobile; senha=mobile (-pmobile); database name=mobile e mobile.sql é o arquivo exportado
* strapiDB é o nome do serviço no docker-compose

## Importando o banco de dados (mariadb/mysql) para o container

```console
docker-compose exec strapiDB bash
mysql -u mobile -pmobile mobile < mobile.sql
```

## Exportando o banco de dados (postgree) do container

```console
docker-compose exec strapiDB bash
pg_dump -c -C -h localhost -U usuario database > /export/projeto.sql

```

## Importando o banco de dados (postgree) para o container

```console
docker-compose exec strapiDB bash
psql -U usuario database < /export/projeto.sql

```
