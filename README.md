初学GitHub，多多指教  
补上短板真的会变成庸才吗？  
  
--------------------------------------------------------------------------------

## 数据结构·栈
  2019/10/9
*备注：本篇笔记参照2020《王道考研·数据结构》且笔记残缺，仅适用于Jasamineee一人，不好意思。*
* 关于“&”符号与指针
  > 
    栈的操作有：  
    初始化栈InitStack(&S)，  
    判断是否为空StackEmpty(S)，  
    ~~进栈Push(&S,&x)~~ 进栈Push(&S,x)  
    出栈Pop(&S,&x)，  
    读栈顶元素GetTop(S,&x)，  
    销毁栈DestroyStack(&S)  

  此处的 “ & ” 表示 _引用_ ，达到 _传址_ 的目的。  
  
* 进栈出栈代码解释
  >
    进栈  
    S.data[++S.top]=x;   
    表示：1. 这里的栈顶指针指向栈顶元素。  
          2. 栈顶指针先指向下一个（无数字）地址，后把进入栈的值x赋值给栈顶指针所在的位置。  
          3. ++S.top 先加+后赋值。  
  >
    出栈  
    x=S.data[S.top--];  
    表示：数字x先赋值出栈，后栈顶指针向下-1.  
    
* 选择题错题概念：
  >
   * 栈和队列有相同的逻辑结构（都是线性结构）。  
   * n个不同元素进栈，（）种出栈序列。记住公式！  
   * 函数调用时，系统要用栈保存必要的信息。  
   * 一个栈的输入序列为1,2,3...,n,输出序列的第一个元素是i,则第j个元素是（_不确定_）   
    原因：第j个元素可能在i前，也可能在i后出栈。  
    
  -----------------------------------------------------------------------------------
### 在webstorm中提交更改到Github中
>本地文件修改->本地仓库（记录历史信息）->远程仓库

```
Microsoft Windows [版本 10.0.18362.418]
(c) 2019 Microsoft Corporation。保留所有权利。

E:\supermarket>git status    //查看git状态
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   src/App.vue

no changes added to commit (use "git add" and/or "git commit -a")

E:\supermarket>git remote list      
error: Unknown subcommand: list
usage: git remote [-v | --verbose]
   or: git remote add [-t <branch>] [-m <master>] [-f] [--tags | --no-tags] [--mirror=<fetch|push>] <name> <url>
   or: git remote rename <old> <new>
   or: git remote remove <name>
   or: git remote set-head <name> (-a | --auto | -d | --delete | <branch>)
   or: git remote [-v | --verbose] show [-n] <name>
   or: git remote prune [-n | --dry-run] <name>
   or: git remote [-v | --verbose] update [-p | --prune] [(<group> | <remote>)...]
   or: git remote set-branches [--add] <name> <branch>...
   or: git remote get-url [--push] [--all] <name>
   or: git remote set-url [--push] <name> <newurl> [<oldurl>]
   or: git remote set-url --add <name> <newurl>
   or: git remote set-url --delete <name> <url>

    -v, --verbose         be verbose; must be placed before a subcommand


E:\supermarket>git remote   

E:\supermarket>git remote add origin https://github.com/Jasmine2333/Jasmine2333.git       // 关联远程仓库与本地仓库

E:\supermarket>git remote     //查看注册的远程仓库
origin

E:\supermarket>git push       //推送
fatal: The current branch master has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin master


E:\supermarket>git push --set-upstream origin master    //
Enumerating objects: 24, done.
Counting objects: 100% (24/24), done.
Delta compression using up to 8 threads
Compressing objects: 100% (20/20), done.
Writing objects: 100% (24/24), 102.36 KiB | 5.12 MiB/s, done.
Total 24 (delta 0), reused 0 (delta 0)
To https://github.com/Jasmine2333/Jasmine2333.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

E:\supermarket>
```
在修改完本地的文件后，快捷键Ctrl+K ，输入提交内容，Commit+Push到远程仓库和本地仓库
