#微信公众平台服务框架

##本框架功能
本框架在开源代码的基础上衍生而来，可以快速搭建一个微信公共平台框架，以便于后续的微信后台开发。

##文件介绍
config.php 中含所有配置信息，包含了数据库的用户名密码，欢迎词和404反馈词等，可以自己进行定制。
db.sql db_op.php 数据库操作文件
user_command_funs 自定义命令处理函数
extern_request_funs 外部网址调用处理函数
weixin_auth.php 用于微信服务器的第一次认证
weixin.php 主处理函数

其他有些是调试和测试文件。

##本框架使用指南
本框架的使用很简单，主要进行如下步骤：

1.导入数据库文件db.sql
	
具体来说可以使用一下命令：

	mysql -u -p
	(输入密码) 
	source db.sql  //take care of path of file

2.修改代码中的配置
	
打开config.php，将其中的$_username，$_password和$_dbname修改为你的数据库的用户名，密码和数据库名，也可以修改$WELCOME_MSG和$NO_RESPONSE（可选）。

3.将当前所有文件上传至web服务器中对应的html文件夹下。

4.可以在公共号的后台进行验证以及work了。

##本框架的特色
框架使用的是数据库驱动的关键字应答方式。可以处理用户的三种类型的请求。

第一种是常见的关键字请求，比如说用户发送了`help`，则系统会在数据库中查找该关键字的对应回复，并返回给用户使用。

第二种是可以自定义用户命令，比如说用户发送`#get# word`，在框架中用户可以自定义该命令get所对应的处理方式。且该命令采用数据库驱动方式，可以任意增加和删除用户自定义的命令。在用户需要增加一个自定义命令时，只需要在数据库中增加一条记录，并在user_command_funs.php增加相应的数据处理函数即可。

第三种是外部请求命令，比如说用户发送了一个关键字`知乎`，后台需要请求知乎的api在进行回复给系统。同样，本框架只需要在数据库中增加一条外部请求记录，该记录中包含对应的api。当遇到这种请求时，框架会进行web请求，用户只需要在extern_request_funs.php中增加一个返回数据的拼接函数，用于决定最后数据的具体形式即可。

其他高级功能有空再说。


	