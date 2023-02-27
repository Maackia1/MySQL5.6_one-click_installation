## 简单喵喵两句：

+ ##### MySQL 官网下载地址：[MySQL 官网](https://downloads.mysql.com/archives/installer/)

+ ##### 本版本由 [阿发你好](https://www.afanihao.cn) 制作，在 mysql-5.6.39-winx64.zip 文件的基础上稍做改动，简化了安装过程

+ ##### 此数据库默认密码为空，初次登录可在 SQLyog 等工具直接登陆后，再执行 "修改root密码.sql" 文件，即可生成密码：123456。

+ ##### 不建议使用 MySQL 命令行操作，建议使用本文档附带的 SQLyog 或其它图形化工具。


---


### `Ⅰ.` 文档说明【稍作了解即可】


+ `1.`  作者删除了一些目录，如 docs，include...等，其中 lib 目录有 800 MB 大小，但是这并不会影响运行
+ 
	+ ![1](https://user-images.githubusercontent.com/95027227/219694706-038322ac-eab5-4a46-9bdc-b4e4b40adad7.png)


+ `2.` 添加了一些配置文件，仅需了解即可

~~~
 "my-default.ini" 是原有的一个参考文件
 
 "my.ini" 是自建的文件, 它是 MySQL 的配置文件, 里面已经添加了一些常用配置
 
 注意：MySQL的意思是让我们根据 my-default.ini 来创建一个自己的配置文件
~~~


+ `3.` 快捷脚本使用，选中要执行的脚本，右键以管理员身份运行即可
+
	+ ![2](https://user-images.githubusercontent.com/95027227/219694709-6cde4e21-d2ce-4f27-bd97-313fe66fb51a.png)


+ `4.` 更改 MySQL 数据库密码的 SQL 命令如下，如需更改，替换数字 " 123456 " 并在 SQLyog 或其它工具中执行即可

```
GRANT ALL PRIVILEGES ON *.* TO 'root'@'127.0.0.1' IDENTIFIED BY '123456' WITH GRANT OPTION;
GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' IDENTIFIED BY '123456' WITH GRANT OPTION;
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY '123456' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```


***


### `Ⅱ.` 安装过程如下：


+  `1.` 下载 "MySQL5.6 免安装版 (64bit).zip" 文件后，建议将文件夹放在根目录下，如：D:\\MySQL
+ 
	+ ![3](https://user-images.githubusercontent.com/95027227/219694713-4ff34501-8b93-4a53-a8e6-c7ec13b52d21.png)


+  `2.`  解压之后，可以看到后缀名为 ".cmd"文件，右键 "以管理员身份" 运行 "安装MySQL服务器.cmd" 文件即可完成安装。
+ 
	+ ![4](https://user-images.githubusercontent.com/95027227/219694722-9c94ab52-8c45-44b2-9e3d-796103abc92c.png)


+  `3.`  弹出如下图所示窗口即为成功。
+ 
	+ ![5](https://user-images.githubusercontent.com/95027227/219694727-dcefc844-3733-45f8-b653-f12b51240d87.png)


***

### `Ⅲ.` 验证过程如下：


+  `1.` .使用快捷组合键：【Win + R】，接着在命令框中输入：services.msc
+ 
	+ ![6](https://user-images.githubusercontent.com/95027227/219694733-fa116d38-a9be-4d2c-bc59-6474d142fe9f.png)


+  `2.`  在服务窗口中可以看到 MySQL 服务已经正常启动
+ 
	+ ![7](https://user-images.githubusercontent.com/95027227/219694738-96473a6c-da72-45e5-9fcf-997510f36a53.png)


***


### `Ⅳ.` 初次登录及修改密码：


+  `1.`  此数据库默认初始密码为空，**初次使用 SQLyog 工具登录 MySQL 数据库时无需密码**
+ 
	+ ![8](https://user-images.githubusercontent.com/95027227/219694743-2ef0ece0-f4ec-4431-8615-cfad4673faad.png)


+  `2.`  **注意：读者请务必执行这一步**，在 sqlyog 等图形化工具执行 "修改root密码.sql" 文件或直接粘贴下一步的代码，文件默认密码为：123456。
+ 
	+ ![9](https://user-images.githubusercontent.com/95027227/219694745-9437cbb0-185e-4b8a-bc0d-d16eb0ab77eb.png)


+  `3.`  若需更改数据库密码，可将数字：" 123456 " 替换为所需密码，如：a1b2c3

```
GRANT ALL PRIVILEGES ON *.* TO 'root'@'127.0.0.1' IDENTIFIED BY 'a1b2c3' WITH GRANT OPTION;
GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' IDENTIFIED BY 'a1b2c3' WITH GRANT OPTION;
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'a1b2c3' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```


+  `4.`  再次链接则需要密码才能成功登录
+ 
	+ ![10](https://user-images.githubusercontent.com/95027227/219694751-b6081550-64b4-460a-bc95-ea1cfc6706e3.png)

***

### `Ⅴ.` 卸载过程如下：


+  `1.`  可以使用 [Geek Uninstaller 卸载软件](https://geekuninstaller.com/download) 先卸载 SQLyog 等图形化工具

+  `2.` 接着卸载此版本的 MySQL 5.6，右键管理员身份运行 " 卸载MySQL服务.cmd " 即可
+ 
	+ ![11](https://user-images.githubusercontent.com/95027227/219694757-22d36347-39ce-41a3-885f-5e5f6cfb7d45.png)

+  `3.`  在执行完后，使用快捷键【 Win + R 】输入：regedit，打开注册表，使用快捷键【 Ctrl + F 】输入 MySQL，并将找到的 MySQL 文件删除

	+ 一般为这三个路径（可能有所不同，以读者本身计算机为准，删除即可）

```
HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Eventlog\Application\MySQL
HKEY_LOCAL_MACHINE\SYSTEM\ControlSet002\Services\Eventlog\Application\MySQL
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Eventlog\Application\MySQL
```

+  `4.` 删除读者安装在计算机中的 MySQL 文件夹，如：D:\\MySQL

+  `5.` 重启计算机

***

### `Ⅵ.` 其它事项：


#### `一`. 安装及卸载问题

+ 先检查 MySQL 存放路径是否有中文、空格等特殊字符，请尽量使用无空格的路径。

+ 在本文档之前使用过安装版 MySQL 进行安装/卸载，**但在 安装 / 卸载 的过程中失败**，本文档 **建议读者直接重装系统**


#### `二`. 报错问题

+  `1.`  右键管理员身份运行 " 运行MySQL服务.cmd " 会报错，错误代码如下。
	+ ps：但在 SQLyog 工具使用并无影响，可能是小 bug ... 希望有大佬给予解答！  

```
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: NO)
请按任意键继续. . .
```
+ 
	+ ![12](https://user-images.githubusercontent.com/95027227/219694761-8e0a331e-8ee1-4a40-a554-10ff00e27ace.png)
