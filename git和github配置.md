# git和GitHub配置
### 1. 安装git
从官网下载 [Git客户端](https://github.com/git-for-windows/git/releases/download/v2.45.1.windows.1/Git-2.45.1-64-bit.exe).     
[git安装教程](https://blog.csdn.net/m0_46278037/article/details/118789168?spm=1001.2014.3001.5501)

### 2.GitHub注册

点击地址进入 [官网](https://blog.csdn.net/m0_46278037/article/details/118789168?spm=1001.2014.3001.5501).  按要求注册GitHub账号，并创建仓库。

### 3.git和GitHub配置

- 在桌面上点击鼠标右键，点击`Git Bash Here`

- git配置

  由于本地 Git 仓库和 GitHub 仓库之间的传输是通过SSH加密的，所以我们需要配置验证信息：

  使用以下命令生成 `SSH Key`：

  - 输入 ssh-keygen -t rsa -C "123456789@qq.com"，邮箱换成自己的，ssh-keygen没有空格，其他的有空格。接下来直接按4次Enter键

  - 成功的话会在 默认路径下生成 `.ssh` 文件夹，进去，打开 `id_rsa.pub`，复制里面的 `key`。

  - 配置git的用户名和邮箱

    ``git config --global user.name "用户名"``
    ``git config --global user.email "邮箱"``

- GitHub配置

  - 点击右上角头像，再点击settings（账户配置）

  - 点击 SHH and GPG keys

  - 点击 New SSH key

  - 填入title和key （上面git获取的key）

  - 验证配置是否成功

    在git bash输入命令 ssh -T git@github.com ，第一次配置会让你输入yes/no，输入yes 

    出现成功信息：You've successfully authenticated，说明SSH连接正常

- 托管

  - 再本地新建仓库（文件夹推荐和github远程仓库名相同），然后git init 初始化项目

  - 关联本地与Github仓库

    ``git remote add origin git@github.com:github用户名/github仓库名.git``

  - 同步仓库到本地

    ``git pull git@github.com:2021AY/github仓库名.git``

  - 把本地代码提交到Github

    - 执行增加命令：`git add .` ，add后面的点，表示的是提交所有文件。如果想指定提交文件，可以写文件名。
    - 执行提交命令：`git commit -m "第一次提交github的测试"` 。-m 后面是 提交备注。
    - 执行推送命令：`git push -u origin   master`

- 其他Git命令

  - `git log` 查看变更历史
  - `git remote add origin git@github.com:xxxxxxx.git` 将本地仓库与远程仓库关联
  - `git remote set-url origin git@github.com:xxxxx.git` 上一步手抖了，可以用这个命令来挽回
  - `git branch` 新建分支
  - `git merge` 合并分支
  - `git stash` 通灵术
  - `git stash pop` 反转通灵术
  - `git revert` 后悔了
  - `git reset` 另一种后悔了
  - `git diff` 查看详细变化
