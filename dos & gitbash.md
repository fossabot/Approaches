### dos命令，有时还是要了解一下的，下面列举了一下自己常用的命令

#### ***cmd中：***

1. 查看系统版本
    `ver`
	
2. 清空命令
	`cls`
	
3. 更改文件名
	`ren 旧名 新名`（shell中 `mv 旧名 新名`）
	
4. 査看文本内容（gitbash中 cat 文本）
	`type 文件名`
	
5. 査看某个命令的帮助
	`命令 /?`
	
6. 新建文本
	`echo >xx.txt`
	
   补充内容
	`echo mmm>>xx.txt`
7. 退出cmd
	`exit`(shell中则是`quit`)
	
8. 直接进入别的盘
	`e:`
	
9. 复制文件到e盘（`hw.class在c:/Users/TGQ/Desktop里`）(输命令也要在Desktop里)
	`copy hw.class e:`
	
10. 屏幕键盘
	`osk`
11. 服务项（window.update系统更新设置）
	`services.msc`
	
12. 注册表
	`regedit.exe`


--------------------------------------------

##### *自制‘栗子’： 完全cmd命令编译HELLO WORLD!*
###### win+R调出命令提示符 键入cmd

```javascript 
echo class hw {public static void main(String[] args ){ System.out.println("HELLO WORLD!"); }}>>hw.txt
ren hw.txt hw.java
javac hw.java
java hw
//HELLO WORLD!
```

----------------------------------------------------------



#### ***cmd登录ftp中：***

1. 查看当下目录
	`lcd`
2. 更改下载目录
	`lcd c:/Users/TGQ/Desktop`
3. 退出ftp
	`quit或bye`



-------------------------------------------------------

#### ***xshell中：***
1. 清除屏幕命令
	`clear`
	
2. 复制
	`cp`
	
3. 查看文件内容
	`cat 文件名`
	
4. 用户登录信息
	`last`
	
5. 时间
	`date`
	
6. 查看系统版本
	`unname`
	
7. 删除非空文件
	`rm -rf 文件名`
	
8. 重命名文件夹
	`mv 旧名 新名`
	
9. 进入vi编辑
	`vi 文件（例如 hw.java）`
   不保存退出
	`：q`
   强制性退出
	`：q!`
   保存并退出
	`：wq`
	
10. 查看当前文件
	`ls`(或者`dir`)
	
11. 退出一级目录
	`cd ..`(cmd中有无空格都行)

--------------------------------------------------------


##### *自制‘栗子’： 综合应用cmd的登录ftp与xshell的vi编译*

- dos-->cmd-->ftp
  - `open  address`
  - `user-name`
  - `password`

- 之后上传压缩文件到阿里云服务器 
 - `put ds.zip`(或 ds.rar)
 - `get xx`(同理下载命令)

- xshell登录到阿里云服务器,并解压ds.zip到ds/list文件夹中
 - `rar x ds.rar (或 unzip ds.zip)`

- 若没有编译，则 
  - `javac -encoding GBK *.java`
  
- 回到根目录，执行java程序
  - `cd ~` （~表示根目录）
  - `java ds/list/TestList`









