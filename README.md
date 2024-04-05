# Github MLaidler Style - Remaster Hugo Theme
Modified version of the Hugo theme, Github-Style, to fit my personal static pages theme - 'repository just to save this'

 - If you want to modify my menu, u can go on and edit the html file: 'layouts/partials/header.html'

### Download 
Check our release to download the latest zip file version.

You can try first to install the original theme and then change the files.

Or click [here](https://github.com/matheuslaidler/github-style-remaster/releases/tag/download)

You can just follow the original theme tutorial to install:
https://github.com/MeiK2333/github-style
 
# Sobre // About

Este projeto é uma adaptação de um já existente, um tema no estilo GitHub para a criação de blogs estáticos utilizando Hugo. O tema original foi criado por MeiK2333 e eu o modifiquei para se adequar ao meu projeto. Realizei correções de alguns bugs e personalizei o site de acordo com minhas preferências, incluindo a adição de um menu próprio que será padrão em todas as páginas do meu site no GitHub. Adicionei também funções novas e modifiquei funções já existentes, como ter colocado a alternância entre os temas Dark/Light para o meu menu e deixei um botão desse na versão mobile também dentro do menu do github style para facilitar. Todos os créditos ao criador original do tema são devidos, além dos meus próprios pela remasterização, caso alguém decida utilizá-lo. Planejo utilizar este tema na nova versão do meu acervo pessoal, disponibilizado através do GitHub Pages.

This project is an adaptation of an existing one, a GitHub-style theme for creating static blogs using Hugo. The original theme was created by MeiK2333 and I modified it to suit my project. I made corrections to some bugs and customized the site according to my preferences, including the addition of a proprietary menu that will be standard on all pages of my site on GitHub. I also added new functions and modified existing ones, such as having placed the Dark/Light theme switch for my menu and left a button for this in the mobile version also within the github style menu to facilitate. All credits to the original creator of the theme are due, in addition to my own for the remastering, in case someone decides to use it. I plan to use this theme in the new version of my personal blog, made available through GitHub Pages.

## Preview

 - v1

   ![preview](https://github.com/matheuslaidler/github-style-remaster/assets/76860503/6dbbe32d-afe2-4773-8b53-8327059218c2)

## Requirements

Hugo installed... // Hugo instalado...

You may need to use git // Talvez - provavelmente - precisará usar o git (isso depende de como vc vai fazer seu site)

You can use those command lines with something like Win Powershell or any Linux Terminal // use powershell ou terminal

## Tutorial

Tutorial same as github-style - almost

## Init hugo site

```bash
hugo new site mysite
cd mysite
```

## Install the theme

Installing as submodule can be done with the original theme tutorial

You can download and drag the folder "github-style" to "themes".

```bash
git clone https://github.com/matheuslaidler/github-style-remaster.git
```

PS: Rename your previous `posts` folder to `post` to use our theme - inside `content` 

```bash
cd <you-project-folder>
mv content/posts content/post
```
 - if you have just the content folder: `hugo new post/teste.md` to create a post with the right folder


## Setting your hugo theme

Edit your hugo.toml

Edit/Add the "theme" value;

`theme = "github-style`

-- don't forget to add your url on 'baseURL'

## Setup readme

```bash
hugo new readme.md
echo '`Hello World!`' > content/readme.md
```

## LocalHost -  Previewing your new hugo site

```bash
hugo server -D
```
(or just hugo server)

## Pin post

```
---
pin: true
---
```


## Limit display content

### Approach 1: use summary

```
---
title: "title"
date: 2019-10-22T18:46:47+08:00
draft: false
summary: "The summary content"
---
```

### Approach 2: use `<!--more-->`

Use `<!--more-->` to separate content that will display in the posts page as abstraction and the rest of the content. This is different from summary, as summary will not appear in the post.
```
---
title: "title"
date: 2019-10-22T18:46:47+08:00
draft: false
---
abstraction show in the post page
<!--more-->
other content
```

## Add last modified date

add to `hugo.toml`

```toml
lastmod = true

[frontmatter]
  lastmod = ["lastmod", ":fileModTime", ":default"]
```

## Use [gitalk](https://github.com/gitalk/gitalk) to support comments

add to `config.toml`

```toml
enableGitalk = true

  [params.gitalk]
    clientID = "Your client ID" 
    clientSecret = "Your client secret" 
    repo = "repo"
    owner = "Your Github username"
    admin = "Your Github username"
    id = "location.pathname"
    labels = "gitalk"
    perPage = 30
    pagerDirection = "last"
    createIssueManually = true
    distractionFreeMode = false
```

## Support LaTeX

In you post add `math: true` to [front matter](https://gohugo.io/content-management/front-matter/)

```
---
katex: math
---
```

Then the [katex script](https://katex.org/docs/autorender.html) will auto render the string enclosed by delimiters.

```
# replace ... with latex formula
display inline \\( ... \\)
display block $$ ... $$
```

![image](https://github.com/matheuslaidler/github-style-remaster/assets/76860503/68d8cb20-3e8d-4b3b-b4a9-4920b6407317)


## Support MathJax
you can add MathJax:true to frontmatter

```
mathJax: true
```

## Support collapsible block

You can create a collapsible block like this:

```
{{<details "summary title">}}

block content

{{</details>}}
```

And it will show like this:

<details>
  <summary>summary title</summary>
  <p>block content</p>
</details>


## Credits

- MeiK2333 - Github Style
  
[![Github](https://img.shields.io/website?label=github+Repository&style=for-the-badge&url=https://github.com/MeiK2333/github-style)](https://github.com/MeiK2333/github-style)


- MLaidler - Github Style Remaster
  
[![Github](https://img.shields.io/website?label=github+Repository&style=for-the-badge&url=https://github.com/matheuslaidler/github-style-remaster)](https://github.com/matheuslaidler/github-style-remaster)

