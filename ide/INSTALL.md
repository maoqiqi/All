# 安装 IntelliJ IDEA

系统要求：https://www.jetbrains.com/help/idea/installation-guide.html

## 目录

* [Windows系统](#Windows系统)
* [Mac系统](#Mac系统)
* [Ubuntu系统](#Ubuntu系统)
* [Donate](#Donate)
* [About](#About)
* [License](#License)


## Windows系统

IntelliJ IDEA 的安装是非常简单的，不需要做过多的选择，可以说简单到都是 `Next` 即可。

![安装步骤截图](images/idea_first_install.jpg)

> * ① 表示在桌面上创建一个快捷图标，建议勾选上，方便我们在安装后定位 IntelliJ IDEA 安装目录。
> * ② 表示关联 Java 和 Groovy 文件，建议都不要勾选，正常我们在 Windows 的文件系统上打开这类文件都是为了快速查阅文件里面的内容，如果关联上之后，由于 IntelliJ IDEA 打开速度缓慢，不方便我们查看。
> * 建议在 Windows 系统上关联此类文件可以用 EmEditor、Notepad++ 这类轻便的编辑器。

已有旧版本安装新版本：

![已有旧版本安装新版本步骤截图](images/idea_repeatedly_install_1.jpg)

> * 上图，显示我目前电脑中已经有一个 IntelliJ IDEA 版本，如果我勾选了①，则表示安装之前会先卸载掉电脑上的旧版本。
> * 如果勾选了② ，则 IntelliJ IDEA 会直接安静地卸载旧版本，而旧版本的个性化设置不会被删除。
> * 在小版本迭代中建议是卸载掉旧版本的，然后再进行新版本安装，因为小版本迭代一般都是 Bug 的修复，保留旧版本没有多大意义。
> * 在大版本迭代中建议是保留旧版本，也就是不勾选上图①，IntelliJ IDEA 是支持一台电脑装多个版本的。

接下来的步骤我们假设勾选了①再进行安装：

![已有旧版本安装新版本步骤截图](images/idea_repeatedly_install_2.jpg)

> * 上图，由于上一步勾选了卸载旧版本选项，所以出现了选择删除旧版本的配置选项。
> * 第一个选项：删除旧版本的缓存和本地历史记录。
> * 第二个选项：删除旧版本的个人个性化设置。建议两个都不要勾选。
> * 点击 uninstall，进入全自动的卸载过程，卸载完成接下来的步骤跟首次安装一致。


## Mac系统

Mac下安装安装 IntelliJ IDEA 与安装其他软件一样，不在叙述。

> 目前的最新 IntelliJ IDEA 版本已经默认都是使用它自己带的 JDK 环境。

![使用自己的JDK](images/idea_mac_jdk.png)

如果你的 Mac 安装有多个 JDK，你想使用高版本的 JDK 运行 IntelliJ IDEA 可以按如下方式进行修改：

* 在 `应用程序` 中找到 `IntelliJ IDEA` 然后对此进行 `右键 > 显示包内容 > Contents > Info.plist`，效果如上图所示。
* 找到上图红圈标注的代码，修改 `JVMVersion` 的属性值，如果是 JDK 7，则改为 `1.7*`。如果是 JDK 8，则改为 `1.8*`。


## Ubuntu系统



## Donate

感谢您的耐心阅读，如果您发现文章中有一些没表述清楚的，或者是不对的地方，请给我留言，你的鼓励是作者写作最大的动力。

如果您认为本文质量不错，读后觉得收获很大，不妨小额赞助我一下，让我更有动力继续写出高质量的文章。


## About

* **作者**：March
* **邮箱**：fengqi.mao.march@gmail.com
* **码云**：https://gitee.com/maofengqi
* **头条**：https://toutiao.io/u/425956/subjects
* **简书**：https://www.jianshu.com/u/02f2491c607d
* **掘金**：https://juejin.im/user/5b484473e51d45199940e2ae
* **知乎**：http://zhihu.com/people/maofengqi
* **豆瓣**：https://www.douban.com/people/maofengqi/
* **CSDN**：http://blog.csdn.net/u011810138
* **Github**：https://github.com/maoqiqi
* **开源中国**：https://my.oschina.net/maoqiqi
* **喜马拉雅听书**：https://www.ximalaya.com/zhubo/31419312/
* **SegmentFault**：https://segmentfault.com/u/maoqiqi
* **StackOverFlow**：https://stackoverflow.com/users/8223522


## License

```
   Copyright 2019 maoqiqi

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```