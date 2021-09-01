# Cat

连接文件并打印到标准输出设备

## 格式

```
cat [-AbeEnstTuv] [--help] [--version] fileName
```

## 选项（Options）

```
-n 或 --number : 由 1 开始对所有输出的行数编号;
-b 或 --number-nonblank ：和 -n 相似，只不过对于空白行不编号;
-s 或 --squeeze-blank：当遇到有连续两行以上的空白行，就代换为一行的空白行；
-v 或 --show-nonprinting：使用 ^ 和 M- 符号，除了 LFD 和 TAB 之外；
-E 或 --show-ends : 在每行结束处显示 $；
-T 或 --show-tabs: 将 TAB 字符显示为 ^I；
-A, --show-all：等价于 -vET；
-e：等价于"-vE"选项；
-t：等价于"-vT"选项；
```

## 示例

**注**：“>”，会覆盖输出到的文件，“>>”，会在输出到的文件末追加；

1. 把 【file1】 的文档内容加上【行号】后输入到【file2】 这个文档里（**覆盖输入**）

```
cat -n file1 > file2
```

2. 把 【file1】 和 【file2】 的文档内容加上【行号】（空白行不加）之后将输入到 【file3】 文档里（**末尾追加**）

```
cat -b file1 file2 >> file3
```

3. 清空 /etc/test.txt 文档内容

```
cat /dev/null > /etc/test.txt
注：
* dev/null，在类 Unix 系统中，/dev/null 称空设备，是一个特殊的设备文件，它丢弃一切写入其中的数据（但报告写入操作成功），读取它则会立即得到一个 EOF；
* 在程序员行话，尤其是Unix行话中，/dev/null被称为比特桶[2]或者黑洞；
* 空设备通常被用于丢弃不需要的输出流，或作为用于输入流的空文件。这些操作通常由重定向完成；
* 相关可查阅维基百科；

```


