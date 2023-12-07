# NYCU-thesis-template

國立陽明交通大學的碩博士論文Latex

NYCU (National Yang Ming Chiao Tung University) thesis template. Some graduate students in our lab have submitted their thesis to NYCU library with this template. This template supports English TOC & 中文目錄. You can change this by uncommenting a command.

---
## 圖書館的資訊
* 學位論文編寫事項 https://www.lib.nycu.edu.tw/custom_label?menu=64&lid=6
* 書名頁學位名稱英文，請依照註冊組提供各學院、系所學位中英文名稱.
  * https://aa.nycu.edu.tw/reg/%E7%B5%B1%E8%A8%88%E8%B3%87%E8%A8%8A
* 臺灣博碩士論文知識加值系統 https://ndltd.ncl.edu.tw/
  * 可用來查詢前人的論文, 看之前的畢業生是怎麼寫
* 圖書館FB: https://www.facebook.com/NYCULIB
* 
---
這份latex有投稿到overleaf上作為template XD
https://www.overleaf.com/latex/templates/nycu-thesis-template/jgcmcnchmbrc

實驗室同學大多使用此樣板上傳論文到圖書館, 應該是沒太多問題(!?)

如果是overleaf的新使用者 & 願意贊助的話, 可以用這個推薦連結: https://www.overleaf.com?r=cc96d36b&rm=d&rs=b (幫我增加一下點數 XD)

----
## 使用方式
* 論文的主頁是 main.tex, 在這邊輸入個人資料 (自己名字, 指導教授, 論文名稱...等), 然後在此頁案按compile就會生成PDF了
* 論文章節是拆成多個檔案, 可留意main.tex裡面提到的資訊

## 本樣板特色 (自己說的XD)
* 支援中文+英文版的目錄格式
  * 開啟 \toggletrue{toc-use-cn} 就變成中文目錄
* 支援碩士+博士論文格式
  * 開啟 \toggletrue{iamphd} 就變成博士論文
* 畢業系所的資料改到主頁, 在main.tex裡填入系所的資訊, 就會連帶更新後面的封面、書名頁、中英文摘要

### 主頁的說明(main.tex)
* 使用英文目錄: 不需要改動
* 使用中文目錄: 把%\toggletrue{toc-use-cn}的註解(%)拿掉

#### 填寫個人資料
```
% --------------------------------------------
% 在這邊寫自己的資料

% 論文名稱
\newcommand{\chineseTitle}{中文論文名字}
\newcommand{\englishTitle}{English Title}

% 自己的名字
\newcommand{\studentCnName}{學生名字}
\newcommand{\studentEnName}{XXXX Wu} % 書名頁
\newcommand{\studentEnNameA}{Wu, XXXX} % 封面用
% 英文名字有兩種寫法, 一個是姓在後, 一個是放前面. 

% 教授的名字
\newcommand{\advisorCnName}{指導教授名字}
\newcommand{\advisorEnName}{OOOO Tseng}     % 書名頁
\newcommand{\advisorEnNamex}{Tseng, OOOO}   % 封面用

% 共同指導教授的名字, 若有再填寫即可.
% 如果你有第三位共同指導教授, 就自己改tex裡面的內容吧 XD
%\newcommand{\advisorCnNameB}{共同指導教授名字}
%\newcommand{\advisorEnNameB}{OOO Lin}     % 書名頁
%\newcommand{\advisorEnNameBx}{Lin, OOO}   % 封面用


% 論文的日期
\newcommand{\ThesisDate}{August 2022}           
\newcommand{\ThesisDateTW}{中華民國~ 一一一年八月} 

% 博士班就把下方註解拿掉吧!!
%\toggletrue{iamphd}
% --------------------------------------------
```

#### 封面&書名頁
* 目前設計是假設論文名稱都是一行. 如果中文or英文名稱太長會自動換行, 可以手動調整inside.tex裡的標題字體大小, 這樣就可以讓浮水印剛好包住校名還有系所資訊. (看起來比較好看!?)

```
% [書名頁] 各學院、系所、學位中文、英文名稱: 
\newcommand{\CollegeCnName}{資訊學院} % 這個其實沒用到, 不過為了一致還是放進來
\newcommand{\CollegeEnName}{College of Computer Science}
\newcommand{\DepartInstitCnName}{網路工程研究所} % 系所名稱, 請看下方[說明1]
\newcommand{\DepartInstitEnName}{Institute of Network Engineering}
\newcommand{\DegreeName}{Master of Science} % 學位名稱, 常見的是Master of Science, 不過這個有很多寫法, 要記得查學校的資料.
\newcommand{\ResearchTopic}{Computer Science} % 研究領域, 請看下方[說明2]

% [說明1]
% 這邊需要填寫 XX系 or OO所 的名稱
% 如果你的單位是系所合一, 就用 Department. 如: 土木系碩士班請用 Department
% 只有所的話, 就用Institute. 如: 電信所請用Institute


% [說明2]
% 書名頁的最後會有 in OOOO 的內容. 這個目前找不到通用性的寫法. 
% 大家就自行找前人的畢業論文, 看同系所的人是怎麼寫, 就跟他們寫一樣的吧.
% 不過有些系所不需要寫這個東西, ex: 教育所. 不需要的話就把\ResearchTopic整句刪掉

% 中英文名稱請看學校網站: https://aa.nycu.edu.tw/reg/統計資訊/
```


#### 口試後才有的文件
* 口試結束後, 會有一些文件(3&5)需要口委們簽名, 最後上傳到圖書館需要加這些東西. 論文初稿不需要. (我當年畢業不需要4 XD)
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
* Ref有很多種風格寫法, 本篇論文是採用bibliographystyle\{IEEEtran\}
* overleaf上有其他style語法, 可以參考: https://www.overleaf.com/learn/latex/Bibtex\_bibliography\_styles

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
* 2023.12: 大幅度更新(!?) 直接整合碩博士的寫法, 還有把系所的資訊拉到主頁當變數, 也考慮到有共同指導教授的情境.