# OpenCore Bootloader for Hackintosh on Clevo NH5x/NH70 series
## 本分支为 dev 分支，可能会发生有预料之外的错误。
+ 支持 Clevo NH5xRD_RC_RA_RH(Q)/NH70RD_RC_RA_RH(Q) 系列的所有机器。
+ 所有功能基本可用。**支持 macOS Big Sur。**
+ **安装之前需要先刷入蓝天原厂 BIOS，并手动禁用 SGX、Fastboot、VT-d、Platform Trust、CFG Lock。**
    - SGX Fast Boot VT-d: Advanced -> Advanced Chipset Control
    - Platform Trust: Advanced -> Chipset Configuration
    - CFG Lock: Advanced -> Power & Performance -> CPU - Power Management Control -> CPU Lock Configuration
+ **启动之后需要手动更换三码，避免出现问题。**
+ Big Sur 上可以用此命令开启 hidpi `bash -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/dev/hidpi.sh)"`
+ 可能还有些小问题，欢迎提交 PR 一起完善。
-----------------------------------------
感谢：[@Dortania](https://github.com/dortania) [@daliansky](https://github.com/daliansky) [@a328661276](https://github.com/a328661276)
