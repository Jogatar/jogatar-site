# Website Jogatar

Seja bem vindo, participante do Jogatar. A ideia desse projeto é criarmos um sites simples, para compartilharmos todos os projetos desenvolvidos durante a #ImersaoGameDev, da Alura.

## O Rascunho do Site

O protótipo do site pode ser encontrado em [https://www.figma.com/file/dcRsAYEJnYWQ5HGYIJjxJf/Portifolio?node-id=0%3A1](https://www.figma.com/file/dcRsAYEJnYWQ5HGYIJjxJf/Portifolio?node-id=0%3A1).

O site, inicialmente, terá a seguinte estrutura:

![Estrutura do Site](https://github.com/Jogatar/jogatar-site/blob/master/assets/images/estrutura.jpg)

## O ambiente

Para trabalhar nesse projeto, você precisa de 3 coisas:

* Uma conta no Github e o git instalado na sua máquina
* Um bom editor de texto (sugestão: VS Code, Atom ou Sublime)
* O Docker instalado na sua máquina

## Montando o ambiente

Uma vez que os requisitos tenham sido instalados, siga os seguintes passos:

1. clone o projeto
2. execute os comandos abaixo

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
