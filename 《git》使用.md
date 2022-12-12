# 《git》使用

## 一、Git基础

### 1.1 利用PUSH推送到远程

①远程数据库取别名[^1]

```c
$ git remote add <name> <url>		//记远程数据库的链接名为自定义名字,方便下次推送
```

②利用push命令向数据库推送内容

```c
$ git push <repository> <refspec>... //<repository>处输入目标地址，<refspec>处指定推送的分支。
```

③运行以下命令便可向远程数据库‘origin’进行推送。当执行命令时，如果您指定了-u选项，那么下一次推送时就可以省略分支名称了。但是，首次运行指令向空的远程数据库推送时，必须指定远程数据库名称和分支名称。

```
$ git push -u origin master
```

### 1.2 克隆远程数据

①利用clone指令复制数据库

```
$ git clone <repository> <directory>
```

②执行以下指令后，会在目录(tutorial2) 复制远程数据库。

```
$ git clone https://nulab.backlog.jp/git/BLG/tutorial.git tutorial2
```

### 1.3 从克隆数据库进行PUSH

```
$ git push
```

### 1.4 从远程数据库进行PULL[^2]

①利用pull从远程数据库拉取最新内容

```
$ git pull <repository> <refspec>...
```

```
$ git pull origin master
```

### 1.5 PUSH冲突

①先pull拉取远程数据库最新内容

```
$ git pull origin master
```

②手动修改冲突项

③再次push远程数据库

④用log命令来确认数据库的历史记录是否准确

```
$ git log --graph --oneline
*   d845b81 合并
|\
| * 4c01823 添加pull的说明
* | 95f15c9 添加commit的说明
|/
* 3da09c1 添加add的说明
* ac56e47 first commit
```



## 二、Git高级

```
add 把变更录入到索引中
```

```
commit 记录索引的状态
pull 取得远端数据库的内容
```



## 注释

[^1]:执行推送或者拉取的时候，如果省略了远程数据库的名称，则默认使用名为”origin“的远程数据库。因此一般都会把远程数据库命名为origin。
[^2]:使用pull指令进行拉取操作。省略数据库名称的话，会在名为origin的数据库进行pull。
