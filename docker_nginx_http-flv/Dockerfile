# 指定镜像
FROM ubuntu:20.04
# 支持中文
ENV LANG="C.UTF-8"
# 设置时区, 以防某些软件需要确定时区
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && \
    echo "$TZ" > /etc/timezone
    
# 安装ssh并设置自动启动脚本
COPY install_ssh write_ssh \
     /root/
RUN cat /root/install_ssh | bash && \
    rm -rf /root/install_ssh

# 安装cmake
COPY ./depend_file/cmake-3.28.3.tar.gz \
     install_cmake \
     /root/
RUN cat /root/install_cmake | bash && \
    rm -rf /root/install_cmake

# 需要安装cmake
# 安装nginx_http-flv内核
COPY ./depend_file/nginx-1.24.0.tar.gz ./depend_file/nginx-http-flv-module-1.2.11.tar.gz ./depend_file/nginx_http-flv.conf \
     write_nginx_http-flv_setting install_nginx_http-flv \
     /root/
RUN cat /root/install_nginx_http-flv | bash && \
    rm -rf /root/install_nginx_http-flv
