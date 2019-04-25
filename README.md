# django_rest_swagger_tutorial

django rest swagger framework tutorial

基于[django_rest_tutorial](https://github.com/zhusheng/django_rest_tutorial)进行迭代。

swagger框架你可以理解为一个装饰器，把我们的rest框架包装的更加好看、好用。

## 配置swagger框架

授权部分，在rest框架部分已经做了，这里我们补充一些swagger框架提供的授权即可。

- 安装
`pip install django-rest-swagger`

- 添加到settings.py中

INSTALLED_APPS = [
    ...
    'rest_framework_swagger',
    ...
]

- 修改主urls.py文件

```python
# swagger
from rest_framework_swagger.views import get_swagger_view

schema_view = get_swagger_view(title='API')

urlpatterns = [
    path('docs/', schema_view),
]
```

- 在settings.py文件中增加如下代码

```python
LOGIN_URL = 'rest_framework:login'
LOGOUT_URL = 'rest_framework:logout'
```

运行效果图如下：
![image](https://raw.githubusercontent.com/zhusheng/blog/master/django/08.png)