# Chattr

用于改变文件或目录属性

注：lsatter，用于查看文件或目录属性

## 语法

```
chattr [-RVf] [-+=AacDdijsSu] [-v version] [文件或目录...]
```

## 选项（Options）

```
-R: 递归处理，将指定目录下的所有文件及子目录一并处理；
-V: 显示指令执行过程；
-f: 

```

## 属性

```
-: 关闭属性；
+: 开启属性；
=: 指定属性；
A: Atime，告诉系统不要修改对这个文件的最后访问时间；
a：Append Only，系统只允许在这个文件之后追加数据，不允许任何进程覆盖或截断这个文件;
c：Compress，系统以透明的方式压缩这个文件;
D: 检查压缩文件中的错误
d：No dump，在进行文件系统备份时，dump程序将忽略这个文件;
i：Immutable，系统不允许对这个文件进行任何的修改;
j: Journal，设定此参数使得当通过mount参数：data=ordered 或者 data=writeback 挂 载的文件系统，文件在写入时会先被记录(在journal中)。     如果filesystem被设定参数为 data=journal，则该参数自动失效； 
s：Secure Delete，让系统在删除这个文件时，使用0填充文件所在的区域，保密性地删除文件或目录，即硬盘空间被全部收回;
S：Sync，一旦应用程序对这个文件执行了写操作，使系统立刻把修改的结果写到磁盘;
u：Undelete，当一个应用程序请求删除这个文件，系统会保留其数据块以便以后能够恢复删除这个文件;
```

## 示例

1. 用chattr命令防止系统中某个关键文件被修改

```
chattr +i /etc/resolv.conf
```

2. 让某个文件只能往里面追加数据，但不能删除，适用于各种日志文件

```
chattr +a /var/log/messages
```

## 说明

```
1. 通过chattr命令修改属性能够提高系统的安全性，但是它并不适合所有的目录;
2. chattr命令不能保护/、/dev、/tmp、/var目录;
3. chattr一些功能是由Linux内核版本来支持的，如果Linux内核版本低于2.2，那么许多功能不能实现;
```

