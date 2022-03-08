​        如果你还在用过去的，制作安装系统U盘的方式，那你需要准备N个U盘，并且每次更新镜像都要解压或者用写盘软件重新写盘。同时在今天，可能需要多个系统的安装盘。

​		今天我介绍的 **Ventoy** 就是为了制作多系统安装U盘的一个非常方便的开源工具。使用它便可以在一个U盘上承载多个系统镜像，并且更新起来非常方便。

​		有了 Ventoy ，日后便无需反复地格式化U盘。只需将 ISO 系统镜像文件直接拷贝到U盘中，便可从它的多系统引导菜单中直接选择并引导启动。同时 Ventoy 支持常见的操作系统（Windows/WinPE/Linux/VMware 等）。

​		Ventoy还有一个好处就是可以





## 第一步 下载Ventoy

**官网地址：** https://www.ventoy.net/cn/index.html

​                	https://github.com/ventoy/Ventoy/releases/tag/v1.0.46

进入官网后，选择合适的版本下载，我用的是windows系统，因此只需下载第一个windows版本的就行了
[![img](https://s1.ax1x.com/2020/10/18/0OqwZ9.png)](https://s1.ax1x.com/2020/10/18/0OqwZ9.png)





## 第二步 安装Ventoy到U盘

将下载的压缩包解压，如图所示：
[![img](https://s1.ax1x.com/2020/10/18/0OLnW6.png)](https://s1.ax1x.com/2020/10/18/0OLnW6.png)




插上U盘，双击`Ventoy2Disk.exe`进入安装界面，它会自动识别U盘：
[![img](https://s1.ax1x.com/2020/09/30/0K9XsP.png)](https://s1.ax1x.com/2020/09/30/0K9XsP.png)
点击`安装`，会自动格式化U盘，待进度条到头后会提示安装成功。如果你的U盘之前已经安装了低版本的ventoy，那么点击`升级`,就会自动升级到新版本。



## 第三步 下载WePE

**官网地址：**http://www.wepe.com.cn/
大家如果手头宽裕，可以先付费再获取下载链接。当然如果你不想花钱，直接点击我已付费，就能获取到真实的下载链接。我用的是64位系统，因此下载64位版本的即可。
[![img](https://s1.ax1x.com/2020/10/18/0XSeBT.png)](https://s1.ax1x.com/2020/10/18/0XSeBT.png)





## 第四步：将WePE生成iso文件，并拷到U盘目录下

双击下好的WePE安装包，点击下图所示的图标，将WePE生成iso文件
[![img](https://s1.ax1x.com/2020/09/30/0KCdWd.png)](https://s1.ax1x.com/2020/09/30/0KCdWd.png)





## 第五步： 将iso包和ghost系统包放入U盘中

至此，系统启动盘就做好了

## 第六步： 将电脑关机，将U盘插电脑上重启

> 注意：要进bios中将安全启动设置为disabled

## 第七步：通常情况下，电脑会自动识别启动Ventoy,如不识别，按下F12或者F8（具体以机型为准）,识别成功后，会如图所示：

[![img](https://s1.ax1x.com/2020/10/16/0HeFdf.png)](https://s1.ax1x.com/2020/10/16/0HeFdf.png)




[![img](https://s1.ax1x.com/2020/10/16/0HeQe0.png)](https://s1.ax1x.com/2020/10/16/0HeQe0.png)



## 第八步：想装那个系统就选择哪一个iso,会直接进入安装引导。如果想进PE装gho系统，就选WePE开头的iso启动进入PE。

安装gho也很简单，进入PE后，打开`DiskGenius`，然后选中要安装的磁盘，将其改为MBR格式。最好全盘格式化再分区，当然也可以只格式化C盘。分区的时候，要选择4K对齐（4096字节）。

之后点击快捷图标`CGI备份还原`，进入如下界面
[![img](https://s1.ax1x.com/2020/10/18/0Obl9K.png)](https://s1.ax1x.com/2020/10/18/0Obl9K.png)




默认操作是还原分区，这个无需改变。我们只需选择要安装的磁盘为C盘，然后再从本地硬盘中选中要装的GHO文件。为了稳定，建议将U盘中的系统复制到硬盘中的非系统分区内。最后选择完成后重启就OK了。这时就可以拔下U盘了，不然系统重启后仍会以U盘启动进PE。