### obs推流

1. 前往[官网](https://obsproject.com/)下载安装obs

2. 新建场景

   ![image-20240507103229310](https://github.com/WHHHHHHHY/Linux_http-flv_nginx_why/blob/main/photo/image-20240507103229310.png?raw=true)

3. 添加设备, 使用摄像头或显示器直播

   ![image-20240507103432845](https://github.com/WHHHHHHHY/Linux_http-flv_nginx_why/blob/main/photo/image-20240507103432845.png?raw=true)

4. 设置直播推流. $\textcolor{red}{注意!}$, 9处的推流码需要自行设置(不要设成Lenovo, 不然和我的设备冲突, 且最好不要设置成奇奇怪怪的字符, 大小写英文字母就行)

   ![image-20240507103851664](https://github.com/WHHHHHHHY/Linux_http-flv_nginx_why/blob/main/photo/image-20240507103851664.png?raw=true)

5. 设置输出格式, 编码器最好和我一样吧, 其他不一样也行

   ![image-20240507104525700](https://github.com/WHHHHHHHY/Linux_http-flv_nginx_why/blob/main/photo/image-20240507104525700.png?raw=true)

6. 推流, 可以在浏览器输入`http://192.168.134.154:port2/stat`查看直播推流, 最好按`F12`勾上`Disable cache`再刷新, 不然可能刷新不出来

   ![image-20240507105525390](https://github.com/WHHHHHHHY/Linux_http-flv_nginx_why/blob/main/photo/image-20240507105525390.png?raw=true)

   ![image-20240507105400694](https://github.com/WHHHHHHHY/Linux_http-flv_nginx_why/blob/main/photo/image-20240507105400694.png?raw=true)

### VLC拉流

1. 前往[官网](https://www.videolan.org/vlc/)下载VLC

2. 点击网络串流

   ![image-20240507105914358](https://github.com/WHHHHHHHY/Linux_http-flv_nginx_why/blob/main/photo/image-20240507105914358.png?raw=true)

3. 输入url, `http://192.168.134.154:port2/live?port=20002&app=http-flv&stream=Lenovo`该处的`Lenovo`换成你上述输入的, 点击播放

   ![image-20240507110005353](https://github.com/WHHHHHHHY/Linux_http-flv_nginx_why/blob/main/photo/image-20240507110005353.png?raw=true)
