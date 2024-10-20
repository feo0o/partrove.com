---
title: 【教程】ShareX 截图自动添加背景
date: 2024-10-21T09:24:57+08:00
lastmod: 2024-10-21T09:24:57+08:00
author: ParTrove
cover: https://gn-img-a1.partrove.com/common/cover/tutorials-sharex-background-effect.png
categories:
  - 教程
tags:
  - 软件
  - Windows
draft: false
---


ShareX 是 Windows 系统下一款非常强大的截图软件，它除了常规的截图功能之外，还具备截图后自动添加特效以及给快捷键绑定不同截图效果等高级功能。  

<!--more-->

下面我们就介绍如何使用这两个高级功能，配置 ShareX 使其在截图后自动添加渐变背景，并且通过配置快捷键，使不同快捷键截出的图片拥有不同的背景效果。  

## 最终效果  

先来看一下配置完成后的最终效果。  

**常规截图（快捷键：Ctrl+Alt+S）**  

![c1s1](https://gn-img-a1.partrove.com/articles/illustrations/sharex/c1s1.png)  

**透明背景（快捷键：Ctrl+Alt+T）**  

![c1s2](https://gn-img-a1.partrove.com/articles/illustrations/sharex/c1s2.png)  

**渐变背景（快捷键：Ctrl+Alt+G）**  

![c1s3](https://gn-img-a1.partrove.com/articles/illustrations/sharex/c1s3.png)  

## 安装特效插件  

ShareX 官方有个图像特效页面 [Image effects](https://getsharex.com/image-effects)，先从这个页面下载我们需要的 [Background gradient](https://getsharex.com/image-effects/BackgroundGradient.sxie) 插件，然后双击打开下载的插件，会弹出提示启用图像效果，选择“是”。  

![c2s1](https://gn-img-a1.partrove.com/articles/illustrations/sharex/c2s1.png)  
## 配置项说明  

打开 ShareX 的 ***任务设置*** ，依次点击 ***图像*** —— ***特效*** —— ***图像特效配置*** ，打开特效配置界面。  

![c3s1](https://gn-img-a1.partrove.com/articles/illustrations/sharex/c3s1.png)  

在最左边特效列表里选中 BackgroundGradient，对应右边可配置的项目依次如下：  

### Rounded corners  

让截图的四个角呈现出圆角效果。  

**CornerRadius**  

圆角半径，数值越大则呈现出的圆弧越大，反之则四角越“尖”。  
### Shadow  

截图背景的阴影效果。  

**Opacity**  

阴影的透明度，取值范围 0-1，数值越大越不透明，阴影越明显。  

**Size**  

阴影区域的范围，数值越大的话，使用特效后往截图周围添加的阴影范围越大，从而使最终输出的图片尺寸越大。  
这里要注意，调大阴影数值的时候，在预览界面看到原始截图会缩小，但实际上是不影响原始截图大小的。  

**Darkness**  

阴影浓度，数值越大阴影效果越浓厚。  

**Color**  

阴影颜色。

**Offset**  

偏移量，也就是调整阴影显示的方向。X 是在水平方向显示阴影，负数时阴影显示在左边，正数显示在右边，Y 则是在垂直方向显示阴影，负数显示在上边，正数显示在下边。数值的绝对值越大，阴影面积越大。  

**AutoResize**  

这里暂时没搞明白配置项的具体意义，建议选择 True，如果选 False 的话，上面的配置项都不会有效果。
### Canvas  

画布相关的配置，也就是特效往原始截图周围添加的额外区域。  

**Margin**  

四周的留白宽度，注意这里的宽度会跟上面的 Offset 相叠加，例如 Offset 配置了 Y:10，这里再配置 Bottom:10，那么底部总的宽度就是 20。  

**MarginMode**  

留白宽度的计算方式，AbsoluteSize 按数值计算，PercentageOfCanvas 按百分比计算。  

**Color**  

画布颜色，也就是最底层的颜色。
### Background  

相对于原始图片，特效添加的背景。

**Color**  

背景颜色，只有在下面的 UseGradient 选择 False 时才生效。  

**UseGradient**  

是否使用渐变色。  

**Gradient**  

渐变配置，只有上面的 UseGradient 选择 True 时才生效。点开选项框后面的小按钮，可以打开渐变配置界面，在这里可以选择软件内置的渐变预设，也可以添加自己的渐变配置。

![c3s2](https://gn-img-a1.partrove.com/articles/illustrations/sharex/c3s2.png)  
## 配置快捷键  

知道了所有配置项的意义，那么现在就来实战配置三个快捷键，实现最开始展示的三个最终效果。  

这里先说个小知识，ShareX 是支持为每个快捷键定制一套单独配置项的，具体就是在快捷键配置里面的 覆盖xxx，不覆盖就使用全局配置，覆盖就保存单独的配置。

**常规截图**  

先打开 ShareX 的快捷键设置，默认配置里有个 ***截图矩形区域*** ，点击最右边的快捷键设置按钮，按下键盘按键即可设置成想要的快捷键，例如 Ctrl+Alt+S。

![c4s1](https://gn-img-a1.partrove.com/articles/illustrations/sharex/c4s1.png)  

然后再点击中间的设置按钮，在弹出的设置界面中选择 ***任务*** ，再勾选 ***覆盖”截图后“设置*** ，然后在下面的下拉框中取消添加图像特效（点一下，字体从加粗变成普通的就是取消了）。  

![c4s2](https://gn-img-a1.partrove.com/articles/illustrations/sharex/c4s2.png)  

软件会自动保存配置，设置完成后关掉界面即可。  

**透明背景**  

在快捷键设置页面，点击顶部的 添加 按钮新增一个快捷键，然后在新加的快捷键左边按钮依次选  ***屏幕截图*** —— ***截图矩形区域*** 。同样再点最右边按钮设置快捷键，例如 Ctrl+Alt+T。  

点击中间的设置按钮，先在 ***任务*** —— ***覆盖”截图后“设置*** 里面，选上添加图像特效。  

然后先勾选 ***图像*** —— ***覆盖图像设置*** ，再打开 ***特效*** —— ***图像特效配置*** ，然后在弹出的特效界面选择 BackgroundGradient ，依次调整以下配置项：  

- Background —— Color 设置成透明；  
- Background —— UseGradient 设置成 False。

关闭保存即可（注意要先选择上 BackgroundGradient 这个特效再关闭，不要选到别的特效上了）。

![c4s3](https://gn-img-a1.partrove.com/articles/illustrations/sharex/c4s3.png)  

**渐变背景**  

设置流程跟透明背景的一样，也是先新增一个快捷键，例如绑定为 Ctrl+Alt+G。  

然后也是进入到特效配置界面，依次调整一下配置项：  

- Background —— UseGradient 设置成 True；  
- Background —— Gradient 选择一个中意的渐变效果。  

关闭保存。  

![c4s4](https://gn-img-a1.partrove.com/articles/illustrations/sharex/c4s4.png)    

至此三个效果的快捷键都配置完成，按下对应快捷键就可以截出相应效果的背景图了。  

![c4s5](https://gn-img-a1.partrove.com/articles/illustrations/sharex/c4s5.png)  