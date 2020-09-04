# GIT 命令手册

> Git是一种开源的分布式版本控制系统，它可以方便您在笔记本电脑上进行GitHub活动桌面。这个备忘单总结了常用的Git命令行指令，以便快速参考。

## 安装

> GitHub提供了包含图形用户的桌面客户端接口为最常见的存储库操作和一个自动为高级场景更新Git的命令行版本。
>

- GitHub for Windows
  https://windows.github.com

- GitHub for Mac
  https://mac.github.com

- Git for All Platforms（提供了用于Linux和POSIX系统的Git发行版Git SCM官方网站）

  http://git-scm.com

## 配置工具

> 为所有本地存储库配置用户信息

~~~powershell
## 设置要附加到提交事务的名称
$ git config --global user.name "[name]"  

## 设置要附加到提交事务的电子邮件
$ git config --global user.email "[email address]"

## 启用有帮助的命令行输出着色
$ git config --global color.ui auto
~~~

- 如果用了 **--global** 选项，那么更改的配置文件就是位于你用户主目录下的那个，以后你所有的项目都会默认使用这里配置的用户信息。
- 如果要在某个特定的项目中使用其他名字或者电邮，只要去掉 **--global** 选项重新配置即可，新的设定保存在当前项目的 **.git/config** 文件里。

## 创建存储库

> 创建一个新的存储库或从现有的URL获取一个存储库

~~~powershell
## 使用指定的名称创建新的本地存储库
$ git init [project-name]

## 下载项目及其整个版本历史
$ git clone [url]
~~~

![img](https://www.runoob.com/wp-content/uploads/2015/02/1352126739_7909.jpg)

## 修改编辑

> 检查编辑并创建提交事务

~~~powershell
## 列出所有要提交的新文件或已修改文件
$ git status

## 快照文件，为版本控制做准备
$ git add [file]

## 重置文件，但保留其内容
$ git reset [file]

## 显示尚未提交的文件差异
$ git diff

## 显示暂存和最后一个文件版本之间的文件差异
$ git diff --staged

## 在版本历史中永久记录文件快照
$ git commit -m "[descriptive message]"
~~~

- ![img](https://www.runoob.com/wp-content/uploads/2015/02/1352126739_7909.jpg)

## 团队协作

> 命名一系列提交并组合完成的工作

~~~powershell
## 列出当前存储库中的所有本地分支
$ git branch

## 创建一个新的分支
$ git branch [branch-name]

## 切换到指定的分支并更新工作目录
$ git checkout [branch-name]

## 将指定分支的历史记录组合到当前分支中
$ git merge [branch]

## 删除指定的分支
$ git branch -d [branch-name]
~~~

## 重构文件名

> 重新定位并删除版本化的文件

~~~powershell
## 从工作目录中删除文件并执行删除操作
$ git rm [file]

## 从版本控制中删除文件，但将文件保存在本地
$ git rm --cached [file]

## 更改文件名并为提交做好准备
$ git mv [file-original] [file-renamed]
~~~

## 抑制跟踪

> 排除临时文件和路径

~~~powershell
*.log
build/
temp-*
## 一个名为.gitignore的文本文件可以防止意外版本控制
## 与指定模式匹配的文件和路径

## 列出此项目中所有忽略的文件
$ git ls-files --other --ignored --exclude-standard
~~~

## 保存碎片

> 搁置和恢复未完成的更改

~~~powershell
## 临时存储所有修改的跟踪文件
$ git stash

## 列出所有已隐藏的变更集
$ git stash list

## 还原最近隐藏的文件
$ git stash pop

## 丢弃最近隐藏的变更集
$ git stash drop
~~~

## 浏览历史

> 浏览并检查项目文件的演变过程

~~~powershell
## 列出当前分支的版本历史
$ git log

## 列出文件的版本历史记录，包括重命名
$ git log --follow [file]

## 显示两个分支之间的内容差异
$ git diff [first-branch]...[second-branch]

## 输出指定提交的元数据和内容更改
$ git show [commit]
~~~

## 重新提交

> 消除错误和工艺更换的历史

~~~powershell
## 在[commit]之后撤销所有提交，在本地保留更改
$ git reset [commit]

## 丢弃所有历史记录并将更改返回到指定的提交
$ git reset --hard [commit]
~~~

## 同步更改

> 注册一个存储库书签并交换版本历史记录

~~~powershell
## 从存储库书签下载所有历史记录
$ git fetch [bookmark]

## 将书签的分支组合到当前本地分支中
$ git merge [bookmark]/[branch]

## 上传所有本地分支提交到GitHub
$ git push [alias] [branch]

## 下载书签历史记录并合并更改
$ git pull
~~~



