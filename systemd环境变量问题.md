在 ```docker run``` 的时候配了几个环境变量，服务是用docker内的systemd启动的，启动后发现服务拿不到环境变量，看了看网上的资料，记录一下。     

systemd 是一号进程，不会去读 profile bashrc 这些文件,所以要么指定 systemd 的 conf 文件添加环境变量，要么在服务的启动配置里加环境变量。    

最好还是在服务的启动配置里加环境变量 [Service] 下添加 ```Environment=[env name]=[env value]```. 添加到 systemd 的 conf 里还得重启 systemd，非常麻烦. 


