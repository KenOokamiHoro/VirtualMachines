---
description: 那么多虚拟机软件我该选哪一个？
---

# 操作系统虚拟化软件的选择

随着虚拟化技术的发展，虚拟机软件也像雨后春笋一样冒出了一大把，那到底哪个适合自己呢？

## 提前公布答案

因为 VirtualBox 是为数不多的开源软件（虽然某些部份是私有的），Host 和 Guest 都支持主流的三大桌面系统（Windows / macOS / GNU/Linux ） ，性能还 OK ，于是就它了 ……

~~主要是没钱.webp.png~~

## 常见的虚拟机软件

* Xen 通过一种叫做半虚拟化的技术获得高效能的表现，甚至在某些与传统虚拟技术不友好的架构上（如x86），Xen也有极佳的表现。但是这要求虚拟机使用经过修改的客户端操作系统。
* **基于内核的虚拟机**（英语：**K**ernel-based **V**irtual **M**achine，缩写为 **KVM**）是一种用于Linux 内核中的虚拟化基础设施，可将Linux内核转化为一个虚拟机监视器。
* QEMU 通过动态的二进制转换模拟 CPU，并且提供一组设备模型，使它能够运行多种未修改的客户机 OS，可以通过与 KVM 一起使用进而接近本地速度运行虚拟机（接近真实电脑的速度）。
* VMware 虚拟机软件是由 VMware 公司开发的一系列虚拟机软件，既有面向桌面，属于 Type 2 类型的 VMware Workstation / VMware Fusion，也有属于 Type 1 类型的 VMware ESXi 等等。
* Windows 上还有微软半路收购来的 Microsoft Virtual PC （Windows XP - Vista），主要用来模拟 Windows XP 的 Windows Virtual PC（Windows 7），和~~船~~全新的 Hyper-V （Windows Server 2008 和 Windows 8 开始）
* macOS 上的话，最出名的应该是 Parallels Desktop，主打 macOS 和 Windows 虚拟机之间的无缝衔接。
* 而从 Innotek 卖到 Orcale 的 Orcale VirtualBox 大概是为数不多的跨 Host OS 众多（也没有多到哪里去啦， Windows / macOS / GNU/Linux 和 Orcale 自家的 Solaris）而且还部份开源的虚拟机软件了……

## 不同的 Host OS 的支持程度

> 对于 Type 1 类型的虚拟机软件而言，因为基本上都是跟着一个操作系统一起安装的，多半不用考虑这个问题……  （例如 Xen）

这个当然要看汝现在在用的 Host OS 啦，例如：

* KVM 既然叫做基于内核的虚拟机嘛，那就肯定只支持 GNU/Linux 做 Host OS 啦，可能还需要定制的内核。
* Parallels 其实之前做过面向 Windows 的 Parallels Workstation，奈何打不过对手凉了…… 于是就剩专精 macOS 的 Parallels Desktop 啦。
* Windows Virtual PC 和 Hyper-V 既然是微软自己家的，自然只支持 Windows 做 Host OS。（以及作为 Type 1 类型的虚拟机， Hyper-V 神奇的会使其它 Type 2 类型的虚拟机软件停止工作，[例如 VMware](https://blogs.vmware.com/workstation/2019/08/workstation-hyper-v-harmony.html) 。

## 不同的 Guest OS 的支持程度

这个当然要看汝想装的 Guest OS 是什么啦，流行的几个虚拟机软件基本上都支持常见的三大系统做 Guest OS，虽然可能性能和稳定性等等略有差异……

## 支持的功能

除了之前提到的功能以外，这个就比较见仁见智啦。可能有些倾向系统间的协作（例如文件交换），有些又倾向安全性（例如隔离和加密），还有些比较注重某一方面的性能（例如图形性能），或者注意支持的虚拟硬盘/光盘格式（方便更换软件）等等……

## 无责任瞎总结

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x8F6F;&#x4EF6;</th>
      <th style="text-align:left">&#x4F18;&#x52BF;</th>
      <th style="text-align:left">&#x52A3;&#x52BF;</th>
      <th style="text-align:left">&#x9002;&#x7528;&#x4EBA;&#x7FA4; or &#x573A;&#x666F;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Hyper-V</td>
      <td style="text-align:left">
        <p>&#x5FAE;&#x8F6F;&#x5B98;&#x65B9;&#x51FA;&#x54C1;</p>
        <p>&#x652F;&#x6301;&#x52A8;&#x6001;&#x5185;&#x5B58;&#x5206;&#x914D;</p>
      </td>
      <td style="text-align:left">
        <p>&#x53EA;&#x4E0E; Windows Professional &#x6216; Windows Server &#x4E00;&#x540C;&#x63D0;&#x4F9B;&#xFF1B;</p>
        <p>&#x574A;&#x95F4;&#x4F20;&#x95FB;&#x5BF9;&#x4E8E; Linux &#x652F;&#x6301;&#x6781;&#x5DEE;&#xFF1B;</p>
        <p>&#x548C;&#x5176;&#x5B83;&#x865A;&#x62DF;&#x673A;&#x8F6F;&#x4EF6;&#x4E0D;&#x517C;&#x5BB9;&#xFF08;&#x76EE;&#x524D;&#xFF09;</p>
      </td>
      <td style="text-align:left">&#x5BF9;&#x4E8E;&#x51E0;&#x4E4E;&#x53EA;&#x60F3;&#x5728; Windows &#x673A;&#x5668;&#x4E0A;&#x865A;&#x62DF;
        Windows &#x7684;&#x4EBA;</td>
    </tr>
    <tr>
      <td style="text-align:left">[QEMU/]KVM</td>
      <td style="text-align:left">
        <p>&#x81EA;&#x7531;&#x7684;&#x5F00;&#x6E90;&#x8F6F;&#x4EF6;</p>
        <p>&#x865A;&#x62DF; GNU/Linux &#x6548;&#x7387;&#x9AD8;</p>
      </td>
      <td style="text-align:left">
        <p>&#x53EA;&#x652F;&#x6301; GNU/Linux &#x505A; Host OS</p>
        <p>&#x5B89;&#x88C5;&#x548C;&#x914D;&#x7F6E;&#x7565;&#x7E41;&#x7410;&#xFF08;&#x4F7F;&#x7528;&#x67D0;&#x4E9B;&#x7BA1;&#x7406;&#x8F85;&#x52A9;&#x5DE5;&#x5177;&#x53EF;&#x4EE5;&#x7F13;&#x89E3;&#xFF09;</p>
        <p>&#x865A;&#x62DF; Windows &#x65F6;&#x6548;&#x7387;&#x548C;&#x786C;&#x4EF6;&#x517C;&#x5BB9;&#x6027;&#x4F4E;</p>
      </td>
      <td style="text-align:left">&#x73B0;&#x6709;&#x7684; GNU/Linux &#x65E5;&#x5E38;&#x7528;&#x6237;</td>
    </tr>
    <tr>
      <td style="text-align:left">Parallels Desktop</td>
      <td style="text-align:left">
        <p>&#x652F;&#x6301; macOS &#x7684;&#x5927;&#x591A;&#x6570;&#x7279;&#x6027;</p>
        <p>&#x865A;&#x62DF; Windows &#x65F6;&#x65E0;&#x7F1D;&#x7A0B;&#x5EA6;&#x9AD8;</p>
      </td>
      <td style="text-align:left">&#x53EA;&#x652F;&#x6301; macOS &#x505A; Host OS</td>
      <td style="text-align:left">&#x73B0;&#x6709;&#x7684; macOS &#x65E5;&#x5E38;&#x7528;&#x6237;</td>
    </tr>
    <tr>
      <td style="text-align:left">VirtualBox</td>
      <td style="text-align:left">
        <p>&#x81EA;&#x7531;&#x7684;&#x5F00;&#x6E90;&#x8F6F;&#x4EF6;</p>
        <p>&#x652F;&#x6301;&#x591A;&#x79CD;&#x865A;&#x62DF;&#x786C;&#x76D8;&#x683C;&#x5F0F;</p>
        <p>&#x65B9;&#x4FBF;&#x4ECE;&#x5176;&#x4ED6;&#x5E73;&#x53F0;&#x8FC1;&#x79FB;</p>
        <p>&#x652F;&#x6301;&#x591A;&#x79CD;&#x5E38;&#x89C1;&#x64CD;&#x4F5C;&#x7CFB;&#x7EDF;&#x4F5C;&#x4E3A;
          Host OS&#x3002;</p>
      </td>
      <td style="text-align:left">
        <p>&#x5916;&#x89C2;&#x548C;&#x6027;&#x80FD;&#x7565;&#x5DEE;</p>
        <p>&#x5927;&#x90E8;&#x5206;&#x529F;&#x80FD;&#x9700;&#x8981;&#x5B89;&#x88C5;&#x79C1;&#x6709;&#x7684;&#x6269;&#x5C55;&#x5305;&#x3002;</p>
      </td>
      <td style="text-align:left">&#x9002;&#x7528;&#x4E8E;&#x770B;&#x91CD;&#x5F00;&#x6E90;&#x3001;&#x9690;&#x79C1;&#x3001;&#x548C;&#x5B89;&#x5168;&#x6027;&#x7684;&#x7528;&#x6237;&#x4EEC;</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>VMware &#xFF08;Player /</p>
        <p>Workstation /</p>
        <p>Fusion&#xFF09;</p>
      </td>
      <td style="text-align:left">&#x6027;&#x80FD;&#x548C;&#x7A33;&#x5B9A;&#x6027;&#x8F83;&#x597D;&#xFF0C;&#x652F;&#x6301;&#x7684;&#x865A;&#x62DF;&#x786C;&#x4EF6;&#x8F83;&#x4E30;&#x5BCC;&#x3002;</td>
      <td
      style="text-align:left">&#x514D;&#x8D39;&#x7248;&#x7684; Player &#x529F;&#x80FD;&#x9609;&#x5272;&#x4E25;&#x91CD;&#xFF08;&#x751A;&#x81F3;&#x4E0D;&#x652F;&#x6301;&#x5FEB;&#x7167;&#xFF09;&#x4ED8;&#x8D39;&#x7248;&#x4EF7;&#x683C;&#x7A0D;&#x8D35;</td>
        <td
        style="text-align:left">&#x5177;&#x6709;&#x652F;&#x4ED8;&#x610F;&#x613F;&#x4E0E;&#x652F;&#x4ED8;&#x80FD;&#x529B;&#xFF0C;&#x4E14;&#x975E;&#x5E38;&#x6CE8;&#x91CD;&#x865A;&#x62DF;&#x673A;&#x7684;&#x7A33;&#x5B9A;&#x6027;&#x548C;&#x6027;&#x80FD;&#x7684;&#x4EBA;</td>
    </tr>
  </tbody>
</table>







