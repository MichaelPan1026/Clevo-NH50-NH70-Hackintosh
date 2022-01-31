# OpenCore Bootloader for Hackintosh on Clevo NH5x/NH70 series

## 简介
+ 支持 Clevo NH5xRD_RC_RA_RH(Q)/NH70RD_RC_RA_RH(Q) 系列的所有机器
+  除睡眠外几乎完美

## 前提准备及安装方法
1. 制作一个安装 U盘（记得布置 ESP 与 MSR 分区）
2. 下载 [Release](https://github.com/MichaelPan1026/Clevo-NH50-NH70-Hackintosh/releases) 文件并解压，放置在 U盘的 ESP 分区内
3. 重启选择 U盘启动，选择 Install 项目
4. 安装时不要登入账号，不要联网，安装完成更换三码后才可联网登录账号
5. 安装完成后，记得将 U盘 ESP 分区内文件拷贝到电脑硬盘的 ESP 分区并添加 macOS 启动项

## 注意事项
+ **安装过程中一定不要联网，安装完成后一定记得更换三码**

## 其他
+ 关闭 CFG Lock：使用 OpenCore 选单中的 GRUB Shell，回车进入命令行，输入`setup_var 0x3E 0x0`，回车，然后`exit`退出
>关闭 CFG Lock之后需要将配置文件`config.plist`中`AppleCpuPmCfgLock`和`AppleXcpmCfgLock`两项 Quirks 禁用

+ 可选项目（需要在 BIOS 中通过文件启动 GRUB Shell 来调出完整选项，输入`setup_var 0x133 0x1`）：禁用 SGX、Fastboot、VT-d、Platform Trust（下面是 BIOS 中的位置）
  - SGX、Fast Boot、VT-d: Advanced -> Advanced Chipset Control
  - Platform Trust: Advanced -> Chipset Configuration
+ 开启 HIDPI（Big Sur及以上）：`bash -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/dev/hidpi.sh)"`

-----------------------------------------

感谢：[@Dortania](https://github.com/dortania) [@daliansky](https://github.com/daliansky) [@takoyakiwhite](https://github.com/takoyakiwhite)
