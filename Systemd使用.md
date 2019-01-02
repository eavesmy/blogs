## 介绍:
Wiki: [https://en.wikipedia.org/wiki/Systemd](https://en.wikipedia.org/wiki/Systemd)    
作为目前大部分Linux发行版内置的一号进程, Systemd 非常值得学习。    
与之配套的日志管理为 [Journalctl](https://www.freedesktop.org/software/systemd/man/journalctl.html)    
在使用 systemd 启动进程之前，需要编写配置文件。

## 配置文件
- 用户编写的配置文件放入该目录下:     
``` /usr/lib/systemd/system/   ```
- 系统的一些配置文件在:
``` /etc/systemd/system/ ```
    
在编写配置文件后，使用 ``` systemctl daemon-reload ``` 更新配置文件，systemd 会自动将 ``` /usr/lib/systemd/system/ ``` 里的文件加软链，指向 ```/etc/systemd/system/``` 里。

## 常用命令
- 启动进程  ```systemctl start [service] ```
- 重启进程  ```systemctl restart [service] ```
- 停止进程  ```systemctl stop [service] ```
- 查看进程状态  ```systemctl status [service] ```
- 查看某进程日志 ```journalctl -u [service] ``` 加上 ```-f```参数可以像 tail 一样实时输出。

## 配置文件
配置文件里有以下三个常用的title,具体配置方法参考[man](https://jlk.fjfi.cvut.cz/arch/manpages/man/systemd.service.5),这里介绍的比较全。或者网上搜索，有很多。
```
[Unit]
[Service]
[Install]
```
## 远程
对，没错，systemctl 可以远程管理进程，```systemctl status [service] -H user@host```,只要user有root权限就可以，当然要保证靶机启动了 sshd 服务。    
借用 systemctl 可以实现多机器进程的管理，搭个后台做进程管理方便多了。

## Supervisor
supervisor 也是一个进程管理软件，功能也很强大，但总的来说还是 systemd 更加稳定、功能丰富。
