### Git

1. 设置本机全局账户

   > ```bash
   > git config --global user.name "username"
   > git config --global user.email "email@example.com"
   > ```

2. 查看本机Git账户

   > ```bash
   > git config user.name
   > git config user.email
   > ```

3. 在本机适当目录初始化一个Git仓库

   > ```bash
   > git init
   > // ls -ah 可以查看隐藏的.git文件夹
   > ```

4. 添加文件到Git仓库，分两步：（可以多次add，一次commit）

   > ```bash
   > git add readme.txt // 把文件修改提交到暂存区（stage）
   > git commit -m "message" // 把暂存区（stage）内容提交到版本库
   > ```

5. 查看当前工作区是否有未追踪的文件、暂存区是否有未提交的修改

   > ```bash
   > git status
   > ```

6. 查看工作区和版本库里面对应文件的区别

   > ```bash
   > git diff readme.txt
   > ```

7. 查看commit记录

   > ```bash
   > git log
   > git log --pretty=oneline
   > git log --graph --pretty=oneline --abbrev-commit // 可以查看分支合并情况
   > ```

8. commit回退

   > ```bash
   > git reset --hard HEAD^
   > git reset --hard HEAD~3
   > git reset --hard <commitID> // 回到指定的提交
   > ```

9. 查看执行过的命令记录，可以用于查找commitID

   > ```bash
   > git reflog
   > ```

10. 把工作区的修改撤回，处于复原状态

    > ```bash
    > git restore <file>
    > ```

11. 把暂存区的修改撤回到add前的状态，处于待add状态

    > ```bash
    > git restore --staged <file>
    > // 如果已经commit了，那么只能选择commit回退了
    > ```

12. 把本地仓库和远程仓库建立连接（origin是默认的远程库名称，当然可以自定义）

    > ```bash
    > git remote add origin <远程库地址> // 首次，默认在origin下创建master分支
    > ```

13. 把本地库内容推送到远程库（库名origin、分支名master）

    > ```bash
    > git push -u origin master // 首次
    > ```

14. 查看远程库信息

    > ```bash
    > git remote -v
    > ```

15. 解除本地库和远程库的链接

    > ```bash
    > git remote rm <远程库名称>
    > ```

16. 把本地库当前分支，与指定的远程库分支建立连接

    > ```bash
    > git push --set-upstream origin master
    > ```

17. 在本地仓库创建分支，基于当前所在分支创建

    > ```bash
    > git branch <name>
    > ```

18. 在本地仓库切换分支

    > ```bash
    > git switch <name>
    > ```

19. 在本地仓库创建并切换到创建的分支，基于当前所在分支创建

    > ```bash
    > git switch -c <name>
    > ```

20. 在本地仓库创建并切换到创建的分支，基于远程库中的origin/<name>分支创建

    > ```bash
    > git switch -c <name> origin/<name>
    > ```

21. 查看本地仓库中的分支

    > ```bash
    > git branch
    > ```

22. 删除分支

    > ```bash
    > git branch -d <name> // -D 强制删除
    > ```

23. 合并分支，把指定的分支合并到当前所在分支

    > ```bash
    > git merge <name>
    > ```

24. 把工作区未提交的修改内容，存储起来

    > ```bash
    > git stash
    > ```

25. 把某次commit合并到当前分支

    > ```bash
    > git cherry-pick <commitID>
    > ```

26. 查看远程仓库信息

    > ```bash
    > git remote -v
    > ```

27. 获取本地库当前分支对应的远程库上的分支的最新代码

    > ```bash
    > git pull
    > ```

28. 把本地库当前分支代码，推送到远程库对应分支上

    > ```bash
    > git push
    > ```

29. 把本地未push的分叉提交整理成直线

    > ```bash
    > git rebase // 好像没什么软用
    > ```

30. 给分支上的commit打tag

    > ```bash
    > git tag v1.0 <commitID> // 默认当前分支最新的commitID
    > git tag -a v0.1 -m "description" <commitID>
    > ```
    >
    > 注意：
    >
    > > 标签总是和某个commit挂钩。如果这个commit既出现在master分支，又出现在dev分支，那么在这两个分支上都可以看到这个标签。

31. 展示tag标签信息

    > ```bash
    > git tag // 列出所有tag标签
    > git show <tagname> // 展示标签的详细信息
    > ```

32. 把本地tag标签推送到远程仓库

    > ```bash
    > git push origin v1.0
    > git push origin --tags
    > ```

33. 删除tag标签

    > ```bash
    > git tag -d <tagname> // 删除本地库中的tag
    > git push origin :refs/tags/<tagname> // 删除远程仓库中的tag
    > ```

34. 设置命令的别名

    > ```bash
    > git config --global alias.st status
    > ```
    >
    > git的全局配置文件，一般在目录用户主目录下的.gitconfig中

35. 图形工具

    > sourceTree

补充：

> 1. merge模式
>
>    > fast-forward模式（默认），仅移动分支指针，看不到分支合并记录
>    >
>    > --no-ff模式，创建新的提交，可以清晰看出合并记录

