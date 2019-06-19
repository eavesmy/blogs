#### 1. 在 mysqld 的配置文件中添加 ``` skip-grant-tables ```。
#### 2. 重启 mysqld ``` sudo systemctl restart mysql ```。
#### 3. 无需密码，直接使用 mysql 登录,进入后修改密码,     
```
> use mysql;
> update from user set authentication_string = password("new pwd") where user = 'root';
> flush privileges;
```
#### 4. 然后退出，把配置文件里的那行 ``` skip-grant-tables ``` 删除掉，重启 mysqld 服务 ``` sudo systemctl start mysql ``` 即可。
