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


Period 2---->( go back to the history version )
<1>.`git log` Want much more simple one??? Use this:: `git log --pretty=oneline`

<2>. BACK TO THE PERVIOUS VERSION: `git reset --hard HEAD^`, which means go
back to the last version, and `HEAD^^`means two before the current one.And 
you can guest `HEAD^^^^^...` means ^^^^^... one before the current one.Another
easier way is `git reset --hard HEAD~100(n)` back to the 100(n)'s version.

<3>.Suppose you have been the previous version,How can you go back??????????
Get it!-->`git reflog` to check its 版本号, example below
e6c1ec6 HEAD@{0}: reset: moving to e6c1ec6
420fc57 HEAD@{1}: reset: moving to HEAD^
e6c1ec6 HEAD@{2}: commit: The third time modify
420fc57 HEAD@{3}: commit: another commit(hello-world's)
c86920c HEAD@{4}: commit: this is commit note again
9582e93 HEAD@{5}: commit (initial): readme.txt提交

git reset --hard e6c1ec6,then back to the newest version.


Period 3---->( Difference of 工作区 and 暂存区 )

工作区：就是电脑上看到的目录，比如testgit里的文件(.git目录除外,it is repository)

版本库：.git/ directory.其中有很多的东西，最终要的就是stage(暂存区).还有Git
为我们自动创建了的第一分支master,以及指向master的一个指针HEAD.

As we mention before :
                git state1: git add--> to add the file to 'stage'
                            git state2: git commit--> to add the stage file
                                        to master brunch

Back to the last version:
        1: edit it directly
        2: git reset --hard HEAD^
another---->git checkout -- readme.md  TO REMOVE THE EDITED PART DIRECTLY!!!
        And this must noted: git checkout readme.md TO (BUILD)ADD A(NEW) BRUNCH


删除文件：
edited 2016/3/1

...or create a new repository on the command line
        echo "#git_learning" >> README.md
        git init 
        git add README.md
        git commit -m "some note"
        git remote add https://github.com/hzsai/git_learning.git
        git push -u origin master

...or push an existing repository frome the command line
        git remote add origin https://github.com/hzsai/git_learning.git
        git push -u origin master //in the first time to use associate with the remote 
        git push origin master

 
sync a github repo to computer
        :git init //to initial a dictoery
        :git add . //add all file to to stage
        :git commit -m "commit all file"
        :git remote add origin https://gihub.com/hzsai/github_example
                        //assoicate with github_example repo
        :git pull origin master //as it say ' to pull from remote
        :git push -u origin master //to add your local file to the remote
                                // -u is needed to ... 
