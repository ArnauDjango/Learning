# Learning
## Django Memento

### Configurations

#### templates
```
# config/settings.py
TEMPLATES = [
{
...
'DIRS': [str(BASE_DIR.joinpath('templates'))], # new
...
},
]
```

#### static

```
# config/settings.py
STATIC_URL = '/static/'
STATICFILES_DIRS = [str(BASE_DIR.joinpath('static'))] # new

```

## GitHub Memento

### First commit 

```
git init
git config --global user.name "Arnaud"
git config --global user.email web@arnaudjango.fr
git status 
git add .
git commit -m "My first commit !"
git remote add origin https://github.com/arnaudjango/zesite.git
git push -u origin master
```
