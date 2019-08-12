---
layout: post
author: Vincent
---

From the definition of Google:

> [Colaboratory](https://colab.research.google.com/) *is a research tool for machine learning education and research. It's a Jupyter notebook environment that requires no setup to use. With Colaboratory you can write and execute code, save and share your analyses, and access powerful computing resources, all for free from your browser.*

Do you want to know more about Google Colab ? Check their [FAQ](https://research.google.com/colaboratory/faq.html)


## Mount Google Drive

Mounting Google Drive means that you'll be able to use the storage you have from your Google Drive to store and access files of your project.

```python
from google.colab import drive
drive.mount('/content/gdrive')
```

Google should print this line as output :

> Go to this URL in a browser: https://account.google.com/...

Click on the link, agree the terms and then copy paste the authorization code on Google Colab.

Change your current directory:

```python
import os
os.chdir("/content/gdrive/My Drive/path_to_project")
os.listdir()
```

## Useful commands

```python
!pip install scipy==1.0.0
```

Which version of Python is installed :

```python
!python --version
```

Package's details :

```python
!pip show scipy
```

Show a syntax-highlighted file through a pager :

```python
%pycat /content/gdrive/My\ Drive/myfile.py
```
