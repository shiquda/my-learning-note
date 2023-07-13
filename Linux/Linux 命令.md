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
ls [-a -l -h] [Linux路径]
```

- -a -l -h 是可选的选项
  - `-a`（all）：显示隐藏内容
    - 隐藏内容：以“.”开头的文件/文件夹
      - e.g. `.test.txt`
  - `-l`（long） 以列表形式展示
  - `-h`（human-readable） 与-l搭配使用用更加人性化的方式显示文件大小的单位。
    - e.g. 4096 =>4.0K
  - 以上命令可以联合搭配使用，如：`ls -lah`
    - 先后顺序无要求
- Linux路径是此命令可选的参数

#### HOME目录和工作目录🔗 [BV1n84y1i7td-P13-[04:13]](https://www.bilibili.com/video/BV1n84y1i7td?p=13&t=253.7)

##### HOME目录

Linux系统的命令行终端在启动的时候，默认会加载:

- 当前登录用户的HOME目录作为当前工作目录，所以`ls`命令列出的是HOME目录的内容
- HOME目录:每个Linux操作用户在Linux系统的个人账户目录,路径在:`/home/用户名`
  - 比如Linux用户是shiquda,其HOME目录是:`/home/shiquda`
  - Windows系统和Linux系统，均设有用户的HOME目录

##### 工作目录

Linux命令行在执行命令的时候，需要一个工作目录，打开命令行程序(终端)**默认设置工作目录在用户的HOME目录**。

### 目录切换相关命令（cd/pwd）

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

- pwd命令**没有选项与参数**，直接输入即可显示当前路径

### 相对路径、绝对路径、特殊路径符

#### 相对路径和绝对路径🔗 [BV1n84y1i7td-P16-[00:18]](https://www.bilibili.com/video/BV1n84y1i7td?p=16&t=18.7)

##### 相对路径

以**当前目录**为起点描述路径的写法，路径描述**无需以/开头**。

- e.g. `cd Desktop`

##### 绝对路径

以**根目录**为起点描述路径的写法，路径描述**需以/开头**。

- e.g. `cd /home/shiquda/Desktop`

#### 特殊路径符🔗 [BV1n84y1i7td-P16-[04:50]](https://www.bilibili.com/video/BV1n84y1i7td?p=16&t=290.6)

- `.`表示当前目录
- `..` 表示一级目录
- `~` 表示HOME目录

### 创建目录命令（mkdir）

#### mkdir：创建目录（Make Directory）🔗 [BV1n84y1i7td-P17-[00:15]](https://www.bilibili.com/video/BV1n84y1i7td?p=17&t=15.2)

语法：

```linux
mkdir [-p] Linux路径
```

- 参数必填，表示**Linux路径**，即要创建的文件夹的路径，**相对路径或绝对路径均可**；
- `-p`（parents）选项可选，表示**自动创建不存在的父目录**，适用于**创建连续多层级的目录**。

### 文件操作命令1（touch、cat、more）

#### touch：创建文件🔗 [BV1n84y1i7td-P18-[00:17]](https://www.bilibili.com/video/BV1n84y1i7td?p=18&t=17.6)

语法：

```linux
touch Linux路径
```

- touch命令**无选项**，**参数必填**，表示**要创建的文件路径**。
  - 绝对路径、相对路径、特殊路径符均可

#### cat：查看文件内容（Concatenate）🔗 [BV1n84y1i7td-P18-[02:34]](https://www.bilibili.com/video/BV1n84y1i7td?p=18&t=154.3)

语法：

```linux
cat Linux路径
```

- cat命令同样**无选项**，**参数必填**，表示**要创建的文件路径**。
  - 又是绝对路径、相对路径、特殊路径符均可

#### more：查看文件内容🔗 [BV1n84y1i7td-P18-[02:34]](https://www.bilibili.com/video/BV1n84y1i7td?p=18&t=154.3)

语法：

```linux
more Linux路径
```

- `more`命令同样可以查看文件内容，同cat不同的是:
  - `cat`是直接将内容**全部显示**出来
  - `more`**支持翻页**，如果文件内容过多，可以一页页的展示
- 在查看的过程中：
  - 通过**空格**翻页
  - 通过按键**Q**退出查看

### 文件操作命令2（cp、mv、rm）

#### cp：复制（copy）🔗 [BV1n84y1i7td-P19-[00:21]](https://www.bilibili.com/video/BV1n84y1i7td?p=19&t=21)

`cp`命令可以用于**复制**文件/文件夹。
语法：

```linux
cp [-r] 参数1 参数2
```

- `-r`（recursive）选项，**可选**，用于复制文件夹使用，表示**递归**
- `参数1`，Linux路径，表示被复制的文件或文件夹
- `参数2`，Linux路径，表示要复制去的地方

#### mv：移动（move）🔗 [BV1n84y1i7td-P19-[03:09]](https://www.bilibili.com/video/BV1n84y1i7td?p=19&t=189.5)

`mv`命令可以用于**移动**文件/文件夹。
语法：

```linux
mv 参数1 参数2
```

- `参数1`，Linux路径，表示**被移动**的文件或文件夹；
- `参数2`，Linux路径，表示要**移动去**的地方。
  - 如果目标不存在，则进行改名，确保目标存在。

#### rm：删除（remove） 🔗 [BV1n84y1i7td-P19-[06:24]](https://www.bilibili.com/video/BV1n84y1i7td?p=19&t=384.5)

`rm`命令可用于删除文件、文件夹

语法：

```linux
rm [-r -f] 参数1 参数2 ...... 参数N
```

同`cp`命令一样，`-r`选项用于**删除文件夹**。

- `-f`表示force，**强制删除** (不会弹出提示确认信息)
  >普通用户删除内容不会弹出提示(CentOS?)，只有root管理员用户删除内容会有提示，所以一般普通用户用不到-f选项
- `参数1 参数2 ...... 参数N` 表示要删除的文件或文件夹路径，按照空格隔开

##### rm中的通配符

rm命令支持**通配符***，用来做**模糊匹配**
符号* 表示通配符，即匹配任意内容 (包含空)，示例:

- `test*`，表示匹配任何以test开头的内容
- `*test`，表示匹配任何以test结尾的内容
- `*test*`，表示匹配任何包含test的内容

### 查找命令（which、find）

#### which：查找命令的程序文件🔗 [BV1n84y1i7td-P20-[00:20]](https://www.bilibili.com/video/BV1n84y1i7td?p=20&t=20.3)

Linux命令的本体就是一个个的二进制可执行程序，和Windows系统中的exe文件，是一个意思。
可以通过`which`命令，查看所使用的一系列命令的程序文件存放在哪里。
语法：

```linux
which 要查找的命令
```

#### find：查找文件🔗 [BV1n84y1i7td-P20-[03:12]]

##### 按文件名查找

(<https://www.bilibili.com/video/BV1n84y1i7td?p=20&t=192.4>)
语法：

```linux
find 起始路径 -name "被查找文件名"
```

##### 通配符🔗 [BV1n84y1i7td-P20-[07:13]](https://www.bilibili.com/video/BV1n84y1i7td?p=20&t=433.6)

##### 按文件大小查找文件

语法：

```linux
find 起始路径 -size +|-n[kMG]
```

- +、- 表示大于和小于
- n表示大小数字
- kMG表示大小单位，k(小写字母)表示kb，M表示MB，G表示GB
示例:
- 查找小于10KB的文件：`find / -size -10k`
- 查找大于100MB的文件：`find / -size +100M`
- 查找大于1GB的文件：`find / -size +1G`
- 查找大小介于100MB和200MB之间的文件：`find / -size +100M -size -200M`

### grep、wc和管道符（|）

#### grep：在文件中搜索匹配的文本（Global Regular Expression Print）🔗 [BV1n84y1i7td-P21-[00:20]](https://www.bilibili.com/video/BV1n84y1i7td?p=21&t=20.9)

可以通过`grep`命令，从文件中**通过关键字过滤文件行**。
语法:

```linux
grep [-n] 关键字 文件路径
```

- 选项`-n`，**可选**，表示在结果中显示匹配的行的行号
- 参数，关键字，**必填**，表示过滤的关键字
  - 带有**空格或其它特殊符号**，建议使用`""`将关键字**包围**起来
- 参数，文件路径，**必填**，表示要过滤内容的文件路径，**可作为内容输入端口**

#### wc：数量统计（Word Count）🔗 [BV1n84y1i7td-P21-[04:24]](https://www.bilibili.com/video/BV1n84y1i7td?p=21&t=264)

语法：`wc [-c -m -l -w] 文件路径`

- 选项，-c，统计bytes数量
- 选项，-m，统计字符数量
- 选项，-l，统计行数
- 选项，-w，统计单词数量（按空格划分）
- 参数，文件路径，被统计的文件，**可作为内容输入端口**

#### |：管道符🔗 [BV1n84y1i7td-P21-[07:23]](https://www.bilibili.com/video/BV1n84y1i7td?p=21&t=443.4)

写法：`|`

功能：将符号左边的结果，作为符号右边的输入

示例：

`cat a.txt | grep itheima`，将cat a.txt的结果，作为grep命令的输入，用来过滤`itheima`关键字

可以支持嵌套：

`cat a.txt | grep itheima | grep itcast`

- 这里的左边`cat a.txt`的返回值作为一个参数传给后面的`grep itheima`，
- 再把拼成的`cat a.txt | grep itheima`的返回值作为一个参数整体传给`grep itcast`。

### echo、tail和重定向符

#### echo：输出🔗 [BV1n84y1i7td-P22-[00:24]](https://www.bilibili.com/video/BV1n84y1i7td?p=22&t=24.8)

功能：将文本或变量的值输出到标准输出（通常是终端），相当于print

语法：

```linux
echo 参数
```

- 参数：被输出的内容

> 带有 空格 或 \ 等特殊符号的时候，建议用双引号包围被输出的内容，以防识别为参数。

#### ` ：反引号🔗 [BV1n84y1i7td-P22-[02:12]](https://www.bilibili.com/video/BV1n84y1i7td?p=22&t=132.8)

功能：被两个反引号包围的内容，会作为命令执行

示例：

- echo \`pwd\`，会输出当前工作目录
- 而 echo pwd ，仅输出 pwd

#### `>` & `>>` ：重定向符🔗 [BV1n84y1i7td-P22-[03:29]](https://www.bilibili.com/video/BV1n84y1i7td?p=22&t=209.4)

功能：将符号左边的结果，输出到右边指定的文件中去

- `>`，表示**覆盖输出**
- `>>`，表示**追加输出**

示例：
shiquda@LAPTOP:~/test$ cat test.txt
> test test test

覆盖原有内容：
shiquda@LAPTOP:~/test$ echo test > test.txt
shiquda@LAPTOP:~/test$ cat test.txt
> test

追加内容：
shiquda@LAPTOP:~/test$ echo test >> test.txt
shiquda@LAPTOP:~/test$ cat test.txt
> test
test

#### tail：查看文件尾部内容🔗 [BV1n84y1i7td-P22-[06:39]](https://www.bilibili.com/video/BV1n84y1i7td?p=22&t=399.1)

功能：查看文件尾部内容

语法：`tail [-f -num] Linux路径`

- 参数：被查看的文件
- 选项：-f，持续跟踪文件修改。
  - 当指定的文件被更改时，会自动输出新增加的内容
  - 可以使用`Ctrl + C`强制退出
- 选项，-num，表示查看尾部的行数，不填**默认为10**。
  - 使用时要把num替**换为相应的数字**，例如 -5
