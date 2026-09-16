# Amazon Data Center Operations Manager 面試準備（中文整合稿）

## 使用原則

這份草稿以已確認的實際經驗與數據為基礎，回答時採用「結論先行＋STAR」，需要說明技術選項時再加入 `Options／Decision`。

每題建議控制在二至三分鐘，並優先說清楚：

- 當時的環境規模與客戶影響。
- 我個人的責任、判斷和行動，而不只說「我們」。
- 評估過的選項、風險、限制和取捨。
- 可驗證的量化結果。
- 從事件中建立了哪些長期改善機制。

## 跨題共通管理機制：Documentation Lifecycle

所有專案、變更、演練或Incident完成後，我都要求完成文件整理、審查、歸檔和溝通，不能把「技術工作完成」直接當成「工作正式結案」。

結案文件依工作類型至少包括：

- 最終Scope、Architecture及As-built Configuration。
- MOP、SOP、EOP、Runbook、Rollback及Validation方法。
- Project Decision、Change Record、Incident Timeline及重要Evidence。
- RCA、Lessons Learned、Corrective／Preventive Actions。
- 未完成風險、相依性、Owner、期限及驗證方式。
- Asset、CMDB、Vendor、Contact與Escalation資料。

文件歸檔時必須具備Owner、Version、Approval、Effective Date及Review Date，並依資訊分級與Need-to-know原則，向相關部門公告結案結果、影響、操作變更和後續責任。Critical Procedure或重大變更需要確認相關人員已閱讀、接受Training或完成必要認證。

後續只要Architecture、Configuration、Procedure、Contact、Vendor或Failure Mode改變，就必須把文件更新列入Change的Definition of Done，同步更新Version History及相關連結；舊版本保留為可追溯紀錄，但明確標示Superseded，避免工程師在Incident期間使用過期文件。

這個機制形成：

`Complete → Review → Document → Approve → Archive → Communicate → Maintain`

對應Leadership Principles：

- Ownership
- Insist on the Highest Standards
- Earn Trust
- Learn and Be Curious

本版本已融入以下實際經驗：

- 遊戲橘子、鴻海、泰偉電子的 Local Data Center 經驗
- 管理 300 台以上伺服器
- 10G 三點環形網路
- 後續管理 500 個以上服務
- Power、Cooling、Capacity、People、Change、Supply Chain、Security 管理方法
- 每題標註 Amazon Leadership Principles

本版本新增：

- 第4題：馬來西亞連鎖網咖遊戲上線後的掉單P0事件，包含War Room、Rollback、Kafka Root Cause與自動化改善。
- 第5題：先驗證Data Source、Timestamp、Sampling Frequency、Aggregation及完整性，再建立時間線與驗證Root Cause。
- 第7題：7×24團隊的情境演練、能力驗證和壓力下協作。
- 第13題：過度相信Monitoring Dashboard平均值的真實錯誤判斷，並加入Metrics來源、CPU Peak、採集頻率與AWS Data Center適用性的追問。
- 第14題：`Scenario Simulation → Observe → Identify Gaps → Correct → Re-test`持續驗證循環。
- 跨題共通機制：所有專案、變更、演練與Incident結案後完成文件歸檔、部門公告及後續版本維護。

這一輪只更新中文內容草稿，不更新網站或推送Git。

---

## 1. 請介紹你自己

我有超過 23 年企業 IT 經驗，以及超過 14 年的人員管理經驗。我的主要專長包括實體資料中心、基礎架構營運、網路、雲端、資訊安全、自動化、Incident Management，以及跨國團隊管理。

我的實體機房管理經驗主要來自遊戲橘子、鴻海和泰偉電子。這些環境都是公司自行管理的 Local Data Center。我曾負責管理 300 台以上伺服器、10G 三點環形網路，後續管理的服務規模超過 500 個。

在泰偉電子，我從零建置約 20 個機櫃的 Payment Data Center，範圍包括雙路電力、UPS、配電、冷卻、環境監控、消防、網路、防火牆、伺服器、儲存、備份和監控，並通過 Visa 支付機房相關稽核（Visa payment data center audit）。

我管理資料中心時，不會只關注伺服器是否正常。我會同時管理 Power、Cooling、Capacity、Network、People、Change、Supply Chain 和 Security，因為任何一個環節失效，都可能造成服務和客戶影響。

我也持續研究新技術，特別是Kafka Data Streaming（Kafka資料串流）與事件驅動架構。系統上線後，我協助整合IT環境的Metrics、Logs、Infrastructure Events與Change Records，以及營運環境的交易、使用者行為和服務結果，讓IT與Operations可以根據同一條資料流進行判斷。

針對不同需求，我會設計不同的自動化應用：在IT Operations方面，用於Monitoring、Event Correlation、Incident Triage、Runbook執行和服務恢復；在Business Operations方面，用於即時Dashboard、交易異常識別、影響範圍判斷和營運決策支援。近期我也開始將AI導入IT營運流程，讓AI協助關聯Metrics、Logs、Changes和歷史Incident Knowledge，更快判斷異常類型、可能原因及建議檢查步驟，以縮短MTTD與初步診斷時間。AI定位為Decision Support，高風險操作仍必須由工程師驗證，並依照Change與Approval流程執行。

我也曾帶領最多 60 人的跨國團隊，管理每年約 300 萬至500 萬美元的預算。我的核心能力是把複雜的技術環境轉換成可量測、可管理、可持續改善的營運服務。

對應 Leadership Principles：

- Ownership
- Deliver Results
- Dive Deep
- Hire and Develop the Best
- Think Big
- Learn and Be Curious

---

## 2. 為什麼選擇 Amazon？為什麼對 Data Center Operations Manager 有興趣？

我想加入 Amazon，是因為 AWS 的資料中心營運會直接影響全球客戶。這個職位要求的不只是技術能力，也包括安全、營運紀律、風險管理、人員發展和持續改善，這些都和我的工作經驗及管理方式非常接近。

我的實體機房經驗來自遊戲橘子、鴻海和泰偉電子。我曾管理 300 台以上伺服器、10G 三點環形網路，以及後續超過 500 個服務，也曾從零建置約 20 個機櫃的 Payment Data Center。

此外，我在多間公司都是AWS的企業客戶，曾從遊戲服務、CDN與跨國網路、Hybrid Cloud、資訊安全及企業IT營運等不同角度使用AWS。不同客戶關注的重點並不相同：遊戲服務重視Latency、Peak Traffic與Availability；跨國服務重視Network Quality與Multi-region Resilience；企業環境則更重視Security、Compliance、Cost Control與Disaster Recovery。

這些經驗讓我不只具備營運基礎設施的觀點，也了解客戶實際如何感受AWS服務。對客戶而言，單一設備或Dashboard正常並不代表服務正常；他們更關心端到端服務是否可用、事件資訊是否透明、恢復時間是否可預期，以及問題是否真正得到改善。我希望把這些不同的Customer Perspectives帶進AWS，透過正式的營運與回饋機制，協助團隊持續改善Capacity、Reliability、Incident Response和Customer Communication，讓AWS提供更穩定、更符合客戶需求的服務。

加入AWS對我而言，也是把過去管理Local Data Center的能力帶到更大規模環境中驗證和提升。我過去建立的Safety、Capacity、Change、Incident、Monitoring、Automation及7×24 Team Management方法具有可移轉性，但我不會假設Local Data Center與AWS的作業方式完全相同。我會先學習Amazon既有的標準、程序和Metrics，再用營運數據驗證哪些經驗可以直接應用、哪些必須因應AWS的規模、複雜度和風險模型調整。這同時能讓我快速貢獻，也能持續提高自己的資料中心管理能力。

我認為 Data Center Manager 的責任不是單純把 Server 顧好，而是要在 Power、Cooling、Capacity、Network、People、Change、Supply Chain 和 Security 這些彼此相依的系統中，持續維持 Availability。

例如進行 UPS 維護時，不能只確認 UPS 本身，還要確認另一側電力負載、ATS、Generator、Battery Runtime、Critical Workload、Rollback Plan，以及誰有 Stop Work Authority。

這種以風險、客戶影響和營運紀律為核心的管理方式，與 Amazon Leadership Principles 非常一致。我希望把既有的實體機房、7×24 營運、事件處理和團隊管理經驗帶到 AWS，也進一步學習 AWS 在全球規模下的資料中心管理標準。

對應 Leadership Principles：

- Customer Obsession
- Ownership
- Insist on the Highest Standards
- Think Big
- Learn and Be Curious

---

## 3. 請分享你帶領過最複雜的資料中心專案

### 面試結論

在泰偉電子，我從零帶領建置一座約20個機櫃的Payment Data Center。這個專案不只是完成Network和System建置，而是從零建立六個彼此相依的範圍：Data Center Infrastructure、System Environment、CI/CD and Deployment Automation、Monitoring and Operations Data Platform、Third-party Vendor and Cost Governance，以及7×24 Operations Team。

我的目標不是把設備開機就交付，而是建立完整的Production Environment，讓系統可以持續部署、即時監控、用數據判斷異常，並由受過訓練的團隊全天候維運。最後我們完成機房、平台、資料和營運團隊的零到一建置，並通過Visa支付機房相關稽核。

### Situation

在泰偉電子，公司需要建立一座支援 Payment Services 的 Local Data Center。這不是單純採購伺服器，而是從零建立完整的資料中心基礎設施。

專案規模約為 20 個機櫃，包含雙路電力、UPS、配電、冷卻、環境監控、消防、網路、防火牆、伺服器、儲存、備份和監控。

### Task

我是公司的IT最高主管，必須從零建立完整的Technology and Operations Platform。範圍不只包括資料中心、Network及System Environment，也包括CI/CD、自動化部署、Monitoring and Observability、營運數據中台、第三方供應商與成本治理，以及後續7×24維運團隊。

我必須負責整體架構、預算、供應商、施工、Commissioning、驗收、資產交接和營運制度，並確保環境符合Payment Service要求及Visa支付機房稽核控制要求。

### Options／Decision

我們評估過沿用既有環境、完全交由外部 IDC 管理，或建立專用的 Local Data Center。

我選擇建立專用環境，因為 Payment Service 對電力、網路、存取控制、備份、稽核和營運管理都有較高要求。專用環境可以從設計階段整合這些控制。

### Action

我將專案分成設計、採購、施工、設備安裝、測試、Commissioning 和 Handover 等階段，並為供應商定義責任與驗收標準。

我把建置工作分成六個Workstreams（工作流）：

#### 1. Data Center Infrastructure

- 檢查完整Power Chain，而不是只看UPS總容量。
- 確認Cooling、Rack Space、Network Port、Fiber、消防、環境監控及未來Capacity。
- 對電力、冷卻、消防、門禁及機櫃施工建立驗收條件與Commissioning測試。

#### 2. Network and System Environment

- 建立10G三點環形網路、Network Segmentation、Firewall及Load Balancer，提高站點與服務之間的Network Resilience。
- 建立Development、Staging及Production Environment，完成Server、Virtualization、Storage、Backup、Database、Middleware及Application Runtime所需環境。
- 定義帳號權限、Configuration Baseline、Patch、Backup、High Availability及Disaster Recovery標準。

#### 3. CI/CD and Deployment Automation

- 使用Git、Jenkins／GitLab CI及Ansible建立標準化CI/CD與自動部署流程，將Version Control、Build／Release、Configuration Template、Approval、Pre-check、Post-check及Rollback納入交付流程。
- 確保Development、Staging及Production使用一致且經過驗證的Artifact，降低人工部署和Configuration Drift風險。
- 對高風險變更建立MOP、Maintenance Window、Stop Condition及Rollback Plan。

#### 4. Monitoring and Operations Data Platform

- 建立涵蓋Power、Cooling、Network、Server、Storage、Application及Service的Monitoring、Logging與Alerting機制。
- 規劃營運數據中台，整合IT環境的Metrics、Logs、Infrastructure Events及Change Records，以及營運環境的交易、使用者行為和服務結果。
- 透過共同的Timestamp、Service ID及Transaction ID建立關聯，支援即時監控、異常分析、影響範圍判斷和營運決策。
- 執行備份還原、Failover及Rollback測試，確認Dashboard正常之外，端到端服務也真正可用。

#### 5. Third-party Vendor and Cost Governance

- 對機電、消防、網路、Server、Storage、Software及維護供應商建立RACI、Scope of Work、交付里程碑、SLA、Escalation Path及Acceptance Criteria。
- 透過技術規格與BOM比較不同方案，不只比較採購價格，也評估Capex、Opex、TCO、維護合約、備品、授權及設備生命週期。
- 建立Budget Baseline、Purchase Approval、Change Order Control、Monthly Forecast及Budget Variance Review，避免未經核准的需求擴張與成本失控。
- 將付款與設計審查、設備交付、測試、Commissioning及最終驗收里程碑連結；未達驗收標準，不進入下一階段付款或正式接手。
- 追蹤Vendor Performance、Support Response、Spare Parts Lead Time及重複故障，作為續約、議價和替換供應商的依據。

#### 6. 7×24 Operations Team

- 從零定義Role and Responsibility、Skill Matrix、On-call Rotation及Shift Handover。
- 建立Severity、Escalation、SOP／MOP／EOP、Runbook和Incident Command機制。
- 透過Training、Shadow／Reverse Shadow、Critical Procedure Certification及Incident Simulation，驗證工程師能在壓力下正確執行。
- 規劃Vendor Support、Spare Parts、Asset Inventory、Maintenance Responsibility及跨部門溝通機制。

最後，我協調IT、開發、資安、財務、供應商和營運團隊完成驗收與Handover，並將As-built Architecture、Configuration、MOP、Runbook、測試結果、風險和Vendor資料完成審查、歸檔及公告。後續所有變更都必須同步更新文件和Version History。

### Result

我們從零完成約20個機櫃的Payment Data Center，並通過Visa支付機房稽核。交付範圍不只包括機房、Network與System Environment，也包含CI/CD、自動部署、Monitoring and Observability、營運數據中台、第三方供應商與成本治理，以及可執行7×24營運的團隊、流程和文件。

透過Budget Baseline、BOM／TCO比較、Change Order Control、分階段驗收及Vendor Performance Review，我能持續掌握Scope、成本、進度和交付品質，避免只完成設備採購，卻留下後續維護成本與營運風險。這裡描述的是通過支付機房相關稽核，不將它擴大表述為未經確認的其他認證。

正式營運後，環境支援300台以上伺服器及後續500個以上服務，維持99.95%以上可用性，RTO低於一小時，RPO低於15分鐘。

### Learning

我學到，資料中心專案不是設備成功開機就算完成。真正的Production Readiness必須同時包含Environment、CI/CD、Observability、數據治理、測試、文件、人員、第三方供應商、成本和日常營運機制。只有基礎設施、系統、部署、資料、供應商與7×24團隊都能穩定運作，才算真正完成從零到一的交付。

對應 Leadership Principles：

- Ownership
- Think Big
- Deliver Results
- Insist on the Highest Standards
- Dive Deep

---

## 4. 請分享一次重大服務中斷，以及你如何處理並防止再次發生

### 面試結論

我曾處理一次遊戲上線後，隨著同時在線人數增加而快速惡化的掉單P0事件。我立即啟動War Room、建立每10分鐘一次的客戶溝通節奏，並同步確認最新版本的更新範圍，協助工程師把調查集中在實際變更的Service與Dependency。在30分鐘內仍未確認Root Cause時，我向客服及客戶說明新舊版本差異；客戶確認新功能暫時不是營運必要項目後，我們共同決定以可逆的Rollback先恢復營運，並在事件發生後45分鐘內完成回滾。後續RCA確認Kafka容量擴展未有效完成，導致Producer寫入逾時並在重試後失敗。事件後，我將關鍵檢查自動化並交付第一線使用，也在8小時內完成客戶報告。

### Situation

當時我們與馬來西亞當地前三大的連鎖網咖合作，進行遊戲服務串接與正式上線。

遊戲上線初期，約5,000名使用者同時在線時，服務仍維持正常；當同時在線超過6,000人後，開始頻繁出現掉單，也就是Application呼叫Kafka Producer送出訂單訊息時發生Timeout或Error，重試後仍未成功寫入Kafka，導致部分交易沒有進入後續處理流程。當人數接近10,000人時，Producer寫入失敗的情況進一步惡化，客戶正式向我們反映服務問題。

這個事件的特徵是服務沒有完全中斷，但交易完整性隨負載增加而下降。相較於單純的網站無法連線，這類Partial Failure更難偵測，也更容易直接影響客戶營運與信任。

### Task

身為負責營運與技術協調的主管，我需要同時完成四個目標：

1. 快速確認影響範圍並恢復客戶營運。
2. 建立清楚的Incident Command及跨團隊分工。
3. 在Root Cause尚未確認前，做出可逆且風險可控的決策。
4. 找出系統性原因，建立Monitoring、Capacity和Automation改善機制。

### Action

#### 1. 啟動P0 War Room與初步排查

收到客戶反映後，我立即啟動War Room，將事件定義為P0，並指定工作流負責人處理Infrastructure、Application、Database、Kafka與Customer Communication。

我先請第一線人員依照Runbook確認：

- 客戶端至服務端的Network Connectivity與Latency。
- Server、Load Balancer及關鍵System Health。
- CDN連線、Error與Origin狀態。
- AWS官方服務狀態是否有已知異常。
- 最近是否有Application、Configuration或Architecture Change。

上述基礎項目未發現明顯異常，而且問題表現為「使用者增加後掉單率上升」，因此我判斷需要將調查重點轉向Transaction Processing Path、Application Dependency、Kafka與Database，而不是繼續只查外部網路。

#### 2. 建立客戶溝通節奏

我直接向客戶說明目前影響、已完成的檢查、正在驗證的假設及下一步，並承諾每10分鐘提供一次更新。

即使當時尚未找到Root Cause，我也持續告知客戶：

- 現在已確認和排除哪些範圍。
- 哪些團隊正在處理。
- 是否有新的服務影響。
- 下一個Decision Point及更新時間。

這使客戶不需要反覆追問，也讓技術團隊可以集中處理問題。

#### 3. 30分鐘Decision Point：先Rollback恢復營運

P0啟動約30分鐘後，Application、Database與Infrastructure團隊仍未能確認Root Cause。

在決策前，我同步檢查最新Release的Change Record、Release Notes、Application Version、Deployment Manifest及Configuration Difference，確認這次更新實際影響哪些Service、API、Kafka Dependency與Deployment Component。這協助工程師把調查範圍從整個Production Environment縮小到本次版本實際變更的元件，同時保留尚未排除的Kafka與Database路徑。

當時可考慮三個選項：

1. 維持現況繼續調查，但掉單可能持續增加。
2. 在原因不明時直接擴充或修改Production，可能擴大Blast Radius。
3. 回復到上一個已驗證的Version與Architecture，先降低客戶影響，再繼續RCA。

我也向客服／客戶窗口說明新舊版本的功能差異、已知影響、Rollback風險和預估恢復方式。客戶確認新版本提供的新功能暫時不會影響主要營運，因此在技術團隊完成Rollback可行性與風險評估後，我們共同選擇第三個方案。Rollback是當時最可逆、最能快速恢復營運，而且風險相對可控的處置。

我們在事件發生後45分鐘內完成Rollback，將Application Version及相關Deployment Architecture／Configuration恢復到上一個已驗證狀態，並持續檢查服務連線、Producer寫入結果、交易處理、錯誤狀態與客戶回報，確認營運恢復。

#### 4. 深入RCA：建立端到端交易時間線

服務恢復後，我將事件回報層級提升至CEO，並持續帶領Application、Database及Infrastructure團隊進行RCA。

我要求團隊不要各自只看單一系統，而是依照完整Dependency建立交易處理路徑：

`Client → CDN／Load Balancer → Application／API → Kafka → Consumer → Database`

我們依照同一條時間線比對：

- Client Request、Application Error及Transaction Result。
- Kafka Producer的ACK、Retry、Timeout及Error。
- Kafka Broker Health、Request Queue、CPU、Memory、Network及Disk I/O。
- Partition Distribution、Replication、ISR與Under-replicated Partition狀態。
- Consumer Group Status、Consumer Lag及Message Processing Rate。
- Database IOPS、Latency、Connection Pool、Lock／Wait及Slow Query。
- 5,000、6,000及10,000使用者階段的負載與錯誤變化。

最後確認Root Cause位於Kafka寫入路徑：當服務負載越過原有容量門檻後，Kafka節點承載超過預期，而Scale-out流程沒有如設計般有效完成。Producer Request Latency與寫入錯誤隨負載增加，部分Producer請求發生Timeout，並在Retry後仍未取得成功ACK，因此訂單訊息沒有成功寫入Kafka，最終形成掉單。

這也讓我們確認，Kafka不能只用「節點是否啟動」判斷擴容成功；還需要驗證Broker是否Ready、Producer是否成功取得ACK、Partition與負載是否有效分布、Consumer是否跟上，以及端到端Transaction是否恢復。這些細節應依當時實際RCA紀錄回答，不使用未確認的數字。

#### 5. 建立長期改善機制

事件後，我推動以下改善：

- 將5,000、6,000與10,000使用者階段的行為納入Capacity Baseline和Load Test Scenario。
- 為Kafka建立Capacity Threshold、Consumer Lag、Producer Error／Retry、Broker Health、Partition及Replication相關檢查。
- 驗證Scale-out不只完成Node Provisioning，也確認Broker Ready、Workload Distribution及End-to-end Processing。
- 將Database I/O、Latency、Connection Pool與Kafka指標放在同一條Transaction Timeline分析。
- 建立Rollback Trigger、Decision Point、Stop Condition與Validation Checklist。
- 將Network、CDN、AWS Status、Application Dependency、Kafka及Database檢查做成自動化工具或標準化指令，讓第一線人員可以快速完成初步診斷。
- 更新P0 Runbook、Escalation Matrix、Customer Communication Template及Capacity Review機制。

所有Incident Timeline、Decision Log、RCA、Lessons Learned和Corrective Actions都在事件完成後整理、審查及歸檔，並向相關部門公告。後續如果Architecture、Kafka、Database、Monitoring、Threshold或Runbook有任何修改，文件必須同步更新Version History，避免使用過期資訊。

### Result

- 建立P0 War Room並以每10分鐘一次的節奏持續向客戶回報。
- 在Root Cause尚未確認時，採取可逆的Rollback決策，並在事件發生後45分鐘內將Application Version及相關Deployment Architecture／Configuration恢復到上一個已驗證狀態，優先讓客戶恢復營運。
- 找出Kafka節點容量與Scale-out流程未有效完成，造成Producer寫入逾時、重試後仍失敗的Root Cause。
- 將相關檢查標準化及自動化，使第一線人員後續能更快確認Network、CDN、AWS、Application、Kafka及Database等關鍵環節。
- 在8小時內完成並提交客戶Incident Report，包含Timeline、影響、處置、Root Cause與Corrective Actions。
- 客戶對我們的恢復速度、透明溝通和後續改善給予高度肯定。

### Learning

我從這次事件學到三件事。

第一，Network、Server、CDN及AWS Status都正常，不代表端到端Transaction一定正常。對掉單問題，必須沿著完整交易鏈路檢查Kafka、Consumer及Database，而不是只看Infrastructure Dashboard。

第二，在P0 Incident中，不應等到Root Cause完全確認才採取行動。當客戶影響持續擴大時，應設定Decision Point，在可逆、Blast Radius可控的前提下先Rollback，恢復服務後再深入RCA。

第三，Scale-out完成不能只代表新增資源或Node啟動，還必須驗證工作負載是否真正轉移、Partition與Consumer是否正常，以及端到端交易是否恢復。

### 面試官可能追問

#### Q1：為什麼將事件定義為P0？

因為問題直接影響客戶交易，而且影響會隨同時在線人數增加而快速擴大。即使服務沒有完全中斷，Transaction Integrity已經受到影響，需要跨Application、Database、Kafka、Infrastructure及Customer Management團隊立即處理。

#### Q2：為什麼不直接Scale out，而是選擇Rollback？

在30分鐘Decision Point時，Root Cause尚未確認。直接修改Production可能擴大Blast Radius；上一個Version與Architecture則是已驗證狀態，Rollback更可逆，也更適合先降低客戶影響。

#### Q3：如何確認Rollback成功？

我會同時確認Service Health、Transaction Result、Application Error、Kafka Processing、Database狀態及客戶端實際回報。技術恢復不代表事件結束，必須確認端到端交易重新正常運作。

#### Q4：Kafka應該檢查哪些項目？

我會檢查Producer Error／Retry／Timeout、Broker Health、Request Queue、CPU、Memory、Network、Disk I/O、Partition Distribution、ISR、Under-replicated Partition、Consumer Lag和Message Processing Rate，再與Database I/O及Application Error建立同一條時間線。

#### Q5：你如何避免同樣事件再次發生？

我會透過Capacity Baseline、Load Testing、Scale-out Validation、Transaction-level Monitoring、自動化Health Check、Rollback Trigger和定期情境演練持續驗證。每項改善都必須指定Owner、期限及驗證方式，文件也必須同步更新。

對應Leadership Principles：

- Customer Obsession
- Ownership
- Bias for Action
- Dive Deep
- Earn Trust
- Insist on the Highest Standards
- Deliver Results

---

## 5. 你如何找出根本原因，並使用數據解決問題？

### 面試結論

我不會看到Dashboard（監控儀表板）上的數字就直接推論Root Cause（根本原因）。在監控建置階段，我會先建立Observability Standard（可觀測性標準），統一定義時間基準、指標名稱、資料來源、單位、標籤、採集頻率、Aggregation（資料彙總方式）和資料保留規則。

Incident（事件）發生時，我不是重新統一時間格式，而是驗證各資料來源是否仍符合既有標準，以及Data Pipeline（資料處理鏈路）是否存在延遲、遺失或異常。確認數據具備完整性、一致性與足夠解析度後，我才會建立Incident Timeline（事件時間線）、驗證假設並找出根本原因。

### Situation

在AXIOM，我負責五個站點的Infrastructure（基礎架構）和Operations（營運）。當時MTTD（Mean Time to Detect，平均偵測時間）約15分鐘、MTTR（Mean Time to Repair，平均修復時間）約30分鐘，事件偵測和處理方式不夠一致。

我發現問題不只是告警速度。雖然Metrics（指標數據）、Logs（日誌）和Alerts（告警）已有基本標準，但不同工具的資料用途、採集頻率和Aggregation Window（彙總時間區間）不同，仍可能造成表面上不一致的結果。如果沒有先驗證數據完整性與實際定義，工程師可能根據被平均值稀釋的Peak（尖峰）、延遲寫入的Log或不完整的Sample（樣本）做出錯誤判斷。

### Task

我要找出偵測和恢復時間偏長的原因，並建立一套可量測、可重複的RCA（Root Cause Analysis，根本原因分析）方法，而不是只增加人力或依靠個人經驗猜測。

### Action

我整合Prometheus、Grafana、ELK和PagerDuty，把Metrics（指標數據）、Logs（日誌）、Alerts（告警）和Incident Notifications（事件通知）連結起來。

#### 1. 平時建立標準，事件中驗證數據

在平時建置和治理監控系統時，我先要求團隊建立Observability Standard（可觀測性標準），包括：

- Time Standard（時間標準）：使用統一時區及NTP（Network Time Protocol，網路時間協定）同步。
- Metric Definition（指標定義）：明確記錄名稱、來源、單位、Dimension（維度）、Owner（負責人）及適用情境。
- Collection Standard（採集標準）：定義Sampling Frequency（採集頻率）、Aggregation Window（彙總時間區間）和Retention（資料保留期間）。
- Log Standard（日誌標準）：定義欄位、Severity（嚴重程度）、Service Name（服務名稱）、Transaction ID（交易識別碼）和錯誤分類。
- Data Pipeline Health（資料處理鏈路健康狀態）：監控Agent、Exporter、Collector、Log Pipeline和Alert Engine本身。

對每一項Critical Service（關鍵服務）與Infrastructure Component（基礎架構元件），我也會建立Failure Mode Matrix（故障模式矩陣），定義：

- Service／Asset（服務／資產）。
- Failure Mode（故障模式）。
- Primary Signal（主要判斷訊號）與Supporting Evidence（佐證資料）。
- Baseline（正常基準線）。
- Degradation Criteria（效能下降條件）與Failure Criteria（故障條件）。
- Persistence（持續時間或連續發生次數）。
- Blast Radius（影響範圍）與Severity（事件嚴重程度）。
- Response Action（應變措施）、Escalation（升級路徑）與Owner（負責人）。

這樣工程師看到告警時，不只知道數值異常，也知道它代表什麼風險、需要哪些證據、影響哪些服務，以及下一步應採取什麼行動。

Incident發生時，我不會重新制定這些標準，而是確認各資料來源是否依照標準正常運作：

- Data Source（資料來源）：數據是否來自預期的OS、Hardware Sensor、Network Device、Application、Database或外部服務。
- Metric Type（指標類型）：Gauge（即時狀態值）、Counter（累積計數值）、Rate（變化率）、Histogram（分布統計）或Event（事件）是否被正確解讀。
- Timestamp（時間戳記）：資料是否仍使用標準時區，NTP同步是否正常，以及是否存在Clock Skew（系統時間偏差）。
- Sampling Frequency（採集頻率）：Sensor、Agent、Exporter和Collector是否按照設定頻率產生及採集數據。
- Aggregation（資料彙總方式）：Dashboard顯示的是Raw Value（原始值）、Average（平均值）、Maximum（最大值）、Minimum（最小值）、Sum（總和）還是P95／P99（第95／99百分位數）。
- Data Completeness（資料完整性）：是否存在Missing Sample（樣本遺失）、Gap（資料空窗）、Duplicate（重複資料）、Delay（延遲）或Out-of-order Data（資料順序錯亂）。
- Unit與Dimension（單位與維度）：百分比、Bytes、Bits、Milliseconds、Seconds及Instance／Site標籤是否一致。
- Collection Health（採集鏈路健康狀態）：Agent、Exporter、Log Pipeline及Alert Engine本身是否正常。

我也會將Dashboard結果與其他獨立來源進行Cross-validation（交叉驗證），例如：

- Raw Metrics（原始指標數據）與設備原始Counter（累積計數器）。
- OS（作業系統）、Application（應用程式）、Database（資料庫）及Hardware Logs（硬體日誌）。
- Network Interface（網路介面）、Firewall（防火牆）、Load Balancer（負載平衡器）及CDN（內容傳遞網路）紀錄。
- Cloud Service Status（雲端服務狀態）與Change Records（變更紀錄）。
- Synthetic Check（模擬交易檢查）、Transaction Result（交易結果）及客戶回報。

如果兩個來源不一致，我不會挑選比較符合原本假設的數據，而是先找出差異原因，並明確標示目前已知、未知和仍待驗證的部分。

#### 2. 依既有標準建立事件時間線

確認資料可信後，我要求團隊依照既有時間與資料標準建立Incident Timeline（事件時間線），對照：

- 系統與應用程式Metrics。
- Network Traffic和連線狀態。
- Logs和Error Messages。
- 最近的Change Records。
- Alert Routing和Escalation紀錄。
- 人員回應、判斷和交接時間。

我會先找出第一個可以被證實的異常訊號，再檢查異常前後是否有Change（變更）、Capacity（容量）轉折、Error（錯誤）增加或Dependency（相依服務）狀態改變，將「現象」和「可能原因」分開記錄。最早出現的異常訊號不一定是Root Cause，它只是建立調查假設的起點。

#### 3. 用假設驗證，而不是只看Correlation（相關性）

我會根據時間線建立數個可能假設，並依Evidence（證據）逐一驗證：

- 問題是否只發生在特定Site、Instance、Rack、Network Path或Service Version。
- 正常與異常對象之間有什麼差異。
- 異常是否和最近Change或負載變化具有一致時間關係。
- Rollback、隔離或修正後，症狀是否按照預期消失。
- 所提出的Root Cause能否完整解釋所有主要現象，而不只是其中一項Metric。

只有當Evidence（證據）、Failure Mechanism（故障機制）和修正後的驗證結果一致時，我才會將它定義為Root Cause（根本原因）。若只能證明相關性，我會標示為Contributing Factor（促成因素）或Working Hypothesis（待驗證假設）。

#### 4. 將結果轉成可重複機制

我也重新定義SLO（Service Level Objective，服務水準目標）、Error Budget（錯誤預算）、Severity（事件嚴重程度）、Runbook（操作手冊）和Escalation Threshold（升級門檻），減少無效告警，讓工程師優先處理真正可採取行動的告警。

每次RCA完成後，我會保存Data Source（資料來源）、Query（查詢條件）、Time Range（時間範圍）、Dashboard Snapshot（儀表板快照）、Incident Timeline（事件時間線）、Decision Log（決策紀錄）和Evidence（證據），並將Corrective Actions（改善措施）指定Owner（負責人）、期限和驗證方式。文件完成審查與歸檔後向相關部門公告；後續若Metric（指標）、Threshold（門檻值）、Query或Architecture（系統架構）改變，相關文件必須同步更新。

### Result

MTTD（平均偵測時間）從15分鐘降低到2分鐘，改善約86.7%；MTTR（平均修復時間）從30分鐘降低到8分鐘，改善約73.3%。

數據口徑：範圍為AXIOM五個站點納入Incident Review的Production Incidents。MTTD從第一個可被監控系統觀察到的異常訊號起算，到產生可採取行動的告警為止；MTTR從事件正式啟動到服務恢復並完成基本驗證為止。Planned Maintenance、演練告警及重複Ticket不納入。實際統計期間與Incident件數必須以Ticket、PagerDuty及RCA紀錄確認後填入，面試時不使用推估件數。

### Learning

我學到，Data Center和Infrastructure Monitoring的問題通常不是沒有資料，而是資料太多、缺乏關聯。

我也學到，錯誤或未經驗證的數據可能讓團隊更快走向錯誤方向。因此Data Validation不是RCA之前的行政工作，而是RCA本身的第一個技術步驟。

有效的Monitoring必須形成：

`Data Validation → Timeline → Correlation → Hypothesis → Verification → Root Cause → Corrective Action`

### 面試官可能追問

#### Q1：你如何證明數據是正確的？

我會確認Data Source（資料來源）、Metric Definition（指標定義）、Unit（單位）、Timestamp（時間戳記）、Sampling Frequency（採集頻率）和Aggregation（資料彙總方式），再用Raw Counter（原始計數器）、Logs（日誌）、Equipment Event（設備事件）、Synthetic Check（模擬交易檢查）或另一個獨立系統交叉驗證。單一Dashboard不能自行證明數據正確。

#### Q2：如果Metrics和Logs顯示不同結果呢？

Metrics（指標數據）和Logs（日誌）在監控建置前就應該有統一的時間、命名、欄位和資料保留標準。因此，事件發生時我不會重新統一格式，而是先確認兩者比較的是不是相同的Time Range（時間範圍）、Service Scope（服務範圍）、Transaction Status（交易狀態）和Metric Definition（指標定義）。

我也會檢查Sampling Interval（採集間隔）、Aggregation Window（彙總時間區間）、Collection Delay（採集延遲）、Missing Data（資料缺失）及Monitoring Pipeline Health（監控資料鏈路健康狀態）。Metrics通常反映一段時間內的數值變化，Logs通常記錄特定事件，兩者可能描述同一事件的不同階段，不應直接判定其中一方錯誤。

如果仍然不一致，我會沿著端到端交易路徑逐段比對數量：

`Client Request → Application → Kafka Producer → Kafka Consumer → Database`

例如，Application收到的請求數高於Kafka Producer成功送出的訊息數，我會檢查Application到Kafka之間的Timeout（逾時）、Retry（重試）、ACK（確認回應）和送出失敗。如果Kafka收到的訊息數高於Database完成的訂單數，我會繼續檢查Consumer Lag（消費延遲）、處理失敗和Database Write Error（資料庫寫入錯誤）。第一個出現數量差異的處理階段，會成為後續RCA的重要調查方向，但仍需要Failure Mechanism（故障機制）和修復結果加以驗證。

#### Q3：如何避免把Correlation誤認為Root Cause？

我會要求Root Cause（根本原因）必須能解釋主要症狀、時間順序和Failure Mechanism（故障機制），並透過Rollback（回滾）、隔離、重現或修正後驗證確認。只有時間相近但缺乏機制證據的項目，只能列為Contributing Factor（促成因素）或Hypothesis（假設）。

#### Q4：如果歷史數據不完整怎麼辦？

我不會自行補齊或推測缺少的數據。我會清楚標示Evidence Gap（證據缺口），使用其他Logs（日誌）、Events（事件）、Configuration（設定資料）、Change Records（變更紀錄）和現場回報交叉確認，並把缺少的Telemetry（遙測資料）列為Corrective Action（改善措施），確保下次能取得必要證據。

#### Q5：內網平常在5ms內，升到10ms算不算異常？

10ms可能是Anomaly（異常偏移），但不一定是Incident（事故），也不一定代表SLO Breach（違反服務水準目標）。我會先確認比較的是相同Site、VLAN／VRF、Source-Destination Probe Pair（來源與目的探測點）、Route（路由）、Traffic Load（流量負載）和Time Window（時間區間）。

接著比較P50、P95、P99、Packet Loss（封包遺失）、Jitter（延遲抖動）、TCP Retransmission（TCP重傳）、Interface Error（介面錯誤）和Application Response Time（應用程式回應時間）。如果只有單一Sample升到10ms，可能只是Transient Spike（短暫尖峰）；如果P95持續偏離正常Baseline，或同時出現Packet Loss、Route Change及服務影響，就應提高Severity並啟動調查。

所以Baseline只告訴我「平常表現」，SLO則定義「服務可以接受的最低標準」。兩者不能混為一談。

#### Q6：內部SLO怎麼定義？

我會先定義使用者真正需要的Service Outcome（服務結果），再建立SLI（Service Level Indicator，服務水準指標）、SLO（Service Level Objective，服務水準目標）及OLA（Operational Level Agreement，內部營運協議）。

SLI可以用以下方式計算：

`Good Events（符合標準的事件）÷ Valid Events（所有有效事件）`

SLO文件必須寫明Service Owner、使用者、SLI定義、資料來源、Good／Bad Event、Measurement Window（統計期間）、目標、排除條件、Error Budget（錯誤預算）、Escalation及Review Date。SLO數字必須由Business、Service Owner和Operations共同確認，不能只根據歷史平均值自行決定。

MTTD、MTTR、Escalation Time等比較適合作為Operational KPI（營運指標）；服務Availability、成功率及Latency達標比例才是使用者導向的SLO。

對應 Leadership Principles：

- Dive Deep
- Are Right, A Lot
- Insist on the Highest Standards
- Learn and Be Curious
- Deliver Results

---

## 6. 請分享一個改善效率的自動化專案

### Situation

在Unition，Google Cloud（GCP）是主要營運環境，AWS是Disaster Recovery（災難復原，DR）環境。原本的DR演練只涵蓋GCP整體異常後切換至AWS，End-to-end Recovery Process約需13小時。

我檢視完整User Journey後發現，使用者在到達GCP之前，還依賴Authoritative DNS及CDN。如果Cloudflare DNS或單一CDN先發生異常，即使GCP本身完全正常，使用者仍可能無法進入服務；只演練Cloud DR並不能涵蓋這些Failure Domain。

因此我主動提出將BCP從單一Cloud DR擴充成三層：

1. DNS Provider Failure：Cloudflare DNS異常時切換至Amazon Route 53。
2. CDN Failure：將Index及Content拆開，依受影響範圍切換備援CDN。
3. Cloud Platform Failure：GCP整體異常時，將服務、資料及流量切換至AWS。

第三層原有流程另外存在三段Critical Path（關鍵路徑）高度依賴人工：

- Database Restore完成後，需要人工尋找Recovery Checkpoint並確認最新交易資料。
- DNS設定、複核及切換步驟過長，而且操作分散在不同工具。
- Application與業務驗證沒有一致的Checkpoint，開發人員需要逐項人工確認，等待時間過長。

### Task

我的任務不是只把GCP到AWS的操作寫成Script，而是重新定義完整BCP：先辨識故障發生在哪一層，再採取足以恢復服務、但Blast Radius最小的切換方式。同時，在不犧牲Data Integrity、Security、Approval、Audit Trail及Rollback能力的前提下，縮短第三層完整DR的Recovery Time。

### Options／Decision

我們評估過維持單一Cloud DR、任何異常都直接切換整個平台，以及依Failure Domain分層恢復三個方向。

我選擇分層恢復。因為DNS或CDN故障時直接啟動完整Cloud DR，不但恢復時間較長，也會加入Database及Application切換風險。我將三層都設計為受控Workflow：自動完成重複工作，但在Provider Cutover、Recovery Point選擇及Go-live前保留Health Check、Approval、Stop Condition和Rollback能力。

### Action

我將BCP拆成以下三層。

#### 1. DNS Provider Failure：Cloudflare切換至Amazon Route 53

我預先在Route 53建立Hosted Zone，透過版本化設定持續同步並比對Cloudflare與Route 53的關鍵DNS Records，避免真正故障時才臨時建立Zone。

DNS故障判斷不依賴Cloudflare本身，而是使用Provider-independent Health Check（供應商外部健康檢查），從多個地區確認：

- Authoritative Name Server是否回應。
- SOA／NS及關鍵A、AAAA、CNAME Records是否可解析。
- 是否出現Timeout、SERVFAIL或大範圍解析失敗。
- Application Origin本身是否仍健康，避免把Origin故障誤判為DNS故障。

當多個獨立檢測點連續達到Trigger Condition後，Workflow會顯示影響範圍及建議動作，經授權後透過Domain Registrar API，將Authoritative Name Server由Cloudflare切換至Route 53。流程會保存變更前後的NS Set、Approver、Timestamp及Rollback設定，並持續檢查Authoritative DNS及多地Public Resolver的實際解析結果。

Name Server切換不是保證瞬間生效，因為仍受Parent Delegation TTL與Resolver Cache影響，所以Success Criteria不能只看Registrar API回傳成功，而是要確認外部Resolver逐步取得Route 53答案，且端到端服務可用。若網域啟用DNSSEC，還必須預先設計DS Record及Key Rollover程序，否則切換後可能因驗證失敗產生SERVFAIL。

#### 2. CDN Failure：Index與Content獨立切換

我將Index與Content拆成不同Hostname、Health Check及Failover Policy：

- **Index：** 檢查HTML入口、版本、導流設定、Status Code及Response Time，確保使用者能正確進入服務。
- **Content：** 檢查JavaScript、CSS、Image及其他Static Assets的Availability、Latency、Object Version與必要Checksum。

系統透過Active Probe及實際使用者指標判斷CDN健康狀態。當單一CDN異常時，可以只將受影響的Index或Content Hostname切換至備援CDN，而不必移動全部流量。切換前會確認Backup CDN、Origin、TLS Certificate及Cache內容可用；切換後則驗證多地HTTP Response、Asset完整性及Error Rate。

這種設計把故障範圍限制在實際異常的元件。例如Content CDN異常時，只切換Static Content，不影響仍正常的Index及Application Traffic。

#### 3. Cloud Platform Failure：GCP切換至AWS

第三層才是原有的完整Cloud DR。我將這一層再拆成可以平行執行、但在關鍵節點會合的Database、DNS、Application及Business Validation工作流。

##### 3.1 Database Recovery與資料完整性驗證

我先和Database、開發及營運單位共同定義Recovery Checkpoint（資料恢復確認點），包括：

- 最後成功Backup或Replication Checkpoint的時間。
- AWS Restore使用的Recovery Point與完成狀態。
- 最新一筆已提交交易的Business Timestamp。
- 固定時間區間內的Transaction Count。
- 關鍵金額、狀態或其他Control Total。
- Source與DR環境之間允許的RPO（Recovery Point Objective，可接受資料損失時間）差異。

原本這些項目由人員分別登入系統查詢。我將Restore與Validation串成Workflow：系統先確認Backup／Replication狀態及完整性，再選擇最近一次符合條件的Recovery Point；AWS端完成Restore後，自動執行版本化的SQL Validation Scripts，直接在Dashboard顯示資料截止時間、交易筆數、Control Total及Reconciliation Difference（對帳差異）。

如果GCP來源仍可讀，Workflow會直接比對兩端結果；如果來源已不可讀，就以最後成功Checkpoint、備份Metadata及事前保存在獨立位置的Control Total作為驗證依據。這可避免把「Restore Job成功」錯誤地視為「資料已完整且足夠新」。

##### 3.2 DNS Cutover自動化

原本DNS切換需要人工修改多筆Record、重複複核並在不同介面間操作。我將DNS Provider API整合至單一受控介面，預先版本化Primary與DR的Record Set、AWS Endpoint及Rollback設定。

Workflow包含：

- Pre-check：確認AWS Target Health、Certificate、Load Balancer、Record Value及必要的TTL策略。
- Approval Gate：由授權人員核准正式Cutover。
- API Update：以Idempotent方式更新已核准的DNS Records。
- Propagation Validation：檢查Authoritative DNS及多個Public Resolver的解析結果。
- Service Validation：確認流量確實進入AWS，並驗證TLS、HTTP／API及關鍵服務。
- Rollback：若超過Timeout、Error Rate或資料驗證門檻，恢復上一個Record Set。

因此，工程師可在單一介面完成切換，但仍保留RBAC、Approval、Audit Log及Rollback。API回傳成功只代表Record Update完成，不代表客戶流量與服務已恢復，所以Post-check必須驗證實際解析及端到端服務。

##### 3.3 Application與Database Change驗證

開發驗證時間過長的主因，是各團隊對「可以Go-live」沒有一致定義。我與開發團隊共同建立Validation Matrix，將驗證項目分成：

- Database Schema Version及Migration Status。
- Application Configuration與必要Dependency。
- API Health及關鍵Endpoint。
- Database Read／Write。
- Queue、Cache及Background Job狀態。
- Authentication及授權流程。
- Critical Transaction Flow與營運對帳結果。

我將Database Schema Changes、Stored Procedure及必要Migration Scripts納入Git，使用Flyway管理版本、執行順序及Checksum，讓AWS DR Database可以確認與Production相容的Schema Version。接著由CI/CD執行Smoke Test、API Test及SQL Reconciliation，將結果集中顯示，開發與營運只需要檢查例外並完成Go／No-go Approval。

Flyway負責的是Database Schema與Migration版本一致性，不能單獨證明最新交易資料已恢復；Data Freshness與Completeness仍由Recovery Point、Transaction Timestamp、Record Count及業務對帳規則確認。

##### 3.4 流程控制與演練

整個Workflow加入RBAC、Least Privilege、Approval Gate、Pre-check、Post-check、Timeout、Retry、Stop Condition及Rollback，並保留每次執行的Approver、Recovery Point、DNS Change、Schema Version、Validation Result與時間紀錄。

我也將原本依序等待的工作重新安排：AWS Infrastructure Readiness、Database Restore前置作業、DNS Pre-check及Application Test Preparation可以平行進行；只有Data Validation、正式DNS Cutover及Go-live Approval需要在指定Hold Point會合。最後透過定期DR Drill驗證Runbook與自動化結果，而不是等真正事故才使用。

### Result

我主動把原本只涵蓋Cloud Failure的DR，擴充成DNS Provider、CDN及Cloud Platform三層BCP，讓團隊能依故障層級執行最小必要切換。

第三層完整DR從啟動、AWS環境確認、Database恢復、DNS切換，到Application及營運共同完成驗證的End-to-end Recovery Time，由13小時縮短到4小時。

這套設計也曾在一次Cloudflare DNS故障時實際發揮作用。因為Route 53 Zone、Registrar API Workflow及外部驗證機制已經準備完成，我們不需要等待Cloudflare全面恢復，也不必啟動風險較高的完整Cloud DR，就能切換DNS Provider，避免故障演變成長時間服務中斷。

這裡的4小時是DR Recovery Execution Time：從Incident Commander正式啟動DR開始，到AWS端Infrastructure、Database、DNS及Application完成技術驗證，並由營運單位完成Business Validation為止。除非公司已正式把它定義為RTO，否則面試時不直接將4小時稱為RTO。實際演練次數及比較期間應以DR Drill Record、Workflow Log、Change Ticket及Validation Report確認。

### Learning

我學到，BCP不能只防範Cloud Platform故障，而要沿著完整User Journey識別DNS、CDN、Cloud及Data等Failure Domain。恢復策略也不是規模越大越好，而是要選擇能控制Blast Radius、又足以恢復服務的最小動作。

另外，Automation不代表取消治理。每一層仍需要明確的Trigger Condition、Success Criteria、Approval、Timeout、Stop Condition、Post-check及Rollback，並透過演練確認真正可執行。

對應 Leadership Principles：

- Invent and Simplify
- Ownership
- Think Big
- Bias for Action
- Deliver Results

---

## 7. 你如何管理7×24資料中心營運團隊？

我會從People、Process、Technology和Metrics四個方面管理。

### People

我會建立Skill Matrix，列出每位工程師在Power、UPS、Cooling、Network、Monitoring、Security和Incident Management的能力。

如果只有一個人了解UPS、網路或監控系統，這個人本身就是Knowledge Single Point of Failure。

因此我會安排：

- Cross-training。
- Shadow和Reverse Shadow。
- Critical Procedure Certification。
- 公平的On-call Rotation。
- One-on-one和Development Plan。
- Succession Planning。

### Process

我會建立Severity（事件嚴重程度）、Escalation（升級機制）、Shift Handover（班別交接）、SOP（Standard Operating Procedure，標準作業程序）、MOP（Method of Procedure，具體操作程序）、EOP（Emergency Operating Procedure，緊急操作程序）、Runbook（操作手冊）和Stop Work Authority（停止作業權限）。

我會明確區分：SOP用於日常重複作業，MOP用於經過規劃的變更或維護，EOP用於電力、網路、冷卻或關鍵服務異常等緊急情境。每一份Critical Procedure（關鍵程序）必須包含Trigger Condition（啟動條件）、Pre-check（事前檢查）、角色分工、操作步驟、Hold Point（暫停確認點）、Stop Condition（停止條件）、Rollback（回復方式）和Post-check（事後驗證）。

文件完成不代表程序有效。我會透過Peer Review（同儕審查）、Tabletop Exercise（桌上推演）、受控演練、Shadow／Reverse Shadow及Critical Procedure Certification驗證工程師是否能正確執行。

重大事件期間，會分開Incident Command、Technical Recovery、Validation和Stakeholder Communication。

### Technology

我會整合Infrastructure、Network、Environmental和Service Monitoring，避免只收到大量無法採取行動的Alarm。

### Metrics

我會追蹤：

- Availability
- MTTD、MTTA、MTTR
- Change Failure Rate
- Incident Recurrence Rate
- Capacity Utilization
- SLA Attainment
- Backlog Aging
- Team Workload

### 每月異常情境模擬

除了日常排班、On-call、Skill Matrix和Runbook，我每月會安排一次受控的異常情境模擬。

我不會事先告訴團隊完整答案，而是觀察他們如何偵測、判斷、升級、分工、溝通和恢復服務。演練可能涵蓋Network Ring、Server、Storage、Monitoring、Critical Service、Failover、Vendor Support或主要負責人不在場等情境。

演練的目的不是責怪工程師，而是確認人員、程序和系統能否在壓力下正常運作。因此我會採用Blameless Review，但每一項改善仍然需要明確的Accountability。

我會將發現的缺口轉成：

- Training與Skill Matrix改善。
- Runbook、MOP、SOP或EOP更新。
- Monitoring與Escalation Threshold改善。
- Cross-training與Succession Planning。
- Architecture、Redundancy或Vendor Support改善。

所有問題都會指定Owner和完成時間，修正後再透過下一次演練驗證。

演練、Shift Handover、Critical Procedure及Incident相關文件都必須有明確Owner和版本。每次完成後進行歸檔與部門溝通；若流程、聯絡人、設備或架構改變，文件更新必須和Change一起完成，並視需要重新Training或認證。

以我在Mlytics管理15人SOC和Cloud CDN Operations Team的經驗為例，我將文件覆蓋率從20%提升到90%，新人準備時間從六個月縮短到一個月，內部晉升超過60%，也培養兩位成員在六個月內取得AWS認證。

數據口徑：文件覆蓋率以Critical SOP／Knowledge Base清單中，已完成、通過Review且具備Owner與Version的文件數，除以應建立的文件總數計算；新人準備時間從到職日起算，到通過Critical Procedure、Shadow／Reverse Shadow及獨立值班認證為止；內部晉升率只計算正式晉升，不把一般Training Completion列為晉升。統計期間、符合晉升資格人數及實際晉升人數必須以HR與Training Records確認；AWS認證則為兩位成員在六個月內通過。

對應 Leadership Principles：

- Hire and Develop the Best
- Strive to be Earth’s Best Employer
- Ownership
- Insist on the Highest Standards
- Earn Trust

---

## 8. 請分享一次你培養團隊成員的經驗

### Situation

在Mlytics，我管理15人的SOC和Cloud CDN Operations Team。當時文件覆蓋率只有20%，新人需要六個月才能獨立工作。

### Task

我要縮短新人準備時間、消除Knowledge SPOF，並培養未來的Team Leads和Technical Specialists。

### Action

我先建立Skill Matrix，確認每位成員的技能、經驗和能力缺口。

接著重新設計：

- Role Levels和職涯路徑。
- Training Plan。
- SOP和Knowledge Base。
- Shadow與Reverse Shadow。
- On-call實作和Incident Simulation。
- One-on-one及定期Feedback。
- Succession Planning。

我也讓成員負責AWS、Monitoring和Automation等改善專案，使學習和實際責任連結。

### Result

文件覆蓋率從20%提升到90%，新人準備時間從六個月縮短到一個月，內部晉升率超過60%，兩位成員在六個月內取得AWS認證。

數據口徑：文件覆蓋率以Critical SOP／Knowledge Base清單中，已完成、通過Review且有Owner與Version的文件數除以應建立的文件總數計算；新人準備時間從到職日起算，到通過Critical Procedure、Shadow／Reverse Shadow及獨立值班認證為止；內部晉升率只計算正式晉升，不把一般Training Completion列為晉升。統計期間、符合晉升資格人數及實際晉升人數需以HR與Training Records確認；AWS認證則為兩位成員在六個月內通過。

### Learning

我學到，最有效的Training不是只安排課程，而是讓成員逐步承擔真實責任，再透過觀察、回饋和驗證確認他們能獨立完成工作。

對應 Leadership Principles：

- Hire and Develop the Best
- Strive to be Earth’s Best Employer
- Earn Trust
- Ownership

---

## 9. 請分享一次你在資訊不完整時做出決策的經驗

### Situation

我曾處理一次遊戲正式上線後，隨同時在線人數增加而快速惡化的P0掉單事件。約5,000人在線時服務正常，超過6,000人後開始掉單，接近10,000人時問題明顯惡化。

我立即啟動War Room，安排Application、Database、Kafka、Infrastructure及Customer Communication工作流，並每10分鐘向客戶更新。事件啟動30分鐘後，各團隊仍未確認Root Cause，但交易影響正在持續擴大。

### Task

我必須在Root Cause尚未確認的情況下，決定要繼續調查、直接修改Production，或先恢復上一個已驗證狀態。我的目標是快速降低客戶影響，同時避免一個未驗證的動作擴大Blast Radius。

### Options／Decision

我評估三個選項：

1. **維持現況繼續調查：** 不增加新的變更風險，但掉單可能持續擴大。
2. **直接Scale out或修改Production Architecture：** 可能快速改善容量，但在原因未明時可能改錯位置並擴大影響。
3. **Rollback至上一個已驗證版本：** 暫時放棄新功能，但最可逆，也能快速回到已知穩定狀態。

在決策前，我檢查Change Record、Release Notes、Application Version、Deployment Manifest及Configuration Difference，確認最新版本實際變更的Service、API及Dependency。我也向客戶說明新舊版本差異、Rollback風險及預估恢復方式。客戶確認新功能暫時不是主要營運必要項目後，我選擇第三個方案。

### Action

我要求團隊先確認Rollback Package、Database Compatibility、Configuration及Dependency，再依MOP恢復上一個已驗證的Application Version與Deployment Configuration。整個過程設定Stop Condition及Rollback Validation，不把Deployment成功直接視為服務恢復。

完成後，我們同步驗證：

- Application及API Health。
- Kafka Producer寫入與ACK結果。
- Transaction是否進入後續流程。
- Database狀態及資料一致性。
- Error Rate、Latency及客戶端實際回報。

### Result

我們在事件發生後45分鐘內完成Rollback並恢復客戶營運。服務穩定後，我帶領團隊繼續進行RCA，最後確認Kafka超過原有容量門檻，而Scale-out流程沒有有效完成，造成Producer Timeout，Retry後仍未取得ACK，最終形成掉單。

後續我建立Kafka Capacity Baseline、Producer Error、Consumer Lag、Broker Health及Scale-out End-to-end Validation，避免只看到Node啟動就判定擴容成功。

### Learning

我學到，資訊不完整時不能用猜測取代Evidence，也不能一定要等Root Cause完全確認才行動。應該比較各選項的Customer Impact、Reversibility、Blast Radius及Recovery Time，選擇能最快降低風險的方案，再於服務恢復後完成深入RCA。

對應 Leadership Principles：

- Bias for Action
- Are Right, A Lot
- Customer Obsession
- Ownership

---

## 10. 當多項工作同時緊急，但資源有限時，你如何排序？

### Situation

在泰偉電子建置約20個機櫃的Payment Data Center時，Facility施工、設備安裝、Network與System建置、Commissioning、Visa支付機房稽核準備、Vendor交付及既有Production Operation同時進行。每項工作都有Deadline，但工程師、Maintenance Window及第三方資源有限。

### Task

身為IT最高主管，我需要確保有限資源優先投入對Safety、Payment Service、Compliance及Go-live影響最大的工作，同時不能讓既有Production Operation失去支援。

### Action

我建立統一的Priority Matrix，不依FIFO或誰催得最急排序：

1. **Safety：** Power、UPS、Cooling、Fire Protection、高風險施工及人員安全問題。
2. **Production Impact：** 已影響Payment Service、客戶或可能造成重大中斷的工作。
3. **Compliance Blocker：** 可能阻擋Visa支付機房稽核、Access Control、Logging、Backup或Change Control的缺口。
4. **Critical Path：** 具有Long Lead Time、會阻塞Commissioning或影響多個後續工作包的項目。
5. **Recoverability：** 沒有Redundancy、Rollback、Critical Spare或替代供應商的工作優先於可安全延後的項目。
6. **Routine Work：** 一般Provisioning、低風險改善及可延後的需求。

我將工作拆成Facility、Network／System、Security／Compliance及Operations Readiness等Workstream，每項工作指定Owner、Dependency、完成條件及Escalation Path。每天檢查Critical Path與Risk Register，並向Stakeholders說明哪些工作被延後及其影響。

為避免專案吸收所有人力，我保留部分Team Capacity處理Production Incident；接近Commissioning及Go-live時，非必要Production Change必須延後。Vendor工作則以RACI、里程碑、驗收結果及Escalation管理，對Long Lead Item提早準備替代方案。

### Result

我們完成約20個機櫃的Payment Data Center，通過Visa支付機房相關稽核，並完成後續7×24營運交接。正式營運後，環境支援300台以上Server及後續500個以上Service。

### Learning

我學到，資源有限時的目標不是完成最多工作，而是先降低最高且不可逆的風險。Safety、Production Impact、Compliance Blocker及Critical Path需要優先處理；一般工作即使很緊急，也不能排在會阻止整體交付或造成重大中斷的問題之前。

對應 Leadership Principles：

- Customer Obsession
- Ownership
- Bias for Action
- Deliver Results

---

## 11. 請分享一次你在品質與交付速度之間做取捨的經驗

### Situation

在一次重要版本發布前，Security Scan發現受影響的URL／API存在SQL Injection風險，但該版本同時承載重要業務需求，原定發布時間不能輕易延後。

這不是單純的「要不要上線」，而是品質、安全與業務時效之間的風險決策。我不能直接把Security Gate改成Pass，也不能只因為Scan失敗就停止所有討論。

### Task

我的任務是先確認漏洞是否真實、可能影響及是否已被利用，再向業務主管完整揭露Residual Risk。若業務仍需要發布，就必須建立正式Risk Exception、Compensating Controls、監控、人力待命、Rollback Trigger及永久修復期限。

### Options／Decision

我評估三個選項：

1. **停止發布，等待程式完全修復：** 安全風險最低，但會影響重要業務時程。
2. **忽略掃描結果直接發布：** 速度最快，但沒有風險Owner、補償控制及稽核依據，因此我不接受。
3. **限時Risk Exception後受控發布：** 先驗證漏洞，加入多層補償控制及Rollback能力，再由Business Owner、Security及Technical Owner共同決策。

我選擇第三個方案，但前提是Compensating Controls能有效降低Exploitability，而且Risk Exception必須有Owner、Expiry Date、永久修復期限及重新掃描條件。

### Action

#### 1. 驗證與風險分析

我要求Security與Application團隊確認：

- 是否為True Positive。
- 受影響的URL、API及Parameter。
- 是否需要Authentication及Internet Exposure。
- Application使用的Database Account權限。
- 可能接觸的資料及Blast Radius。

我將結果、延後發布的業務影響，以及可以採取的控制措施向業務主管報告，讓決策建立在可理解的風險上，而不是只看到Scanner顯示Fail。

#### 2. Compensating Controls

在正式發布前，我們：

- 開啟WAF SQL Injection Managed Rules。
- 針對漏洞URL／API建立Virtual Patch。
- 加入Rate Limit，限制自動掃描及大量異常Request。
- 確認Application Database Account符合Least Privilege。
- 限制Database只接受必要的Application來源連線。
- 確認Backup、Recovery及DB Audit Logging可用。

WAF規則會先確認False Positive及正常交易影響，再切換至Block模式。WAF只能降低短期Exploitability，不能取代Parameterized Query等程式修復。

#### 3. Monitoring與Compromise Assessment

我要求SOC／NOC集中監控：

- WAF Block及Rule Match。
- Web Access Log與Application Error。
- Database Audit Log及異常DB Login。
- 異常大量查詢、Download及Data Access。
- Schema、Account及Privilege Change。
- Error Rate、Latency及Critical Transaction Result。

同時回查漏洞可能存在期間，確認是否已有SQL Injection Pattern、大量資料存取、異常登入或權限變更。若發現疑似利用跡象，事件會轉為Security Incident處理，而不是繼續一般Release。

#### 4. Release Support與Rollback

上線期間由我負責Change／Incident Coordination，待命人員包括：

- Application Developer與Technical Lead。
- Security／AppSec及SOC。
- WAF／CDN Engineer。
- DBA。
- DevOps／SRE。
- QA。
- NOC／Customer Service。
- Business Owner。

Rollback Trigger包括發現成功利用跡象、WAF無法有效阻擋、Database出現異常、Error Rate超過門檻或Critical Transaction Validation失敗。

#### 5. Permanent Fix

發布後，開發仍必須使用Parameterized Query、Input Validation及最小權限完成永久修復，再重新執行Code Review、SAST、DAST及Security Scan。Risk Exception到期前若未修復，必須重新Escalate，不能自動延長。

### Result

重要版本在風險透明、責任明確、具備監控及Rollback能力的條件下發布。Security Finding沒有被隱藏或改成Pass，而是透過正式Risk Acceptance持續追蹤至永久修復及重新驗證。

實際永久修復時間、WAF Block數量、Release後是否偵測到攻擊及重新掃描日期，應由Security Ticket、WAF Log、Change Record及Scan Report確認；在原始資料確認前不使用未驗證數字。

### Learning

我學到，速度與品質的取捨不是接受未知風險。管理者必須讓Residual Risk可以被解釋、核准、監控並設定到期日，同時保留停止與回復能力。Compensating Control可以爭取修復時間，但不能變成永久接受漏洞的理由。

對應 Leadership Principles：

- Insist on the Highest Standards
- Ownership
- Have Backbone; Disagree and Commit
- Deliver Results

---

## 12. 請分享一次降低成本但不降低可靠性的經驗

### Situation

在Unition，Google Cloud原本由公司依個別需求採購，有效價格約為牌價的80%。以單一公司的Cloud用量談判，議價能力、Support Coverage及Escalation條件較有限；但母公司及其他關係企業具有更大的整體Cloud需求與採購規模。

我發現，如果將適合的共通需求整合到集團層級，可以提高議價能力並減少重複採購。不過，若只追求Volume Discount，也可能增加Committed Usage浪費、Vendor Lock-in或Single Point of Failure。

### Task

我的任務是利用母公司整體規模降低TCO、改善合約與支援條件，同時保留必要的Redundancy、Security、Data Portability及Exit Capability，不能因為集中採購而降低Production Reliability。

### Options／Decision

我評估三個選項：

1. 各公司維持獨立採購，彈性較高，但議價能力及治理一致性較弱。
2. 全部集中到最低價的單一Vendor，折扣可能最大，但會增加集中風險。
3. 整合集團需求與談判，但依Service Criticality決定哪些項目可以集中、哪些仍需保留第二供應商或Migration Plan。

我選擇第三個方案，因為它可以同時利用Scale與控制Concentration Risk。

### Action

我先統一Unition與母公司相關單位的：

- 服務Scope及Technical Requirement。
- 實際使用量、Growth Forecast及Committed Usage。
- 合約到期日、計價單位及Payment Term。
- SLA、Support Level及Escalation Path。
- Security、Compliance、DR及Data Location要求。
- 既有Invoice、Discount、Service Credit及Hidden Cost。

接著用一致的TCO Model比較Vendor，不只看單價，也納入Implementation、Migration、License、Support、Maintenance、Incident及Exit Cost。對適合整合的服務，我將需求彙整至母公司層級，談判：

- Volume Tier及Committed Usage Discount。
- Price Protection及Renewal Cap。
- 7×24 Support Coverage與Escalation。
- Response／Resolution SLA及Service Credit。
- Capacity Commitment。
- Security責任及事件通報。
- Data Portability、Termination Assistance及Exit Plan。
- 付款與實際交付、驗收結果連結。

可靠性方面，我依Service Criticality決定採購策略。Critical Service不因折扣取消Backup、DR或備援；若集中到單一Vendor會形成不可接受的Failure Domain，就保留第二供應商或經過驗證的Migration Plan。

合約生效後，我每月比對Usage、Invoice、Commit Consumption、SLA Performance及Service Credit，避免取得帳面折扣後，因Over-commit或未使用資源反而提高TCO。

### Result

Unition結合母公司的整體採購規模，將Google Cloud有效價格由牌價的80%談到60%。這代表Discount由20% off list提升至40% off list；若以原合約80%的實付價格作為Baseline，相對成本降低為：

`(0.80 - 0.60) ÷ 0.80 = 25%`

在相同Service Scope、預估使用量及合約期間下，約節省50,000美元，同時改善合約與Support／Escalation條件，並保留Critical Service所需的DR、Data Portability及Exit Capability。

數據口徑：50,000美元以原80%價格下的Baseline Cost，減去新60%價格下的Contract Cost計算；兩者必須使用相同的Cloud Service Scope、Usage Forecast、Currency及Contract Period。資料來源以新舊Contract、Purchase Order、Invoice及Usage Report為準。除非確認這是完整12個月的Recurring Saving，面試時使用「合約期間節省約50,000美元」，不直接稱為年度節省。

### Learning

我學到，Frugality不是取得最低單價，而是利用規模、標準化及合約治理降低TCO，同時控制Vendor Lock-in與Concentration Risk。只有能由Invoice與實際使用量證明、而且沒有犧牲可靠性的改善，才是真正的節省。

對應 Leadership Principles：

- Frugality
- Ownership
- Earn Trust
- Deliver Results

---

## 13. 請分享一次失敗或錯誤判斷，以及你學到什麼

### Situation

過去管理資料中心和基礎架構時，我曾經太相信Monitoring Dashboard，認為只要監控數值維持在正常範圍，系統就沒有明顯風險。

當時部分監控資料使用一段時間內的平均值。在一個監控週期中，大部分時間的數值正常，但中間可能出現短時間Peak；經過平均計算後，Peak被正常數值稀釋，使Dashboard看起來仍然正常，沒有及時反映現場真正發生的異常。

以CPU為例，OS通常提供累積CPU Time，而不是一個真正零時間的「瞬間CPU使用率」。Monitoring平台需要比較兩次Counter，計算兩個時間點之間的CPU平均使用率。如果CPU只在短時間內達到100%，但計算窗口很長，這段使用量仍會反映在Counter中，卻只會呈現為被稀釋後的區間平均值，無法還原真正的100% Peak。

### Task

身為管理者，我需要承認原本的監控設計存在盲點，找出哪些異常被平均值隱藏，並改善技術監控、現場確認和事件處理方式。

我的目標不是單純調低Threshold，因為這可能產生更多Noise和Alert Fatigue；真正的目標是讓Monitoring能反映設備和服務的即時狀態及實際Failure Mode。

### Mistake

我當時的錯誤，是把「Dashboard沒有告警」等同於「現場沒有異常」。

另一個錯誤，是沒有先區分Metrics本身的資料型態：

- Gauge：讀取當下的狀態，例如Available Memory或Temperature。
- Counter：持續累加的數值，例如CPU Time、Network Bytes或Error Count。
- Window Metric：OS或設備已經計算好的區間數值，例如1、5、15分鐘Load Average。
- Event：某個時間發生的事件，例如OOM、Link Down或Disk Error。

OS、設備或Sensor通常提供原始Counter、狀態值及Event；Average、Maximum、Minimum、P95／P99、Rate of Change和Peak Duration，多半是Monitoring平台根據多個Samples及時間窗口計算出來的。

我過度依賴單一Average，沒有同時檢查：

- Maximum Value。
- Peak Duration。
- P95或P99 Percentile。
- 短時間內的Rate of Change。
- Consecutive Threshold Breaches。
- 設備Log和Error Event。
- 現場環境與設備狀態。
- 使用者實際感受到的服務品質。

後來我了解到，Average適合觀察長期趨勢，但不一定適合偵測短時間異常尖峰。

### Action

我先重新檢查監控資料的Collection Interval、Aggregation Window、Threshold和告警條件。

我也檢查完整資料鏈路：

`OS／Hardware Sensor → Exporter／Agent → Collection／Scrape → Time-Series Database → Query Step → Dashboard／Alert`

真正有效的時間解析度，取決於Sensor更新、Exporter讀取、Scrape Interval及Dashboard Query Step中最慢的一層。如果原始數據已進入Time-Series Database，可能透過短窗口和Maximum找到；如果採集解析度不足，就不能從後續的Average或Maximum還原真正的短時間Peak。

除了Average，我也加入或要求團隊關注：

- Maximum Value、Peak和Spike。
- P95或P99 Percentile。
- Peak Duration和Rate of Change。
- Consecutive Threshold Breaches。
- Network、Server、Application和Environmental Events的時間關聯。
- 設備Log、現場巡檢與硬體告警。
- Synthetic Check及使用者實際服務狀態。

我不會取消Average，因為Average仍然適合Capacity和Trend Analysis。我的原則是：

- High is bad的指標看Maximum，例如CPU、Temperature、Latency及Queue Depth。
- Low is bad的指標看Minimum，例如Available Memory、Voltage、Battery Runtime及Success Rate。
- 使用者體驗看P95／P99，例如Application或Storage Latency。
- 判斷是否構成事件看Peak Duration及Consecutive Threshold Breaches。
- Counter類型先計算Rate或Increase，不能直接解讀原始累積值。

我也注意到，對長時間CPU平均值執行`Maximum`，得到的只是「多個區間平均值中的最高值」，不是真正的瞬間Maximum。因此，必須先確認底層採集與計算窗口是否足以識別目標Failure Mode。

我要求團隊不能只根據單一Dashboard做判斷，而要交叉確認Metrics、Logs、設備狀態、服務狀態和現場回報。當數據與現場狀況不一致時，必須建立時間線並進一步Dive Deep，而不是直接相信彙總後的圖表。

另外，我開始每月安排受控的異常情境模擬。在非正式或隔離環境中製造短時間資源尖峰、網路異常或服務異常；若涉及正式環境，則必須經過Change Approval，並預先定義Blast Radius、Stop Condition和Rollback Plan。

模擬用來檢查Monitoring是否能及時發現異常、告警是否正確升級，以及團隊是否按照Runbook處理。每次演練後，我們都會找出被忽略的監控節點、告警盲點和程序缺口，指定Owner完成修正，並在後續演練中重新驗證。

每次演練或Incident結束後，我會將監控調整、告警邏輯、Failure Mode、RCA與驗證結果整理歸檔並通知相關團隊。後續若Metric Source、Scrape、Aggregation、Threshold或Escalation有變更，必須同步更新文件和Version History。

### AWS Data Center適用性

這種Sampling與Aggregation風險可能存在於任何大型資料中心，但我不會假設AWS內部使用特定Sensor頻率、Aggregation Window或Alarm Threshold，因為這些內部設定並未公開。

在AWS Data Center Operations Manager的工作場景中，我會把相同原則從CPU延伸到：

- UPS、PDU及Circuit的Current Spike、Maximum Demand與Phase Imbalance。
- Rack Inlet Temperature、Humidity、Cooling及局部Hotspot。
- Server的Fan、PSU、Temperature、Hardware Event及Throttling。
- Network Interface Error、Packet Drop、Buffer及Microburst。
- Storage Latency、Queue、Timeout及Controller Event。
- BMS、Electrical Monitoring System及設備告警。

判斷時不能只看機房或設備群組的Average，還要確認單一設備、單一Circuit、單一Rack或單一介面的異常是否被整體平均值掩蓋，並交叉比對Equipment Alarm、Redundancy Status、Hardware Event與現場巡檢。

### Result

改善後，團隊能看到以前可能被平均值隱藏的短時間Peak，也能更早識別設備或服務異常。

監控方式不再只依賴Average，而是同時觀察Peak、Duration、Trend、Percentile、Logs和現場狀況。每月情境模擬也讓我們能持續驗證Monitoring、Escalation和Incident Response是否真正有效。

這個案例目前沒有使用未確認的改善百分比或時間數字；正式面試時應以可驗證的實際結果為準。

### Learning

我學到，Monitoring是協助決策的工具，不能完全取代現場觀察和工程判斷。

「沒有告警」不代表「沒有風險」，而「平均值正常」也不代表過程中沒有發生異常。身為管理者，我不只要確認Dashboard是否正常，也要確認監控方法是否能偵測真正的Failure Mode。

當Metrics、Logs、現場狀況與使用者體驗不一致時，應該優先深入調查差異，而不是直接相信其中一項資料。

### 面試結論

這次經驗改變了我的管理方式。現在我會先確認Metric Type、資料來源、採集頻率和Aggregation方式，再同時使用Average、Maximum／Minimum、Percentile、Logs、Equipment Events、現場檢查和情境模擬驗證營運狀態。

我的重點不是認為AWS一定存在某個特定監控問題，而是證明我了解這項普遍的工程風險，知道如何識別、驗證和降低它。

### 面試官可能追問

#### Q1：Metrics都是從OS Log取得的嗎？

不是。Metrics主要來自OS Kernel Counter、Hardware Sensor、SNMP、BMC、Exporter或Application Instrumentation。Logs主要記錄特定事件，用來調查當時發生什麼事情。簡單來說，Metrics告訴我數值如何變化，Logs和Events則協助說明變化原因。

#### Q2：OS或設備提供的是即時數據，還是時間區間數據？

兩種都有。Gauge通常是讀取當下最新狀態；Counter是持續累加值，需要比較兩個時間點才能計算Usage或Rate；有些指標本身已經是時間窗口結果；Event則代表某個時間發生的事情。實際看到的資料通常是Near Real-Time，仍會受到Sensor與採集頻率影響。

#### Q3：CPU瞬間吃滿100%看得到嗎？

取決於Peak Duration與計算窗口。Linux通常提供累積CPU Time，短時間100%使用會留在Counter差值中，但如果使用60秒或更長的計算窗口，最後只會看到被稀釋的區間平均值。即使再取`max_over_time`，也可能只是多個區間平均值中的最高值。要看更短Peak，必須提高底層時間解析度，並同時觀察Per-Core CPU、Load、Run Queue、I/O Wait及Application Latency。

#### Q4：AWS Data Center也會有這種問題嗎？

Sampling與Aggregation是所有Monitoring系統都需要控制的工程風險，但我不會推測AWS未公開的內部設定。我的做法是驗證Sensor Resolution、Polling Interval、Aggregation Window和Alarm Logic，再將Metrics與Equipment Events、Redundancy Status、BMS／Electrical Monitoring及現場狀況交叉比對。

#### Q5：為什麼不把所有Metrics都設定成一秒？

因為更高頻率會增加設備、網路、儲存與Query負載。正確方式是根據Service Criticality與Failure Mode分層設定。一般Capacity Metric可以使用較長窗口，快速變化或高風險指標則需要更高解析度或Event-based Telemetry。

#### Q6：如何避免調整後產生大量False Positive？

我不會只降低Threshold，而會組合Peak Duration、Consecutive Breaches、Rate of Change、多個Metrics關聯、Equipment Events、Alert Suppression、Deduplication及Maintenance Window，兼顧Detection Sensitivity與Alert Quality。

### AWS官方參考

- [EC2 CloudWatch Metrics](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/viewing_metrics_with_cloudwatch.html)：EC2 Basic Monitoring的Data Point涵蓋5分鐘，Detailed Monitoring涵蓋1分鐘；EC2提供的Minimum、Maximum及Average最低Granularity為1分鐘。
- [CloudWatch High-resolution Metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/publishingMetrics.html#high-resolution-metrics)：自訂High-resolution Metrics可使用1秒Granularity。
- [AWS Data Center Controls](https://aws.amazon.com/trust-center/data-center/our-controls/)：AWS公開說明其使用Building Management及Electrical Monitoring Systems監控電氣、機械、溫度與濕度，並透過Scenario Simulation、Corrective Actions及Lessons Learned持續改善。

對應 Leadership Principles：

- Ownership
- Dive Deep
- Learn and Be Curious
- Insist on the Highest Standards
- Are Right, A Lot

---

## 14. 你認為管理現代資料中心最大的挑戰是什麼？

### 面試主答案

我認為最大的挑戰不是管理單一設備，而是在Power（電力）、Cooling（冷卻）、Network（網路）、Server（伺服器）、Storage（儲存）、People（人員）和Process（程序）彼此相依的環境中，持續控制風險和Blast Radius（故障影響範圍）。

我的做法是先建立Service Catalog（服務目錄）與Failure Mode Matrix（故障模式矩陣）。對每一項Critical Service和Infrastructure Component，我會定義正常Baseline、SLI、SLO、Degradation Criteria、Failure Criteria、持續時間、Severity、影響範圍、Escalation和Recovery Action。這樣團隊不會因為單一數值升高就直接宣布故障。

例如，市電中斷不一定代表服務中斷。如果UPS和Generator正常接手，它是Utility Power Event（市電事件）；如果A路電力失效但B路仍正常，則是Redundancy Degradation（備援能力下降）；只有當Rack或服務失去供電時，才是Service-impacting Power Failure（影響服務的電力故障）。我的角色是整合IT Operations、Facilities、Electrical、Network和Service Owner的資訊，快速判斷風險及影響範圍，而不是取代專業電力或冷卻工程師。

網路方面，我不會因為單一Latency升高就判斷海纜中斷。我會交叉確認BFD、BGP、Interface、Optical Signal、Packet Loss、Traceroute、不同地區Probe及Carrier資訊，再判斷是Node、Circuit、Carrier還是International Path問題。Carrier正式確認前，只會標示為Suspected Upstream International Path Issue（疑似上游國際路徑異常）。

對於Baseline，我不只看Average，而會按照Site、Path、Traffic Level和Time Window建立P50、P95、P99、Packet Loss和Jitter基準。假設同一條內網路徑的P95平常在5ms內，升到10ms可能是Anomaly，但是否成為Incident，仍要看持續時間、影響範圍、Packet Loss、Route Change和Application SLO。

最後，我透過MOP、SOP、EOP、Critical Procedure Certification和每月受控情境模擬，持續驗證人員、程序、監控、備援和Vendor Support。每次演練或事件後都指定Owner、期限及驗證方式，修正完成後更新文件、審查、歸檔並公告相關部門。

我的Operational Excellence（營運卓越）是一個持續循環：

`Define → Measure → Detect → Respond → Review → Correct → Re-test`

---

### 一、資料中心營運標準架構

| 管理領域 | 必須定義的內容 |
| --- | --- |
| Service Catalog（服務目錄） | Service Owner、Criticality、使用者、Business Impact及Dependency |
| Failure Mode（故障模式） | 主要訊號、佐證資料、失效條件、持續時間及處理方式 |
| Power（電力） | Utility、ATS、UPS、Generator、PDU、A／B Feed、備援及容量 |
| Cooling（冷卻） | 溫度、濕度、Hotspot、Airflow、CRAC／CRAH及冷卻備援 |
| Network（網路） | BGP／OSPF／BFD、Latency、Loss、Jitter、Carrier及Path Diversity |
| Server／Storage | Hardware Health、CPU、Memory、PSU、Disk、IOPS、Latency及Replication |
| Capacity（容量） | Power、Cooling、Rack、Port、IP、Storage、Spare及Staff Headroom |
| Observability（可觀測性） | Metrics、Logs、Events、Synthetic Check、資料品質及監控鏈路健康 |
| Incident（事件） | Severity、Incident Commander、Escalation、通報及恢復驗證 |
| Change（變更） | Risk Assessment、MOP、Pre-check、Post-check、Rollback及Approver |
| DR／BCP | RTO、RPO、Failover、Restore、Dependency及定期演練 |
| People（人員） | Skill Matrix、On-call、Cross-training、Certification及Succession |
| Vendor／Spare | Vendor SLA、Critical Spare Matrix、到場時間及Escalation Path |
| Safety／Security | Electrical Safety、Fire、Water Leak、Access Control及Remote Access |
| Documentation（文件） | SOP、MOP、EOP、Runbook、Owner、Version、Archive及Communication |

---

### 二、電力事件如何分類？

我會和Facilities及Electrical團隊沿著完整Power Chain（電力鏈路）確認：

`Utility → Switchgear → ATS → UPS → PDU → Rack PDU → Server PSU`

| 狀況 | 營運判定 |
| --- | --- |
| 市電中斷，但UPS與Generator正常接手 | Utility Power Event，尚未形成服務中斷 |
| A路失效，但B路正常 | Redundancy Degradation，必須評估剩餘風險 |
| UPS進入Bypass、電池能力不足或Generator未Ready | Imminent Risk（即將發生的風險） |
| A／B Feed同時失效或Rack PDU沒有輸出 | Power Failure（電力故障） |
| Server或Customer-facing Service停止 | Service-impacting Incident |

我不會只看單一Voltage或Alarm，而會交叉確認Breaker、ATS位置、UPS輸入輸出、Battery、Generator、PDU、Server Dual PSU及服務狀態。事件Severity會根據Customer Impact、Redundancy Loss、Affected Scope及Time to Recover決定。

---

### 三、如何區分Node、Circuit與海纜問題？

#### Network Node Failure（網路節點故障）

- Management Interface無法存取。
- BFD Session、BGP或OSPF Neighbor中斷。
- 多個相鄰設備同時回報該節點失聯。
- Line Card、Power Module或Interface出現硬體事件。
- 流量依照設計轉移到備援節點。

#### Circuit／Carrier Failure（線路／電信商故障）

- Physical Interface或Optical Signal異常。
- CRC、Input Error、Discard或Loss of Signal增加。
- BFD／BGP Session中斷。
- 同一Carrier的相關Circuit出現共同異常。
- 備援Carrier仍然正常。

#### Suspected Submarine Cable Issue（疑似海纜異常）

- 多個地理位置的Probe同時發現相同國際方向異常。
- 多家ISP出現相似Latency或Packet Loss變化。
- BGP Route或AS Path發生共同改變。
- Traceroute顯示流量繞行其他國家或路徑。
- 國內連線正常，但特定國際方向異常。
- Carrier或海纜營運商提供正式確認。

單一站點Latency變高只能視為症狀，不能直接證明海纜中斷。在正式確認前，我會保留Hypothesis（假設），避免因過早下結論而採取錯誤動作。

---

### 四、如何快速判斷Blast Radius？

我會事先建立Physical Topology（實體拓撲）和Service Dependency Map（服務相依圖），並為資產加上Region、Site、Room、Power Feed、Carrier、Rack、Cluster、Service和Customer等標籤。

事件發生時依序確認：

1. 是單一Device、Rack、Room、Site還是Region？
2. 是單一Carrier、Circuit還是所有出口？
3. 是單一Service、部分Customer還是全部Customer？
4. 備援路徑和備援電力是否仍可用？
5. 是否失去N+1、A／B Feed或其他Fault Isolation Boundary？
6. Business KPI，例如成功交易量或服務成功率，是否已受影響？
7. 故障是否可能沿Dependency擴散？

我會要求Incident Dashboard同時呈現「What failed、What is affected、What is still healthy、Where can we fail over」，讓Incident Commander可以快速決定Isolation、Failover、Rollback或Escalation。

---

### 五、如何建立內部SLI、SLO與Baseline？

我會先定義Service Outcome（服務結果），再決定如何量測：

`SLI = Good Events（符合標準的事件）÷ Valid Events（所有有效事件）`

SLO文件必須包含：

- Service Owner與使用者。
- Service Scope與Dependency。
- SLI Definition與Data Source。
- Good Event／Bad Event定義。
- Measurement Window（統計期間）。
- SLO Target與計算方式。
- Exclusion（排除條件）。
- Error Budget（錯誤預算）。
- Alert、Escalation及未達標處理政策。
- Reviewer、Approver及Review Date。

Baseline則依照Site、Path、Traffic Load、Route、工作日、尖峰時段和Failover狀態分開建立，並同時觀察Minimum、Maximum、P50、P95、P99、Rate of Change和Peak Duration。

Baseline代表過去的正常行為，SLO代表服務可以接受的最低目標，SLA則是對客戶的正式承諾，三者不能混用。MTTD、MTTR和Escalation Time屬於Operational KPI，不能取代使用者導向的Availability、Success Rate或Latency SLO。

---

### 六、5ms升到10ms的面試回答

10ms可能是Anomaly（異常偏移），但不一定是Incident，也不一定是SLO Breach。

我會先確認是否為相同Source-Destination Probe Pair、Site、VLAN／VRF、Route、Traffic Load和Time Window，再比較P50、P95、P99、Packet Loss、Jitter、TCP Retransmission、Interface Error和Application Response Time。

- 單一Sample變成10ms，沒有其他異常：可能是Transient Spike。
- P95持續偏離5ms Baseline，但服務仍正常：Performance Degradation，需要調查。
- 只發生於特定Path或Rack：Localized Issue。
- 多條路徑同時升高：檢查Shared Dependency。
- 同時出現Packet Loss、Route Change、Timeout或Customer Impact：提高Severity並啟動Incident Response。
- 超過已核准的Latency SLO：SLO Breach。

告警判斷必須同時考慮Absolute Limit（絕對限制）、Relative Deviation（相對偏差）、Persistence（持續性）和Impact（影響），不能只使用一條固定數值。

---

### 七、Operational Excellence與持續改善

文件完成不代表程序有效。因此，我每月安排受控的Scenario Simulation（情境模擬），驗證Monitoring、Escalation、Incident Command、Failover、Rollback、Vendor Support和Stakeholder Communication。

每次演練後，我會檢查：

- 告警是否涵蓋真正的Failure Mode。
- 採集頻率是否符合RTO及偵測需求。
- Runbook是否缺少必要步驟。
- 備援是否存在未發現的Dependency。
- Escalation Contact是否有效。
- 工程師是否知道Hold Point及Stop Condition。
- 技術恢復後，是否完成Service及Data Validation。

所有問題都指定Owner、完成時間和驗證方式。修正後同步更新MOP、SOP、EOP、Runbook、Architecture、Contact、SLO和Monitoring Definition，完成審查、歸檔及相關部門公告，再透過下一次演練重新驗證。

### 公開參考資料說明

以下資料用來支持管理方法，不代表AWS台灣資料中心未公開的內部門檻：

- [AWS Reliability Pillar：Monitor All Components](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/rel_monitor_aws_resources_monitor_resources.html)：監控所有服務層級、商業KPI及外部端點。
- [AWS Reliability Design Principles](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/design-principles.html)：測試Recovery Procedure、限制單點故障及避免猜測容量。
- [AWS Fault Isolation／Bulkhead Architecture](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/rel_fault_isolation_use_bulkhead.html)：使用故障隔離邊界限制Blast Radius。
- [AWS Operational Readiness Review](https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/ops_ready_to_support_const_orr.html)：在上線前審查Operations、Security、People、Rollback及Recovery需求。
- [Google SRE：Monitoring Distributed Systems](https://sre.google/sre-book/monitoring-distributed-systems/)：Latency、Traffic、Errors、Saturation及Tail Latency管理。
- [Google SRE：Implementing SLOs](https://sre.google/workbook/implementing-slos/)：SLI、SLO、Error Budget及持續改善方法。
- [IETF RFC 5880：BFD](https://www.rfc-editor.org/rfc/rfc5880.html)：網路雙向轉送故障偵測機制。
- [Uptime Institute Tier Classification](https://uptimeinstitute.com/tiers)：Redundant Capacity及Concurrent Maintainability概念。
- [NIST SP 800-34](https://csrc.nist.gov/pubs/sp/800/34/r1/upd1/final)：Contingency Planning、Recovery需求及演練原則。

對應 Leadership Principles：

- Ownership
- Dive Deep
- Insist on the Highest Standards
- Think Big
- Success and Scale Bring Broad Responsibility
- Learn and Be Curious
- Bias for Action

---

## 15. 請分享一次改善多站點網路營運的自動化經驗

### Situation

過去管理多個站點的Fortinet Firewall、Router及Switch時，主要依靠工程師逐台人工操作。不同工程師的命名、設定方式、操作順序及驗證標準不一致，容易產生Configuration Drift，也使後續交接、稽核、故障分析及Rollback變得困難。

### Task

我的任務是建立一致、可審核、可重複執行的Network Change流程，降低人工疏失並確保多站點設定一致，但不能因為自動化而取消Security、Approval、Testing或Rollback。

### Options／Decision

我評估三個方案：

1. 維持人工操作並增加Checklist。
2. 採購大型商業Network Automation平台。
3. 使用Git、標準化Template及Ansible建立受控自動化流程。

我選擇第三個方案，因為能先從有限站點Pilot，提供Version Control、Peer Review、Audit Trail及Rollback，也能逐步擴大而不讓所有Production Site一次承擔風險。

### Action

我將Git設定為Configuration Source of Truth，管理Template、Variable、Version History及Change Request。所有變更必須經過Peer Review及Approval；Password、API Token及其他Secret不寫入Git，而由受控Credential Store及Runner取得。

Ansible使用對應設備廠牌的Collection、Module或API執行變更，Workflow包括：

- **Inventory與Scope：** 明確定義Site、Device、Role及Change Group。
- **Pre-check：** 確認設備可達性、HA、Interface、Route、Configuration及必要Capacity。
- **Configuration Diff：** 顯示預計修改內容；只有工具支援時才使用Check Mode或Dry Run，不假設每個Module都支援。
- **Approval Gate：** 由授權人員確認Scope、MOP、Success Criteria及Rollback。
- **Controlled Deployment：** 透過Least Privilege Runner分階段執行。
- **Post-check：** 驗證HA、Routing、Policy、Interface、Connectivity及Service Result。
- **Rollback：** 未達Success Criteria時停止後續Site，並恢復上一個已驗證版本。

### Result

多站點開始使用相同Template與Validation Standard，降低Configuration Drift，也建立完整的Change History及交接依據。五個站點的Network Change Time由1.5小時縮短至8分鐘，Configuration Error Rate降低75%，Deployment Failure Rate低於1%。

數據口徑：Change Time從核准變更開始，到所有Scope內設備完成Post-check為止；Configuration Error Rate以因設定錯誤需要Rollback或Rework的Change數除以Production Change總數；Deployment Failure Rate以未達Success Criteria的Deployment數除以Production Deployment總數。正式面試前需以Git、Pipeline及Change Ticket確認期間與樣本數。

### Learning

我學到，Network Automation的價值不只是速度，而是把標準、審核、驗證、稽核及恢復能力直接放進流程。Pipeline顯示成功不代表服務成功，仍要驗證設備及端到端服務結果。

對應 Leadership Principles：

- Invent and Simplify
- Insist on the Highest Standards
- Ownership
- Deliver Results

---

## 16. 請分享一次處理硬體物流或供應商延誤的經驗

### Situation

在建置資料中心時，正式Firewall及Switch需要從國外出貨，但船期發生延誤。這些Network Devices位於整個專案的Critical Path；如果等待正式設備到貨，後續Server、Security、Application、Commissioning及驗收工作都會被阻塞。

### Task

身為專案與IT負責人，我需要避免整體Data Center交付延期，同時不能因使用Temporary Equipment而降低Network Reliability、Security及後續可維護性。

### Options／Decision

我評估三個方案：

1. 等待正式設備並延後整體專案。
2. 先進行其他工作，但所有依賴Network的測試仍然延後。
3. 要求Vendor提供符合需求的借用設備，先建立可驗證的Temporary Environment，正式設備到貨後再進行受控替換。

我選擇第三個方案，因為它可以保護Critical Path，但前提是借用設備的Capacity、Feature、License及Migration Plan都必須通過審查。

### Action

使用借用設備前，我要求團隊及Vendor確認：

- Firewall Throughput、Concurrent Session、Interface及HA能力。
- Switch Port、VLAN、Trunk及必要的Routing功能。
- Firmware、License及Feature Compatibility。
- Security Policy、VPN、Logging及Monitoring能力。
- 正式設備到貨後的Configuration Migration、Maintenance Window及Rollback Plan。

我們將借用Firewall建立為HA Active-Active模式，Switch完成Trunk及必要VLAN設定，再依MOP執行HA、Routing、Security Policy、Logging及端到端Connectivity Test。這裡不只確認Device Up，也驗證實際Service Path。

正式設備到貨後，我們重新執行Pre-check，確認Firmware、Interface Mapping、License及Configuration Compatibility，再依Maintenance Window完成Configuration Migration、Failover Test及Post-check。臨時設備在Asset與Vendor紀錄中保持可追蹤，正式替換完成後依約歸還。

### Result

資料中心建置沒有因國際船期延誤而影響整體交付；正式設備到貨後，我們也在兩個月內完成替換，使Temporary Solution沒有成為長期Technical Debt。

### Learning

我學到，Hardware Logistics不是單純追蹤Delivery Date，而是Critical Path、Compatibility、Temporary Capacity、Asset Control及Migration Risk的整合管理。臨時方案一定要在採用前定義Exit Plan及完成期限。

對應 Leadership Principles：

- Ownership
- Bias for Action
- Deliver Results
- Earn Trust

---

## 17. 你如何處理低績效工程師？

這題目前採管理方法回答；正式面試若被要求「請分享一次」，必須改用真實成員案例，不能虛構人物或結果。

### Management Approach

我不會只根據印象認定工程師績效不好，而會先使用Evidence確認差距，例如：

- Ticket SLA及Backlog Aging。
- Rework或Repeated Error。
- Shift Handover完整性。
- Escalation Accuracy。
- Critical Procedure Certification。
- On-call Readiness及Team Collaboration。

接著透過One-on-one確認原因屬於：

- Skill Gap：能力或經驗不足。
- Expectation Gap：不清楚角色及標準。
- Resource Gap：缺少工具、權限、文件或支援。
- Workload Issue：工作量或排班不合理。
- Motivation／Behavior Issue：具備能力但沒有履行責任。

### Improvement Plan

我會與成員建立具體的30／60／90天計畫：

- **30天：** 完成必要Training、Runbook Review及Shadow。
- **60天：** 在Mentor監督下完成Critical Procedure及指定Ticket。
- **90天：** 獨立處理指定工作、On-call及Shift Handover。

過程中提供Mentor、Reverse Shadow、Lab及每週Feedback，並使用事先約定的Success Criteria檢查改善，而不是到期後才告知結果。

### Accountability

Blameless是用來找出系統、流程與培訓問題，但不代表沒有Accountability。如果公司已提供清楚目標、合理時間與必要支援，績效仍未達到職位要求，我會依正式Performance Management及HR制度處理，必要時調整職務或進入正式改善程序。

對應 Leadership Principles：

- Hire and Develop the Best
- Earn Trust
- Insist on the Highest Standards
- Ownership

---

## 18. 請分享一次你決定停止高風險工作的經驗

### Situation

在一次Data Center Firewall及Switch Cutover前，Vendor與內部工程師已進入Maintenance Window，也準備按照核准MOP執行。但在Pre-check階段，我發現Production現況與文件不一致：部分VLAN／Trunk Mapping、Routing及HA狀態沒有完整反映在MOP中，而且Rollback Plan缺少部分Port Mapping與Validation Criteria。

當時專案有交付壓力，停止變更會影響既定進度；但如果繼續，可能造成Network Loop、Asymmetric Routing、HA異常或服務無法完整恢復。

### Task

身為負責人，我必須決定是否按照原定時間繼續執行。我需要保護Production Environment，也要向Vendor及Stakeholders清楚說明為什麼必須停止。

### Action

我在任何Production Configuration改變前啟動Stop Work Authority，並執行以下動作：

1. 保存Running Configuration、Topology及設備狀態。
2. 召集Network Engineer、Vendor及Service Owner比對實際環境與MOP。
3. 確認VLAN、Trunk、Routing、HA、Security Policy及Service Dependency。
4. 重新評估Blast Radius及受影響Service。
5. 補齊Port Mapping、Success Criteria、Hold Point、Stop Condition及Rollback。
6. 在Lab或隔離環境重新驗證設定與切換順序。
7. 完成Peer Review及Approver重新核准後，再安排Maintenance Window。

重新執行時，我要求分階段Cutover。每個階段完成HA、Interface、Route、Policy、Connectivity及Critical Service Post-check後，才能進入下一階段。

### Result

我們在Production變更前發現並修正文件與實際環境的差異，沒有把未確認風險帶入正式環境。MOP及Rollback Plan完成修正與重新驗證後，才依核准流程完成Cutover。

事件後，我將「Running Configuration與MOP一致性」加入所有高風險Network Change的Pre-check Checklist，並要求Critical Port Mapping及Rollback步驟通過雙人Review。

### Learning

我學到，Stop Work不是阻礙交付，而是管理者保護客戶、團隊及Production的責任。即使Maintenance Window已開始，只要Safety、Redundancy、MOP或Rollback條件不完整，就不應因為Sunk Cost或時程壓力繼續執行。

對應 Leadership Principles：

- Insist on the Highest Standards
- Ownership
- Have Backbone; Disagree and Commit
- Customer Obsession
