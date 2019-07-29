# a0-submit-assignments-through-github-classroom

Assignment 0 for SC001: Submit Assignments Through GitHub Classroom

這份前置作業會教大家如何透過 Git 將之後的作業上傳到 GitHub 上，同時也會教一些基本 Linux 指令讓你操作你的系統。所以與其說是作業，不如說是教學喔。Git 和 Linux 指令都是業界程式開發必備的技能，透過上傳作業趁機學習這些重要的工具可以說是一石二鳥！

__本次作業包含： 4 個問題。總共預計完成時間為：45分鐘。__

_如果作業卡關 歡迎各位到社團提問，也非常鼓勵同學們互相討論作業之 概念，但請勿把 code 給任何人看（也不要把程式碼貼在社團裡）分享妳/你的 code 會剝奪其他學生獨立思考的機會，也會因此讓其他學生的程式碼與你/妳的極度相似，讓防抄襲軟體認定有抄襲嫌疑._

## Problems

### Problem 1 - 認識 Git & GitHub 與下載作業 (20 min)

[__Git__](https://git-scm.com/) 是一個免費的 __版本控制工具__ ，而 [__GitHub__](https://github.com/) 是一個利用 Git 集合並管理 __開源程式專案的平台__ ，兩者是完全不同的概念但彼此的關係緊緊相連。簡單來說，GitHub 上會充滿各種程式專案，而開發者可以在線下利用 Git 進行 __專案下載（clone）__ 、 __提交修改（commit）__ 、 __上傳更新過的專案（push）__ 等等。這邊的中文都是我自己尋找的生動詞彙而不是直翻，建議大家記得英文單字就好。

而其中的精華盡在其 __版本控制__ 與 __專案合作__ 的功能：每一次的提交修改都會被記錄下來，也就是如果你發現程式走錯路了，你永遠可以返回之前某個提交點的狀態重新來過；一個專案若有多個開發者，每一個開發者可以各自將專案下載至自己的作業環境中，而在修改過後若想更新 GitHub 上的專案，你必須先 __下載其他人新的修改（pull）__ 並與你的修改 __合併（merge）__ 後才能上傳。

GitHub 亦提供許多其他功能，包括開 Issues 與開發者溝通專案問題，或是渲染（將原始碼轉成易瀏覽的形式） Markdown（一種文字轉網頁 HTML 格式的工具）檔案等等。

現在你在的這個網頁就是 GitHub 上的其中一個專案，你所瀏覽的這篇漂亮的教學文就是以 Markdown 撰寫並渲染成網頁 HTML 格式給你看的！而接下來我們要使用 Git 將作業下載到自己的作業環境，或稱本地端。

#### 步驟

1. 安裝 Git
    1. 到 [這裡](https://git-scm.com/downloads) 選擇你的作業系統，下載並安裝。
    2. Windows：如果在安裝過程中看到系統問是否要選擇 __Git Bash Here__ ，選擇是。Git Bash 可以讓之後所有的操作指令和 Mac / Linux 使用者統一。
2. 打開 Terminal （終端機）
    1. MacOSX：用 Spotlight Search 搜尋 Terminal。
    2. Windows：桌面按右鍵，選 __Open Bash Here__ 。
3. 更換目錄
    1. MacOSX：建議在 home directory （使用者目錄）進行作業。輸入 `cd ~` 並 enter。`cd` 代表 change directory，即更換目錄。`~` 代表 home directory 的路徑。
    2. Windows：建議在桌面進行作業。若前一步驟是在桌面按右鍵，那麼打開後的 terminal 即是在 `.../Desktop` 這個目錄，無須更換。若想在別的目錄進行作業，輸入 `cd <path>` 並 enter。 `cd` 代表 change directory，即更換目錄。`<path>` 請用目標目錄的路徑取代。
4. 檢查 Git 是否正確安裝
    1. 輸入 `which git`。若有成功安裝，則會印出 Git 程式的路徑。若沒有安裝成功則不會印出任何東西，請尋求幫助。
5. 下載此份作業
    1. 回到 GitHub 此份專案的網頁，點擊綠色按鈕 __Clone or download__ ，並複製呈現的 URL
    2. 輸入 `git clone <url>`。`<url>` 請用複製的 URL 取代。
    3. 輸入 `ls` 確認作業成功下載。`ls` 代表 list，即列出當前目錄下的所有檔案與子目錄。若下載成功，會看到 `a0-submit-assignments-through-github-classroom-xxx` 印出，即子目錄 `a0-submit-assignments-through-github-classroom-xxx` 存在。`xxx` 理應是你的 GitHub 帳號。
    4. 更換目錄至此專案。這邊請動動腦， __請問要用上面出現過的哪個指令呢？__

若成功進入下載後的專案，terminal 的 prompt (`$`) 之前顯示的當前路徑會是 `.../a0-submit-assignments-through-github-classroom-xxx`。

#### 提示

- 輸入路徑到一半時，可按鍵盤上的 `tab` 進行自動完成。
- 在 terminal 按上鍵可以回溯之前輸入過的指令。
- 根目錄（root）是整個系統的最上層路徑，路徑表示為 `/`。每下一層目錄，即多一個 `/`，例如 `/hello` 為根目錄底下的 `hello` 目錄，`/hello/world` 為根目錄底下的 `hello` 目錄底下的 `world` 目錄，以此類推。
- 路徑分 __絕對路徑__ 與 __相對路徑__ 。絕對路徑即從根目錄（root）開始算起，而相對路徑從當前目錄開始算起。例如在當前目錄 `/hello` 下，相對路徑 `world` 與絕對路徑 `/hello/world` 同義。
- `pwd` 可以顯示當前目錄的絕對路徑。
- 輸入並 enter 太冗了，之後稱作執行。

### Problem 2 - 修改，暫存，提交 （10 min）

終於要來正式進行版本控制了。

這邊講解一下 __暫存（stage）__ 和 __提交（commit）__ 的概念。情境是這樣的：揚鴻針對專案裡的檔案進行了多個修改。揚鴻跑了 `git status` 這個指令，檢視一下剛剛的修改：

```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   A.txt
    modified:   B.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

這代表修改的檔案包括 `A.txt` 及 `B.txt`。

但是在提交這些修改之前，揚鴻想到這兩個修改應該要是不同意義的。`A.txt` 的修改主要是增加一些註解，而 `B.txt` 的修改是修正一些 bug。如果這兩個修改同時提交，那未來審視這個專案的修改歷史時會引起混亂。正確的觀念應該是分別提交 `A.txt` 及 `B.txt` 的修改。

這時揚鴻需要先用 `git add A.txt` __暫存__ `A.txt` 的修改，並用 `git commit -m <message>` __提交__ 。為了清楚描述這個修改，揚鴻必須提供一個 commit message，也就是 `<message>`。接著再針對 `B.txt` 的修改做一樣的事情。

於是揚鴻這麼做了：

```
$ git add A.txt
$ git commit -m "Add comments"
$ git add B.txt
$ git commit -m "Fix bugs"
```

看到揚鴻這麼做的你，馬上就知道這個 problem 要怎麼完成了。

#### 步驟

1. 設定 Git 的使用者資料，才能在 commit 中留下紀錄（並找到修改的負責人）。執行 `git config --global user.email <email>` 和 `git config --global user.name <name>`，`<email>` 以你自己的 E-mail 取代，`<name>` 以自己的名字取代。
2. `Assignment0` 目錄下有兩份檔案，`coffee_or_tea.txt` 及 `dog_or_cat.txt`。用任何編輯器（Notepad++，Sublime，甚至 Word 都行）打開，將出現的問題刪掉，並加上自己的回答（e.g. 刪掉 `<Coffee or tea?>`，輸入 `Coffee`）。存檔。
3. 提交修改 __兩次__ 。兩份檔案的修改分別提交，先提交哪份的修改都可以，並附上 __清楚的 commit message__ 。

#### 提示

- 在 `git add` 後 `git commit` 前，執行 `git status` 時，暫存的修改會從紅色變綠色。
- 可用 `git reset HEAD <file>` 將修改從暫存區移除。

### Problem 3 - 上傳修改 （5 min）

剛剛的修改都在本地端，也就是遠方 GitHub 上的專案還處於你剛剛下載時的樣子。這時要更新遠端，就要進行 __上傳（push）__ 。

指令是這樣子的：`git push <remote> <branch>`。`<remote>` 是遠端的端點名，因為一個專案可以有很多的遠端端點。現在這個專案只有一個預設的遠端 `origin`。`<branch>` 是分支，因為一個專案可以開很多分支，但我沒教你。現在這個專案只有一個分支 `master`，也就是主分支。

完整的指令便是：`git push origin master`

#### 步驟

1. 將剛剛提交的修改上傳到遠端 GitHub。

到 GitHub 重新整理，會看到修改後的檔案們。

### Problem 4 - 下載修改（10 min）

其實 GitHub 上是可以直接修改檔案的，普遍是在 GitHub 上修改 Markdown 檔案，因為可以預覽渲染結果。而在遠端修改後，同樣的本地端的檔案仍然不會自動因此改變，所以要 __下載（pull/fetch）__ 修改。

指令跟 push 大同小異：`git pull <remote> <branch>`。

#### 步驟

1. 在 GitHub 網頁上，點進 `README.md`。點選 __鉛筆圖示（Edit this file）__ 。
2. 至檔案下方心得區中書寫自己的心得。
3. 至編輯區下方 __Commit changes__ 表格的第一格寫上 commit message。沒錯，這也是一個 commit！
4. 按 __Commit changes__ 提交。

### Extra Problem With no Extra Points - 分支

不知道 __分支（branch）__ 依然能夠正常使用 Git，但想像你在某個時間點想為專案嘗試性的加入一些功能，但還不確定是不是真的要採用這個功能，或這個功能是不是真的能夠成功建立。這時你就可以從 `master` branch 分一條支線出去，如此一來在分支上不論怎麼亂改，都能無痛換回原本的 `master` branch。

先執行 `git branch` 檢視一下專案目前有的分支：

```
$ git branch
* master
```

也就是目前只有一個 `master` branch。我們可以用 `git checkout -b <new-branch>` 來添加分支，`<new-branch>` 即新的分支名，而 `-b` 是選擇新增分支（而非只是前往）。現在我們來新增一個分支 `new`，然後重新檢視專案目前的分支：

```
$ git checkout -b new
Switched to a new branch 'new'
$ git branch
  master
* new
```

可以看到星星跑道我們剛剛新增的 `new` branch 之前，代表現在在 `new` branch。

我們來進行一些修改，例如刪除那兩份檔案。執行 `rm Assignment0/*`，`*` 代表目錄下所有檔案。這時看看我們的 git status：

```
$ git status
On branch new
...
	deleted:    Assignment0/coffee_or_tea.txt
	deleted:    Assignment0/dog_or_cat.txt
...
```

可以看到檔案被刪除了。這時我們一次提交這兩個修改。執行 `git add Assignment0/*` 暫存修改後，執行 `git commit -m "Delete files"` 提交。

現在在 `new` branch 我們失去了這兩個檔案。我們後悔了，於是決定換回 `master` branch 重新來過。

執行 `git checkout <branch>` 可以切換至 `<branch>`，所以要前往 `master` branch 要執行 `git checkout master`。

檢查一下你的目錄，那兩個檔案回來了嗎？

## 評分標準

- Functionality
    - 在 GitHub 及本地的兩份檔案 `coffee_or_tea.txt` 和 `dog_or_cat.txt` 必須被修改。
    - 在 GitHub 及本地的 `README.md` 心得區必須有心得。
    - 在 commit history 中應有兩個檔案修改的 commit 和一個 `README.md` 修改的 commit
- Style
    - Commit message 必須清楚描述此次的 commit

## 心得區

This is good!
