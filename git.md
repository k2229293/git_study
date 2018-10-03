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
22.  
