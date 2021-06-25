# Kong no Docker Compose

Este é o modelo oficial do Docker Compose para [Kong] [kong-site-url].

# O que é Kong?

Você pode encontrar a distribuição oficial do Docker para Kong em [https://hub.docker.com/_/kong](https://hub.docker.com/_/kong).

# Instalando o kong

Execute o arquivo dockercompose.yaml em sua IDE de prefenrencia ou até mesmo no seu terminal utilizando o comando docker-compose up -d, após isso digite o comando docker-compose ps para validar se os containers estão funcionais.

# Validando interfaces kong

Ao executar vá no navegador e digite: localhost:8000 (Api do kong) e localhost:8001 (kong backend ) 

Kong estará disponível através da instância `nginx-lb` na porta` 8000` e `8001`. Você pode personalizar o modelo com suas próprias variáveis ​​de ambiente ou configuração de armazenamento de dados.


# Configurando o Konga


Para acessar o kong (interface grafica do kong) no seu navegador digite localhost:1337, defina um usuário e senha e logo após defina as configurações. Na aba default defina as seguintes configurações.

Name: kong
Kong Admin URL

Agora o konga esta pronto para ser usado


# Importando as Api's no Konga

Agora importe as api's no menu esquerdo, opção Snapshots e importe o arquivo "ConfigsKonga.json"
Agora va na aba service e veja se o backend esta configurado, além disso vá em rotas e verifique as rotas configuradas.

Pronto! Tudo ok.

Obs: O arquivo DPSP.postman_collection estão configuradas todos os metodos das apo's de Mock


A documentação de Kong pode ser encontrada em [https://docs.konghq.com/][kong-docs-url].

## Problemas

Se você tiver problemas ou perguntas sobre esta imagem pergunte para Leonardo Pinho 11 93466-6775

##DOCS

[kong-site-url]: https://konghq.com/
[kong-docs-url]: https://docs.konghq.com