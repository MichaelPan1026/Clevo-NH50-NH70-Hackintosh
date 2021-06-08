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
+ 关闭 CFG Lock：
    - 方法一：魔改 BIOS，适用于对 BIOS 文件修改较熟练的用户（BIOS中位置：Advanced -> Power & Performance -> CPU - Power Management Control -> CPU Lock Configuration）
    - 方法二：通过 OpenCore 的 EFI Tools（CFGLock.efi）

>关闭 CFG Lock之后需要将配置文件`config.plist`中`AppleCpuPmCfgLock`和`AppleXcpmCfgLock`两项 Quirks 禁用

+ 可选项目：禁用 SGX、Fastboot、VT-d、Platform Trust（下面是 BIOS 中的位置）
  - SGX Fast Boot VT-d: Advanced -> Advanced Chipset Control
  - Platform Trust: Advanced -> Chipset Configuration
+ 开启 HIDPI（Big Sur及以上）：`bash -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/dev/hidpi.sh)"`
+ 支持 macOS Monterey（OTA），升级后开机读条很慢，蓝牙和内置喇叭不可用，谨慎更新！

-----------------------------------------

感谢：[@Dortania](https://github.com/dortania) [@daliansky](https://github.com/daliansky) [@takoyakiwhite](https://github.com/takoyakiwhite)