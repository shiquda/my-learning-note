# Linux 命令

## 入门

### 命令基础

#### 什么是命令、命令行？🔗 [BV1n84y1i7td-P12-[01:21]](https://www.bilibili.com/video/BV1n84y1i7td?p=12&t=81.8)

- 命令行：即Linux终端(Terminal)，是一种命令提示符页面；
- 命令：即Linux程序。一个命令就是一个Linux的程序。

#### Linux命令基础格式

##### 通用格式

```linux
command [-options] [parameter]
```

其中[]表示是可选项。
e.g.

```linux
cp -r test1 test2
```

- command：命令本身
  - cp：复制命令本身
- -options:[可选，非必填] 命令选项
  - -r：选项（复制文件夹）
- parameter：[可选，非必填] 命令参数（多代表指向目标）
  - test1 test2：参数，指向被复制以及复制成为对象

#### ls：列出目录内容（List）

  ls命令的作用是列出目录下的内容，语法细节如下

```linux
1s [-a -1 -h] [Linux路径]
```

- -a -l -h 是可选的选项
  - -a：显示隐藏内容
    - 隐藏内容：以“.”开头的文件/文件夹
      - e.g. `.test.txt`
  - -l 以列表形式展示
  - -h 与-l搭配使用用更加人性化的方式显示文件大小的单位。
    - e.g. 4096 =>4.0K
  - 以上命令所以联合搭配使用，如：`ls -lah`
    - 先后顺序无要求
- Linux路径是此命令可选的参数

#### HOME目录和工作目录🔗 [BV1n84y1i7td-P13-[04:13]](https://www.bilibili.com/video/BV1n84y1i7td?p=13&t=253.7)

##### HOME目录

Linux系统的命令行终端在启动的时候，默认会加载:

- 当前登录用户的HOME目录作为当前工作目录，所以`ls`命令列出的是HOME目录的内容
- HOME目录:每个Linux操作用户在Linux系统的个人账户目录,路径在:`/home/用户名`
  - 比如Linux用户是itheima,其HOME目录是:`/home/itheima`
  - Windows系统和Linux系统，均设有用户的HOME目录

##### 工作目录

Linux命令行在执行命令的时候，需要一个工作目录，打开命令行程序(终端)**默认设置工作目录在用户的HOME目录**。

### 目录切换相关命令

#### cd：切换工作目录（Change Directory）🔗 [BV1n84y1i7td-P15-[00:21]](https://www.bilibili.com/video/BV1n84y1i7td?p=15&t=21.4)

语法：

```linux
cd [Linux路径]
```

- cd命令**无需选项，只有参数**，表示要切换到哪个目录下
- cd命令**直接执行，不写参数**，表示回到用户的HOME目录

#### pwd：显示当前工作目录的路径（Print Working Directory）🔗 [BV1n84y1i7td-P15-[03:54]](https://www.bilibili.com/video/BV1n84y1i7td?p=15&t=234.3)

语法：

```linux
pwd
```

- pwd命令**没有选项与参数**，直接输入即可
