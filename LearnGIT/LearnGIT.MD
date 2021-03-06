外行人學GIT -- 繼Linux之後Linux又一強檔力作
===

##始
先看看大概八年前Linus在"股溝技術講座"的演講[Tech Talk: Linus Torvalds on git](https://www.youtube.com/watch?v=4XpnKHJAok8)，一個小時左右，真的有興趣的人可以看看這個天才中年基客略顯狂妄的發言，對版本控制完全沒有概念的猴仔第一次看完全不知他在公三小，經過一番被git玩弄的過程之後才開始略懂略懂，影片大意其實就是**「Linus找不到一個好用的版本控制軟體管理Linux核心所以自已寫了一個，因為他寫的這個軟體優點實在罄竹難書，所以只有又笨又醜的人才會選擇其它工具!」**

##第一章 開動
下載與安裝的部分就不多說了，就給大家一個官網下載連結： [![git logo](./GITlogo.png)](http://git-scm.com/downloads)。然後就是下一步、下一步、下一步………

##第一節 新建資料庫
新建資料庫有兩種方式，一種是在自已電腦上建立，另一種則是到GitHub網站上建立一個帳號，然後線上創建資料庫，以下分別介紹。

###本地電腦創建資料庫
非常簡單，找到一個你想要儲存資料庫的資料夾，在終端機裡進入這個資料夾，打下指令：
```
git init
```
簡單明瞭，把git叫出來，初始置設(initialize)一個新的資料庫
git會自動創建一個隱藏資料夾.git，所以通常你看不到有任何動靜；無論如何現在您就可以在這個資料庫裡開始工作了。

###在GitHub網站上建立資料庫
先到GitHub網站輸入帳號、Email、密碼新建一個帳號，帳號建立之後歡迎頁就可以看到一個綠色 +New repository 的按鍵，按下去就可以開始新建資料庫了。
設定好資料庫名稱、內容概述(非必要)，選擇公開或私人(私人資料庫要付費才能使用)，然後勾選是否要建立讀我檔README.md(Git資料庫會建議創建一個讀我檔), 如果這是一個全新的資料庫就請勾選，如果您打算把原來的資料庫匯入，那就不必勾選。
一切就緒後，按下Create repository鍵就完工了!

##第二章 基本操作
抓取(pull)

加入(add)

提交(commit)

推送(push)

參考資料
=======
