# git flow vs github flow vs gitlab flow
本文即將介紹三種最被廣泛使用的WorkFlow(工作流程)


* Git flow
* Github flow
* Gitlab flow



## Git flow
先來介紹Git flow，他是最早誕生也是最早被廣泛使用的工作流程。<br>
它的特點是專案中會有兩個長期存在的分支，分別為主分支**Master**以及開發分支**Develop**。
主分支用於存放對外發布的版本，在這裡的版本都是穩定的版本；而開發分支則是存放最新的開發版本。<br>

再來，還會有三種短期分支。都是開發完被merge進develop或master就會被刪除的分支。<br><br>

* 功能分支（feature branch）
* 修復分支（hotfix branch）
* 預發分支（release branch）
<br>
一、主分支Master<br>

首先，代碼庫會有一個且只有一個主分支。所有正式上線的版本，都是使用主分支版本。<br>
Git主分支的名字，默認叫做Master。專案一開起就會自動建立，版本庫初始化以後，默認在主分支進行開發。<br>
主分支只用來發布重要版本，平時的開發版本則應該在另一條分支上進行。<br><br>

![](https://imgur.com/rw5NlMY.png)<br>

二、開發分支Develop<br>
此分支用來存放最新開發版本的代碼。如要正式對外發布則對Develop分支merge。<br><br>

![](https://imgur.com/CSSYqJz.png)<br><br>
在默認情況下，Git 的merge為（fast-farward merge），會直接將Master分支指向Develop分支。<br>
而如果使用--no-ff參數merge，則會執行正常合併，在Master分支上生成一个新節點。這是為了保證版本History的清晰。<br>

* 默認情況<br>
![](https://imgur.com/nALludX.png)<br>
* 使用--no-ff參數<br>
![](https://imgur.com/FUG9L1a.png)<br>
* Git Flow 示意圖<br>
![](https://imgur.com/yjhAIgK.jpg)<br>

* feature branch示意圖<br>
![](https://imgur.com/O6E22LL.jpg)<br>
* hotfix branch示意圖<br>
![](https://imgur.com/CYHQiTX.jpg)<br>

Git flow的优点是清晰可控，缺点是相对复杂，需要同时维护两个长期分支。大多数工具都将master当作默认分支，可是开发是在develop分支进行的，这导致经常要切换分支，非常烦人。
更大问题在于，这个模式是基于"版本发布"的，目标是一段时间以后产出一个新版本。但是，很多网站项目是"持续发布"，代码一有变动，就部署一次。这时，master分支和develop分支的差别不大，没必要维护两个长期分支。

参考链接：
<a href="http://www.ruanyifeng.com/blog/2012/07/git.html">阮一峰-Git分支管理策略</a>、<a href="http://www.ruanyifeng.com/blog/2015/12/git-workflow.html">阮一峰- Git 工作流程</a>
