+++
date = "2017-03-29T13:18:56-03:00"
comments = true
title = "Iniciando com Hugo"
slug = ""
tags = ["hugo", "html", "go"]
author = "Jhonata Menezes"
menu = "teste"
description = "Iniciando com o gerador de HTML Hugo"
draft = true
share = true
image = "/images/hugo.png"
+++

[Hugo](https://gohugo.io/) é um gerador de html estatico, desenvolvido na linguagem de programação Go (Golang) o conteudo é escrito em Markdown se mostrando rapido na geração de html.O intuito deste post é fazer o basico com essa ótima ferramenta, criar um projeto novo e fazer um post, então vamos iniciar.

### Instalação
Para instalar Hugo é necessario apenas seguir os procedimentos demonstrados na documentação https://gohugo.io/overview/installing/
no meu caso que estou usando Ubuntu irei usar o pacote deb hugo_0.19-64bit.deb que foi obtido atraves do projeto no [github](https://github.com/spf13/hugo/releases)
```bash
wget "https://github.com/spf13/hugo/releases/download/v0.19/hugo_0.19-64bit.deb" && sudo dpkg -i hugo_0.19-64bit.deb
```
Executando 'hugo version' deverá aparecer a versão do Hugo, estou utilizando a 0.19.

Para criar um diretorio onde sera seu espaço de trabalho execute: `hugo new site nome_do_meu_blog` e sera criada uma pasta nome_do_meu_blog com uma hierarquia de diretorios. Executando `hugo --help` é possivel ver outras opções e parametros do hugo.
`hugo new post/iniciando-com-hugo.md` ira criar uma pasta `post` dentro de `content` com um arquivo chamado `inciando-com-hugo.md`. Este arquivo é onde deve ser feito a edição, para publicação de conteudo.

Um exemplo simples de conteudo em draft (esboço)
```markdown
+++
date = "2017-03-29T13:18:56-03:00"
title = "Iniciando com Hugo"
Description = "Iniciando com o gerador de HTML Hugo"
draft = true
+++
```

### Edição e visualização
Hugo contem um servidor web embutido com live reload `hugo server --baseURL "http://192.168.56.12/" --buildDrafts --bind 192.168.56.111`
baseUrl e bind é preciso pois executo dentro de uma maquina virtual, sabendo que o padrão é sempre listar localmente, buildDrafts é para exibir o conteudo em esboço.

### config.toml
config.toml é o arquivo de configuração, tem alguns paramentro padrão para o hugo como também para o tema que esta sendo utilizando, segue o meu config.
```yaml
Subtitle = "Blog Forseti Tecnologia"
description = "Compartilhando problemas enfrentados pela equipe da Forseti"
baseURL  = "https://git-forseti.github.io/"
theme = "bleak"
languageCode = "en-us"
buildDrafts = false
publishdir = "public"
author = "Forseti Tecnologia e Comunicação"
canonifyURLs = false


[params]
dateform = "2 Jan, 2006"
dateformfull = "2 Mon Jan 2006 15:04:05 MST"
description = "Passando o conhecimento para a internet"
logofile = ""
faviconfile = ""
highlightjs = true
progressively = true
lang = "pt-br"
github = "https://github.com/git-forseti/"
email = "forseti@forseti.com.br"
linkedin = ""
twitter = ""
```
Todas as configurações são encontradas na [documentação](https://gohugo.io/overview/introduction/)

### Temas
Os temas são faceis de instalar, existe varios temas montados e bem legais, apenas clonar `git clone https://github.com/Zenithar/hugo-theme-bleak.git` dentro da pasta themes. No atual momento estou utilizando `http://themes.gohugo.io/bleak/`, é possivel ter mais de um dentro da pasta, voce tambem pode configurar o padrao dentro de config.toml

http://themes.gohugo.io/

### Gerando HTML
Chamando apenas `hugo` ele gera os arquivos estaticos dentro da pasta public (porque eu configurei no config.toml), com esses arquivos eu posso enviar para qualquer servidor web e visualiza-los.

### Extra
Para utiliza o [Github Pages](https://pages.github.com/) para arquivos estaticos, utilizo um comando simples para enviar, coloco a pasta no gitignore `echo "public/" >> .gitignore"` e `git worktree add -B gh-pages public/ origin/gh-pages` (a partir da versão 2.5 do Git), com esse comando a pasta public é uma branch diferente, gere os arquivos estaticos, entre no public/, 'comita' e envie. Ao acessar https://seu_usuario.github.io/repositorio o conteudo estará disponível. O legal que o custo é zero em servidor ou hospedagem e a publicação mais simples ainda, sendo possivel automatizar o mesmo.

Até a próxima.

___

Jhonata Menezes [Github](https://github.com/jhonata-menezes) [Linkedin](https://www.linkedin.com/in/jhonata-santos-a3659011a/)

  
  




