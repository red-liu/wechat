#微信公众平台自助服务


如果你了解数据库，并有自己的服务器，那么这个程序可以帮助你快速的创建你的开发版的微信公众服务信息，免得在微信的后台一步步添加信息。
目前支持回复的信息类型为：
***
	1.文本
	2.图文类，仅仅一条
***

###Clone 或下载项目源码。

   1. 打开 /functions.php 文件， 修改里面的数据库配置信息和欢迎词
    ![修改数据库配置](http://ww2.sinaimg.cn/large/61ffc92ejw1e4r8bwmduhj20jo05vgmz.jpg)
    
   2. 进入微信公众平台，高级功能，开启开发模式，并设置接口配置信息。其中 URL 为 {yoursite}/weixin.php 的实际位置， Token 为上一步设置的 Token 。
	
   3. 验证后，把weixin.php删除或者改名字，把weixin-new.php修改为 wexin.php.
	
   4. 导入数据库文件db.sql 添加数据，您可以参考里面已经有的数据进行修改。
	***
		[1] equls 类型为用户输入的内容和关键词完全匹配
	    [2] startwith类型为用户输入的内容以此内容开头，并可以自行定义方法到title中。
	***
    
	
###向你的微信公众号发送消息并测试吧！

	