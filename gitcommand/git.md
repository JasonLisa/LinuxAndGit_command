# **git命令**

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

============================

# **git add 相关**
> - git add -A  提交所有变化
>- git add -u  提交被修改(modified)和被删除(deleted)文件，不包括新文件(new)
>- git add .  提交新文件(new)和被修改(modified)文件，不包括被删除(deleted)文件