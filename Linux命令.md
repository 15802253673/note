# Linux命令

## 常用命令

* `copy` 复制文件

  ```reStructuredText
   将包整体上传到bankApi的common下
   copy eft-bank-api-icbtarget\bank_icbc.jar D:\common\bank_icbc.jar
  ```

* `mkdir 文件夹名` 创建文件夹

* `rm -rf 文件名 ` 删除文件

* `mv ` 移动

  ```reStructuredText
  将文件移动到指定目录底下，也可以移动时修改文件名相当于修改文件名称
  mv bank_abc.jar ../abc/bank_abc.jar
  ```

* `mv bank_abc.jar bank_abc.jar.abt ` 修改文件名称

* `java -jar` 启动jar包

* ```reStructuredText
  nohup java -jar bank_jar --spring.profile.test --server.port=38001
  ```

* `ls -als` 所有文件

* `ll -als` 所有文件

* `sz 文件名` 下载文件

* `rz` 上传文件

* `ps -ef|grep 文件名` 搜索文件并显示信息

* `kill -9 进程号` 杀死进程

* `su - root` 切换账号

* `sudo -s` root用户切换

* `lsof -i:端口号` 查看端口号信息

* 查看端口命令

  ```tex
  1、netstat -a 查看所有端口
  2、netstat -tunlp 查看端口占用情况
  3、netstat -tunlp|grep + 端口号  查看某端口占用情况
  4、netstat -ntlp|grep + 端口号  查看某端口占用情况
  ```

* `tial -f nohup.out` 查看启动日志

* `sh start.sh` 启动.sh启动脚本命令

* `cat + 文件名` 查看文件内容(不可修改内容)

* `vi + 文件名` 查看文件内容（可修改内容）

* `vim + 文件名` 查看文件内容（可修改内容）

* 修改文件

  ```tex
  1、在vi或者vim查看下
  2、insert在光标位置修改内容
  3、修改完成以后 shift+: 输入保存命令
  4、wq保存或者wq!强制保存
  ```

## 操作数据库

1. `mysql -ufins -p` mysql登录用户命令(fins为用户)
2. `Fins_123456`  登录密码
3. `show databases;` 显示所有库名
4. `use financial;` 指定使用库
5. 执行sql