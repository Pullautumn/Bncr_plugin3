# Bncr_plugins
## 企业微信对接方法
企业微信网址 https://work.weixin.qq.com/  
  
1.创建企业微信账号，获取corpId（我的企业-企业信息-企业ID）  
2.新建一个应用（应用管理-自建-创建应用），进入应用获取corpSecret（Secret）  
3.应用内找“接收消息”-“启用api接收”，URL填“无界地址/api/bot/wxWork”，Token和EncodingAESKey随机生成并记录，先不要点“保存”  
4.应用内找“开发者接口”-“企业可信ip”，输入无界的所在服务器的IP地址  
5.在无界config里加入wxWork配置信息并填写以上获取的内容，安装3个依赖@wecom/crypto xml2js form-data，重启无界  
6.在第3步的界面点击保存，如提示保存成功则对接完成（保存出现问题的仔细检查配置并想办法解决响应速度，平台要求1秒内响应）  
  
注意：1.要启用管理员功能请在已有管理员权限的平台输入set wxWork admin 用户ID,给应用发送消息的时候用户ID在控制台可以看到  
     2.要启用官方命令需要在官方命令插件里@platform一行添加wxWork  
     3.微信应用需要配置可信IP，没有固定IP就只能跟我一样不定时换IP，很麻烦  
     4.在“我的企业”-“微信插件”中设置以后可以用微信接收企业微信的消息，但是有些功能会受限（比如消息撤回）  
     5.目前只支持文本、图片和视频三种格式  
     6.企业管理员邀请好友会暴露姓名，用小号邀请还没试过

## 企业微信客服接口对接方法
1.创建企业微信账号，获取corpId（我的企业-企业信息-企业ID）  
2.创建客服账号（应用管理-微信客服-客服账号）  
3.在“应用管理-微信客服-通过API管理微信客服账号-企业内部开发”里把该客服账号添加进去  
4.打开“应用管理-微信客服-接收事件服务器”，URL填“无界地址/api/bot/wxWorkKF”，Token和EncodingAESKey随机生成并记录，先不要点“保存”  
5.在无界config里加入wxWorkKF配置信息并填写以上获取的内容，安装3个依赖@wecom/crypto xml2js form-data，重启无界  
6.在第4步的界面点击保存，如提示保存成功则对接完成（保存出现问题的仔细检查配置并想办法解决响应速度，平台要求1秒内响应）  

注意事项见上面，客服接口没有撤回功能，但是别人只要点击客服账号的接入链接就能开启对话，比较方便。
