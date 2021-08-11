## 命令的使用

1. 切换用户 

   ```shell
   [shy@iZwz9hqwizo4t69d3za509Z ~]$ su root
   ```

   

2.  添加用户

   ```shell
   useradd
   ```

   

3. rz, sz命令

   ```shell
   rz：运行该命令会弹出一个文件选择窗口，从本地选择文件上传到服务器(receive)，即windows上传到linux服务器
   
   sz：将选定的文件发送（send）到本地机器，即从linux服务型下载到windows
   
   前提需要安装，命令如下
   yum install -y lrzsz
   
   rz命令上传文件乱码情况，通过vim /etc/locale.conf把LANG=XXX
   修改为LANG=zh_CN.UTF-8
   注意Centos7的字符集配置文件为/etc/locale.conf，如果是7之前的版本，应修改/etc/sysconfig/i18n，修改完之后记得reboot
   ```

4. ls -il

   获取文件和文件夹的节点号，多用于删除乱码文件，用例如下：

   ```shell
   [root@iZwz9hqwizo4t69d3za509Z /]# ls -il
   total 20
     135037 lrwxrwxrwx.   1 root root    7 Nov  3  2020  bin -> usr/bin
   50516461 dr-xr-xr-x.   5 root root 4096 May 21 11:39  boot
          3 drwxr-xr-x   19 root root 2880 Aug  9 19:19  dev
        132 drwxr-xr-x.  96 root root 8192 Aug  9 20:32  etc
   33793481 drwxr-xr-x.   2 root root    6 Aug  9 19:38  home
     135105 lrwxrwxrwx.   1 root root    7 Nov  3  2020  lib -> usr/lib
        148 lrwxrwxrwx.   1 root root    9 Nov  3  2020  lib64 -> usr/lib64
   50516465 drwxr-xr-x.   2 root root    6 Nov  3  2020  media
        149 drwxr-xr-x.   2 root root    6 Nov  3  2020  mnt
       8761 -rw-r--r--    1 root root    0 Aug  9 20:14 '?'$'\246\207\364\317''O'$'\234\323''?'$'\337\312\364\231''l9{a'$'\375''1'$'\254''i'$'\375''A'$'\347''C8'$'\377''V@'$'\370\300\213'
   16984995 drwxr-xr-x.   2 root root    6 Nov  3  2020  opt
   
   ```

   find ./ -inum 8761| xargs rm -rf   删除8761节点号的文件

5. mkdir 创建文件夹

   ```java
   mkdir java
   ```

6. nohup java -jar demo.jar >jarLog.txt &

7. lsof -i:8080查看8080端口占用

   ```shell
   [root@iZwz9hqwizo4t69d3za509Z java]# lsof -i:8080
   COMMAND   PID USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
   java    26442 root   17u  IPv6 134195      0t0  TCP *:webcache (LISTEN)
   ```

8. kill -9 pid 杀掉进程
9. service --status-all 查看正在运行的服务
10. 查看当前系统默认采用的字符集 命令：locale 或者echo $LANG