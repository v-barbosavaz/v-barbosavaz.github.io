---
layout: post
author: Vincent
---

In this tutorial, I will guide you through the process of quickly creating your portfolio/blog using [GitHub Pages](https://pages.github.com/).

> *GitHub Pages is a static site hosting service designed to host your personal, organization, or project pages directly from a GitHub repository.*

[GitHub](https://github.com/) initially is a web-based platform for version control using [Git](https://git-scm.com/). Developers can collaborate on open-source projects, share ideas and more.

## Create your first GitHub Pages

GitHub created great tutorials to start with GitHub Pages:
- [Create a repo](https://pages.github.com/)
- [Blog with Jekyll](https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages/)

A tutorial to master Jekyll:
- [How to use Jekyll](https://jekyllrb.com/docs/step-by-step/01-setup/)

I used them to create mine. I propose a condensed tutorial for those who do not like documentation.

### Create a GitHub account and a new repository

Get a [GitHub](https://github.com/) account beforehand, if you don’t have it yet. Create a [new repository](https://github.com/new) named *username.github.io*, where *username* is your username on GitHub. For instance, if your GitHub username is *vincent*, then your repository name would be *vincent.github.io*. Click on *Create repository*.

### Create a local copy on your computer

1. Open Terminal (CMD Windows)
2. Change the current working directory to the location where you want to store your project

```bash
cd directory
```

3. Type *git clone URL*, where *URL* is the clone URL for the repository. Press Enter.

```bash
git clone https://github.com/username/username.github.io
```

### Home page and Jekyll theme

In the terminal, enter the project folder and add *index.html*, *_config.yml* files:

```bash
cd username.github.io
touch index.html
touch _config.yml
```

Copy paste in *index.html*:

```html
---
layout: default
title: Username
---
<h1>Welcome to my GitHub Pages</h1>
```

Copy paste in *_config.yml*:

```text
theme: jekyll-theme-cayman
title: Username
description: Description
```

### Publish changes

In the terminal:

```bash
git add --all
git commit -m "Initial commit"
git push -u origin master
```

## Advanced techniques

### Change theme

GitHub Pages supports a list of themes that can be found here:

[GitHub Pages themes](https://pages.github.com/themes/)

Jekyll themes:

[Jekyll themes](https://jekyllthemes.io/)

## Conclusion

There you go, you should now see your brand new personal web page hosted on your GitHub.

Open your favorite navigator and see the magic: https://github.com/username/username.github.io
