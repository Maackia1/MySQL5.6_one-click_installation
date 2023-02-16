## 简单喵喵两句：

+ ##### MySQL 官网下载地址：[MySQL 官网](https://downloads.mysql.com/archives/installer/)

+ ##### 本版本由发哥制作，在 mysql-5.6.39-winx64.zip 文件的基础上稍做改动，简化了安装过程，邵发老师的个人网站：[阿发你好](https://www.afanihao.cn)

+ ##### 此数据库默认密码为空，初次登录可在 SQLyog 等工具直接登陆后，再执行 "修改root密码.sql" 文件，即可生成密码：123456。

+ ##### 不建议使用 MySQL 命令行操作，建议使用本文档附带的 SQLyog 或其它图形化工具。


---


### `Ⅰ.` 文档说明【稍作了解即可】


+ `1.`  作者删除了一些目录，如 docs，include...等，其中 lib 目录有 800 MB 大小，但是这并不会影响运行

	+ ![[博客园/MySQL/MySQL 5.7简易安装/1.png]]


+ `2.` 添加了一些配置文件

~~~
 "my-default.ini" 是原有的一个参考文件
 
 "my.ini" 是自建的文件, 它是 MySQL 的配置文件, 里面已经添加了一些常用配置
 
 注意：MySQL的意思是让我们根据 my-default.ini 来创建一个自己的配置文件
~~~


+ `3.` 快捷脚本使用，选中要执行的脚本，右键以管理员身份运行即可

	+ ![op](博客园/MySQL/MySQL%205.7简易安装/2.png)


+ `4.` 更改 MySQL 数据库密码的 sql 命令如下，如需更改，替换数字 " 123456 " 并在 SQLyog 或其它工具中执行即可

```
GRANT ALL PRIVILEGES ON *.* TO 'root'@'127.0.0.1' IDENTIFIED BY '123456' WITH GRANT OPTION;
GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' IDENTIFIED BY '123456' WITH GRANT OPTION;
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY '123456' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```


***


### `Ⅱ.` 安装过程如下：


+ 1. 下载 "MySQL5.6 免安装版 (64bit).zip" 文件后，建议将文件夹放在根目录下，如：D:\\MySQL

	+ ![[博客园/MySQL/MySQL 5.7简易安装/3.png|650]]


+ 2. 解压之后，可以看到后缀名为 ".cmd"文件，右键 "以管理员身份" 运行 "安装MySQL服务器.cmd" 文件即可完成安装。

	+ ![[博客园/MySQL/MySQL 5.7简易安装/4.png|650]]

+ 3. 弹出如下图所示窗口即为成功。

	+ ![[博客园/MySQL/MySQL 5.7简易安装/5.png|650]]


***

### `Ⅲ.` 验证过程如下：

+ 1. 使用快捷组合键：【Win + R】，在命令框中输入：services.msc，在服务窗口中可以看到 MySQL 服务已经正常启动

	+ ![[博客园/MySQL/MySQL 5.7简易安装/6.png|650]]

***

### `Ⅳ.` 初次登录及修改密码：

+ 1. 此数据库默认初始密码为空，初次使用 SQLyog 工具登录 MySQL 数据库时无需密码，**注意，请在务必执行下一步
 
	+ ![[博客园/MySQL/MySQL 5.7简易安装/7.png|600]]


+ 2. ==**注意：务必执行这一步**==，在 sqlyog 等图形化工具执行 "修改root密码.sql" 文件或直接粘贴下一步的代码，文件默认密码为：123456。

	+ ![[博客园/MySQL/MySQL 5.7简易安装/8.png|600]]


+ 3. 若需更改数据库密码，可将数字：" 123456 " 替换为所需密码，如【a1b2c3】

```
GRANT ALL PRIVILEGES ON *.* TO 'root'@'127.0.0.1' IDENTIFIED BY 'a1b2c3' WITH GRANT OPTION;
GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' IDENTIFIED BY 'a1b2c3' WITH GRANT OPTION;
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'a1b2c3' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```


+ 4. 再次链接则需要密码才能成功登录

	+ ![[博客园/MySQL/MySQL 5.7简易安装/9.png|650]]

***

### `Ⅴ.` 卸载过程如下：


+ 1. 如需卸载此版本的 MySQL，右键管理员身份运行 " 卸载MySQL服务.cmd "

	+ ![[博客园/MySQL/MySQL 5.7简易安装/10.png|650]]


+ 2. 在执行完后，使用快捷键【 Win + R 】输入regedit，打开注册表，使用快捷键【 Ctrl + F 】输入 MySQL，并将找到的 MySQL 文件夹删除

	+ 一般为这三个路径（可能有所不同，删除即可）

```
HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Eventlog\Application\MySQL
HKEY_LOCAL_MACHINE\SYSTEM\ControlSet002\Services\Eventlog\Application\MySQL
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Eventlog\Application\MySQL
```

+ 3. 删除读者安装在电脑MySQL文件夹,如（D:\\MySQL）


+ 4. 重启电脑即可 

***

### `Ⅵ.` 其它事项：


#### 1. 报错问题

+ 先检查 MySQL 存放路径是否有中文、空格等特殊字符，请尽量使用无空格的路径。

+ 在本文档之前使用过安装版 MySQL 进行安装/卸载，但安装/卸载失败的问题，本文档建议直接重装系统
