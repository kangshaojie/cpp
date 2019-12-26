# C++大作业

学号：18062022

姓名：康少杰

# 实验过程

## 一

按 NebulaGraph UP主发的视频安装Nebula Graph

开始分配了40G的内存，在make时爆了，重新安装了Ubuntu，分配了70G，好了

# 二

对源码进行了简单的修改，更改文件的路径是：src/daemons/GraphDaemon.cpp

源码：

```c++
void signalHandler(int sig) {		 void signalHandler(int sig) {
     switch (sig) {		     // switch (sig) {
         case SIGINT:		        // case SIGINT:
         case SIGTERM:		         // case SIGTERM:
             FLOG_INFO("Signal %d(%s) received, stopping this server", sig, ::strsignal(sig));		             // FLOG_INFO("Signal %d(%s) received, stopping this server", sig, ::strsignal(sig));
             gServer->stop();		             // gServer->stop();
             break;		             // break;
         default:		         // default:
             FLOG_ERROR("Signal %d(%s) received but ignored", sig, ::strsignal(sig));		            // FLOG_ERROR("Signal %d(%s) received but ignored", sig, ::strsignal(sig));
     }		     // }

```

更改后：

```c++
if (sig == SIGINT ||  sig == SIGTERM) {
         FLOG_INFO("Signal %d(%s) received, stopping this server", sig, ::strsignal(sig));
         gServer->stop();
     } else {
         FLOG_ERROR("Signal %d(%s) received but ignored", sig, ::strsignal(sig));    }
 }
}
```

# 三.操作过程

### 先百度了怎么用git提交代码，在https://www.cnblogs.com/jackchensir/p/8306448.html中的内容的帮助下，我生成了SSH公钥，步骤如下：

* ssh-keygen -t rsa -C "1220604348@qq.com" //生成一段密钥；
* vim cat~/.ssh/id_rsa.pub;复制密钥
* 将密钥粘贴到GitHub的setting中的SSH中；

### 配置用户名和邮箱：

```c++
$ git config --global user.name "kangshaojie"
$ git config --global user.email "1220604348@qq.com"
```

### 更改分支：

```c++
git remote -v //查看现有的从属关系
git remote rm origin // 消除当前远程origin
git remote add origin https://github.com/kangshaojie/nebula.git
git branch change // 创建一个 change 分支
git checkout change // 切换到change分支
```

### 添加文件：

```c++
git add src/daemons/GraphDaemon.cpp // add修改文件
```

### 上传代码：

```c++
git commit
git push
```

遇到的问题，刚开始push的change出现问题，最后发现是代码格式问题，修改后push成功。

#### 在添加文件是百度了一些git的用法：

git add -A 保存所有的修改 
git add . 保存新的添加和修改，但是不包括删除 
git add -u 保存修改和删除，但是不包括新建文件。

撤销操作：

git status 先看一下add 中的文件 
git reset HEAD 如果后面什么都不跟的话 就是上一次add 里面的全部撤销了 
git reset HEAD XXX/XXX/XXX.cpp 就是对某个文件进行撤销了

## 总结：

本次大作业真的让我收获良多，一是我学会了使用虚拟机，刚开始是想装双系统，但机械硬盘速度太慢，最后用了虚拟机操作。二是了解到GitHub这个神奇的网站（这一点应该C++课给我的收获）。三是在Ubuntu系统上使用git上传和clone文件。在上c++课之前，虚拟机和Ubuntu在我眼中都是大佬的词汇，但现在我也是真正学会Ubuntu系统的使用。最大的收获还是自学能力的提升，这次大作业真的可以说是从无到有，从小到大没接触过的东西，在一个月内学会。真的是收获良多，感谢老师为我打开新世界的大门。

