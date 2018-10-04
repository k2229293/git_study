------
1. git仓库初始化
    git init
2. 设置git的名字和邮箱
    git config --global user.name xxx
    git config --global user.email xxx
3. 将readme.txt加到缓冲区
    git add xxx
4. 将缓冲区递交
    git commit -m "xxx"
5. 将xxxx克隆到本地
    git clone xxx
6. 将xxx克隆到本地指定目录yy
    git clone xxx yy
7. 忽略后缀为.swp的文件
    echo *.swp >> .gitignore
8. 忽略所有后缀为.a的文件，除了lib.a
    in .gitignore:
    *.a
    !lib.a
9. 查看多少个文件未被追踪
    git status
10。 查看多少个文件未被提交
    git status
11. 工作目录中一个文件被删除，但版本库还没删，请先找出被删除的，再删除
    git status
    git rm delet.rb
12. 偶然将一个文件加到缓冲区，删除该文件
    git rm --cached deleted.rb
13. 你做了些修改，并想稍后再继续。你须先保存状态，但不需提交。
    git stash
14. 我们有个文件oldfile.txt,我们想重新将其命名为newfile.txt,并缓存该修改。
    git mv oldfile.txt newfile.txt
15. 你加了很多文件至缓冲区，但是现在意识到你的项目需要重构，创建u 一个新的文件夹scr并使用git将所有.html文件移入该文件夹
    mkdir src
    git mv *.html
16. 你要查看最近提交的hash
    git log -1
17. 我们想给现在的提交打标签new_tag
    git tag new_tag
18. 在版本库里有许多标签没有推送至远程库，现将他们推送
    git push origin --tags
19. README文件已经提交，但是有个forgotten_file.rb忘记提交了， 把该问价加到之前的提交里去
    git add forgotten_file.rb
    git commit --amend -m "add"
20. 自定义提交时间为2016年1月10日
    git commit --date=2016.01.10 -m "commit"
21. 有两个修改文件，本来打算一次提交一个，但是不小心全部放到缓冲区了，现在想把a.txt退出来，下次提交。
    git reset HEAD a.txt
22. 你提交得太快，现在你想撤销上次最后的提交，并同时保持缓冲区。
    git reset --soft HEAD~1
23. 一个文件已经被修改了，但是你不想保存该修改， 从最后一次提交恢复config.rb文件。
    git checkout config.rb
24. 这个项目有远程版本库， 识别它。
    git remote
25. 远程版本库有url关联，查看url
    git remote -v
26. 把远程库的修改拉到本地
    git pull origin master
27. 添加远程库，并且关联url：http://xxx
    git remote add origin http://xxx
28. 你的本地master分支分自origin/master分支，将你的分支重基到origin/master分支， 并推送至远程。
    git rebase origin/master
    git push origin master
29. 你的app.rb自从上次提交后修改了，找出修改了哪些地方。
    git diff app.rb
30. 有人把密码放入config.rb了，找出谁做的
    git blame config.rb
31. 你想写个代码，但是会有可能破坏，创建分支test_code 
    git branch test_code
32. 创建新分支my_branch，并切换到该分支
    git checkout -b my_branch
33. 你需要修复v1.2的bug，切换到v1.2标签
    git checkout v1.2
34. 在同时有v1.2分支时，切换到v1.2标签
    git checkout tag/v1.2
35. 你在上次提交时忘记切换分支了，创建新分支test_code，并将其位于上次提交前。
    git branch test_code HEAD~1
36. 你创建了很多分支，其中有一个叫delete_me分支，你需要将其删除。
    git branch -d delete_me
37. 你在本地分支做了些修改，并想分享它，但是并没有想与master分支合并，只推送test_branch分支到远程版本库。
    git push origin test_branch
38.我们有个文件在feature分支，将其合并至master分支。
    git merge feature
39. 有个新的分支被推送到我们的远程分支了，取得这些修改，同时不要把它们合并至本地版本库
    git fetch origin
40. 将feature分支重基到master分支
    git checkout feature
    git rebase master
41. 优化版本库的打包，并确保冗余包被移除
    git repack -d
42. 你的新特性分支不值得花时间，所以你准备删除， 但是它有个提交，该文件包含了README文件，你想让该提交放在master分支。
    git log --graph --branches #找到hash_code
    git checkout master
    git cherry-pick hash_code
43. 你的项目截止日期到了，你需要数一下代码里有多少个doto
    git grep -c todo
44. 将之前第一次提交的附加信息更改了。
    git log//取得附加信息及hash_code
    git rebase -i hash_code
    将更改信息改成r
45. 你提交了几次，但是想把这些提交并作一次提交。
    git log # 取得hash_code
    git rebase -i hash_code
    留着第一次的不变，接下来几个改成s
46. 合并分支long-feature-branch,并提交
    git merge --squash long-feature-branch
47. 你提交了几次，但是次序错了请更改次序
    git log
    git rebase -i hash_code
48. 有个bug不知道什么时候被引进来了，你知道运行ruby prog.rb 5应该输出15，找出第一次输出错的提交hash
    git bisect start
    git bisect good 开头的hash_code
    git bisect bad master
    ruby prog.rb 5
    ...重复判断 good/bad
49. 你对feature.rb做了些修改，关系到两个特性，但是这些修改都没有进缓存区，只缓存第一个特性的修改。
    git add feature.rb -e
    删除不想添加的行，保存
50. 你正在一个分支工作，但是一个主要的问题需要你处理， 但是忘记了它的名字，切换到那个分支。
    git reflog // 显示层级经历过的所有记录
    git checkout branch_name 
51. 你提交几次后，想把中间那次的提交取消，所有提交都已经执行，你不能重新来过。
    git log //找到需要取消的hash_code
    git revert hash_code
52. 你通过git reset --hard HEAD^来删除最近一次的commit（这不是明智的做法），你改变了主意，想找回来，恢复删除的提交。
     git reflog//找到经历过的hash_code
     git checkout hash_code
 53. 你需要将分支mybranch合并至现在的分支（master）,但mybranch有一些错误的修改云引起了冲突， 解决这些冲突，这样你就可以完成交叉合并。
     git merge myubranch//发现冲突,并保存了冲突信息
     git mergetool//进入编辑器修改
     git commit -m "merged"
 54. 你想把远程的版本库http://xxx取回放到yy文件夹，并作为子git项目存在，并非克隆项目或者只是拷贝文件。
     git submodule add http://xx
     
