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
- 了解 SBI 以及 ABI 标准及相关规范，查询了解了一下grub uefi sbi的大致区别。
- 编写运行基于rust的第一个riscv裸机程序。


### （2023-10-24）周二
- 开始训练营第二阶段，由于提前预习过，所以直接开始完成lab1的相关实验。
    -   独立完成实验内容，编写实验报告。
    -   关于内核态及用户态切换的过程及原理有了更深的理解，但是riscv的汇编不太熟练，需要加强学习。
tips
    - stvec 寄存器包含基地址 BASE 以及模式 MODE 两个域，其中 MODE 域表示异常处理程序入口地址的寻址方式。注意 **基地址 BASE 域必须 4 字节对齐**，所以在计算异常处理程序的入口地址时，需要把末两位即 MODE 域中的两位恒置 0。


### （2023-10-25）周三
- 尝试完成lab2相关实验
    -   对项目模块不够熟练，实验过程不是很顺利，虽然最后完成了实验，决定在明天重新整理完成一次。
    -   学习riscv的多级分页，在虚拟内存下跳板机制的原理及实现方法，在分页模式下实现分时多任务。

### （2023-10-26）周四
- 重新完成lab2相关实验
    -   由于昨天在完成lab2时感觉不是很顺利，可能是对项目整体不是很了解，决定重新梳理项目结构，了解项目中相关结构体的定义及方法。
    -   在重新阅读实验手册并梳理项目后，思路相比昨天有了很大的变化，顺利的重新完成lab2。

### （2023-10-27）周五
- 尝试完成lab3相关实验
    -   阅读实验手册ch5，学习进程相关定义及调度原理。[https://www.zhihu.com/question/66902460]
    -   了解了fork和exec函数的由来
    -   lab3的实验完成的相对顺利，但是实验中的 **stride** 调度算法理解的不是很透彻，准备后面抽空在查阅一下文档。

### （2023-10-39）周日
-  回顾了一下 rust 相关知识，条件编译、内存模型相关知识。
-  学习 [buddy_system_allocator](https://github.com/rcore-os/buddy_system_allocator) 用法，rust 全局分配符的定义。

### （2023-10-30）周一
-  查阅关于 **stride** 调度算法的相关知识，有了新的理解。
[(资料)](https://nankai.gitbook.io/ucore-os-on-risc-v64/lab6/tiao-du-suan-fa-kuang-jia#stride-suan-fa)
-  完成lab4相关实验
    -  查阅了一些关于 [virtio-drivers
](https://github.com/rcore-os/virtio-drivers)的知识，后续好好学习一下。
    -  学习文件系统与文件描述符相关知识
    -  了解学习 easy-fs 文件系统。
-  文件系统相关知识需要再抽空复习一下

### （2023-10-31）周二
-  完成lab5相关实验
    - 学习线程原理，锁机制及信号量。当前系统设计不考虑多核，相关内容需要注意。
    - 学习理解 银行家算法 。
    - lab5 的实验未能完成，需要明天整理一下，debug比较麻烦。


### （2023-10-31）周二
-  完成lab5相关实验
    - 重新整理了一下代码，完成lab5实验。关于实验中使用的银行家算法有待商榷，后续尝试整理优化
    - github的评测提示不太友好，消耗很多时间。