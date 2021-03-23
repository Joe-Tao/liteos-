# LiteOS复现帮助文档

## 一、软件要求

### -***Ubuntu Version 14.04及以上版本，作为编译Huawei LiteOS的服务器。***

​    *本文档使用的使ubuntu*

### -***GNU Arm Embedded Toolchain编译器，用于代码编译。***

### -***GNU Make构建器，用于文件组织与链接。***

### -***python 2.7/3.2+，pip包管理工具，kconfiglib库，用于编译前通过图形化界面完成配置。***

### -***需要qemu模拟的话，需要安装qemu***。

## 二、Linux下的编译

### 1、获取Huawei LiteOS代码

[https://gitee.com/LiteOS/LiteOS] master分支

### 2、***在源码中tools/build/config/ 中选择需要的开发板***

*本文档选用rearview-pbx-a9*

### 3、***将需要的开发板复制到源码根目录下，并重命名为.config***

### 4、***配置想要执行的Demo***

*在源码根目录下执行make menuconfig命令，打开menuconfig的图形化配置界面，使能想要执行的Demo。
配置完成后，输入字母“S”保存配置项，其默认会保存到根目录下的.config文件中，回车即可完成保存。最后输入字母“Q”退出menuconfig配置。*

### 5、清理工程

*在编译开始前，先在根目录下执行make clean命令删除以前编译出的二进制文件*

### 6、编译工程

*在根目录下执行make 命令完成工程编译，生成的系统镜像文件、反汇编等文件在根目录下out/realview-pbx-a9 中*

## 三、QEMU运行

*通过qemu-system-arm 并设置kernel为生成的镜像文件，以非图形界面启动虚拟机。
虚拟机启动后，就会运行Huawei LiteOS，并进入shell交互界面（出现“Huawei LiteOS #”提示符）*

了解官方文档Shell教程：
https://gitee.com/LiteOS/LiteOS/blob/master/shell/README_CN.md