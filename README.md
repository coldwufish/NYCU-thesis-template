# NYCU-thesis-template

國立陽明交通大學的碩博士論文Latex

NYCU (National Yang Ming Chiao Tung University) thesis template. Some graduate students in our lab have submitted their thesis to NYCU library with this template. This template supports English TOC & 中文目錄. You can change this by uncommenting a command.

---
這份latex有投稿到overleaf上作為template XD
https://www.overleaf.com/latex/templates/nycu-thesis-template/jgcmcnchmbrc

實驗室同學大多使用此樣板上傳論文到圖書館, 應該是沒太多問題(!?)

如果是overleaf的新使用者 & 願意贊助的話, 可以用這個推薦連結: https://www.overleaf.com?r=cc96d36b&rm=d&rs=b (幫我增加一下點數 XD)

----
## 使用方式
* 論文的主頁是 paper.tex, 在這邊輸入個人資料 (自己名字, 指導教授, 論文名稱...等), 然後在此頁案按compile就會生成PDF了
* 論文樣板是網工所, 如果是其他系所的人, 請去修改 covers 裡面的 inside.tex 與 front.tex
* 論文章節是拆成多個檔案, 可留意paper.tex裡面提到的資訊

### 主頁的說明(paper.tex)
* 使用英文目錄: 不需要改動
* 使用中文目錄: 把%\toggletrue{toc-use-cn}的註解(%)拿掉

#### 填寫個人資料
```
% --------------------------------------------
% 在這邊寫自己的資料
\newcommand{\chineseTitle}{中文論文名字}
\newcommand{\englishTitle}{English Title}
\newcommand{\studentCnName}{學生名字}
\newcommand{\studentEnName}{XXXX Wu} % 書名頁
\newcommand{\studentEnNameA}{Wu, XXXX} % 封面用
% 英文名字有兩種寫法, 一個是姓在後, 一個是放前面. 

\newcommand{\advisorCnName}{指導教授}
\newcommand{\advisorEnName}{OOOO Tseng} % 書名頁
\newcommand{\advisorEnNameA}{Tseng, OOOO} % 封面用
\newcommand{\ThesisDate}{August 2022} % 碩論的日期
\newcommand{\ThesisDateTW}{中華民國~ 一一一年八月}
% --------------------------------------------
```

#### 封面&書名頁
* 碩博士的版本都有放進去, 保留要用的即可. 記得修改自己的系所名稱.
* 目前的設計是假設論文名稱都是一行. 如果中文or英文名稱太長, 導致有換行的話, 可以手動調整標題的字體大小. 因為目前的浮水印剛好包住校名
```
% 1. 第一頁的封面, 記得修改系所
\input{covers/front.tex}        % 碩士論文的封面
\input{covers/front_phd.tex}    % 博士論文版的封面 博士論文版的封面

% 2. 第二頁的書名頁, 記得修改系所, 日期
\input{covers/inside.tex}       % 碩士論文的書名頁
\input{covers/inside_phd.tex}   % 博士論文版的書名頁 博士論文版的書名頁
```

#### 口試後才有的文件
* 口試結束後, 會有一些文件(3&5)需要口委們簽名, 最後上傳到圖書館要加入的東西. 論文初稿不需要. (我當年畢業不需要4 XD)
```
% 3. 論文電子檔著作權授權書: auth.pdf
%\includepdf[pages={1},pagecommand={\thispagestyle{empty}}]{auth.pdf}

% 4. 博士論文指導教授推薦書(碩士論文免附): phd_recommend.pdf
%\includepdf[pages={1},pagecommand={\thispagestyle{empty}}]{phd_recommend.pdf}

% 5. 學位論文審定同意書(審定書): approval_ch.pdf
%\includepdf[pages={1},pagecommand=
```

#### 論文正文
* 論文的內文, 每個章節一個.tex檔案 (put your statements in the following)
* 也可以全部塞同一個檔案, 就看個人習慣
```
\input{Sections/1.Introduction} \newpage
\input{Sections/2.Relatedwork} \newpage
\input{Sections/3.Architecture} \newpage
\input{Sections/4.Methodology} \newpage
\input{Sections/5.Evaluation} \newpage
\input{Sections/6.Conclusion} \newpage
```

#### 參考文獻
* 參考文獻寫在另一個檔案: ref.bib. 
```
\iftoggle{toc-use-cn} % 使用中文
{\addcontentsline{toc}{chapter}{參考文獻}
\renewcommand{\bibname}{參考文獻} } 
{\addcontentsline{toc}{chapter}{References}
\renewcommand{\bibname}{References}
} 

\bibliographystyle{IEEEtran}
\bibliography{ref}
```

----
閒聊: 大概每年的6月份會更新一下. 除非我換工作離開學校(!?) 不然應該會一直更新下去 XD

* 原始檔案已經不可考, 是研究所時期實驗室傳承下來的版本, 想當年還沒有overleaf, 自己裝miktex超麻煩 zzz...
* 2023.06: 更新學校浮水印, 改了一下浮水印的語法 (原本的會噴error msg), 也把一些環境變數(usepackage那些)弄到另一個檔案, 看起來會比較清爽!?
* 2023.11: 竟然有人發現編排順序跟學校的格式不一樣!! (致謝應該要往前挪一個) 之前都沒人注意到 XDD
* 2023.11: 竟然有人寄信詢問碩論格式的事!! (原來有其他人會用, 覺得感動XD) 因為原本是針對英文論文去整理, 後來弄出中文目錄了. 可是回頭來看又覺得中英混雜很奇怪, 就改成 純英文目錄 & 純中文目錄 了!! 目前預設是英文目錄, 把開頭的某個註解拿掉就變成中文目錄. 
* 2023.11: 調整一下排版, 看起來比較美觀(!?)
* 2023.11: 再多補充一些說明還有使用心得(?) 剛剛發現中文的Figure與Table忘了改成中文, 也一併修正.