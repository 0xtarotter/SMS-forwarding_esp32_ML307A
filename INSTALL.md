# SMS转发助手 ESP32-C3 固件刷机教程

这是用于公开发布的干净固件包。

## 隐私说明

本包不包含个人 WiFi SSID、WiFi 密码、手机号、通知 Token、Webhook 或私有配置。
固件首次使用时会开启配置热点，所有个人配置都需要用户在 Web 后台自行填写。

默认热点：SMS-WIFI-xxxx
默认热点密码：tarotter
后台地址：http://192.168.4.1/
默认后台账号：admin
默认后台密码：admin123

固件编译时间：2026-05-16 23:46:10
固件校验码：B5423711
推荐刷入文件：firmware/code.ino.merged.bin
merged.bin SHA256：915afcb7e500a53127c714509d466b63913663dc0d04dfe3933ada29589928ea

## Windows 刷机

1. 安装 Python 3。
2. 打开命令提示符，安装 esptool：

python -m pip install esptool

3. 把 ESP32-C3 接入电脑，确认串口号，例如 COM3。
4. 在本 ZIP 解压目录执行：

python -m esptool --chip esp32c3 --port COM3 --baud 921600 write_flash 0x0 firmware/code.ino.merged.bin

如果失败，把 921600 改成 460800 或 115200 再试。

## Linux 刷机

1. 安装 esptool：

python3 -m pip install --user esptool

2. 查看串口：

ls /dev/ttyACM* /dev/ttyUSB* 2>/dev/null

3. 如果权限不足，临时授权，例如：

sudo chmod 666 /dev/ttyACM0

4. 在本 ZIP 解压目录执行：

python3 -m esptool --chip esp32c3 --port /dev/ttyACM0 --baud 921600 write_flash 0x0 firmware/code.ino.merged.bin

如果失败，把 921600 改成 460800 或 115200 再试。

## 首次使用

1. 刷机完成后重启设备。
2. 手机或电脑连接热点 SMS-WIFI-xxxx，密码 tarotter。
3. 浏览器打开 http://192.168.4.1/。
4. 使用 admin / admin123 登录。
5. 在后台配置路由器 WiFi、通知通道、管理员手机号、设备备注等。
6. 保存后设备会按配置连接网络并开始短信转发。

## 文件说明

firmware/code.ino.merged.bin：推荐刷入，地址 0x0。
firmware/code.ino.bin、bootloader、partitions、boot_app0：高级用户分区刷机备用。
SHA256SUMS.txt：用于校验文件完整性。
