# Chgrp

change group，用于变更文件或目录的所属群组

与 [chown](https://www.runoob.com/linux/linux-comm-chown.html) 命令不同，chgrp 允许普通用户改变文件所属的组，只要该用户是该组的一员

## 语法 

```
chgrp [-cfhRv][--help][--version][所属群组][文件或目录...] 或 
chgrp [-cfhRv][--help][--reference=<参考文件或目录>][--version][文件或目录...]
```

## 选项（Options）

```
-c: 当发生改变时输出调试信息；
-f: 不显示错误信息；
-h: 只对符号连接的文件作修改，而不更动其他任何相关文件；
-R: 递归处理，处理指定目录以及其子目录下的所有文件；
-v: 运行时显示详细的处理信息；
--reference=<参考文件或目录>：把指定文件或目录的所属群组全部设成和参考文件或目录的所属群组相同；

```

## 示例

1. 改变文件 file.txt 的群组 group1 属性

```
chgrp -v group1 file.txt
```

2. 根据指定文件 file2.txt 改变文件 file1.txt 的群组属性

```
chgrp --reference=file2.txt file1.txt
```

