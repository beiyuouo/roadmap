# ubuntu

官网: [Ubuntu](http://www.ubuntu.com/)

## 下载

Link: [Download Ubuntu](https://ubuntu.com/download)

更多版本: [Ubuntu Desktop](https://ubuntu.com/download/alternative-downloads)

尽量不要下载最新版，尽量下载 LTS 版本，这是长期支持的版本。但是时至今日，笔者还是喜欢 Ubuntu 18.04 LTS，所以下面都是以 18.04 LTS 为例。

Ubuntu 18.04 LTS 64-bit 下载地址：[https://releases.ubuntu.com/18.04/](https://releases.ubuntu.com/18.04/)

## 系统盘制作

> 注意，这里一共需要两个磁盘，一个是系统盘，一个是要安装到的硬盘。

这里笔者使用了两个 U 盘进行，其中作为系统盘的 U 盘是 USB2.0 的，所以安装会有些慢，而要安装到的 U 盘是 USB3.0 的。

其实制作系统盘有很多方案了，也有很多软件可供选择，这里笔者使用的是 UltraISO。

1. 文件 - 打开 - （刚才下载的.iso 文件）
2. 启动 - 写入硬盘映像 - （选择系统盘） - 写入

## 安装

等待写入完成后，就可以重启了，进入 BISO 界面。因为笔者的电脑是神舟，一般是按 F2 进入 BISO 界面。其他的笔记本热键不确定，一般也都是 F2 F10 F12，有时候还需要按住 Shift 键。

进入 BIOS 后，由于各个厂商 BIOS 也不尽相同，所以界面可能有所区别，这里仅以笔者的电脑为例。

BOOT - UEFI Hard Disk Drive BBS Priorities - ubuntu

另外如果启动的还是 Windows，可以考虑手动调整一下启动顺序，在 BOOT Options 中把 USB 的放前面。

最后在 Exit 界面 Save and Restart 就可以正式进入安装步骤了。

利用 Ubuntu BOOT Manager 启动后，可以看到几个选项，如果你的 U 盘读写较慢，可以考虑使用 Try 的选项，这样你可以在安装的过程中使用浏览器随便冲会浪，不会无聊 hhhh。这里笔者选的是 Install Ubuntu.

1. 语言 - English，这里看个人喜好，可以选择中文。笔者选择英文的原因不是因为装 b，而是中文版本的桌面、文档等路径是用中文显示，这样其实是有一些蛋疼的，笔者个人不是很喜欢
2. 键盘布局 - English(US)
3. 连接 WiFi（可选）
4. 安装选项 - Minimal installation, 取消勾选 Download updates while installing Ubuntu。笔者安装系统的原因主要是为了开发，很多功能是不常使用的，因此就尽可能的最小化安装，这样会快一些，同时省掉一部分空间。后面如果你想要保持系统更新的话，可以选择在安装时更新，但笔者并不是很推荐这样做。
5. This computer currently has Windows Boot Manager on it. What would you like to do? - Something else。注意这里可千万不要勾选错了，不然会把你 Windows 给刷没了！！！也是从这里开始，包括后面的磁盘分区都要谨慎操作，一旦出问题可能就是大问题了...
6. 磁盘分区
   看好要安装到的磁盘，确定磁盘大小正确，一般系统盘提示有 Windows 的 Boot Manager，/dev/sda 之类比较靠前的会是系统磁盘，u 盘一般在 sdb 以后，不要选错。先清掉原先的分区再建立，选中以后点下面的`-`号即可，添加分区的时候就选中然后点下面的`+`号. 这里简单列一下各分区和挂载点：

   - /swap，Logical，16G，Ext4，一般设置内存大小以上
   - /boot，Primary，1024MB，Ext4，引导分区，其实 256MB 应该就够了
   - /，Primary，32G，Ext4，系统分区
   - /home，Logical，剩余空间，Ext4，用户分区，分剩下的空间就可以了

7. 分区划分完 - Install now
8. 接着就是时区设置 - Shanghai
9. 最后就是一些名称，电脑名称，昵称，密码之类的设置了。
10. 静等安装，即可结束

因为笔者已经不知道这样装过多少次系统了，因此这次安装基本没花费多少时间，应该是在 1h 内包括了下载、制作系统盘、安装、启动查看的全部流程，还顺便记录了一下。
