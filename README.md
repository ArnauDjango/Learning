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
### Forms

> In general when the object as created the url take probleme beacause is no created route for the new element ! For resolve this you need to take redirection on models def

```
#blog>models.py
from django.urls import reverse
 
class [...]

  def get_absolute_url(self):
    return reverse('post_detail', args=[str(self.id)])
```

example in this setttings of post_detail in urls.py the pk is send to this url

```
path('post/<int:pk>/, BlogDetailView.as_view(), name='post_detail')
```

#### Forms delete
* Views
```
from django.views.generic.edit import DeleteView
from django.urls import reverse_lazy

class BlogDeleteView(DeleteView):
 model = Post
 template_name = 'post_delete.html'
 success_url = reverse_lazy('home')

```
### Account

* in settings.py you need redirect login and logout action

```
#config/settings.py
LOGIN_REDIRECT_URL = 'home'
LOGOUT_REDIRECT_URL = 'home'
```

* in config/urls.py
```
path('accounts', include('django.contrib.auth.urls')),
```

* For Log In you need to create the template. For the Log Out you nothing to do because it redirected in ``config/settings.py``
```
<!-- blog/templates/registration/login.html -->
{% extends 'base.html' %}
{% block content %}
 <h2>Log In</h2>
 <form method="post">
  {% csrf_token %}
  {{ form.as_p }}
  <button type="submit">Log In</button>
 </form>
{% endblock %}
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
