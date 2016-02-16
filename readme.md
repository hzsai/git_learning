note about git
Period 1---->
        1.`git config --global user.name "HezhenShen"`
        2.`git config --global user.email "hzs1234567szh@gmail.com"` 

 <1>.repositiory(可以理解为一个目录),git可以管理它
        for example: /home/hzs/folder1/testgit
                testgit is a repo.
                cd to testgit

<2>.`git init` to make the direction become a controlable(by git) one

<3>.`git add ***` to add ***(the file) to the repositiory to the buffer

<4>.`git commit -m "readme.txt提交"` 提交文件到仓库

<5>.`git status` 查看状态，一般没有改变会没有提示

<!--- --->(once been modified, it can be found)

<6>.Once you modify the file, you could `git status` to check it, then `git add ***`
`git commit -m "something you want to say"`

<7>What I have modify?  Use this `git diff ***` 


Period 2---->( go back to the history version)
<1>.`git log` Want much more simple one??? Use this:: `git log --pretty=oneline`

<2>. BACK TO THE PERVIOUS VERSION: `git reset --hard HEAD^`, which means go
back to the last version, and `HEAD^^`means two before the current one.And 
you can guest `HEAD^^^^^...` means ^^^^^... one before the current one.Another
easier way is `git reset --hard HEAD~100(n)` back to the 100(n)'s version.

<3>.Suppose you have been the previous version,How can i go back??????????
Get it!-->`git reflog` to check its 版本号, example below
e6c1ec6 HEAD@{0}: reset: moving to e6c1ec6
420fc57 HEAD@{1}: reset: moving to HEAD^
e6c1ec6 HEAD@{2}: commit: The third time modify
420fc57 HEAD@{3}: commit: another commit(hello-world's)
c86920c HEAD@{4}: commit: this is commit note again
9582e93 HEAD@{5}: commit (initial): readme.txt提交
git reset --hard e6c1ec6,then back to the newest version.



