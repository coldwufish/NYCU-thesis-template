# NYCU-thesis-template

國立陽明交通大學的碩博士論文Latex

---
這份latex有投稿到overleaf上作為template XD
https://www.overleaf.com/latex/templates/nycu-thesis-template/jgcmcnchmbrc

實驗室同學大多使用此樣板上傳論文到圖書館, 應該是沒太多問題(!?)

如果是overleaf的新使用者 & 願意贊助的話, 可以用這個推薦連結: https://www.overleaf.com?r=cc96d36b&rm=d&rs=b (幫我增加一下點數 XD)

----
使用方式:
* 論文的主頁是 paper.tex, 在這邊輸入個人資料 (自己名字, 指導教授, 論文名稱...等), 然後在此頁案按compile就會生成PDF了
* 論文樣板是網工所, 如果是其他系所的人, 請去修改 covers 裡面的 inside.tex 與 front.tex
* 論文章節是拆成多個檔案, 可留意paper.tex裡面提到的資訊

```
% 論文的內文, 可以每個章節一個.tex檔案 (put your statements in the following)
\input{Sections/1.Introduction} \newpage
\input{Sections/2.Relatedwork} \newpage
\input{Sections/3.Architecture} \newpage
\input{Sections/4.Methodology} \newpage
\input{Sections/5.Evaluation} \newpage
\input{Sections/6.Conclusion} \newpage
```

----
閒聊: 大概每年的6月份會更新一下. 除非我換工作離開學校(!?) 不然應該會一直更新下去 XD

* 2023.06: 更新學校浮水印, 改了一下浮水印的語法 (原本的會噴error msg), 也把一些環境變數(usepackage那些)弄到另一個檔案, 看起來會比較清爽!?
