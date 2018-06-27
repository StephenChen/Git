
Git 自报用户名邮箱：
`$ git config --global user.name "Your Name"`
`$ git config --global user.email "email@example.com"`

Git 创建仓库：
`$ git init`

Git 把文件添加至仓库：
`$ git add readme.txt readyou.txt`
`$ git commit -m "wrote a readme file"`

Git 库状态：
`$ git status`

Git 查看修改：
`$ git diff readme.txt`

Git 查看日志：
`$ git log`
`$ git log --pretty=oneline`

Git 版本回退：
当前版本 HEAD
上个版本 HEAD^
上上个版本 HEAD^^
上100个版本 HEAD~100
`$ git reset --hard HEAD^`
如果找不到回退之前的版本，往上划找到版本号
`$ git reset --hard 3628164`

Git 撤销到最近一次 git commit 或 git add 时的状态
`$ git checkout -- readme.txt`
场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。
场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。
场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

从版本库删除文件
`$ git rm test.txt`

本地Git仓库和GitHub仓库之间的传输是通过SSH加密
需要设置：
第1步：创建SSH Key。在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：
`$ ssh-keygen -t rsa -C "youremail@example.com"`
一路回车，使用默认值即可,无需设置密码。
第2步：登陆GitHub，打开“Account settings”，“SSH Keys”页面：然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容。点“Add Key”，看到已经添加的Key。

本地关联远程库,远程库的名字就是origin(Git默认的叫法)
`$ git remote add origin git@github.com:stephenchennnnnn/learngit.git`

把本地库的所有内容推送到远程库上
`$ git push -u origin master`

远程库克隆
`$ git clone git@github.com:stephenchennnnnn/gitskills.git`

查看分支 `$ git branch`
创建分支 `$ git branch <name>`
切换分支 `$ git checkout <name>`
创建+切换分支 `$ git checkout -b <name>`
合并某分支到当前分支 `$ git merge <name>`
删除分支 `$ git branch -d <name>`

分支合并图
`$ git log --graph`
`$ git log --graph --pretty=oneline --abbrev-commit`

合并分支禁用Fast forward
`$ git merge --no-ff -m "merge with no-ff" dev`

当前工作现场“储藏”起来，等以后恢复现场后继续工作
`$ git stash`





