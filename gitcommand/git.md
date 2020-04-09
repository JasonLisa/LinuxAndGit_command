## **git命令**

**1.本地创建版本库后,同步到github步骤**

	create a new repository on the command line


>
>echo # LinuxAndGit_command >> README.md
>git init  //初如化当前目录为git 库。
>
>git add README.md
>
>git commit -m "first commit"
>
>git remote add origin https://github.com/JasonLisa/LinuxAndGit_command.git
>
>git push -u origin master

	…or push an existing repository from the command line

>git remote add origin https://github.com/JasonLisa/LinuxAndGit_command.git
>
>git push -u origin master

	…or import code from another repository

>You can initialize this repository with code from a Subversion, Mercurial, or TFS project.

**2.本地库与远程库关联**

	$ ssh-keygen -t rsa -C "youremail@example.com"
>**参考:** <http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001374385852170d9c7adf13c30429b9660d0eb689dd43a000>

**3.本地git 升级**
>git clone git://git.kernel.org/pub/scm/git/git.git

**4.切换远程库**
> git remote set-url origin https://github.com/JasonLisa/mygit.git

------

## **git add 相关**

> - git add -A  提交所有变化
> - git add -u  提交被修改(modified)和被删除(deleted)文件，不包括新文件(new)
> - git add .  提交新文件(new)和被修改(modified)文件，不包括被删除(deleted)文件
> - git add -n 提交之前查看一下有哪些文件会被提交 比如运行`git add -n .`可以查看如果此时`git add .` 会有哪些文件会被添加到暂存区。只是想看一下而以，我个人是这么理解的。
> - 例如有一个文件a.md在暂存区，现在修改了a.md。运行`git add -n .`则显示`add 'a.md'`。如果此时在工作区新建一文件b.md，再运行`git add -n .`则显示`add 'a.md'`和`add 'b.md'`。如果 运行` git add -n -u .`则显示`add 'a.md'`。

------

## git restore 相关

-  `git restore <file>`

-  进行清除工作区的改变；同git chechout 文件名字    的作用是一样的；与git add .的作用相反

- 表示将在工作空间但是不在暂存区的文件撤销更改



git restore --staged 相关

-  `git restore --staged <file>`
- 作用是将暂存区的文件从暂存区撤出，但不会更改文件

**总结**

`git restore --staged` 将文件从暂存区撤出，但不会撤销文件的更改
`git resore` 将不在暂存区的文件撤销更改



------

### git status 相关

[参考]: https://blog.csdn.net/u013374164/article/details/78831273	"status使用方式"

------

###  git checkout -- <file>

-  就一名话：让这个文件回到最近一次`git commit`或`git add`时的状态；

-   [参考]: https://www.jianshu.com/p/285302d1eb73	"git checkout --<file>真正用法"

------

`git restore`、`git restore --staged`、`git checkout -- <file>` 总结一下用法

假如有一个文件readme.md 在各种区中的内容如下 

工作区内容为123 ；暂存区内容为12 ；仓库内容为 1 ；

- 如果想让工作区内容变为暂存区内容，直接`git resore`

- 如果想让工作区内容变为仓库内容，先`git restore`或`git restore --staged`，然后再`git checkout -- <file>`

    如果不小心直接`git checkout -- <file>`，则先`git resrore`或`git restore --staged`操作，再进行一次`git checkout -- <file>`；

-  ***其实理解`git checkout -- <file>`、`git restore`或`git restore --staged` 命令，可以这样理解：它们不仅仅是把文件或谇内容恢复成相应的状态，而且还要撤销相应的操作；比如`git restore --staged`作用是将暂存区的文件从暂存区撤出，但不会更改文件；这句话的是意思是撤销这个文件的上一次的`git add`操作；这句话很重要，是撤销 ，是撤销的操作；所以以后理解类似的东西，要理解成撤销，并且是撤销的操作，不是撤销的文件***

------

`git restore --staged filename`、`git reset HEAD file` 效果一样

------

