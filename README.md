# SMS-forwarding_esp32_ML307A
基于中移物联ML307A的短信转发固件，基于chenxuuu / sms_forwarding开源固件二次编译。优化webui和功能区分
### 设备外观 
![合图.png](https://files.seeusercontent.com/2026/05/16/K6lj/a9723ed.png)
购买渠道请自行发挥，不作任何介绍和保证。

---

SMS转发助手 ESP32-C3 最新固件刷机教程

固件信息

项目基础：https://github.com/chenxuuu/sms_forwarding
适用硬件：ESP32-C3 / MakerGO ESP32 C3 SuperMini，4MB Flash
默认热点：SMS-WIFI-xxxx
默认热点密码：tarotter
后台地址：http://192.168.4.1/
默认后台账号：admin
默认后台密码：admin123

本包内容

firmware/code.ino.merged.bin        推荐刷入的一体化固件
firmware/code.ino.bootloader.bin    bootloader
firmware/code.ino.partitions.bin    分区表
firmware/boot_app0.bin              boot app
firmware/code.ino.bin               应用固件
SHA256SUMS.txt                      文件校验值

推荐方式：刷入 merged.bin

Windows 刷机方法

1. 安装 Python 3：
   https://www.python.org/downloads/windows/

2. 打开 PowerShell 或 CMD，安装 esptool：
   pip install esptool

3. 按住 ESP32-C3 的 BOOT 键，插入 USB；如果不能自动进入下载模式，按一下 RST/EN 后松开 BOOT。

4. 查看串口号，例如 COM3、COM5。

5. 在本 ZIP 解压目录执行：
   python -m esptool --chip esp32c3 --port COM3 --baud 921600 write_flash 0x0 firmware/code.ino.merged.bin

   注意：把 COM3 改成你的实际串口。

Linux / macOS 刷机方法

1. 安装 esptool：
   python3 -m pip install esptool

2. 查看串口：
   ls /dev/ttyACM* /dev/ttyUSB*

3. 如果 Linux 权限不足，执行：
   sudo chmod 666 /dev/ttyACM0

4. 在本 ZIP 解压目录执行：
   python3 -m esptool --chip esp32c3 --port /dev/ttyACM0 --baud 921600 write_flash 0x0 firmware/code.ino.merged.bin

   注意：把 /dev/ttyACM0 改成你的实际串口。

刷入后使用

1. 设备重启后，手机或电脑连接热点：SMS-WIFI-xxxx
2. 热点密码：tarotter
3. 浏览器打开：http://192.168.4.1/
4. 登录：admin / admin123
5. 在后台配置路由器 WiFi、通知通道、管理员号码等信息。

校验

推荐固件 SHA256：
0ffe7c188a0f40aa30f44167ed453c67c909aa80cb60f83a1c0374cdfa55a0e4  firmware/code.ino.merged.bin

完整校验值见 SHA256SUMS.txt。





