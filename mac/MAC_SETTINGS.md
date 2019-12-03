# Mac常用设置

## 目录

* [访达没有显示个人用户文件夹](#访达没有显示个人用户文件夹)
* [Mac如何修改用户名和用户文件夹](#Mac如何修改用户名和用户文件夹)
* [Mac键盘上的Windows按键介绍](#Mac键盘上的Windows按键介绍)
* [Mac修饰键](#Mac修饰键)

## 访达没有显示个人用户文件夹

访达->偏好设置->边栏->用户名打勾。

![访达](images/finder.png)


## Mac键盘上的Windows按键介绍

* Windows按键Control在Mac键盘上相当于Command键。
* Windows按键Alt在Mac键盘上相当于Option键。
* Mac键盘上只有一个delete删除键，删除的是光标前一个字符，如果想实现Windows按键del删除后一个字符的功能，需要Fn+Delete组合。
* Mac键盘上没有Windows按键Home和End，前往当前行的开头或结尾需要使用Command+左箭头键和Command+右箭头键。
* Windows按键F1-F12使用时要配合FN使用，而Mac键盘上是直接使用的。


## Mac如何修改用户名和用户文件夹

打开终端

1. 输入`sudo su`回车
2. 输入登录密码（必须有密码才能执行）
3. 输入`cd /Users`回车
4. 例：输入`mv apple wind`回车。apple就是你原来的个人目录名称（短名称），wind是你想修改的名称。

    > 注：短名称必须全部小写、无空格且只包含字母。

    这时你会发现在Finder里没有桌面、下载等等文件夹了，不要慌，因为原来的个人目录名称被修改了，电脑无法识别了。开始下一步。

5. 使用“系统偏好设置”的“用户与群组(Users & Groups)”面板，来创建一个具有上一步骤中所使用的帐户名称或短名称的新用户。

    当系统提示“‘用户’文件夹中已经有名称为‘帐户名称’的文件夹。您想将该文件夹用作此用户帐户的个人文件夹吗？”时，点按“好”。

    > 注：这将更正个人文件夹中所有文件的所有权，并避免文件夹内容出现权限问题。

7. 注销电脑。
8. 以新创建用户的身份登录（提示钥匙串问题点击更新钥匙串）。您应该能够访问（桌面上、文稿中及该个人目录下其他文件夹中的）所有原始文件。
9. 验证您的数据是否正常后，可通过“用户与群组”面板删除原始用户帐户。

    如果你发现有些文件夹无法访问提示无权限，右键文件夹->显示简介->共享与权限，
    点击右下角小锁（密码应该是无，直接回车就可以了）点+号添加你改名的管理员账号，接着权限改成读与写即可。



修改HostName

打开终端，执行下面命令，"tmp"是你想要修改的计算机名。

```
sudo scutil --set HostName tmp
```

> 执行过后命令，需要强行退出终端，重新打开就好了。

登录github。打开setting->SSH keys，点击右上角 New SSH key，把生成好的公钥id_rsa.pub放进 key输入框中，再为当前的key起一个title来区分每个key。