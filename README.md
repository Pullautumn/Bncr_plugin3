# Bncr_plugins
## 企业微信对接方法
企业微信网址 https://work.weixin.qq.com/  
  
1.创建企业微信账号，获取corpId（我的企业-企业信息-企业ID）  
2.新建一个应用（应用管理-自建-创建应用），进入应用获取corpSecret（Secret）  
3.应用内找“接收消息”-“启用api接收”，URL填“无界地址/api/bot/wxWork”，Token和EncodingAESKey随机生成并记录，先不要点“保存”  
4.应用内找“开发者接口”-“企业可信ip”，输入无界的所在服务器的IP地址  
5.在无界config里加入wxWork配置信息并填写以上获取的内容，安装3个依赖@wecom/crypto xml2js form-data，重启无界  
6.在第3步的界面点击保存，如提示保存成功则对接完成（保存出现问题的仔细检查配置并想办法解决响应速度，平台要求1秒内响应）  
  
注意：1.要启用管理员功能请在已有管理员权限的平台输入set wxWork admin XXX  
     2.要启用官方命令需要在官方命令插件里@platform一行添加wxWork  
     3.微信应用需要配置可信IP，没有固定IP就很麻烦  
