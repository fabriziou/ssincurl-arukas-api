
### 解析arukas容器的映射ip&端口，调用arukas.io API接口实时获取IP和端口

转自：https://wo.ci/toss/ssincurl-arukas-api-gass.html

注意：这个程序会获取你登录的账号里的所有镜像信息，包括镜像的ID、App Name、Image、Instances、Memory、Endpoint、Port、ENV、CMD所有信息，所以登录的Arukas的账号里除了ss，请不要包含其他含有重要信息的镜像。

## 更新docker一键部署

```
docker run -it -p 80:80 -e user=xx@xx.xx -e passwd=yourpassword -e ssname=title jialezi/ss-arukas-api 
```
ENV变量

user=你arukas的登录邮箱

passwd=你的密码

ssname=定义网站的标题，有空格请用引号


## 使用说明：

1.程序需要PHP支持

2.程序需要搭配arukas按照以下镜像及CMD正确生成SS应用容器

image: lowid/ss-with-net-speeder:latest

CMD: ssserver -p 端口号 -k 密码 -m aes-256-cfb

3.编辑api.php中第19&20行，输入您的arukas登陆邮箱与密码

4.根据需求在index.html的51&61行中开启或关闭密码、加密方式输出以及SS:// URL输出

5.上传到网站目录，点击生成即可获取SS账号



优化说明：

0.1.增加加密方式输出（index.html - line 55） 2017/4/25

1.简单优化页面排版，移除不必要链接

2.取消实际端口、CMD输出，注释SS:// URL显示,（index.html - line 61）

3.增加密码输出（index.html - line 51）

4.简化获取账号步骤，取消前台登陆，改为api.php后台登陆

原Github项目地址：https://github.com/bestK/ssincurl

ssincurl - Beautify and optimize By Jonvi
