# github-style-remaster
Modified version of the Hugo theme, Github-Style, to fit my personal static pages theme

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

Tutorial igual para github-style original... porém, add / modifiquei algumas coisas. - estará em inglês;

## Init hugo site

```bash
hugo new site mysite
cd mysite
```

## Install the theme

Installing as submodule:

```bash
git submodule add git@github.com:matheuslaidler/github-style-remaster.git themes/github-style-remaster
```

or download and drag the folder "github-style-remaster" to "themes".

(rename your previous `posts` folder to `post` to use our theme)

## Update the theme

If you just installed the theme, it is already in the latest version. If not, you can update using the below commands

```bash
cd themes/github-style-remaster
git pull
```

Then, you need to rename the previous `posts` folder to `post` again if needed.

```bash
cd <you-project-folder>
mv content/posts content/post
```

## Setup readme

```bash
hugo new readme.md
echo '`Hello World!`' > content/readme.md
```

## Pin post

```
---
pin: true
---
```

## Add new post

Hugo will create a post with `draft: true`, change it to false in order for it to show in the website.

```
hugo new post/title_of_the_post.md
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

add to `config.toml`

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

![latex example](images/latex_example.png)

## Support MathJax
you can add MathJax:true to frontmatter

```
mathJax: true
```
## config.toml or hugo.toml example

```toml
baseURL = 'https://matheuslaidler.github.io'
languageCode = 'pt-BR'
title = 'Github M.Laidler Style'
theme = "github-style-remaster"
googleAnalytics = "UA-123456-789"
pygmentsCodeFences = true
pygmentsUseClasses = true

		
[params]
  author = "Matheus Laidler"
  description = "Projeto que auxilia no aprendizado de conteúdos via divulgação científica, com materiais sobre o mundo da tecnologia e hacking."
  avatar = "/images/perfil.jpg" #or ../../images/perfil.jpg
  github = "matheuslaidler"
  facebook = "matheus.laidler"
  twitter = "matheuslaidler"
  linkedin = "laidlervidal"
  instagram = "matheuslaidler"
  #tumblr = "#"
  youtube = "@matheuslaidler" #/channel/UCkFbbZX6TG6eZPugmW32YFA/
  email = "matheuslaidler@protonmail.com"
  url = "https://matheuslaidler.github.io" #se não colocar ficará como o link do site raiz
  keywords = "matheus laidler, matheuslaidler, matheus-laidler, mlaidler, cibersegurança, wayofsecurity, wayofsec, road2tech, road2technology, acervo de TI, artigos, write ups, blog"
  rss = false
  lastmod = true
  favicon = "images/terminal.png"
  location = "Brazil"
  userStatusEmoji = "👽"
  enableGitalk = true
    
  [params.gitalk]
    clientID = "Your client ID" # Your client ID
    clientSecret = "Your client secret" # Your client secret
    repo = "LuvSia" # 您的博客的github地址Repository name，例如：xxxx.github.io
    owner = "ventusoon" # 您的GitHub ID
    admin = "ventusoon" # 您的GitHub ID
    id = "location.pathname" # 文章页面的链接地址就是ID
    labels = "gitalk" # Github issue labels. If you used to use Gitment, you can change it
    perPage = 15 # Pagination size, with maximum 100.
    pagerDirection = "last" # Comment sorting direction, available values are 'last' and 'first'.
    createIssueManually = true # 设置为true，如果是管理员登录，会自动创建issue，如果是false，需要管理员手动添加第一个评论(issue)
    distractionFreeMode = false # Enable hot key (cmd|ctrl + enter) submit comment.    
    proxy = "https://cors-anywhere.azm.workers.dev/https://github.com/login/oauth/access_token" # 可以自行添加反向代理
  
  [[params.links]] #um icone novo para algo - abaixo do perfil
    title = "Rascunhos"
    href = "https://matheuslaidler.gitbook.io"
	# icon = "images/icone.png" #sem nada => icone padrão de link => "/images/link.png"


  [frontmatter]
    lastmod = ["lastmod", ":fileModTime", ":default"]

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

## deploy.sh example

There are various way to deploy to github, here is a link to official [document](https://gohugo.io/hosting-and-deployment/hosting-on-github/).

Here is an sample. Note line 22 have `env HUGO_ENV="production"`, makes sure googleAnalysis is loaded during production, but is not loaded when we are testing it in localhost.

```bash
#!/bin/sh

if [ "`git status -s`" ]
then
    echo "The working directory is dirty. Please commit any pending changes."
    exit 1;
fi

echo "Deleting old publication"
rm -rf public
mkdir public
git worktree prune
rm -rf .git/worktrees/public/

echo "Checking out gh-pages branch into public"
git worktree add -B gh-pages public origin/gh-pages

echo "Removing existing files"
rm -rf public/*

echo "Generating site"
env HUGO_ENV="production" hugo -t github-style-remaster

echo "Updating gh-pages branch"
cd public && git add --all && git commit -m "Publishing to gh-pages (publish.sh)"

#echo "Pushing to github"
#git push --all
```

Then you can verify the site is working and use `git push --all` to push the change to github. If you don't want to check again every time, you can uncomment the `#git push --all` in the script.

## Credits

- MeiK2333 - Github Style
  
[![Github](https://img.shields.io/website?label=github+Repository&style=for-the-badge&url=https://github.com/MeiK2333/github-style)](https://github.com/MeiK2333/github-style)


- MLaidler - Github Style Remaster
  
[![Github](https://img.shields.io/website?label=github+Repository&style=for-the-badge&url=https://github.com/matheuslaidler/github-style-remaster)](https://github.com/matheuslaidler/github-style-remaster)

