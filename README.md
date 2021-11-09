# rs+node_course



## node
### 包（package）
- 将多个模块组合为一个完整的功能，就是一个包
- 包结构
    bin
        - 二进制的可执行文件，一般都是一些工具包中才有
    lib
        - js文件
    doc
        - 文档
    test
        - 测试代码
    package.json
        - 包的描述文件
    
- package.json	
    - 它是一个json格式的文件，在它里面保存了包各种相关的信息
        name 包名
        version 版本
        dependencies 依赖
        main 包的主要的文件
        bin 可执行文件
            
### npm（Node Package Manager node的包管理器）
- 通过npm可以对node中的包进行上传、下载、搜索等操作
- npm会在安装完node以后，自动安装
- npm的常用指令
    npm -v 查看npm的版本
    npm version 查看所有模块的版本
    npm init 初始化项目（创建package.json）
    npm i/install 包名 安装指定的包
    npm i/install 包名 --save 安装指定的包并添加依赖
    npm i/install 包名 -g 全局安装（一般都是一些工具）
    npm i/install 安装当前项目所依赖的包
    npm s/search 包名 搜索包	
    npm r/remove 包名 删除一个包
        

文件系统（File System)
在Node中，与文件系统的交互是非常重要的，服务器的本质就将本地的文件发送给远程的客户端
• Node通过fs模块来和文件系统进行交互
• 该模块提供了一些标准文件访问API来打开、读取、写入文件，以及与其交互。
• 要使用fs模块，首先需要对其进行加载
– const fs = require("fs");



- Buffer（缓冲区）
    - Buffer和数组的结构的非常类似，Buffer是用来存储二进制数据的
    - Buffer的方法
        - Buffer.from(字符串)
            - 将一个字符串中内容保存到一个buffer中
        - buf.toString()
            - 将buffer转换为一个字符串
        - Buffer.alloc(size)
            - 创建一个指定大小的buffer对象
        - Buffer.allocUnsafe(size)
            - 创建一个指定大小的buffer对象，可以包含敏感数据
				
	
- fs模块

- 在Node通过fs模块来对系统中的文件进行操作，fs模块是node中已经继承好了，不需要在使用npm下载，直接引入即可

- 引入fs
	var fs = require("fs");
	
- fs模块中的大部分操作都提供了两种方法，同步方法和异步方法
	同步方法带sync
	异步方法没有sync，都需要回调函数
	
- 同步和异步调用
  - fs模块中所有的操作都有两种形式可供选择同步和异步。
  - 同步文件系统会阻塞程序的执行，也就是除非操作完毕，否则不会向下执行代码。
  - 异步文件系统不会阻塞程序的执行，而是在操作完成时，通过回调函数将结果返回。

- 写入文件
	1.同步写入
	2.异步写入
	3.简单写入
	4.流式写入
	
- 读取文件
	1.同步读取
	2.异步读取
	3.简单读取
	4.流式读取
	
- 打开状态
  
	| 模式 | 说明                                                  |
	| ---- | ----------------------------------------------------- |
	| r    | 读取文件 , 文件不存在则出现异常                       |
	| r+   | 读写文件 , 文件不存在则出现异常                       |
	| rs   | 在同步模式下打开文件用于读取                          |
	| rs+  | 在同步模式下打开文件用于读写                          |
	| w    | 打开文件用于写操作 , 如果不存在则创建，如果存在则截断 |
	| wx   | 打开文件用于写操作, 如果存在则打开失败                |
	| w+   | 打开文件用于读写, 如果不存在则创建, 如果存在则截断    |
	| wx+  | 打开文件用于读写, 如果存在则打开失败                  |
	| a    | 打开文件用于追加, 如果不存在则创建                    |
	| ax   | 打开文件用于追加, 如果路径存在则失败                  |
	| a+   | 打开文件进行读取和追加, 如果不存在则创建该文件        |
	| ax+  | 打开文件进行读取和追加,如果路径存在则失败             |
	
	
	
- 方法
	- 打开文件
		fs.open(path, flags[, mode], callback)
		fs.openSync(path, flags[, mode])
		
	- 读写文件
		fs.write(fd, string[, position[, encoding]], callback)
		fs.writeSync(fd, string[, position[, encoding]])
		
		fs.read(fd, buffer, offset, length, position, callback)
		fs.readSync(fd, buffer, offset, length, position)
		
	- 关闭文件
		fs.close(fd,callback)
		fs.closeSync(fd);
		
	- 简单文件读取和写入
		fs.writeFile(file, data[, options], callback)
		fs.writeFileSync(file, data[, options])
		
		fs.readFile(path[, options], callback)
		fs.readFileSync(path[, options])
		
	- 流式文件读取和写入
		- 流式读取和写入适用于一些比较大的文件
			fs.createWriteStream(path[, options])
			fs.createReadStream(path[, options])
			
			
			
			
			
			
			
			
			
			
			
			
