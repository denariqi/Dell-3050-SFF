# Dell OptiPlex SFF 3050 i5-7500 HD-630
## BIOS设定
*  恢复factory defaults
*   General → Advanced Boot Options：取消勾选
*   System Configuration → SATA Operation: AHCI
*   System Configuration → Serial Port: Disabled
*   Secure Boot → Secure Boot Enable: Disabled
*   Virtualization Support VT for Direct I/O：可取消勾选

## BIOS 刷写
*  将grub/文件夹复制到U盘，改名为EFI，然后从U盘启动
*  设置 Pre-Allocated DVMT 为64M: 
*  设置64M：setup_var 0x795 0x02
*  设置max：setup_var 0x796 0x03
*  设置CFG：setup_var 0x4ed 0x00
*  恢复BIOS出厂设置，需要重新刷写！！！

## SMBIOS: iMac 19,1
*  CFGLock.efi  更改CFG开关
*  VerifyMsrE2.efi  查看CFG状态
*  WhateverGreen的Framebuffer补丁
*  AAPL,ig-platform-id Data 00001259 使用桌面iGPU驱动显示器时使用
*  framebuffer-patch-enable Data 01000000 启用WhateverGreen kext打补丁
*  framebuffer-stolenmem Data 00003001 设置最小内存为19MB
*  
## 声卡、麦克风修复
*  需要CodecCommander.Kext 
*  运行ComboJack_Installer/install.sh，然后重启，插入耳机时，会弹出对话框询问你插入的是耳机还是耳塞。
