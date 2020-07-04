# GitHub 搜索技巧

> 还在为自学时找不到适合练手的项目而苦恼？
>
> 还在好奇别人是如何在GitHub众多项目中找到高质量代码的？
>
> 真的是因为他们独具慧眼吗？
>
> 不，其实他们只是掌握了正确的搜索方法。
>
> 下面介绍几种常用的GitHub高级搜索方法，相信你看完之后也能很快在GitHub众多项目中找到自己所需的项目。

先上[Github官网介绍搜索语法的文档](https://docs.github.com/cn/github/searching-for-information-on-github)，此文档为Github官网介绍搜索语法的文档，提供各种语言版本，比如中文。


## 目录

* [目录](#目录)
* [了解搜索语法](#了解搜索语法)
   * [查询大于或小于另一个值的值](#查询大于或小于另一个值的值)
   * [查询范围之间的值](#查询范围之间的值)
   * [排除特定结果](#排除特定结果)
   * [使用用户名的查询](#使用用户名的查询)
* [排序搜索结果](#排序搜索结果)
* [使用可视界面搜索](#使用可视界面搜索)
* [常用搜索](#常用搜索)
   * [按星号数量搜索](#按星号数量搜索)
   * [按关注者数量搜索](#按关注者数量搜索)
   * [按复刻数量搜索](#按复刻数量搜索)
   * [按仓库创建或上次更新时间搜索](#按仓库创建或上次更新时间搜索)
   * [按位置搜索](#按位置搜索)
   * [按语言搜索](#按语言搜索)
   * [按主题搜索](#按主题搜索)
   * [按主题数量搜索](#按主题数量搜索)
   * [按仓库名称、说明或自述文件内容搜索](#按仓库名称说明或自述文件内容搜索)
   * [按文件内容或文件路径搜索](#按文件内容或文件路径搜索)
   * [按文件名搜索](#按文件名搜索)
   * [按文件扩展名搜索](#按文件扩展名搜索)
   * [按文件位置搜索](#按文件位置搜索)
   * [在用户或组织的仓库内搜索](#在用户或组织的仓库内搜索)
   * [仅搜索用户或组织](#仅搜索用户或组织)
   * [按用户拥有的仓库数量搜索](#按用户拥有的仓库数量搜索)
   * [按仓库大小搜索](#按仓库大小搜索)
   * [按许可搜索](#按许可搜索)
   * [按公共或私有仓库搜索](#按公共或私有仓库搜索)
   * [基于仓库是否为镜像搜索](#基于仓库是否为镜像搜索)
   * [基于仓库是否已存档搜索](#基于仓库是否已存档搜索)
   * [基于具有 good first issue 或 help wanted 标签的议题数量搜索](#基于具有-good-first-issue-或-help-wanted-标签的议题数量搜索)
   * [搜索 wiki](#搜索-wiki)
* [一些有趣的搜索](#一些有趣的搜索)
* [补充](#补充)
   * [awesome 加强搜索](#awesome-加强搜索)
   * [高亮显示某一行代码](#高亮显示某一行代码)
   * [项目内搜索](#项目内搜索)
* [Donate](#donate)
* [About](#about)
* [License](#license)


## 了解搜索语法

搜索 GitHub 时，您可以构建匹配特定数字和单词的查询。

### 查询大于或小于另一个值的值

您可以使用 >、>=、< 和 <= 搜索大于、大于等于、小于以及小于等于另一个值的值。

* `>n` [cats stars:>1000](https://github.com/search?utf8=%E2%9C%93&q=cats+stars%3A%3E1000&type=Repositories) 匹配含有 "cats" 字样、星标超过 1000 个的仓库。
* `>=n` [cats topics:>=5](https://github.com/search?utf8=%E2%9C%93&q=cats+topics%3A%3E%3D5&type=Repositories) 匹配含有 "cats" 字样、有 5 个或更多主题的仓库。
* `<n` [cats size:<10000](https://github.com/search?utf8=%E2%9C%93&q=cats+size%3A%3C10000&type=Code) 匹配小于 10 KB 的文件中含有 "cats" 字样的代码。
* `<=n` [cats stars:<=50](https://github.com/search?utf8=%E2%9C%93&q=cats+stars%3A%3C%3D50&type=Repositories) 匹配含有 "cats" 字样、星标不超过 50 个的仓库。

您还可以使用范围查询搜索大于等于或小于等于另一个值的值。

* `n..*` [cats stars:<=50](https://github.com/search?utf8=%E2%9C%93&q=cats+stars%3A10..*&type=Repositories) 等同于 stars:>=10 并匹配含有 "cats" 字样、有 10 个或更多星号的仓库。
* `*..n` [cats stars:*..10](https://github.com/search?utf8=%E2%9C%93&q=cats+stars%3A%22*..10%22&type=Repositories) 等同于 stars:<=10 并匹配含有 "cats" 字样、有不超过 10 个星号的仓库。

### 查询范围之间的值

您可以使用范围语法 n..n 搜索范围内的值，其中第一个数字 n 是最低值，而第二个是最高值。

* `n..n` [cats stars:10..50](https://github.com/search?utf8=%E2%9C%93&q=cats+stars%3A10..50&type=Repositories) 匹配含有 "cats" 字样、有 10 到 50 个星号的仓库。

### 排除特定结果

* `NOT` [hello NOT world](https://github.com/search?q=hello+NOT+world&type=Repositories) 匹配含有 "hello" 字样但不含有 "world" 字样的仓库。
* `-QUALIFIER` [cats stars:>10 -language:javascript](https://github.com/search?q=cats+stars%3A%3E10+-language%3Ajavascript&type=Repositories) 匹配含有 "cats" 字样、有超过 10 个星号但并非以 JavaScript 编写的仓库。

**对带有空格的查询使用引号**

如果搜索含有空格的查询，您需要用引号将其括起来。 例如：

* [cats NOT "hello world"](https://github.com/search?utf8=%E2%9C%93&q=cats+NOT+%22hello+world%22&type=Repositories) 匹配含有 "cats" 字样但不含有 "hello world" 字样的仓库。
* [build label:"bug fix"](https://github.com/search?utf8=%E2%9C%93&q=build+label%3A%22bug+fix%22&type=Issues) 匹配具有标签 "bug fix"、含有 "build" 字样的议题。

某些非字母数字符号（例如空格）会从引号内的代码搜索查询中删除，因此结果可能出乎意料。

### 使用用户名的查询

如果搜索查询包含需要用户名的限定符，例如 user、actor 或 assignee，您可以使用任何 GitHub 用户名指定特定人员，或使用 @me 指定当前用户。

* `QUALIFIER:USERNAME` [author:nat](https://github.com/search?q=author%3Anat&type=Commits) 匹配 @nat 创作的提交。
* `QUALIFIER:@me` [is:issue assignee:@me](https://github.com/search?q=is%3Aissue+assignee%3A%40me&type=Issues) 匹配已分配给结果查看者的议题

**@me 只能与限定符一起使用，而不能用作搜索词，例如 @me main.workflow。**


## 排序搜索结果

您可以使用 Sort（排序）菜单或通过将 sort 限定符添加到查询来排序 GitHub 搜索结果。

使用 Sort（排序）菜单可按相关性、星号数量、复刻数量以及项目最近更新时间来排序结果。

要按交互、反应、作者日期、提交者日期或项目最近更新时间来排序，您可以将 sort 限定符添加到搜索查询。

* 按交互排序 `sort:interactions` 限定符按最高反应和评论总数排序。
* 按反应排序 `sort:reactions` 限定符按反应数量或类型排序。
* 按作者日期排序 `sort:author-date` 限定符按作者日期降序或升序排序。
* 按提交者日期排序 `sort:committer-date` 限定符按提交者日期降序或升序排序。
* 按更新日期排序 `sort:updated` 限定符按项目最近更新日期排序。

参考链接：https://docs.github.com/cn/github/searching-for-information-on-github/sorting-search-results


## 使用可视界面搜索

可以使用 [搜索](https://github.com/search) 页面 或 [高级搜索](https://github.com/search/advanced) 页面 搜索 GitHub。

高级搜索 页面 提供用于构建搜索查询的可视界面。 您可以按各种因素过滤搜索，例如仓库具有的星标数或复刻数。 在填写高级搜索字段时，您的查询将在顶部搜索栏中自动构建。


## 常用搜索

### 按星号数量搜索

`stars:n` [stars:500](https://github.com/search?utf8=%E2%9C%93&q=stars%3A500&type=Repositories) 匹配恰好具有 500 个星号的仓库。

### 按关注者数量搜索

`followers:n` [node followers:>=10000](https://github.com/search?q=node+followers%3A%3E%3D10000) 匹配有 10,000 或更多关注者提及文字 "node" 的仓库。

### 按复刻数量搜索

`forks:n` [forks:5](https://github.com/search?q=forks%3A5&type=Repositories) 匹配只有 5 个复刻的仓库。

### 按仓库创建或上次更新时间搜索

`created:YYYY-MM-DD` [webos created:<2011-01-01](https://github.com/search?q=webos+created%3A%3C2011-01-01&type=Repositories) 匹配具有 "webos" 字样、在 2011 年之前创建的仓库。
`pushed:YYYY-MM-DD` [css pushed:>2013-02-01](https://github.com/search?utf8=%E2%9C%93&q=css+pushed%3A%3E2013-02-01&type=Repositories) 匹配具有 "css" 字样、在 2013 年 1 月之后收到推送的仓库。

### 按位置搜索

`location:LOCATION` [repos:1 location:iceland](https://github.com/search?q=repos%3A1+location%3Aiceland&type=Users) 匹配恰好有一个仓库位于冰岛的用户。

### 按语言搜索

`language:LANGUAGE` [org:mozilla language:markdown](https://github.com/search?utf8=%E2%9C%93&q=org%3Amozilla+language%3Amarkdown&type=Code) 匹配标记为 Markdown 且来自所有 @mozilla 仓库的代码。

### 按主题搜索

`topic:TOPIC` [topic:jekyll](https://github.com/search?utf8=%E2%9C%93&q=topic%3Ajekyll&type=Repositories&ref=searchresults) 匹配已归类为 "jekyll" 主题的仓库。

### 按主题数量搜索

`topics:n` [topics:5](https://github.com/search?utf8=%E2%9C%93&q=topics%3A5&type=Repositories&ref=searchresults) 匹配具有五个主题的仓库。

### 按仓库名称、说明或自述文件内容搜索

通过 in 限定符，您可以将搜索限制为仓库名称、仓库说明、自述文件内容或这些的任意组合。 如果省略此限定符，则只搜索仓库名称和说明。

`in:name` [jquery in:name](https://github.com/search?q=jquery+in%3Aname&type=Repositories) 匹配其名称中含有 "jquery" 的仓库。
`in:description` [jquery in:name,description](https://github.com/search?q=jquery+in%3Aname%2Cdescription&type=Repositories) 匹配其名称或说明中含有 "jquery" 的仓库。
`in:readme` [jquery in:readme](https://github.com/search?q=jquery+in%3Areadme&type=Repositories) 匹配其自述文件中提及 "jquery" 的仓库。
`repo:owner/name` [repo:octocat/hello-world](https://github.com/search?q=repo%3Aoctocat%2Fhello-world) 匹配特定仓库名称。

### 按文件内容或文件路径搜索

使用 in 限定符，您可以将搜索限制为源代码文件的内容、文件路径或两者。 如果省略此限定符，则只搜索文件内容。

`in:file` [octocat in:file](https://github.com/search?q=octocat+in%3Afile&type=Code) 匹配文件内容中出现 "octocat" 的代码。
`in:path` [octocat in:path](https://github.com/search?q=octocat+in%3Apath&type=Code) 匹配文件路径中出现 "octocat" 的代码。
`in:file,path` [octocat in:file,path](https://github.com/search?q=octocat+in%3Afile%2Cpath&type=Code) 匹配文件内容或文件路径中出现 "octocat" 的代码。

### 按文件名搜索

`filename:FILENAME` [filename:test_helper path:test language:ruby](https://github.com/search?q=minitest+filename%3Atest_helper+path%3Atest+language%3Aruby&type=Code) 匹配 test 目录内名为 test_helper 的 Ruby 文件。

### 按文件扩展名搜索

`extension:EXTENSION` [icon size:>200000 extension:css](https://github.com/search?utf8=%E2%9C%93&q=icon+size%3A%3E200000+extension%3Acss&type=Code) 匹配大于 200 KB、以 .css 结尾且含有 "icon" 字样的文件。

### 按文件位置搜索

您可使用 path 限定符搜索仓库中特定位置显示的源代码。 使用 path:/ 可搜索位于仓库根目录级别的文件。 或者，指定目录名称或目录路径以搜索位于该命令或其任何子目录中的文件。

`path:/` [octocat filename:readme path:/](https://github.com/search?utf8=%E2%9C%93&q=octocat+filename%3Areadme+path%3A%2F&type=Code) 匹配位于仓库根目录级别且含有 "octocat" 字样的 readme 文件。
`path:DIRECTORY` [form path:cgi-bin language:perl](https://github.com/search?q=form+path%3Acgi-bin+language%3Aperl&type=Code) 匹配位于 cgi-bin 目录或其任何子目录中且含有 "form" 字样的 Perl 文件。
`path:PATH/TO/DIRECTORY` [console path:app/public language:javascript](https://github.com/search?q=console+path%3A%22app%2Fpublic%22+language%3Ajavascript&type=Code) 匹配 app/public 目录或其任何子目录（即使其位于 app/public/js/form-validators 中）中且含有 "console" 字样的 JavaScript 文件。

### 在用户或组织的仓库内搜索

要在特定用户或组织拥有的所有仓库中搜索代码，您可以使用 user 或 org 限定符。 要在特定仓库中搜索代码，您可以使用 repo 限定符。

`user:USERNAME`	[user:defunkt extension:rb](https://github.com/search?q=user%3Agithub+extension%3Arb&type=Code) 匹配来自 @defunkt、以 .rb 结尾的代码。
`org:ORGNAME` [org:github extension:js](https://github.com/search?utf8=%E2%9C%93&q=org%3Agithub+extension%3Ajs&type=Code) 匹配来自 GitHub、以 .js 结尾的代码。
`repo:USERNAME/REPOSITORY` [repo:mozilla/shumway extension:as](https://github.com/search?q=repo%3Amozilla%2Fshumway+extension%3Aas&type=Code) 匹配来自 @mozilla 的 shumway 项目、以 .as 结尾的代码。

### 仅搜索用户或组织

`type:user`	[mike in:name created:<2011-01-01 type:user]() 匹配 2011 年之前创建、名为 "mike" 的个人帐户。
`type:org` [data in:email type:org]() 匹配其电子邮件中含有 "data" 字样的组织。

### 按用户拥有的仓库数量搜索

`repos:n` [repos:>9000](https://github.com/search?q=repos%3A%3E%3D9000&type=Users) 匹配其仓库数超过 9,000 的用户。

### 按仓库大小搜索

size 限定符使用大于、小于和范围限定符查找匹配特定大小（以千字节为单位）的仓库。

`size:n` [size:1000](https://github.com/search?q=size%3A1000&type=Repositories) 匹配恰好为 1 MB 的仓库。

### 按许可搜索

`license:LICENSE_KEYWORD` [license:apache-2.0](https://github.com/search?utf8=%E2%9C%93&q=license%3Aapache-2.0&type=Repositories&ref=searchresults) 匹配根据 Apache License 2.0 授权的仓库。

### 按公共或私有仓库搜索

* `is:public` [is:public angular](https://github.com/search?q=is%3Apublic+angular&type=RegistryPackages) 匹配含有文字 "angular" 的公共包
* `is:private` [is:private php](https://github.com/search?q=is%3Aprivate+php&type=RegistryPackages) 匹配含有文字 "php" 的私有包

### 基于仓库是否为镜像搜索

`mirror:true` [mirror:true GNOME](https://github.com/search?utf8=%E2%9C%93&q=mirror%3Atrue+GNOME&type=) 匹配是镜像且包含 "GNOME" 字样的仓库。
`mirror:false` [mirror:false GNOME](https://github.com/search?utf8=%E2%9C%93&q=mirror%3Afalse+GNOME&type=) 匹配并非镜像且包含 "GNOME" 字样的仓库。

### 基于仓库是否已存档搜索

`archived:true` [archived:true GNOME](https://github.com/search?utf8=%E2%9C%93&q=archived%3Atrue+GNOME&type=) 匹配已存档且包含 "GNOME" 字样的仓库。
`archived:false` [archived:false GNOME](https://github.com/search?utf8=%E2%9C%93&q=archived%3Afalse+GNOME&type=) 匹配未存档且包含 "GNOME" 字样的仓库。

### 基于具有 good first issue 或 help wanted 标签的议题数量搜索

`good-first-issues:>n` [good-first-issues:>2 javascript](https://github.com/search?utf8=%E2%9C%93&q=javascript+good-first-issues%3A%3E2&type=) 匹配具有超过两个标签为 good-first-issue 的议题且包含 "javascript" 字样的仓库。
`help-wanted-issues:>n`	[help-wanted-issues:>4 react](https://github.com/search?utf8=%E2%9C%93&q=react+help-wanted-issues%3A%3E4&type=) 匹配具有超过四个标签为 help-wanted 的议题且包含 "React" 字样的仓库。

### 搜索 wiki

* `in:title` [usage in:title](https://github.com/search?q=usage+in%3Atitle&type=Wikis) 匹配含有 "usage" 字样的 wiki 页面。
* `in:body]` [installation in:body](https://github.com/search?q=installation+in%3Abody&type=Wikis) 匹配其主要正文文本中含有 "installation" 字样的 wiki 页面。


## 一些有趣的搜索

* 如何寻找最火爆的项目

  通过仓库的star数来筛选:[stars:>100000](https://github.com/search?q=stars%3A%3E100000&type=Repositories)然后发现第一名竟然从来没有听说过，看来是在下孤陋寡闻了。

* 如何寻找人气最高的大神

  查找followers大于某个值的用户:[followers:>=50000](https://github.com/search?q=followers%3A%3E%3D50000&type=Users)然后你会发现阮一峰真NB。

* 如何找到github最早注册的用户

  查找用户，并按照创建时间筛选:[created:<2008-01-01](https://github.com/search?q=created%3A%3C2008-01-01&type=Users)。如果你想知道github用户增长趋势，只要不断变化时间搜索就好了。


## 补充

### awesome 加强搜索

awesome一般是用来收集学习、工具、书籍类相关的项目。

[awesome redis](https://github.com/search?q=awesome+redis) 搜索优秀的redis相关项目，包括框架、教程等。

### 高亮显示某一行代码

高亮显示1行：地址后紧跟#L行数，高亮显示多行：地址后紧跟#L行数-L行数。

```
https://github.com/.../XXX.java#L13 // 高亮显示13行
https://github.com/.../XXX.java#L13-L53 // 高亮显示标注13行到53行代码
```

### 项目内搜索

使用按键 t ，可以看到目录结构有变化，都变为平铺显示，不用翻目录就可以直接查看。


## Donate

感谢您的耐心阅读,如果您发现文章中有一些没表述清楚的,或者是不对的地方,请给我留言,你的鼓励是作者写作最大的动力。

如果您认为本文质量不错,读后觉得收获很大,不妨小额赞助我一下,让我更有动力继续写出高质量的文章。

![支付宝](https://cdn.jsdelivr.net/gh/maoqiqi/cdn/alipay.png)
![微信](https://cdn.jsdelivr.net/gh/maoqiqi/cdn/wxpay.png)


## About

* **作者**：March
* **邮箱**：fengqi.mao.march@gmail.com
* **码云**：https://gitee.com/maofengqi
* **知乎**：http://zhihu.com/people/maofengqi
* **头条**：https://toutiao.io/u/425956/subjects
* **简书**：https://www.jianshu.com/u/02f2491c607d
* **掘金**：https://juejin.im/user/5b484473e51d45199940e2ae
* **豆瓣**：https://www.douban.com/people/maofengqi/
* **CSDN**：http://blog.csdn.net/u011810138
* **InfoQ**: https://www.infoq.cn/profile/1625261
* **Github**：https://github.com/maoqiqi
* **开源中国**：https://my.oschina.net/maoqiqi
* **Twitter**：https://twitter.com/maofengqi
* **Facebook**：https://www.facebook.com/fengqi.mao
* **喜马拉雅听书**：https://www.ximalaya.com/zhubo/31419312/
* **SegmentFault**：https://segmentfault.com/u/maoqiqi
* **StackOverFlow**：https://stackoverflow.com/users/8223522

> 著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。


## License

```
   Copyright 2020 March

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