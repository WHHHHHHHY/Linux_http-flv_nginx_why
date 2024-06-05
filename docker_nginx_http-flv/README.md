## 2024.06.05

### 利用Linux, 我能够搭建流媒体服务器

- 启动服务器

  ```sh
  cd Linux_http-flv_nginx_why
  # 此处的imname和imversion换成自己希望的名称
  docker build -f Dockerfile -t imname:imversion .
  # 20000为ssh登录端口, 初始用户为root, 初始密码为set_your_root_passwd
  # 20001为nginx代理界面
  # 20002为rtmp代理端口
  docker run \
  -p port1:20000 -p port2:20001 -p port3:20002 \
  --name http-flv_contain \
  --hostname http-flv \
  --restart=always \ 容器自动启动
  -itd imname:imversion
  ```

- 配置文件

  修改root密码

  ```shell
  # write_ssh
  # 设置root密码
  echo -e 'root:set_your_root_passwd' | chpasswd
  # 将set_your_root_passwd改成你希望的密码
  ```

- 测试

  在`Dell Inspiron 5447`上经测试可成功运行

  在`RaspberryPi5`上经过测试可成功运行