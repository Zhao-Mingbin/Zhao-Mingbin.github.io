# shell 编程

使用文本编辑器建立 .sh文件

```shell
#！/bin/bash
echo "hello world!"
```

其中==#！/bin/bash==用于表示脚本需要用什么解释器执行

刚建立的sh文件不能直接运行，如果希望运行则有两种方法

1. #### 作为可执行程序

   将上面的代码保存为 test.sh，并 cd 到相应目录

   ```shell
   chmod +x ./test.sh  #使脚本具有执行权限
   ./test.sh  #执行脚本
   ```

   注意，一定要写成 **./test.sh**，而不是 **test.sh**，运行其它二进制的程序也一样，直接写 test.sh，linux 系统会去 PATH 里寻找有没有叫 test.sh 的，而只有 /bin, /sbin, /usr/bin，/usr/sbin 等在 PATH 里，你的当前目录通常不在 PATH 里，所以写成 test.sh 是会找不到命令的，要用 ./test.sh 告诉系统说，就在当前目录找。

2. #### 作为解释器参数

   这种运行方式是直接运行解释器，参数就是shell脚本的文件名

   ```shell
   /bin/sh test.sh
   /bin/php test.php
   ```

这种方式运行的脚本，==不需要在第一行指定解释器信息==，写了也没用。

# shell 关键字

常用的关键字如下：

1. echo：打印文字到屏幕

2. exec：执行另一个 Shell 脚本

3. read：读标准输入

4. expr：对整数型变量进行算术运算

5. test：用于测试变量是否相等、 是否为空、文件类型等

6. exit：退出

```shell
#!/bin/bash 

echo "Hello Shell"

# 读入变量
read VAR
echo "VAR is $VAR"

# 计算变量
expr $VAR - 5

# 测试字符串
test "Hello"="HelloWorld"

# 测试整数
test $VAR -eq 10

# 测试目录
test -d ./Android

# 执行其他 Shell 脚本
exec ./othershell.sh

# 退出
exit
```

运行前，你需要新建一个 `othershell.sh` 的文件，让它输出 `I'm othershell`，并且中途需要一次输入，我这里输入的是 10：

```shell
Hello Shell
10
VAR is 10
5
I'm othershell
```

# shell 变量

shell变量分为三种：

- 用户自定义变量
- 预定义变量
- 环境变量

定义变量需要注意下面2点：

- 等号前后一定不要有空格 NUM=10
- 一般变量名用大写 M=1
- 使用 `$VAR` 调用变量，在变量名称前面添加`$`用于调用变量

#### 一、用户自定义变量

**1、变量定义及赋值**

这种变量**只支持字符串类型**，不支持其他字符，浮点等类型，

常见有这 3 个前缀：

1. `unset`：删除变量

2. `readonly`：标记只读变量

3. `export`：指定全局变量

一个例子：

```shell
#!/bin/bash 

# 定义普通变量
CITY=SHENZHEN

# 定义全局变量
export NAME=cdeveloper

# 定义只读变量
readonly AGE=21

# 打印变量的值
echo $CITY
echo $NAME
echo $AGE

# 删除 CITY 变量
unset CITY
# 不会输出 SHENZHEN
echo $CITY
```

但是赋值的变量必须为一个整体不能有空格，要想包含空格需要用引号引用起来，类似于Python字符串定义

**2.引号的特殊用法**

> 但是单引号‘ ’和双引号“ ”也有区别
>
> 从中可以看到，单引号可以保持==原样输出==，而双引号则会替换变量

一个例子：

```shell
[root@localhost ~]:~$ a="hello"
[root@localhost ~]:~$ b="$a world"
[root@localhost ~]:~$ echo $b
hello world
[root@localhost ~]:~$ c='$a world'
[root@localhost ~]:~$ echo $c
$a world
```

**3.``符号的特殊用法**

> 除此之外，与单引号相似的号也有特殊含义，其表示其中引起来的==命令会被执行==，如果不想使用这个符号也可以使用`$()` 来代替

```shell
[root@localhost ~]:~$ d=`date`
[root@localhost ~]:~$ echo $d
Wed Dec 28 06:31:13 PST 2016

[root@localhost ~]:~$ e=$(date)
[root@localhost ~]:~$ echo $e
Wed Dec 28 06:31:48 PST 2016
```

**4、命令行交互`read`**

有时候我们希望在脚本运行时能根据用户的输入决定脚本后续执行逻辑，比如在安装插件的时候经常会让用户选择输入`[N/Y]`的时候。 　　比如有一个脚本`script_test.sh`

```shell
read -p "Please input [Y/N]: " yn
if [ "$yn" == "N" -o "$yn" == "n" ]; then
  echo "NO"
elif [ "$yn" == "Y" -o "$yn" == "y" ]; then
  echo "YES"
fi
```

`read`命令的使用形式为

```sh
read [-pt] variable
　　参数p：后面可以接提示符
　　参数t：后面可以接秒数
例如：
read -p "please input your name" -t 5 name
```

**5、定义变量类型`declare`**

默认情况下，变量的赋值内容都是字符类型的。例如下面的代码，我们期望的是输出一个求和值，但是输出的是一个求和表达式。

```shell
[root@localhost ~]:~$ sum=100+300+500
[root@localhost ~]:~$ echo $sum
100+300+500

如果想要输出求和后的值，可以使用declare命令。

[root@localhost ~]:~$ declare -i sum=100+300+500
[root@localhost ~]:~$ echo $sum
900

declare [-aixr] variable
　　参数a：将variable定义为数组
　　参数i：将variable定义为整型(integer)
　　参数x：将variable设置成环境变量，类似于export的作用
　　参数r：variable为readonly类型，值不能被更改
```

#### 二、Shell中的集合类型

**1、**数组**(`array`)**

**（1）数组定义和赋值**

数组中的元素用括号包围，各元素之间用空格隔开。例如

```sh
[root@localhost ~]:~$ array_name=(v0 v1 v2 v3)

#可以重新设置指定元素的内容，如下所示：
[root@localhost ~]:~$ array_name[2]=v22
[root@localhost ~]:~$ echo ${array_name[2]}
v22
```

**（2）数组元素访问**

输出该数组中所有元素：

```sh
[root@localhost ~]:~$ echo ${array_name[*]} #此处与变量引用相似，也是用$符号,优于变成显示一组数，所以需要加{}
v0 v1 v22 v3
[root@localhost ~]:~$ echo ${array_name[@]}
v0 v1 v22 v3

#数组元素下标从0开始，想要访问指定位置的元素，使用[]指定下标值，如下所示
[root@localhost ~]:~$ echo ${array_name[0]}
v0
[root@localhost ~]:~$ echo ${array_name[1]}
v1
[root@localhost ~]:~$ echo ${array_name[3]}
v3
[root@localhost ~]:~$ echo ${array_name[2]}
v2
[root@localhost ~]:~$ echo ${array_name[4]}
```

**（3）获取数组长度**

获取数组长度使用如下命令

```sh
[root@localhost ~]:~$ echo ${#array_name[@]}
4
[root@localhost ~]:~$ echo ${#array_name[*]}
4

#同样也可以获取单个元素的长度
[root@localhost ~]:~$ echo ${#array_name[2]}
```

#### 2、map

`map`类型中存储的都是键值对。 类比与python中的字典，在Shell中定义`map`变量如下所示：

```sh
declare -A m=(["a"]="1" ["b"]="2")
#输出所有的key
[root@localhost ~]:~$ echo ${!m[@]}
a b
#输出所有的value
[root@localhost ~]:~$ echo ${m[@]}
1 2
#输出指定key对应的value
[root@localhost ~]:~$ echo ${m["a"]}
1
[root@localhost ~]:~$ echo ${m["c"]}
#添加元素
[root@localhost ~]:~$ m["c"]="3"
[root@localhost ~]:~$ echo ${m["c"]}
3
#map中键值对的个数
[root@localhost ~]:~$ echo ${#m[@]}
3
```





























