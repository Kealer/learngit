设置全局配置
git config --global user.name "Kealer"  --
git config --global user.email "iogopo@163.com"

mkdir learngit --新建learngit文件夹

pwd --展示当前路径
ls -ah  --展示所有文件（包括隐藏）

git init --目录变成Git可以管理的仓库

git add README.md   --将文件添加到仓库
git rm file --删除文件
git commit -m "wrote a readme file" --把文件提交到仓库
    -m后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录

git status   --掌握仓库当前的状态
git diff    --查看修改内容

git log --pretty=oneline    --显查看提交历史
git reset --hard commit_id  --回退到某版本号
git reset --hard HEAD^  --回退到上一版本（HEAD指向的版本就是当前版本）
git reset --hard HEAD~100   --回退到上100个版本
git reflog  --查看命令历史

工作区（Working Directory）:有一个隐藏目录.git-Git的版本库-stage（或者叫index）的暂存区+自动创建的第一个分支master，以及指向master的一个指针叫HEAD
版本库（Repository）
前面讲了我们把文件往Git版本库里添加的时候，是分两步执行的：
第一步是用git add把文件添加进去，实际上就是把文件修改添加到暂存区；

第二步是用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支。

因为我们创建Git版本库时，Git自动为我们创建了唯一一个master分支，所以，现在，git commit就是往master分支上提交更改。

你可以简单理解为，需要提交的文件修改通通放到暂存区，然后，一次性提交暂存区的所有修改。

git checkout -- file    --可以丢弃工作区的修改
命令git checkout -- readme.txt意思就是，把readme.txt文件在工作区的修改全部撤销，这里有两种情况：
一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
总之，就是让这个文件回到最近一次git commit或git add时的状态。

创建SSH Key
ssh-keygen -t rsa -C "iogopo@163.com"

.ssh目录:id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。
登陆GitHub，打开“Account settings”，“SSH Keys”页面：
然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：

本地关联远程库
git remote add origin git@github.com:Kealer/learngit.git
















