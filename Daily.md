# Daily
本次训练营在 2023-10-08 开课并发布相关测试及实验。

### （2023-10-11）周三
在这之前有过rust学习经验，所以 rustlings 的相关实验已经完成。<br />
这些天复习 rust 相关内容，加深理解。

### （2023-10-12）周四
学习 risc-v 架构内容
- 基础指令集
- risc-v 汇编语法

### （2023-10-13）周五
学习 risc-v 架构内容
- risc-v 汇编语法
- 64位地址指令

### （2023-10-16）周一
学习 risc-v 架构内容
- risc-v 特权架构

tips
    risc-v 没有栈操作指令 （push pop）

### （2023-10-17）周二
学习 risc-v 架构内容
- risc-v 特权架构

### （2023-10-18）周三
学习 risc-v 架构内容
- 开始学习 rCore-Tutorial-Book 文档，搭建 rCore实验环境。


### （2023-10-19）周四
- 在基于 wsl2 的系统上编译qemu非常慢，耗费大量时间。<br>
    查询了解到是因为**在wsl2系统中访问window下的文件**导致的问题，需要注意。

### （2023-10-20）周五
- qemu8 在启动os环节，关于 virtio-net-device 的启动参数需要注意。从qemu7.2开始在编译时需要修改编译配置，参考 https://wiki.qemu.org/ChangeLog/7.2。
- 后续环节更换qemu为文档中使用的7.0.0版本。第二章实验环节出现 **segmentation faultqemu-riscv64** ，尝试修改项目下的SBI文件后得到解决。

### （2023-10-22）周日
- 配置gdb调试环境，尝试使用clion调试rCore内核。
    - 注意 release 模式下修改 debug 选项。
    - release 下优化等级会导致clion部分断点无效。尝试调整 opt-level 得到解决。
    - rust文件可以正常调试，无法调试汇编文件，gdb提示 **no such file :\*\***
- 学习使用xtask构建项目。

### （2023-10-23）周一
- 开始正式学习 rCore-Tutorial-Book
- 了解SBI 以及 ABI 标准及相关规范，查询了解了一下grub uefi sbi的大致区别。
- 编写运行 基于rust的第一个riscv裸机程序。



