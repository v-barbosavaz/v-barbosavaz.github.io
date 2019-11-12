---
layout: post
author: Vincent
---

A guide covering the basics of setting up a development environment on macOS.

## Xcode

Xcode is an integrated development environment (IDE) for macOS containing a suite of software development tools developed by Apple.

Download and install Xcode from the [App Store](https://apps.apple.com/fr/app/xcode/id497799835?mt=12) or from Apple's [website](https://developer.apple.com/xcode/).

### Command Line Tools

The Command Line Tools package gives Mac terminal users many commonly used tools, utilities, and compilers, including make, GCC, clang, git, cpp and many other useful commands that are usually found in default linux installations.

Install Command Line Tools through terminal:

```bash
xcode-select --install
```

## Homebrew

Homebrew is a free and open-source software package management system that simplifies the installation of software on Apple's macOS operating system and Linux.

Install Homebrew through terminal (Homebrew depends on Apple’s Xcode package: **Command Line Tools**):

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

From: [https://brew.sh](https://brew.sh/)

To confirm Homebrew installed correctly:

```bash
brew doctor
```

## Python

```bash
brew install python
```

### Alias

If you run these commands you'll see that the command "python" points to the default macOS version of Python. You shouldn't use it to develop Python projects.

```bash
python -V
which python
```
```
Python 2.7.16
/usr/bin/python
```

One could type **python3** instead of **python** to use the Homebrew installed Python version. A lazier option is use aliases.

We want to point an alias to the copy of Python that Homebrew manages. To find the path to where Homebrew installed Python run this following command:

```bash
brew info python
```

To create the alias:

```bash
alias python=/usr/local/bin/python3
```

To confirm alias works:

```bash
python -V
which python
```
```
Python 3.7.5
python: aliased to /usr/local/bin/python3
```

## Anaconda

Find the Anaconda bin folder.

```
/Users/vincent/opt/anaconda3/bin
```
```bash
export PATH="/Users/vincent/opt/anaconda3/bin:$PATH"
```

Now you should be able to use conda command.

## Java

Download the last JDK (Java Development Kit):

https://www.oracle.com/technetwork/java/javase/downloads/index.html

## Scala

Install Scala either by installing an IDE such as IntelliJ, or **sbt**, Scala's build tool.

https://www.scala-lang.org/download/

```bash
brew update
brew install sbt
```

### ScalaFX

http://www.scalafx.org/docs/quickstart/

My advice is to clone the Hello World ScalaFX project (especially for the build.sbt file):

https://github.com/scalafx/scalafx-hello-world

## R

1. Go to: https://www.r-project.org/
2. Click on the "download R" [link](https://cran.r-project.org/mirrors.html)
3. Select a mirror site (ex: USA https://cran.cnr.berkeley.edu/)
4. Click on the "Download R for (Mac) OS X" link
5. Click on the .pkg file under *Latest release* section
6. Install R

### RStudio

https://rstudio.com/

## Bonus

### Night Shift

https://support.apple.com/fr-fr/HT207513

Alternative: F.lux https://justgetflux.com/

### Gimp

https://www.gimp.org/downloads/

### Inkscape

https://inkscape.org/

### Latex

1. Go to: https://www.latex-project.org/
2. Click on "get" [link](https://www.latex-project.org/get/)
3. Click on "MacTeX" [link](http://www.tug.org/mactex/mactex-download.html) under Max OS
