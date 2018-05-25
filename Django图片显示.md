Django 图片无法显示问题
=====================
# Step 1:
    在setting.py的最后补充下面的代码
    STATIC_ROOT = os.path.join(BASE_DIR, 'static')
# Step 2:
    建立static文件夹、static文件夹与template文件夹同级
    相对路径 i.e. my_app/static/my_app/example.jpg
# Step 3:
    运行 python manage.py collectstatic
# Step 4:
    在HTML文件中用下面的代码载入资源图片
    {% load static %}
    <img src="{% static "my_app/example.jpg" %}" alt="My image"/>
