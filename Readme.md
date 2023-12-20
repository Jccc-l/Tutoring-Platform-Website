# 家教网站

## (1)启动数据库(MySQL 5.7)
net start mysql  # 启动mysql  
mysql -u mysql -p # 登录mysql
### 首次使用，创建 python_jiajiao 数据库
mysql> CREATE DATABASE IF NOT EXISTS python_jiajiao DEFAULT CHARSET utf8 COLLATE utf8_general_ci;
### 创建管理员命令： 账号密码admin111
insert into b_user(username,password,role,status) values('admin111',md5('admin111'),1,'0');

## (2)后端启动(安装python 3.8)
### 配置环境: server目录下，执行> pip install -r requirements.txt
### 启动django服务，进入server目录下，执行> 
python manage.py runserver

## (3)后端启动
(安装和配置node 16, 不换源npm install可能不成功)  
https://nodejs.org/download/release/v16.20.2/  
https://zhuanlan.zhihu.com/p/649370532  
### 安装依赖: 进入web目录下，执行> 
npm install 
### 运行项目: 进入web目录下，执行> 
npm run dev

## 初始配置:
### (1)前端连接后端地址 web/src/store/constants.ts  
默认地址: const BASE_URL = 'http://127.0.0.1:8000'  
### (2)迁移数据库表, server目录下，执行>
python manage.py makemigrations;  
python manage.py migrate;  
python manage.py makemigrations myapp;  
python manage.py migrate myapp;  