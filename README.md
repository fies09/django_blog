1,下载安装redis
2,下载安装mysql
3,根据settings配置文件创建数据库
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.mysql', # 数据库引擎
            'HOST': '127.0.0.1', # 数据库主机
            'PORT': 3306, # 数据库端口
            'USER': 'root', # 数据库用户名
            'PASSWORD': 'fy961009', # 数据库用户密码
            'NAME': 'blog' # 数据库名字
        }
    }
    
create database blog charset = utf8;
create user 'user'@'%' IDENTIFIED by '123456'
grant all on blog.* to user@'%';
flush privileges；
4,更新应用数据库

python3 manage.py makemigrations

python3 manage.py migrate

5,创建超级管理员

python3 manage.py createsuperuser

6,运行项目

python manage.py runserver

7,admin管理员页面汉化:
setting中修改为:
LANGUAGE_CODE = ‘zh-Hans’

TIME_ZONE = ‘Asia/Shanghai’

8, 生成环境配置文件:
pipreqs ./ --encoding=utf8 --force
