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
