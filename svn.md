---
title: "svn"
tags: ""
---

# SVN

Checkout: Get copy of project from remote repository: 

```bash
 svn checkout URL_REPOSITORI
 
 # Alias
 svn co URL_REPOSITORI
```

Get the URL of the directory you are in, as well as the Repository Root and other info by running the following command in any of the checked out directories:

 ```bash
 svn info
 
 #Returns only the URL of the repository
 svn info --show-item repos-root-url
 ```
