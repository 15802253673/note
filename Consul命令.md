# Consul命令

- `consul -v` 查看版本

- 启动创建节点和数据中心名

  ```shell
  dev模式启动（临时启动，无存储文件）
  consul agent -dev
  consul agent -dev -node mynode -datacenter mydc
  
  server启动方法一（本地存储文件）
  consul agent -server -bootstrap  -ui -node mynode -datacenter mydc -data-dir=/usr/data/consul_data
  
  server启动方法二（本地存储文件）
  -bind 绑定本地IP
  -client 对外连接IP（不指定默认是localhost或者1270.0.1访问）
  consul agent -server -bootstrap -bind 192.168.173.40 -client 192.168.173.40 -ui -node mynode -datacenter mydc -data-dir=D:/consul_data
  ```

- `consul kv`  属性

- `consul kv put key value` 存储key value

- `consul kv get key` 获取value









