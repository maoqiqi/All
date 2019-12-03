# vim程序编辑器


## vim环境设置与记录: ~/.vimrc, ~/.viminfo

* `:set nu` `:set nonu` 就是设置与取消行号。
* `:set hlsearch` `:set hlsearch` 是否将查找的字符串反白的设置值。
* `:set autoiindent` `:set noautoindent` 是否自动缩排，autoindent就是自动缩排。
* `:set backup` 表示是否自动保存备份文件，一般是nobackup的，如果设置backup的话，那么当你改动任何一个文件时，
则原文件会被另存成一个文件名为filename~的文件。
* `:set ruler` 显示或不显示状态栏说明
* `:set showmode` 是否显示--INSERT--之类的字眼在左下角的状态栏。
* `:set backspace=(012)` 当backspace为2时，就是可以删除任意值；为0或1时，仅可删除刚才输入的字符，
而无法删除原本就已经存在的文字了。
* `:set all` 显示目前所有的环境参数设置值。
* `:set` 显示与系统默认值不同的设置参数，一般来说就是你有自行变动过的设置参数。
* `:syntax on` `:syntax off` 表示是否依据程序相关语法显示不同颜色。
* `:set bg=dark :set bg=light` 可以以显示不同的颜色色调，默认是light。

## vim 常用命令示意图

![p](vim.jpeg)

## 其它vim使用注意项

* 中文乱码的问题
* DOS与Linux的断行字符
* 语系编码转换
  * `iconv  --list` 列出iconv支持的语系数据
  * `iconv -f 原本编码 -t 新编码 filename [-0 newfile]`
    * -f: form， 后接原本的编码格式
    * -t： to, 即后来的新编码要是什么格式
    * -o file: 如果需要保留原本的文件， 那么使用-o 新文件名， 可以建立新编码文件。