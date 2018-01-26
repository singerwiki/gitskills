# gitskills
存放常用git命令

#### 一、创建版本库
- 初始化一个Git仓库，使用git init命令。</br>
- 添加文件到Git仓库，分两步：</br>
1. 第一步，使用命令git add <file>，注意，可反复多次使用，添加多个文件；</br>
2. 第二步，使用命令git commit，完成。</br>

#### 二、版本退回
- HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。</br>
- 穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。</br>
- 要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。</br>

#### 三、撤销修改
- 场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。</br>
- 场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。</br>
- 场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。</br>

#### 四、删除文件
- 命令git rm用于删除一个文件。如果一个文件已经被提交到版本库，那么你永远不用担心误删，但是要小心，你只能恢复文件到最新版本，你会丢失最近一次提交后你修改的内容。

#### 五、添加远程库
- 要关联一个远程库，使用命令git remote add origin git@server-name:path/repo-name.git；
- 关联后，使用命令git push -u origin master第一次推送master分支的所有内容；
- 此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；</br>

#### 六、从远程库克隆
- 要克隆一个仓库，首先必须知道仓库的地址，然后使用git clone命令克隆。
- Git支持多种协议，包括https，但通过ssh支持的原生git协议速度最快。

#### 七、创建与合并分支
- Git鼓励大量使用分支：
- 查看分支：git branch
- 创建分支：git branch <name>
- 切换分支：git checkout <name>
- 创建+切换分支：git checkout -b <name>
- 合并某分支到当前分支：git merge <name>
- 删除分支：git branch -d <name>
