# Git 使用操作
###### tags: `skill`

https://backlog.com/git-tutorial/tw/reference/ssh.html
基本概念:
如何寫一個好的git commit message
https://blog.louie.lu/2017/03/21/%E5%A6%82%E4%BD%95%E5%AF%AB%E4%B8%80%E5%80%8B-git-commit-message/
參考資訊：
https://yehchitsai.gitbooks.io/linux-usage/content/use_gitlab.html
搭配 sourcetree 使用
把gitlab上的東西clone下來，file->clone，從gitlab上面複製http網址，選擇本機的資料夾

**clone** :  會把整個專案的內容複製一份到你的電腦裡，這裡指的「內容」不是只有檔案，而是指所有整個專案的歷史紀錄、分支、標籤等內容都會複製一份下來。
**pull**： Pull 指令其實就是去上線抓東西下來（Fetch），並且更新本機的進度（Merge）而已，下載特定進度
**push**：先commit之後,才可以push!
**commit**: 要先stage,才可以commit,commit裡面要寫版號與修改的相關事項

### **指令：**
1.初始設定-在目標目錄底下
`git init`
2.把遠端上的project clone 下來
`git clone http://...`
3.查看git目錄的相關資訊
`git status`
4.把檔案交給git-暫存區 (stash)
`git add xxx(檔案名稱`
5.提交到倉庫(commit) - 要輸入相關資訊,這次修改了什麼
`git commit -m "xxxxx"`
6.同時加到stash跟commit(合併步驟4、5)
`git commit -a -m "xxxxxx`
7.查看git log 狀態
`git log --oneline`
8.HEAD是一個tab,在sourcetree上面就是那個小空心圓,通常會指著目前所在branch的位置
9.merge,當branch 寫的差不多時,回到master,再 `git merge branch`
10.另外一種合併方式->rebase
(重新定義分支的參考基準!,看是要以誰為準!)
11.git stash (在commit之前,把修改先存起來)
git stash 可以放很多份,放多份之後可以再用
`git stash list` 查看
並用 `git stashh pop stash@{2}` 撿回來
12.設定upstream(上游),意旨local與remote的連結
`git push -u origin master`
或是每一次都指定要push到的remote branch
13. pull下載更新
14. git pull = git fetch + git merge
15. git pull --rebase (不會產生多個commit)
-> 如果線上的版本比我的還新時,可以先pull --rebase,再進行push!
16.






使用sub_branch,在sub_branch裡面做好stage->commit之後，然後切換回master_branch,再進行merge!
1. 切換branch,切換到master
`git branch checkout master`
2. branch 要做 merge
`git branch sub_branch`
3. merge回去之後,再做push,就會更新master裡面的code了
5. **整體流程run一次，當你更版好code之後**
放入 stage
`git add xxxx.py`
進行 commit
`git commit -m xxxx.py`
切換 branch 至 master,再從master進行merge!!
`git branch checkout master`
`git branch sub_branch`


1.將gitlab上面的專案clone下來
`git clone 網址`
2.在local端新增branch   (刪除 : `git branch -d branch_name`)
`git branch branch_name`
3.切換branch
`git checkout branch_name`
4.查看branch
`git branch`
5.要上板前,先commit
`git commit -m "your commit"`
6.commit之後,可以push
`git push`
7.將 remote 上的 branch pull 下來到自己的master
`git checkout master`
`git pull origin branch:master`
8.再把自己的master push 到 remote 的 master


### 特殊情境
1.檢視目前的使用者資訊設定
`git config --list`

fork
pull
