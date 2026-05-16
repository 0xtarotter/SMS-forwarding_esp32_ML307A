# SMS-forwarding_esp32_ML307A
基于中移物联ML307A的短信转发固件，基于chenxuuu / sms_forwarding开源固件二次编译。优化webui和功能区分

# 申明
基于个人需求场景编译，不作任何风险保证，支持国内外多数运营商。   
电信✅  移动✅  联通✅ GIFFGAFF✅ CUNIQ✅ T-MOBILE✅ O2✅    
国内移不动测试期间出现二次验证，其他正常。

# 刷写教程

[教程](https://github.com/0xtarotter/SMS-forwarding_esp32_ML307A/blob/main/INSTALL.md)

[原作者 README.md](https://github.com/chenxuuu/sms_forwarding/blob/master/README.md)

# 设备外观 
<img src="https://files.seeusercontent.com/2026/05/16/K6lj/a9723ed.png" width="200" />
购买渠道请自行发挥，不作任何介绍和保证。

---

# 主要功能
* 支持定时消耗流量和定时发送短信功能（保号） - new
* 支持配置通知通道后，设备开机推送开机信息 - new

* 支持最多5个通道通知
* 支持使用通用AT指令与模块进行通信
* 开启后支持通过WEB界面配置短信转发参数、查询当前状态
* 支持多达5个推送通道同时启用，每个通道可独立配置
* 支持将收到的短信转发到指定的邮箱
* 支持通过WEB界面主动发送短信，以便消耗余额
* 支持通过WEB界面进行Ping测试，以极低的成本消耗余额
* 支持长短信自动合并（30秒超时）
* 支持管理员短信远程发送短信和重启设备 （个人无需求场景，未测试）

# 通道支持
| 推送方式 | 说明 | 需要配置 |
|---------|------|---------|
| **POST JSON** | 通用HTTP POST | URL |
| **Bark** | iOS推送服务 | Bark服务器URL |
| **GET请求** | URL参数方式 | URL |
| **钉钉机器人** | 企业群通知 | Webhook URL，可选Secret加签 |
| **PushPlus** | 微信公众号推送 | Token |
| **Server酱** | 微信推送服务 | SendKey |
| **自定义模板** | 灵活的JSON模板 | URL + 请求体模板 |
| **飞书机器人** | 自定义通知 | Webhook URL |


#固件WEBUI展示

![111.png](https://files.seeusercontent.com/2026/05/16/Rx6c/111.png)
![222.png](https://files.seeusercontent.com/2026/05/16/9rWh/222.png)
![333.png](https://files.seeusercontent.com/2026/05/16/5cAa/333.png)
![444.png](https://files.seeusercontent.com/2026/05/16/i1jD/444.png)
![555.png](https://files.seeusercontent.com/2026/05/16/Mx8e/555.png)

# 致谢

基于[@chenxuuu](https://github.com/chenxuuu) 项目二次编译修改，感谢大佬提供先行思路。
