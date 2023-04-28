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

## Exportando o banco de dados do container

```console
docker-compose exec strapiDB bash
mysqldump -u mobile -pmobile --add-drop-database --add-drop-table --databases mobile > /export/mobile.sql
```

* Onde usuário = mobile; senha=mobile (-pmobile); database name=mobile e mobile.sql é o arquivo exportado
* strapiDB é o nome do serviço no docker-compose

## Importando o banco de dados para o container

```console
mysql -u mobile -pmobile mobile < mobile.sql
```