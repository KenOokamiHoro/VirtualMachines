---
description: 所以虚拟机软件哪里可以用？
---

# 操作系统虚拟化软件的常见场景

## TL;DR 

简单来说的话，咱能想到的有这些场景：

* 体验和学习新环境，不用担心没有合适的硬件或者搞坏物理系统
* 运行其它系统中的软件
* 简化系统的迁移和维护
* 保护隐私和安全（试用 or 隔离危险的软件、隔离身份、搭建蜜罐等等）
* 搭建开发和测试环境

## 体验和学习不同的环境

* 例如汝想怀旧的时候，手边没有合适的硬件的话，可以通过运行某些模拟器来尝试。
* 或者汝有兴趣学习一个新的环境的时候（例如开始学习 GNU/Linux 使用的 Windows 用户），可以先考虑把新环境装在虚拟机中。然后就开始随便折腾吧，哪怕里面腥风血雨，汝的物理环境还是一切如常。

## **同时运行其它系统中的软件**

这个就简单了吧，例如在 macOS 上运行只有 Windows 上能用的某些软件。如果只用多重引导的话，一次只能运行一个系统中的软件，而用上虚拟机以后就可以一起开啦……

## 简化系统的迁移和维护

因为虚拟机在物理机上就相当于几个文件，于是主机更换或升级的时候只要把虚拟机文件带到新的主机上再启动基本上就 OK 啦，备份也是相同的原理。

而主机如果出现意外（例如系统或硬件需要更换的时候），只要从备份把虚拟机文件拿回来，再在主机上更新或者重新安装虚拟机软件以后，一切就又回归平静啦（大概吧……）

> 所以啥时候虚拟机的图形性能可以带动大型 3D 游戏咧？这样几乎所有的操作就能在虚拟机里完成了耶……（汝是不是想和咱说那啥显卡直通？）

## 保护隐私和安全

* 例如汝要尝试一些来历不明或者危险的软件的时候（例如年代久远来源不可考、没签名、病毒样本或者某国特色等等）。
* 或者汝开始做一些不想被亲近的人知道的事情的时候，可以把和那件事相关的账户和文件啥的都装在一台虚拟机里（当然仅仅用上虚拟机在某些时候是不够的，汝有可能需要某些[其它技巧](https://program-think.blogspot.com/2010/04/howto-cover-your-tracks-0.html#index)）。

## 搭建开发和测试环境

* 例如汝因为生计所迫在汝不常用的平台上开发软件 or 服务（例如要在 GNU/Linux 上架设网站的 Windows 用户，反之亦然？），汝可以把汝开发需要的系统、软件和工具等等装进虚拟机里。开发的时候用，平常还是继续原来的生活（？）。
* 如果汝要针对不同的目标环境进行测试，不巧这些环境还相互冲突的时候（例如不同版本的浏览器、操作系统内核等等）。汝可以安装好几个有不同版本的虚拟机来一起测试。
* 好几个人一起开发软件的时候，大家的电脑上的配置可能会千差万别。为了避免因为这些差别导致的测试结果差异进而开始扯皮，可以给大家装上同样的虚拟机作为测试环境。如果有必要的话，还可以在某个初始状态设置一个快照，确保每次的测试环境都相同。

（未完待续？）



