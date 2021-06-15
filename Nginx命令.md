# Nginx命令

## 基础命令

- `cat + 文件名` 查看文件内容(不可修改内容)

- `vi + 文件名` 查看文件内容（可修改内容）

- `vim + 文件名` 查看文件内容（可修改内容）

- 修改文件

  ```tex
  1、在vi或者vim查看下
  2、insert在光标位置修改内容
  3、修改完成以后 shift+: 输入保存命令
  4、wq保存或者wq!强制保存
  ```

- nginx重启命令

  ```tex
  1、sudo nginx -t 检查nginx语法
  2、sudo nginx -s reload 重启nginx
  ```

## [nginx配置systemctl](https://www.cnblogs.com/wang-yaz/p/11350013.html)

一. 配置systemctl之前的启动方式

进入sbin目录下执行以下命令：

```tex
1 启动nginx的命令为     /usr/local/nginx/sbin/nginx 
2 停止nginx的命令为    /usr/local/nginx/sbin/nginx -s stop
3 重启nginx的命令为    /usr/local/nginx/sbin/nginx -s reload
```

二. 配置systemctl之后的启动方式

```tex
systemctl status nginx 查看nginx

systemctl start nginx 启动nginx

systemctl stop nginx 停止nginx

systemctl restart nginx 重启nginx
```

三. 配置方法

1.  创建一个nginx.service

    在 /usr/lib/systemd/system/目录下面新建一个nginx.service文件。并赋予可执行的权限

    vim /usr/lib/systemd/system/nginx.service

    chmod +x /usr/lib/systemd/system/nginx.service

2. 编辑service内容

   ```tex
   [Unit]                                                                                      //对服务的说明
   Description=nginx - high performance web server              //描述服务
   After=network.target remote-fs.target nss-lookup.target   //描述服务类别
   
   [Service]                                                                                 //服务的一些具体运行参数的设置
   Type=forking                                                                         //后台运行的形式
   PIDFile=/usr/local/nginx/logs/nginx.pid                               //PID文件的路径
   ExecStartPre=/usr/local/nginx/sbin/nginx -t -c /usr/local/nginx/conf/nginx.conf   //启动准备
   ExecStart=/usr/local/nginx/sbin/nginx -c /usr/local/nginx/conf/nginx.conf           //启动命令
   ExecReload=/usr/local/nginx/sbin/nginx -s reload                                                 //重启命令
   ExecStop=/usr/local/nginx/sbin/nginx -s stop                                                       //停止命令
   ExecQuit=/usr/local/nginx/sbin/nginx -s quit                                                        //快速停止
   PrivateTmp=true                                                                  //给服务分配临时空间
   
   [Install]
   WantedBy=multi-user.target                                               //服务用户的模式
   ```

3. 启动服务

   ```
   在启动服务之前，需要先重载systemctl命令
   systemctl daemon-reload
   systemctl start nginx.service
   ```

## 跨域设置

```tex
#允许跨域请求的域，* 代表所有
add_header 'Access-Control-Allow-Origin' '*';
#允许请求的header
add_header 'Access-Control-Allow-Headers' *;
#允许带上cookie请求
add_header 'Access-Control-Allow-Credentials' 'true';
#允许请求的方法，比如 GET,POST,PUT,DELETE
add_header 'Access-Control-Allow-Methods' *;
```

