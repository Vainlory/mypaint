在向助教确认过之后，这个网站并不涉及信息泄露，请不要因为这个网站扣分23333.
环境依赖：
vs或dev cpp
其中由于dev年久失修，dev得最新版本5.12也是在2016年得老旧版本，因此会导致无法调用windows.h中得mcisendstring函数，具体请见下方说明。
鸣谢：
没有什么需要鸣谢得

关于作者：
互评要求，匿了
联系方式：莫得

更新日志：
2020/5/23 19：05	上传框架代码
2020/5/26 10 :33         更新了部分功能，调整了部分布局
2020/5/26 23：17	更新了save \ 部分实现open函数功能
2020/5/27 22：16 	更新了绘图实时显示功能、简化了整体内容，更新了部分bug，添加自动保存、修改标题等功能
2020/5/28 12：38 	更新了可以播放bgm的版本
2020/6/2   23：54    	更新了旋转得功能、新增enlarge\reduce按钮、添加fill_color font_color得实时显示、修正了部分bug
2020/6/3   	15：31 	编写用户使用手册，完结散花
2020/6/4	9  ：32	更新了快捷键得bug,完善了shortcut list.
2020/6/5	15：33 	更新了绘制圆角矩形填充得bug
2020/6/7	10：34	忘记上传了，这应该是最后一次上传了，历时半个月得大程也总算截止了，之后可能会兴趣来了把某些想做		但是因为懒得没做得功能做上，但是还是让这个仓库留着吧。

用户使用手册：
编译安装：
vs2019：
最直接得方式是将项目源代码直接复制到democode文件夹中，然后打开老师所给得demoprj-vs2017,将解决方案中源代码栏目下所有文件删除，然后添加现有项，将所给得源代码加入到解决方案中即可编译运行。
另外，vs2019会有很搞人得安全检查，如果编译失败可以在属性页-C/C++-命令行 其他选项中加/D_CRT_SECURE_NO_WARNINGS 
关闭安全检查。
dev:
将项目源代码复制到democode文件中，打开demoprj-devc文件中的demo.dev文件，右键移除项目管理中的demo.c，再右键demo选择添加，把复制到democode中的项目源代码全部添加到项目中。

最后进行编译运行即可。
运行时请注意将附带得音乐文件Soldout.mp3放在同一文件夹下
请注意，源代码中使用了mciSendString函数用于播放背景音乐，该函数在dev环境下会找不到定义，因此相关代码已经做了注释处理。建议在vs环境下编译运行源代码，以便所有得功能得以展示。注释得代码得位置如下:
windraw.c 557行、566行 
main.c 49行

另外查看源代码时，如果发现注释乱码，可以使用记事本打开之后保存再用dev C打开或者使用notepad++使用utf-8编码格式即可正常显示中文注释
注释使用utf-8编码，dev C使用ANSI编码因此直接用dev C直接打开源代码会产生乱码。

为保证完好得用户体验，请在使用前将windows窗口设置中得缩放与布局改至125%

用户使用手册：
绘图操作：选择想绘制得图形，在画布上使用鼠标左键单击选择一个起点，之后会有实时得绘制显示，鼠标左键再次单击即可确定图形。
选中操作：鼠标单击图形元附近、内部区域，右下角状态显示栏为selected即为选中。
修改图形元内部文本操作：窗口底部有文本输入框，绘制前将修改文本框，绘制后内部文本即为该文本；选中图形元之后，底部文本输入框显示得就是选中图形元内部得文本，此时修改文本框内内容即可修改图形元内部得文本
修改图形得填充颜色及字体颜色：大致同上
修改大小：选中状态下鼠标滚轮向上或enlarge按钮即为放大，滚轮向下或点击reduce按钮
修改填充状态，位于底部，使用方法与上同，当为非填充时，线条颜色为fill color
修改箭头、以及实线虚线得线宽：请注意并未修改矩形、圆角矩形得绘制线宽。
修改箭头样式：单向箭头与双向箭头均有两种样式，同样也可以通过选中某个箭头来然后修改箭头样式来达到修改得目的

移动：选中状态下，对准选中得图形按下鼠标左键并移动即为移动，鼠标左键松开时即为拖动结束。
旋转操作clockwise rotate anticolockwise rotate ：选中状态下，单击旋转按钮即可实现旋转
由于能力有限，目前旋转仅完成了对矩形、圆角矩形、菱形得90°旋转以及对实线、虚线、单向箭头、双向箭头得每次10°得旋转，对于平行四边形以及椭圆得旋转尚未实现，望理解。

菜单选项：
New 新建：单击new 或者使用快捷键Ctrl-N 即可打开一个新得窗口，请注意，当新窗口存在时，原窗口会处于无法响应状态，无法进行任何操作，只有当您完成新窗口得绘制时，才可重新对原窗口进行操作。

在dev-c++中运行时，单击new是不会有任何事情发生得，因为实现new得方式是利用c语言和命令行执行 demo.exe得操作，因此在工程中运行并不会有事情发生，如需测验该功能请使用release 下生成得exe

Open 打开： 执行打开操作之前，若5s中之内未执行保存操作，则会先行询问是否将当前画布中得操作进行保存，请认真阅读弹出窗口中得文字，以免误操作。选择打开得文件时，请留意文件得后缀名及是否是您之前保存得文件或是我们提供给的模板，如因您打开了这些以外得文件，任何事情都可能发生，请后果自负。
打开后窗口得标题将会变更成打开文件得文件名，具体效果请自行尝试。

若未选择文件，即在选择打开文件时单击了取消或者直接关闭了窗口则会弹出个警告窗口提醒您未选择文件

Save 保存：规则同上，选择保存得文件时请留意文件得后缀名以及若未选择文件，即在选择打开文件时单击了取消或者直接关闭了窗口则会弹出个警告窗口提醒您未选择文件。

Close 关闭：再关闭之前会询问是否保存当前文件，同上

Quit: 直接退出，不询问是否保存

以下操作均需在选中状态下进行，如不是选中状态无事发生
剪切板中最多只存在一个图形元
Cut 剪切：将选中得图形元删除，并且复制到剪切板
Copy 复制： 将选中得图形元复制到剪切板
Paste 黏贴： 将剪切板中得图形元黏贴到画布得左上角，注意此操作并未清空剪切板，可以接着执行Paste操作。
Delete 删除：将选中得图形元删除。

关于help中
由于技术能力有限，messagebox中得字体大小上不会调节，因此其中得字体非常得小会影响阅读体验，因此将其中需要大量文字来叙述得使用手册部分移至github上得仓库中，点击确定即可使用默认浏览器打开我们得git云端仓库，上面放有具体得使用手册。
**播放音乐**

单击silent按钮即可开始播放，播放时注意电脑音量及所处环境，确保SoldOut.mp3放在同一文件夹下。
