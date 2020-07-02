# Website Jogatar

## Nosso prototipo
https://www.figma.com/file/dcRsAYEJnYWQ5HGYIJjxJf/Portifolio?node-id=0%3A1

## Comandos úteis

Pra você, participante do Jogatar, que acabou de clonar o projeto, seguem alguns comandos úteis:

### 1. Construção da imagem

Para construir a imagem do contêiner, usamos o comando abaixo, na pasta do projeto.

```shell
docker build -t jogatar-site .
```

### 2. Execução do contêiner

Criar, dentro da pasta do projeto, a pasta `vendor/bundle`

Então, executar o contêiner com o seguinte comando:

```shell
docker run --rm -it -v "/d/repositorios/jogatar-site:/srv/jekyll" -v "/d/repositorios/jogatar-site/vendor/bundle:/usr/local/bundle" -p 4000:4000 -p 35729:35729 --name jogatar-site jogatar-site bash
```

### 3. Pra executar o servidor de desenvolvimento

Executa o servidor do jekyll.

```shell
jekyll serve --watch --force-polling --livereload
```

Após a execução do `jekyll serve`, verifique, no Kitematic, qual a o IP para acessar o container ou execute, no terminal do host, o comando `docker-machine ip`. O endereço para acesso é [http://IP_DO_DOCKER_MACHINE/jogatar-s]([http://IP_DO_DOCKER_MACHINE/jogatar-s])

## Mais comandos

### Conectando num container que está rodando

Se você precisar se conectar ao container:

```shell
docker exec -it jogatar-site bash
```

## Referências

* [https://dev.to/michael/compile-a-jekyll-project-without-installing-jekyll-or-ruby-by-using-docker-4184](https://dev.to/michael/compile-a-jekyll-project-without-installing-jekyll-or-ruby-by-using-docker-4184)
* [https://programminghistorian.org/en/lessons/building-static-sites-with-jekyll-github-pages](https://programminghistorian.org/en/lessons/building-static-sites-with-jekyll-github-pages)
* [https://ddewaele.github.io/running-jekyll-in-docker/](https://ddewaele.github.io/running-jekyll-in-docker/)
* [https://github.com/envygeeks/jekyll-docker](https://github.com/envygeeks/jekyll-docker)
