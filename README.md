# NYCU-thesis-template (國立陽明交通大學的碩博士論文Latex樣板)
* Overleaf template: https://www.overleaf.com/latex/templates/nycu-thesis-template/jgcmcnchmbrc
* NYCU (National Yang Ming Chiao Tung University) thesis template. This template supports English TOC & 中文目錄. You can change this by uncommenting a command. The Word version of 封面&書名頁 is also available in this project.
* 此樣板已多次上傳論文到圖書館, 應該是沒太多問題(!?)
* 裡面也有提供word版的封面跟書名頁, 有需要的人可以直接取用: https://github.com/coldwufish/NYCU-thesis-template/tree/main/covers/%E5%AD%B8%E6%A0%A1%E6%A0%BC%E5%BC%8F%E8%B3%87%E6%96%99

----
## 使用方式
* 論文的主頁是 main.tex, 在這邊輸入個人資料 (自己名字, 指導教授, 論文名稱...等), 然後在此頁案按compile就會生成PDF了
* 論文章節是拆成多個檔案, 放在Section資料夾裡, 可留意main.tex裡面提到的資訊

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
% #### 下面是自己的資料 ####

% 博士班就把下方註解拿掉吧!!
%\toggletrue{iamphd}

% 論文名稱
\newcommand{\chineseTitle}{論文名稱}
\newcommand{\englishTitle}{English Title}

% 自己的名字 (英文名字有兩種寫法, 一個是姓在後, 一個是放前面還有逗號. )
\newcommand{\studentCnName}{學生名字}
\newcommand{\studentEnName}{XXXX Wu} % 書名頁
\newcommand{\studentEnNameA}{Wu, XXXX} % 封面用

% 教授的名字
\newcommand{\advisorCnName}{指導教授名字}
\newcommand{\advisorEnName}{OOOO Tseng}     % 書名頁
\newcommand{\advisorEnNamex}{Tseng, OOOO}   % 封面用

% 共同指導教授的名字, 若有再填寫即可. 目前只支援兩位指導教授的欄位
%\newcommand{\advisorCnNameB}{共同指導教授名字}
%\newcommand{\advisorEnNameB}{OOO Lin}     % 書名頁
%\newcommand{\advisorEnNameBx}{Lin, OOO}   % 封面用

% 論文提交的日期，可以寫口試日期 or 畢業日期
\newcommand{\ThesisDate}{August 2022}           
\newcommand{\ThesisDateTW}{中華民國~ 一一一年八月} 
```

#### 封面&書名頁

```
% [書名頁] 可參考教務處的 學位授予名稱 寫法
% https://aa.nycu.edu.tw/aa/ch/app/statisticalmap/list?module=statisticalmap&id=4358

% 詳情請向系所承辦人員確認，以系所提供的資訊為主

% 下面變數也改為跟表格一樣的名稱, 後綴的CN與EN表示中英文
% 學校連結: https://aa.nycu.edu.tw/aa/ch/app/statisticalmap/list?module=statisticalmap&id=4358
\newcommand{\NameofCollegeCN}{資訊學院} % 這個其實沒用到, 不過為了一致還是放進來
\newcommand{\NameofCollegeEN}{College of Computer Science}
\newcommand{\NameofDepartmentInstituteCN}{網路工程研究所} % 系所名稱, 請看下方[說明1]
\newcommand{\NameofDepartmentInstituteEN}{Institute of Network Engineering}
\newcommand{\NameofDegree}{Master of Science} % 學位名稱, 常見的是Master of Science, 不過這個有很多寫法, 要記得查學校的資料.
\newcommand{\ResearchTopic}{Computer Science} % 研究領域, 請看下方[說明2]

% [說明1]
% 這邊需要填寫 XX系 or OO所 的名稱
% 如果你的單位是系所合一, 就用 Department. 如: 土木系碩士班請用 Department
% 只有所的話, 就用Institute. 如: 電信所請用Institute

% [說明2]
% 書名頁的最後會有 in OOOO 的內容. 這個目前找不到通用性的寫法. 
% 大家就自行找前人的畢業論文, 看同系所的人是怎麼寫, 就跟他們寫一樣的吧.
% 不過有些系所不需要寫這個東西, ex: 教育所. 
% 不需要的話就把\ResearchTopic整句刪掉
```


#### 口試後才有的文件
* 圖書館有說: **授權書(3)&審定書(5)要裝訂於紙本論文中**，不用放在PDF電子檔裡面。
* 3跟5的插入語法就直接拿掉了 (因為也用不到)

```
% 口試結束後, 會有一些文件(3&5)需要口委們簽名 (我當年畢業不需要4 XD)

% 3. 論文電子檔著作權授權書: (要裝訂在紙本論文)

% 4. 博士論文指導教授推薦書(碩士論文免附) 由各所自定，可有可無。: phd_recommend.pdf
%\includepdf[pages={1},pagecommand={\thispagestyle{empty}}]{phd_recommend.pdf}

% 5. 學位論文審定同意書(審定書): (要裝訂在紙本論文)
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

  * [113年2月19日後上傳圖書館博碩士論文系統者適用] 不用附在論文PDF檔裡面
    * 15. 學位論文發表形式確認書【詳附件 5】
    * 16. 著作彙編之學位論文資訊及彙編學術著作之共同作者貢獻聲明書(非著作彙編之學位論文免附)
    * 可以去這個連結看15與16: https://aa.nycu.edu.tw/userfiles/aach/files/20240125111443441.pdf
      * 心得: 「著作彙編之學位論文」（Thesis by Publication，簡稱TBP） https://ethics.moe.edu.tw/resource/epaper/html/27/
        * 看起來是拿已發表的論文作為畢業論文, 需要填寫這個資料. 如果沒有發論文, 看起來是選"不採用著作彙編".

---
---
## 填寫範例
### 填寫範例 (博士班)
```
\toggletrue{iamphd}
\newcommand{\CollegeCnName}{電機學院} 
\newcommand{\CollegeEnName}{College of Electrical and Computer Engineering}
\newcommand{\InstituteCnName}{電信工程研究所}
\newcommand{\InstituteEnName}{Institute of Communications Engineering}
\newcommand{\DegreeName}{Doctor of Philosophy} 
\newcommand{\ResearchTopic}{Electronics and Electrical Engineering}
```

### 填寫範例 (碩士班)
```
\newcommand{\CollegeCnName}{資訊學院} 
\newcommand{\CollegeEnName}{College of Computer Science}
\newcommand{\InstituteCnName}{網路工程研究所}
\newcommand{\InstituteEnName}{Institute of Network Engineering}
\newcommand{\DegreeName}{Master of Science}
\newcommand{\ResearchTopic}{Computer Science} 
```

---
---
## 圖書館的資訊
* 學位論文編寫事項 https://www.lib.nycu.edu.tw/custom_label?menu=64&lid=6
* 教務處的學位論文相關表件 https://aa.nycu.edu.tw/aa/ch/app/data/list?module=nycu0038&id=2468
* 書名頁學位名稱英文，請依照註冊組提供各學院、系所學位中英文名稱.
  * 學位授予名稱 https://aa.nycu.edu.tw/aa/ch/app/statisticalmap/list?module=statisticalmap&id=4358
* 臺灣博碩士論文知識加值系統 https://ndltd.ncl.edu.tw/
  * 可用來查詢前人的論文, 看之前的畢業生是怎麼寫
* 圖書館FB: https://www.facebook.com/NYCULIB
* 紙本裝訂順序
  * 封面 >> 書名頁 >> 電子檔著作權授權書 >> 紙本延後公開申請書(如果有) >> 審定同意書 >> 論文內容(致謝-附錄) >> 形式確認書 >> 共同作者貢獻度聲明書(彙編著作者)
* 注意: 有簽名的表單不用放到論文電子檔裡面, 上傳圖書館的時候會有相應欄位讓你上傳.

---
---
閒聊: 大概每年的6月份會更新一下. 除非我換工作離開學校(!?) 不然應該會一直更新下去 XD

* 原始檔案已經不可考, 是研究所時期實驗室傳承下來的版本, 想當年還沒有overleaf, 自己裝miktex超麻煩 zzz...
* 2023.06: 更新學校浮水印, 改了一下浮水印的語法 (原本的會噴error msg), 也把一些環境變數(usepackage那些)弄到另一個檔案, 看起來會比較清爽!?
* 2023.11: 竟然有人發現編排順序跟學校的格式不一樣!! (致謝應該要往前挪一個) 之前都沒人注意到 XDD
* 2023.11: 竟然有人寄信詢問碩論格式的事!! (原來有其他人會用, 覺得感動XD) 因為原本是針對英文論文去整理, 後來弄出中文目錄了. 可是回頭來看又覺得中英混雜很奇怪, 就改成 純英文目錄 & 純中文目錄 了!! 目前預設是英文目錄, 把開頭的某個註解拿掉就變成中文目錄. 
* 2023.11: 調整一下排版, 看起來比較美觀(!?)
* 2023.11: 再多補充一些說明還有使用心得(?) 剛剛發現中文的Figure與Table忘了改成中文, 也一併修正.
* 2023.12: 大幅度更新(!?) 直接整合碩博士的寫法, 還有把系所的資訊拉到主頁當變數, 也考慮到有共同指導教授的情境.
* 2024.04: 調整第二頁的書名頁語法, 偵測中英文標題的文字長度, 讓它限制在一列的範圍. 並且加上minipage控制高度, 這樣高度就不會發生變化 (從研究生那邊開始 XD)
* 2024.04: 把目錄的語法弄到另一個檔案(toc_var.tex), 讓主頁看起來比較清爽(!?) 現在上傳圖書館還要附上新的資料:
* 2024.05: 更新一下 & 修飾主頁的內容
* 2024.05: 新增subfigure範例 & 附錄範例
* 2024.06: 根據圖書館的說明修了一下主頁(main.tex)的內容, 還有Excel2Latex的作法.
* 2024.08: 語法大幅度修改, 改成xelatex去編譯. 現在中文內容可以直接使用\textbf{粗體}跟\textit{斜體}了. 還有研究overleaf支援的字體清單, 目前選擇TW-Kai, 這個字體同時支援繁體與簡體中文, 有一些特殊字可以直接顯示, 像是之前有人問過的核苷酸.
* 2024.09: 有人發現誌寫的內文是舊版XD 也改了一下浮水印的用法, 編譯速度應該會比較快(!?)
* 2024.10: 後來發現致謝可以不用出現在目錄 (可能變成非必要項目!?), 就修了一下語法
* 2024.11: 發現英文字體不能粗體, 這個bug修一修之後竟然也把警告訊息也確認書 >> 共同作者貢獻度聲明書(彙編著作者)
* 注意: 有簽名的表單不用放到論文電子檔裡面, 上傳圖書館的時候會有相應欄位讓你上傳.
￼
---
---
閒聊: 大概每年的6月份會更新一下. 除非我換工作離開學校(!?) 不然應該會一直更新下去 XD
￼
* 原始檔案已經不可考, 是研究所時期實驗室傳承下來的版本, 想當年還沒有overleaf, 自己裝miktex超麻煩 zzz...
* 2023.06: 更新學校浮水印, 改了一下浮水印的語法 (原本的會噴error msg), 也把一些環境變數(usepackage那些)弄到另一個檔案, 看起來會比較清爽!?
* 2023.11: 竟然有人發現編排順序跟學校的格式不一樣!! (致謝應該要往前挪一個) 之前都沒人注意到 XDD
* 2023.11: 竟然有人寄信詢問碩論格式的事!! (原來有其他人會用, 覺得感動XD) 因為原本是針對英文論文去整理, 後來弄出中文目錄了. 可是回頭來看又覺得中英混雜很奇怪, 就改成 純英文目錄 & 純中文目錄 了!! 目前預設是英文目錄, 把開頭的某個註解拿掉就變成中文目錄. 
* 2023.11: 調整一下排版, 看起來比較美觀(!?)
* 2023.11: 再多補充一些說明還有使用心得(?) 剛剛發現中文的Figure與Table忘了改成中文, 也一併修正.
* 2023.12: 大幅度更新(!?) 直接整合碩博士的寫法, 還有把系所的資訊拉到主頁當變數, 也考慮到有共同指導教授的情境.
* 2024.04: 調整第二頁的書名頁語法, 偵測中英文標題的文字長度, 讓它限制在一列的範圍. 並且加上minipage控制高度, 這樣高度就不會發生變化 (從研究生那邊開始 XD)
* 2024.04: 把目錄的語法弄到另一個檔案(toc_var.tex), 讓主頁看起來比較清爽(!?) 現在上傳圖書館還要附上新的資料:
* 2024.05: 更新一下 & 修飾主頁的內容
* 2024.05: 新增subfigure範例 & 附錄範例
* 2024.06: 根據圖書館的說明修了一下主頁(main.tex)的內容, 還有Excel2Latex的作法.
* 2024.08: 語法大幅度修改, 改成xelatex去編譯. 現在中文內容可以直接使用\textbf{粗體}跟\textit{斜體}了. 還有研究overleaf支援的字體清單, 目前選擇TW-Kai, 這個字體同時支援繁體與簡體中文, 有一些特殊字可以直接顯示, 像是之前有人問過的核苷酸.
* 2024.09: 有人發現誌寫的內文是舊版XD 也改了一下浮水印的用法, 編譯速度應該會比較快(!?)
* 2024.10: 後來發現致謝可以不用出現在目錄 (可能變成非必要項目!?), 就修了一下語法
* 2024.11: 發現英文字體不能粗體, 這個bug修一修之後竟然也把警告訊息清光了!!