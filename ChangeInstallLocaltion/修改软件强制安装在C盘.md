## 修改软件强制安装在C盘方法

电脑中有些软件不会提供安装路径选择，直接安装在了C盘，占用大量C盘空间，  
通过修改注册表中安装路径的方式可以改变这些软件安装路径

### 第一步 Win + R键打开运行对话框，输入regedit

![Regedit](https://github.com/xiaolanlaia/MarkdownNotes/blob/main/ChangeInstallLocaltion/img/regedit.png)

<br/>

### 第二步 打开下面路径

计算机\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion

![Regedit Edit](https://github.com/xiaolanlaia/MarkdownNotes/blob/main/ChangeInstallLocaltion/img/regedit_edit.png)

<br/>

> **保存注册表**

修改文件之前，先备份一下，养成好习惯，选择 **导出** 将注册表导出到任意位置

![Regedit Edit](https://github.com/xiaolanlaia/MarkdownNotes/blob/main/ChangeInstallLocaltion/img/regedit_save.png)

<br/>

### 第三步 修改注册表

![Regedit Edit](https://github.com/xiaolanlaia/MarkdownNotes/blob/main/ChangeInstallLocaltion/img/regedit_revise.png)

<br/>

修改以下三个文件夹：  ProgramFilesDir (x86)、ProgramFilesPath、ProgramW6432Dir

选中双击进入修改

![Regedit Edit](https://github.com/xiaolanlaia/MarkdownNotes/blob/main/ChangeInstallLocaltion/img/regedit_path.png)

<br/>

将 **数值数据(V)** 的值改为自己软件安装盘符的路径（通常为D盘），点击确定

![Regedit Edit](https://github.com/xiaolanlaia/MarkdownNotes/blob/main/ChangeInstallLocaltion/img/regedit_path_change.png)

<br/>

三个路径都修改完成后就可以进行软件安装，我是安装了Chrome和office这两个默认会安装到C盘的软件

### 第四步 安装软件

安装软件

![Regedit Edit](https://github.com/xiaolanlaia/MarkdownNotes/blob/main/ChangeInstallLocaltion/img/software_d.jpg)

<br/>

可以看到，软件成功安装在了D盘

### 第五步 恢复注册表

如果不是很懂电脑的大佬，建议还是不要随意修改电脑的系统配置，所以安装完软件后还是建议将注册表恢复。
恢复的方法可以在刚才修改注册表的界面再次修改，也可以双击刚才修改之前备份的注册表自动修改

注册表恢复后，建议重启一下电脑，然后打开软件查看是否可以使用


### **一些注意的点**

<br/>

> 1、在修改注册表路径后，在安装软件过程中，打开其他软件可能会出现无法打开或者弹窗报错的情况，
> 正是因为修改了注册表可能导致之前安装的有些软件无法打开，等注册表恢复后就正常了

<br/>

> 2、安装完软件，恢复注册表，重启电脑后，可能会出现点击软件快捷方式无法打开软件，报错的情况

**解决方法：**

右键软件快捷方式进入属性，将 **属性 - 快捷方式** 中的 **目标(T)** 根路径从C盘改为安装的盘符

![Regedit Edit](https://github.com/xiaolanlaia/MarkdownNotes/blob/main/ChangeInstallLocaltion/img/software_d.jpg)

<br/>

点击确定后，再打开软件就正常了

**提示** ：有的软件，比如office安装后有多个软件的快捷方式（word、excel等），需要逐一修改

> 3、office安装后打开软件出现提示未经授权情况

不知道是否是必现的情况，我自己安装时是出现了，所以记录一下

**解决方法：**

打开任意一款office软件，进入 **文件 - 账户**，在更新选项中，立即更新一下就行了

**注意：** 更新时如果注册表的路径已经恢复了，还需要再修改一下再去更新office，
所以建议软件安装完先逐个打开一下看看有没有问题，再恢复注册表

> 4、不一定所有软件都能成功修改安装路径

发现修改此处的注册表安装路径也无法修改华为电脑管家的默认安装路径，不过有的破解软件
安装包是可以自定义选择安装路径，所以我想道理应该是跟修改注册表安装路径一样的道理，
可能只是修改的地方不一样。
