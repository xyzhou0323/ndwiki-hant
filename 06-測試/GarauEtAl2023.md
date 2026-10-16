---
title: Garau 等（2023）：單焦點注意問卷的開發與初始驗證
description: Garau 等（2023）的 Development and Validation of a Novel Self-Report Measure of Monotropism in Autistic and Non-Autistic People 研究介紹：1,110人的 MQ 組均分、孤獨譜系與 ADHD 分組結果，以及探索性八因素結構和測量侷限。
aliases:
  - GarauEtAl2023
  - Garau et al. (2023)
  - 單焦點注意問卷的開發與驗證
tags:
  - work
  - autism
  - attention
  - methodology
sources:
  - tests/2026-10-13/MonotropismQuestionnaire/NeuroXYZ-website-reference/mq-data.js
  - tests/2026-10-13/MonotropismQuestionnaire/NeuroXYZ-website-reference/mq-reference.js
  - tests/2026-10-13/MonotropismQuestionnaire/MQ_preprint_manuscript-tables-supplement.pdf
citation_apa: "Garau, V., Murray, A., Woods, R., Chown, N., Hallett, S., Murray, F., Wood, R., & Fletcher-Watson, S. (2023). Development and validation of a novel self-report measure of monotropism in autistic and non-autistic people: The Monotropism Questionnaire [Preprint]. https://osf.io/g4kc9/"
created: 2026-10-13
updated: 2026-10-13
zh-hans: [[wiki/06-测试/GarauEtAl2023]]
needs-review: true
---

# Garau 等（2023）：單焦點注意問卷的開發與初始驗證

> [!infobox] Garau et al. (2023)
> **作者**：Valeria Garau、Aja Murray、Richard Woods、Nick Chown、Sonny Hallett、Fergus Murray、Rebecca Wood、Sue Fletcher-Watson
> **年份**：2023
> **類型**：預印本；問卷開發與初始驗證研究
> **原題**：Development and Validation of a Novel Self-Report Measure of Monotropism in Autistic and Non-Autistic People: The Monotropism Questionnaire
> **原文**：[OSF 預印本](https://osf.io/g4kc9/)
> **項目資料**：[問卷、研究與開放數據](https://osf.io/wpx5g/)
> **問卷介紹**：[[MQ|單焦點注意問卷（MQ）]]

引用：Garau, V., Murray, A., Woods, R., Chown, N., Hallett, S., Murray, F., Wood, R., & Fletcher-Watson, S. (2023). *Development and validation of a novel self-report measure of monotropism in autistic and non-autistic people: The Monotropism Questionnaire* [Preprint]. https://osf.io/g4kc9/

Garau 等人的研究嘗試把[[單焦點注意]]理論轉化爲可測量的自填問卷，並初步檢驗[[MQ]]的羣體差異、與已有量表的關聯及內部結構。47題由孤獨譜系成年人結合生活經驗和學術知識共同提出與修訂；研究支持進一步探索這種認知風格，沒有建立孤獨譜系或 ADHD 診斷測試。

## 樣本與分組方式

研究通過社交媒體、通訊和口耳相傳招募參與者，排除不符合資格及少於40題有效作答者後，分析樣本爲1,110人，年齡16至78歲，平均39歲（SD＝12）。孤獨譜系組756人，非孤獨譜系組354人。

孤獨譜系組包括臨牀診斷、自我認同和認爲自己可能爲孤獨譜系者；非孤獨譜系組包括回答“不是”或“不確定”者。ADHD 狀態採用同樣的合併規則，因此“ADHD 組”也不等於全部已經臨牀確診。研究結果依賴這套分組方式，不能推廣爲所有診斷人羣的常模。

## 各組整體均分

MQ 採用反向計分後的有效題平均分，範圍1至5。預印本第8頁和表1報告：

| 研究分組 | 人數 | MQ 均分 | 標準差（SD） |
|---|---:|---:|---:|
| 非孤獨譜系組 | 354 | 3.19 | 0.578 |
| 孤獨譜系組 | 756 | 4.15 | 0.347 |

孤獨譜系組均分顯著較高（Mann–Whitney 檢驗，p＜.001）。這是兩組分佈的比較，均分和標準差不能用作個人身份判定界線。

### 孤獨譜系組內部的診斷／認同狀態

作者在敏感性分析中進一步區分三組（均分與標準差見第8頁，人數見表1）：

| 孤獨譜系狀態 | 人數 | MQ 均分 | 標準差（SD） |
|---|---:|---:|---:|
| 臨牀診斷 | 394 | 4.19 | 0.352 |
| 自我認同 | 204 | 4.19 | 0.319 |
| 認爲自己可能爲孤獨譜系 | 158 | 4.01 | 0.329 |

臨牀診斷與自我認同組的均分差異不顯著；“可能”組均分較低。這個結果不意味着問卷能裁定自我認同是否有效，也不意味着4.19是身份閾值。

### 孤獨譜系與 ADHD 狀態的聯合分析

表2的迴歸模型納入1,109人；另1人缺少 ADHD 狀態。由表1的分組人數與表2四捨五入後的係數，可整理出以下模型擬合均分近似值：

| 研究分類組合 | 人數 | 模型擬合均分（約） |
|---|---:|---:|
| 非孤獨譜系、非 ADHD | 253 | 3.03 |
| 非孤獨譜系、ADHD | 100 | 3.59 |
| 孤獨譜系、非 ADHD | 323 | 4.07 |
| 孤獨譜系、ADHD | 433 | 4.20 |

這些近似值由截距3.03、孤獨譜系係數1.04、ADHD 係數0.56和交互係數−0.43相加得到，不是從圖2讀取的精確觀測均分。正文將 ADHD 係數寫爲0.55，表2爲0.56；這裏統一按表2計算，不賦予兩位小數以上的精度。

孤獨譜系狀態與 ADHD 狀態均關聯較高 MQ 得分，但兩者的關聯並非簡單相加：負交互項表示同時被歸入兩組者的得分增量小於純加和預期，並不表示 ADHD 會使孤獨譜系者的均分低於非 ADHD 孤獨譜系者。模型解釋約57.4%的分數方差；橫斷面關聯不能確定因果關係。

## 探索性八因素結構

作者使用最小殘差法提取因素、斜交旋轉，允許維度相互關聯。平行分析建議保留八因素，MAP 檢驗建議四因素，碎石圖支持四至八因素；作者比較五個方案後，綜合擬合指標、概念區分和解釋性選擇八因素。八因素方案的 RMSEA＝.035、TLI＝.935，但 BIC 更偏向七因素，說明因素數量並非所有方法一致支持。

下表依據補充表 S3 和補充材料，沿用原問卷題號；中文名稱與本站測試顯示一致。

| 因素／本站主題 | 原文維度名稱 | 題號 | 內容 |
|---|---|---|---|
| 1．興趣與熱情 | Special interests | 44、43、25、45、28、39、40、14 | 深入、持續的興趣投入與熱情 |
| 2．反覆思考與焦慮 | Rumination and anxiety | 37、42、22、36、47、46 | 反覆思考事件、選擇及不確定性 |
| 3．固定安排的需要 | Need for routines | 20、21 | 日常安排提供穩定感並幫助應對不確定性 |
| 4．環境對注意的影響 | Environmental impact on the attention tunnel | 4、2、3、16、5、26、1、18 | 打斷、環境刺激與活動切換對專注的影響 |
| 5．專注時忽略其他需要 | Losing track of other factors when focusing on special interests | 32、33、12、10 | 專注時較少察覺身體需要、時間及其他事件 |
| 6．決策與任務投入困難 | Struggle with decision-making | 34、35、38、23 | 信息處理、選擇以及投入無興趣任務的困難 |
| 7．興趣對焦慮的緩解 | Anxiety-reducing effect of special interests | 8、19、9 | 興趣活動緩解焦慮並提高圍繞興趣交流的舒適感 |
| 8．社交互動中的體驗 | Managing social interactions | 30、6、27、31、15、13 | 多人交流、目光接觸、表達及對他人反應的預期 |

作者以絕對載荷大於.30爲顯著載荷標準。第26題同時載荷於因素4與8，因在因素4的載荷略高而歸入因素4；第7、11、17、24、29、41題未強載荷於任何因素，排除在八因素結構之外。因此八個題組共41題，不能把八個主題均分直接平均，代替47題的整體均分。

這八個維度用於描述體驗的不同方面，不是八種人格或診斷類型。高分的含義依賴題目內容，例如興趣緩解焦慮與決策困難分別描述調節作用和困難，不能統一解釋爲“問題更嚴重”。各維度仍需獨立樣本和進一步結構驗證。

## 信效度結果與侷限

MQ 與 RAADS-14 的 Spearman 相關爲.78，與 AQ-10 爲.71；這支持與相關特徵的聚合效度，但不能證明可替代診斷評估。內部一致性計算針對排除上述六題後的結構，報告總 omega＝.96、一般因素的層級 omega＝.81；這些整體指標不等於八個題組各自已經充分驗證，也不等於重測信度。

樣本約88%爲白人，教育程度較高；研究自填方式可能限制伴隨智力障礙者參與。研究未檢驗重測信度，本頁所據研究也未驗證本站中文譯文。[[MQ|本站測試頁介紹]]另外列出的八主題組均分，是網站按公開數據計算的描述性參考，來自不同於本研究1,110人分析的篩選樣本，不能歸爲論文直接報告的結果。

研究稿的作者順序與問卷文件的推薦引用不同：研究稿將 Aja Murray 列爲第二作者，問卷推薦引用將其列在第七位。引用研究結論時應使用本頁研究稿引用，引用問卷本身時使用[[MQ]]頁面的問卷引用。

## Related

- [[單焦點注意]] — 被操作化測量的認知風格
- [[MQ]] — 問卷計分、本站測試與主題參考均分
- [[AQ]] — 研究使用其10題短版 AQ-10
- [[RAADS-R]] — 本研究使用 RAADS-14，不能混同於80題 RAADS-R
- [[相關測試]] — 測試與工具導航
