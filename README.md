## kong

# Instalação do Kong no Docker Compose


### O que é Kong?

Você pode encontrar a distribuição oficial do Docker para Kong em [https://hub.docker.com/_/kong](https://hub.docker.com/_/kong).

### Instalando o kong

1 - Primeiro vamos subir o Cassandra, execute o arquivo dockercompose.yaml em sua IDE de prefenrencia ou até mesmo no seu terminal utilizando o comando **docker-compose up -d kong-database**, para garantirmos que não haverá nenhum conflito entre o Kong e o banco de dados Cassandra. Para validar se o container esta up e funcional utilizando o comando **docker ps** ou **docker-compose ps**. 

O resultado deve ser igual ou semelhante a imagem abaixo.

![Cassandra no ar](https://user-images.githubusercontent.com/68164552/111360321-59bb4580-866b-11eb-9055-8943b82ac01a.jpg)

2 - Após esse passo, execute o arquivo dockercompose.yaml em sua IDE de preferência ou até mesmo no seu terminal utilizando o comando **docker-compose up -d** , isso executará o deploy dos demais containers.

Para validar se os containers estão up e funcionais execute o comando **docker ps** ou **docker-compose ps**. 

![Containers no ar](https://user-images.githubusercontent.com/68164552/111360865-04336880-866c-11eb-9a9d-79f2f3255f58.jpg)

Feito todos esses passo vamos validar a funcionalidade do Kong.

### Validando interfaces kong

Ao executar vá no navegador e digite: localhost:8000 (Api do kong) e localhost:8001 (kong backend ) 

Segue abaixo o que é esperado em cada um desses endereços.

localhost:8000 - (Endereço onde o Kong responde)

![8080](https://user-images.githubusercontent.com/68164552/111361764-d13da480-866c-11eb-8d08-7326b1cd361f.jpg)

localhost:8001 (kong backend - API de administração )

![8001](https://user-images.githubusercontent.com/68164552/111361891-f500ea80-866c-11eb-9e59-6eab856b7cf7.jpg)

### Configurando o Konga

Para acessar o konga (interface grafica do kong) no seu navegador digite localhost:1337

![Konga](https://user-images.githubusercontent.com/68164552/111362832-08f91c00-866e-11eb-96c9-6d2e3ba2e00a.jpg)

Defina um usuário e senha

![user](https://user-images.githubusercontent.com/68164552/111369869-4d88b580-8676-11eb-873f-e3807178b1c7.jpg)

Na tela de configuração defina as configurações abaixo

Name: kong

Kong Admin URL: http://kong:8001

![kong konfig](https://user-images.githubusercontent.com/68164552/111371214-df44f280-8677-11eb-9ebf-d81ca23ac2b6.jpg)


Após essas configurações é esperado um dashboard da interface Konga.

![intkonga](https://user-images.githubusercontent.com/68164552/111363618-06e38d00-866f-11eb-9ceb-ae7910777962.jpg)

Pronto! O Kong esta pronto para ser usado

### Importando as Api's no Konga

1 - Vamos importar as API'S do Kong no menu lateral esquerdo, opção Snapshots.
2 - Clique em import from file
3 - Selecione o arquivo configs_konga

![Snapshotkonga](https://user-images.githubusercontent.com/68164552/111372125-ff28e600-8678-11eb-9f0a-f4adb8b085d7.jpg)

4 - Clique em details, depois restore e selecione todas as opções.

![snapshotrestore](https://user-images.githubusercontent.com/68164552/111372818-e66d0000-8679-11eb-92c6-808a0bb56cc4.jpg)

5 - Clique em import objects.

### Validando configurações

Agora vá na aba service e veja se o backend esta configurado.

![snapshotrestore](https://user-images.githubusercontent.com/68164552/111373313-832f9d80-867a-11eb-8030-476a1088ae2a.jpg)

Valide se as rotas estão ok também.

![routes](https://user-images.githubusercontent.com/68164552/111375134-ace9c400-867c-11eb-86ec-d2b47e7b19d5.jpg)


Pronto! Tudo ok.

Obs: O arquivo DPSP_postman_collection_v1 estão configuradas todos os metodos das API'S de Mock!

A documentação de Kong pode ser encontrada em [https://docs.konghq.com/][kong-docs-url]

##DOCS adicionais

[kong-site-url]: https://konghq.com/
[kong-docs-url]: https://docs.konghq.com
