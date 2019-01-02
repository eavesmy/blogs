# 项目结构
### Project
```
	|- app.js Gateway 	启动文件
	|- libs 			项目底层工具
		|- net.js 		http、tcp 服务器及客户端
		|- db.js 		mysql、redis、mongodb 等db链接工具
		|- config.js 	配置读取工具
		|- package.js	网络包处理
	|- components 		依赖组件 ( Client 发来的数据依次通过组件进行处理 )
	|- modules 			RPC服务器
		|- app.js 		启动文件
		|- routes.js 	路由
		|- handler		具体处理逻辑
	|- node_modules 	nodejs依赖
	|- datas 			协议包
		|-sources 		未编译的 protobuf 包
		|-packages 		编译后的 js 网络包
	|- codes			状态码
```
## TODO : 
- 写 tcp & http 客户端
- 将代码扔到生成目录中
- 重新跑一遍生成
- 写db，测试db
- 导入proto包，生成
- 可以先进场景，剩下的慢慢填补
- services 保存 路由
- gate 定时读写配置
