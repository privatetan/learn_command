# Chown

change owner，设置【文件所有者】和【文件关联组】

chown 需要超级用户 root 的权限才能执行此命令

只有超级用户和属于组的文件所有者才能变更文件关联组。非超级用户如需要设置关联组可能需要使用 [chgrp](https://www.runoob.com/linux/linux-comm-chgrp.html) 命令

**使用权限**：root用户，超级管理员

## 语法

````
chown [-chfRv]... [owner][:[group]] FILE...
chown [-chfRv]... --reference=REFILE FILE...
````

## 选项（Options）

```
-c：显示更改的部分的信息；
-h：修复符号链接；
-f：忽略错误信息；
-R：递归处理，指定目录以及其子目录下的所有文件
-v：显示详细的处理信息；
--reference=REFILE：使用参考文件或参考目录RFILE的权限来设置目标文件或目录的所有者和关联组；
```

## 示例

把 【/var/file.txt】 的所有者设置【 root】

```
chown root /var/file.txt 
```

将文件【file.txt】 的拥有者设为【user1】，群体的使用者【group1】 

```
chown user1:group1 file.txt
```

将当前前目录下的【所有文件与子目录】的拥有者皆设为 【user1】，群体的使用者 【group1】

```
chown -R user1:group1 *
```

把 【/home/file.txt 】的关联组设置为 【512 （关联组ID）】，不改变所有者

```
chown :512 /home/file.txt
```

