Amazon Data Center Operations Manager 面試準備（中文整合稿）

使用原則

這份草稿以已確認的實際經驗與數據為基礎，回答時採用「結論先行＋STAR」，需要說明技術選項時再加入 Options／Decision。

每題建議控制在二至三分鐘，並優先說清楚：

當時的環境規模與客戶影響。

我個人的責任、判斷和行動，而不只說「我們」。

評估過的選項、風險、限制和取捨。

可驗證的量化結果。

從事件中建立了哪些長期改善機制。

跨題共通管理機制：Documentation Lifecycle

所有專案、變更、演練或Incident完成後，我都要求完成文件整理、審查、歸檔和溝通，不能把「技術工作完成」直接當成「工作正式結案」。

結案文件依工作類型至少包括：

最終Scope、Architecture及As-built Configuration。

MOP、SOP、EOP、Runbook、Rollback及Validation方法。

Project Decision、Change Record、Incident Timeline及重要Evidence。

RCA、Lessons Learned、Corrective／Preventive Actions。

未完成風險、相依性、Owner、期限及驗證方式。

Asset、CMDB、Vendor、Contact與Escalation資料。

文件歸檔時必須具備Owner、Version、Approval、Effective Date及Review Date，並依資訊分級與Need-to-know原則，向相關部門公告結案結果、影響、操作變更和後續責任。Critical Procedure或重大變更需要確認相關人員已閱讀、接受Training或完成必要認證。

後續只要Architecture、Configuration、Procedure、Contact、Vendor或Failure Mode改變，就必須把文件更新列入Change的Definition of Done，同步更新Version History及相關連結；舊版本保留為可追溯紀錄，但明確標示Superseded，避免工程師在Incident期間使用過期文件。

這個機制形成：

Complete → Review → Document → Approve → Archive → Communicate → Maintain

對應Leadership Principles：

Ownership

Insist on the Highest Standards

Earn Trust

Learn and Be Curious

本版本已融入以下實際經驗：

遊戲橘子、鴻海、泰偉電子的 Local Data Center 經驗

管理 300 台以上伺服器

10G 三點環形網路

後續管理 500 個以上服務

Power、Cooling、Capacity、People、Change、Supply Chain、Security 管理方法

每題標註 Amazon Leadership Principles

本版本新增：

第4題：馬來西亞連鎖網咖遊戲上線後的掉單P0事件，包含War Room、Rollback、Kafka Root Cause與自動化改善。

第5題：先驗證Data Source、Timestamp、Sampling Frequency、Aggregation及完整性，再建立時間線與驗證Root Cause。

第7題：7×24團隊的情境演練、能力驗證和壓力下協作。

第13題：過度相信Monitoring Dashboard平均值的真實錯誤判斷，並加入Metrics來源、CPU Peak、採集頻率與AWS Data Center適用性的追問。

第14題：Scenario Simulation → Observe → Identify Gaps → Correct → Re-test持續驗證循環。

跨題共通機制：所有專案、變更、演練與Incident結案後完成文件歸檔、部門公告及後續版本維護。

這一輪只更新中文內容草稿，不更新網站或推送Git。

1. 請介紹你自己

我有超過 23 年企業 IT 經驗，以及超過 14 年的人員管理經驗。我的主要專長包括實體資料中心、基礎架構營運、網路、雲端、資訊安全、自動化、Incident Management，以及跨國團隊管理。

我的實體機房管理經驗主要來自遊戲橘子、鴻海和泰偉電子。這些環境都是公司自行管理的 Local Data Center。我曾負責管理 300 台以上伺服器、10G 三點環形網路，後續管理的服務規模超過 500 個。

在泰偉電子，我從零建置約 20 個機櫃的 Payment Data Center，範圍包括雙路電力、UPS、配電、冷卻、環境監控、消防、網路、防火牆、伺服器、儲存、備份和監控，並通過 Visa 支付機房相關稽核（Visa payment data center audit）。

我管理資料中心時，不會只關注伺服器是否正常。我會同時管理 Power、Cooling、Capacity、Network、People、Change、Supply Chain 和 Security，因為任何一個環節失效，都可能造成服務和客戶影響。

我也持續研究新技術，特別是Kafka Data Streaming（Kafka資料串流）與事件驅動架構。系統上線後，我協助整合IT環境的Metrics、Logs、Infrastructure Events與Change Records，以及營運環境的交易、使用者行為和服務結果，讓IT與Operations可以根據同一條資料流進行判斷。

針對不同需求，我會設計不同的自動化應用：在IT Operations方面，用於Monitoring、Event Correlation、Incident Triage、Runbook執行和服務恢復；在Business Operations方面，用於即時Dashboard、交易異常識別、影響範圍判斷和營運決策支援。近期我也開始將AI導入IT營運流程，讓AI協助關聯Metrics、Logs、Changes和歷史Incident Knowledge，更快判斷異常類型、可能原因及建議檢查步驟，以縮短MTTD與初步診斷時間。AI定位為Decision Support，高風險操作仍必須由工程師驗證，並依照Change與Approval流程執行。

我也曾帶領最多 60 人的跨國團隊，管理每年約 300 萬至500 萬美元的預算。我的核心能力是把複雜的技術環境轉換成可量測、可管理、可持續改善的營運服務。

對應 Leadership Principles：

Ownership

Deliver Results

Dive Deep

Hire and Develop the Best

Think Big

Learn and Be Curious

2. 為什麼選擇 Amazon？為什麼對 Data Center Operations Manager 有興趣？

我想加入 Amazon，是因為 AWS 的資料中心營運會直接影響全球客戶。這個職位要求的不只是技術能力，也包括安全、營運紀律、風險管理、人員發展和持續改善，這些都和我的工作經驗及管理方式非常接近。

我的實體機房經驗來自遊戲橘子、鴻海和泰偉電子。我曾管理 300 台以上伺服器、10G 三點環形網路，以及後續超過 500 個服務，也曾從零建置約 20 個機櫃的 Payment Data Center。

我認為 Data Center Manager 的責任不是單純把 Server 顧好，而是要在 Power、Cooling、Capacity、Network、People、Change、Supply Chain 和 Security 這些彼此相依的系統中，持續維持 Availability。

例如進行 UPS 維護時，不能只確認 UPS 本身，還要確認另一側電力負載、ATS、Generator、Battery Runtime、Critical Workload、Rollback Plan，以及誰有 Stop Work Authority。

這種以風險、客戶影響和營運紀律為核心的管理方式，與 Amazon Leadership Principles 非常一致。我希望把既有的實體機房、7×24 營運、事件處理和團隊管理經驗帶到 AWS，也進一步學習 AWS 在全球規模下的資料中心管理標準。

對應 Leadership Principles：

Customer Obsession

Ownership

Insist on the Highest Standards

Think Big

Learn and Be Curious

3. 請分享你帶領過最複雜的資料中心專案

Situation

在泰偉電子，公司需要建立一座支援 Payment Services 的 Local Data Center。這不是單純採購伺服器，而是從零建立完整的資料中心基礎設施。

專案規模約為 20 個機櫃，包含雙路電力、UPS、配電、冷卻、環境監控、消防、網路、防火牆、伺服器、儲存、備份和監控。

Task

我是公司的 IT 最高主管，必須負責整體設計、預算、供應商、施工、Commissioning、驗收、資產交接和後續7×24營運，並確保環境符合Payment Service要求及Visa支付機房稽核控制要求。

Options／Decision

我們評估過沿用既有環境、完全交由外部 IDC 管理，或建立專用的 Local Data Center。

我選擇建立專用環境，因為 Payment Service 對電力、網路、存取控制、備份、稽核和營運管理都有較高要求。專用環境可以從設計階段整合這些控制。

Action

我將專案分成設計、採購、施工、設備安裝、測試、Commissioning 和 Handover 等階段，並為供應商定義責任與驗收標準。

我的管理重點包括：

檢查完整 Power Chain，而不是只看 UPS 總容量。

確認 Cooling、Rack Space、Network Port、Fiber 和未來容量。

建立10G三點環形網路，提高站點之間的網路韌性。

對重要變更建立 MOP、Pre-check、Post-check 和 Rollback Plan。

建立環境監控、告警、備份還原和故障切換測試。

協調 IT、開發、資安、財務、供應商和營運團隊。

完成資產清冊、維護責任和後續交接。

將As-built Architecture、Configuration、MOP、Runbook、驗收結果、風險和Vendor資料完成審查與歸檔，公告相關部門；後續變更必須同步更新文件和Version History。

Result

我們成功完成約20個機櫃的Payment Data Center，並通過Visa支付機房稽核。這裡描述的是通過支付機房相關稽核，不將它擴大表述為未經確認的其他認證。

正式營運後，環境支援300台以上伺服器及後續500個以上服務，維持99.95%以上可用性，RTO低於一小時，RPO低於15分鐘。

Learning

我學到，資料中心專案不是設備成功開機就算完成。真正的完成標準是設計、容量、備援、測試、文件、人員、供應商和日常營運都具備清楚的管理機制。

對應 Leadership Principles：

Ownership

Think Big

Deliver Results

Insist on the Highest Standards

Dive Deep

4. 請分享一次重大服務中斷，以及你如何處理並防止再次發生

面試結論

我曾處理一次遊戲上線後，隨著同時在線人數增加而快速惡化的掉單P0事件。我立即啟動War Room、建立每10分鐘一次的客戶溝通節奏；在30分鐘內仍未確認Root Cause時，選擇以可逆的Rollback先恢復營運，並在事件發生後45分鐘內完成回滾。後續RCA確認Kafka容量擴展未有效完成，導致Producer寫入逾時並在重試後失敗。事件後，我將關鍵檢查自動化並交付第一線使用，也在8小時內完成客戶報告。

Situation

當時我們與馬來西亞當地前三大的連鎖網咖合作，進行遊戲服務串接與正式上線。

遊戲上線初期，約5,000名使用者同時在線時，服務仍維持正常；當同時在線超過6,000人後，開始頻繁出現掉單，也就是Application呼叫Kafka Producer送出訂單訊息時發生Timeout或Error，重試後仍未成功寫入Kafka，導致部分交易沒有進入後續處理流程。當人數接近10,000人時，Producer寫入失敗的情況進一步惡化，客戶正式向我們反映服務問題。

這個事件的特徵是服務沒有完全中斷，但交易完整性隨負載增加而下降。相較於單純的網站無法連線，這類Partial Failure更難偵測，也更容易直接影響客戶營運與信任。

Task

身為負責營運與技術協調的主管，我需要同時完成四個目標：

快速確認影響範圍並恢復客戶營運。

建立清楚的Incident Command及跨團隊分工。

在Root Cause尚未確認前，做出可逆且風險可控的決策。

找出系統性原因，建立Monitoring、Capacity和Automation改善機制。

Action

1. 啟動P0 War Room與初步排查

收到客戶反映後，我立即啟動War Room，將事件定義為P0，並指定工作流負責人處理Infrastructure、Application、Database、Kafka與Customer Communication。

我先請第一線人員依照Runbook確認：

客戶端至服務端的Network Connectivity與Latency。

Server、Load Balancer及關鍵System Health。

CDN連線、Error與Origin狀態。

AWS官方服務狀態是否有已知異常。

最近是否有Application、Configuration或Architecture Change。

上述基礎項目未發現明顯異常，而且問題表現為「使用者增加後掉單率上升」，因此我判斷需要將調查重點轉向Transaction Processing Path、Application Dependency、Kafka與Database，而不是繼續只查外部網路。

2. 建立客戶溝通節奏

我直接向客戶說明目前影響、已完成的檢查、正在驗證的假設及下一步，並承諾每10分鐘提供一次更新。

即使當時尚未找到Root Cause，我也持續告知客戶：

現在已確認和排除哪些範圍。

哪些團隊正在處理。

是否有新的服務影響。

下一個Decision Point及更新時間。

這使客戶不需要反覆追問，也讓技術團隊可以集中處理問題。

3. 30分鐘Decision Point：先Rollback恢復營運

P0啟動約30分鐘後，Application、Database與Infrastructure團隊仍未能確認Root Cause。

當時可考慮三個選項：

維持現況繼續調查，但掉單可能持續增加。

在原因不明時直接擴充或修改Production，可能擴大Blast Radius。

回復到上一個已驗證的Version與Architecture，先降低客戶影響，再繼續RCA。

我與客戶說明風險後，選擇第三個方案。Rollback是當時最可逆、最能快速恢復營運，而且風險相對可控的處置。

我們在事件發生後45分鐘內完成Rollback，將Application Version及相關Deployment Architecture／Configuration恢復到上一個已驗證狀態，並持續檢查服務連線、Producer寫入結果、交易處理、錯誤狀態與客戶回報，確認營運恢復。

4. 深入RCA：建立端到端交易時間線

服務恢復後，我將事件回報層級提升至CEO，並持續帶領Application、Database及Infrastructure團隊進行RCA。

我要求團隊不要各自只看單一系統，而是依照完整Dependency建立交易處理路徑：

Client → CDN／Load Balancer → Application／API → Kafka → Consumer → Database

我們依照同一條時間線比對：

Client Request、Application Error及Transaction Result。

Kafka Producer的ACK、Retry、Timeout及Error。

Kafka Broker Health、Request Queue、CPU、Memory、Network及Disk I/O。

Partition Distribution、Replication、ISR與Under-replicated Partition狀態。

Consumer Group Status、Consumer Lag及Message Processing Rate。

Database IOPS、Latency、Connection Pool、Lock／Wait及Slow Query。

5,000、6,000及10,000使用者階段的負載與錯誤變化。

最後確認Root Cause位於Kafka寫入路徑：當服務負載越過原有容量門檻後，Kafka節點承載超過預期，而Scale-out流程沒有如設計般有效完成。Producer Request Latency與寫入錯誤隨負載增加，部分Producer請求發生Timeout，並在Retry後仍未取得成功ACK，因此訂單訊息沒有成功寫入Kafka，最終形成掉單。

這也讓我們確認，Kafka不能只用「節點是否啟動」判斷擴容成功；還需要驗證Broker是否Ready、Producer是否成功取得ACK、Partition與負載是否有效分布、Consumer是否跟上，以及端到端Transaction是否恢復。這些細節應依當時實際RCA紀錄回答，不使用未確認的數字。

5. 建立長期改善機制

事件後，我推動以下改善：

將5,000、6,000與10,000使用者階段的行為納入Capacity Baseline和Load Test Scenario。

為Kafka建立Capacity Threshold、Consumer Lag、Producer Error／Retry、Broker Health、Partition及Replication相關檢查。

驗證Scale-out不只完成Node Provisioning，也確認Broker Ready、Workload Distribution及End-to-end Processing。

將Database I/O、Latency、Connection Pool與Kafka指標放在同一條Transaction Timeline分析。

建立Rollback Trigger、Decision Point、Stop Condition與Validation Checklist。

將Network、CDN、AWS Status、Application Dependency、Kafka及Database檢查做成自動化工具或標準化指令，讓第一線人員可以快速完成初步診斷。

更新P0 Runbook、Escalation Matrix、Customer Communication Template及Capacity Review機制。

所有Incident Timeline、Decision Log、RCA、Lessons Learned和Corrective Actions都在事件完成後整理、審查及歸檔，並向相關部門公告。後續如果Architecture、Kafka、Database、Monitoring、Threshold或Runbook有任何修改，文件必須同步更新Version History，避免使用過期資訊。

Result

建立P0 War Room並以每10分鐘一次的節奏持續向客戶回報。

在Root Cause尚未確認時，採取可逆的Rollback決策，並在事件發生後45分鐘內將Application Version及相關Deployment Architecture／Configuration恢復到上一個已驗證狀態，優先讓客戶恢復營運。

找出Kafka節點容量與Scale-out流程未有效完成，造成Producer寫入逾時、重試後仍失敗的Root Cause。

將相關檢查標準化及自動化，使第一線人員後續能更快確認Network、CDN、AWS、Application、Kafka及Database等關鍵環節。

在8小時內完成並提交客戶Incident Report，包含Timeline、影響、處置、Root Cause與Corrective Actions。

客戶對我們的恢復速度、透明溝通和後續改善給予高度肯定。

Learning

我從這次事件學到三件事。

第一，Network、Server、CDN及AWS Status都正常，不代表端到端Transaction一定正常。對掉單問題，必須沿著完整交易鏈路檢查Kafka、Consumer及Database，而不是只看Infrastructure Dashboard。

第二，在P0 Incident中，不應等到Root Cause完全確認才採取行動。當客戶影響持續擴大時，應設定Decision Point，在可逆、Blast Radius可控的前提下先Rollback，恢復服務後再深入RCA。

第三，Scale-out完成不能只代表新增資源或Node啟動，還必須驗證工作負載是否真正轉移、Partition與Consumer是否正常，以及端到端交易是否恢復。

面試官可能追問

Q1：為什麼將事件定義為P0？

因為問題直接影響客戶交易，而且影響會隨同時在線人數增加而快速擴大。即使服務沒有完全中斷，Transaction Integrity已經受到影響，需要跨Application、Database、Kafka、Infrastructure及Customer Management團隊立即處理。

Q2：為什麼不直接Scale out，而是選擇Rollback？

在30分鐘Decision Point時，Root Cause尚未確認。直接修改Production可能擴大Blast Radius；上一個Version與Architecture則是已驗證狀態，Rollback更可逆，也更適合先降低客戶影響。

Q3：如何確認Rollback成功？

我會同時確認Service Health、Transaction Result、Application Error、Kafka Processing、Database狀態及客戶端實際回報。技術恢復不代表事件結束，必須確認端到端交易重新正常運作。

Q4：Kafka應該檢查哪些項目？

我會檢查Producer Error／Retry／Timeout、Broker Health、Request Queue、CPU、Memory、Network、Disk I/O、Partition Distribution、ISR、Under-replicated Partition、Consumer Lag和Message Processing Rate，再與Database I/O及Application Error建立同一條時間線。

Q5：你如何避免同樣事件再次發生？

我會透過Capacity Baseline、Load Testing、Scale-out Validation、Transaction-level Monitoring、自動化Health Check、Rollback Trigger和定期情境演練持續驗證。每項改善都必須指定Owner、期限及驗證方式，文件也必須同步更新。

對應Leadership Principles：

Customer Obsession

Ownership

Bias for Action

Dive Deep

Earn Trust

Insist on the Highest Standards

Deliver Results

5. 你如何找出根本原因，並使用數據解決問題？

面試結論

我不會看到Dashboard（監控儀表板）上的數字就直接推論Root Cause（根本原因）。在監控建置階段，我會先建立Observability Standard（可觀測性標準），統一定義時間基準、指標名稱、資料來源、單位、標籤、採集頻率、Aggregation（資料彙總方式）和資料保留規則。

Incident（事件）發生時，我不是重新統一時間格式，而是驗證各資料來源是否仍符合既有標準，以及Data Pipeline（資料處理鏈路）是否存在延遲、遺失或異常。確認數據具備完整性、一致性與足夠解析度後，我才會建立Incident Timeline（事件時間線）、驗證假設並找出根本原因。

Situation

在AXIOM，我負責五個站點的Infrastructure（基礎架構）和Operations（營運）。當時MTTD（Mean Time to Detect，平均偵測時間）約15分鐘、MTTR（Mean Time to Repair，平均修復時間）約30分鐘，事件偵測和處理方式不夠一致。

我發現問題不只是告警速度。雖然Metrics（指標數據）、Logs（日誌）和Alerts（告警）已有基本標準，但不同工具的資料用途、採集頻率和Aggregation Window（彙總時間區間）不同，仍可能造成表面上不一致的結果。如果沒有先驗證數據完整性與實際定義，工程師可能根據被平均值稀釋的Peak（尖峰）、延遲寫入的Log或不完整的Sample（樣本）做出錯誤判斷。

Task

我要找出偵測和恢復時間偏長的原因，並建立一套可量測、可重複的RCA（Root Cause Analysis，根本原因分析）方法，而不是只增加人力或依靠個人經驗猜測。

Action

我整合Prometheus、Grafana、ELK和PagerDuty，把Metrics（指標數據）、Logs（日誌）、Alerts（告警）和Incident Notifications（事件通知）連結起來。

1. 平時建立標準，事件中驗證數據

在平時建置和治理監控系統時，我先要求團隊建立Observability Standard（可觀測性標準），包括：

Time Standard（時間標準）：使用統一時區及NTP（Network Time Protocol，網路時間協定）同步。

Metric Definition（指標定義）：明確記錄名稱、來源、單位、Dimension（維度）、Owner（負責人）及適用情境。

Collection Standard（採集標準）：定義Sampling Frequency（採集頻率）、Aggregation Window（彙總時間區間）和Retention（資料保留期間）。

Log Standard（日誌標準）：定義欄位、Severity（嚴重程度）、Service Name（服務名稱）、Transaction ID（交易識別碼）和錯誤分類。

Data Pipeline Health（資料處理鏈路健康狀態）：監控Agent、Exporter、Collector、Log Pipeline和Alert Engine本身。

對每一項Critical Service（關鍵服務）與Infrastructure Component（基礎架構元件），我也會建立Failure Mode Matrix（故障模式矩陣），定義：

Service／Asset（服務／資產）。

Failure Mode（故障模式）。

Primary Signal（主要判斷訊號）與Supporting Evidence（佐證資料）。

Baseline（正常基準線）。

Degradation Criteria（效能下降條件）與Failure Criteria（故障條件）。

Persistence（持續時間或連續發生次數）。

Blast Radius（影響範圍）與Severity（事件嚴重程度）。

Response Action（應變措施）、Escalation（升級路徑）與Owner（負責人）。

這樣工程師看到告警時，不只知道數值異常，也知道它代表什麼風險、需要哪些證據、影響哪些服務，以及下一步應採取什麼行動。

Incident發生時，我不會重新制定這些標準，而是確認各資料來源是否依照標準正常運作：

Data Source（資料來源）：數據是否來自預期的OS、Hardware Sensor、Network Device、Application、Database或外部服務。

Metric Type（指標類型）：Gauge（即時狀態值）、Counter（累積計數值）、Rate（變化率）、Histogram（分布統計）或Event（事件）是否被正確解讀。

Timestamp（時間戳記）：資料是否仍使用標準時區，NTP同步是否正常，以及是否存在Clock Skew（系統時間偏差）。

Sampling Frequency（採集頻率）：Sensor、Agent、Exporter和Collector是否按照設定頻率產生及採集數據。

Aggregation（資料彙總方式）：Dashboard顯示的是Raw Value（原始值）、Average（平均值）、Maximum（最大值）、Minimum（最小值）、Sum（總和）還是P95／P99（第95／99百分位數）。

Data Completeness（資料完整性）：是否存在Missing Sample（樣本遺失）、Gap（資料空窗）、Duplicate（重複資料）、Delay（延遲）或Out-of-order Data（資料順序錯亂）。

Unit與Dimension（單位與維度）：百分比、Bytes、Bits、Milliseconds、Seconds及Instance／Site標籤是否一致。

Collection Health（採集鏈路健康狀態）：Agent、Exporter、Log Pipeline及Alert Engine本身是否正常。

我也會將Dashboard結果與其他獨立來源進行Cross-validation（交叉驗證），例如：

Raw Metrics（原始指標數據）與設備原始Counter（累積計數器）。

OS（作業系統）、Application（應用程式）、Database（資料庫）及Hardware Logs（硬體日誌）。

Network Interface（網路介面）、Firewall（防火牆）、Load Balancer（負載平衡器）及CDN（內容傳遞網路）紀錄。

Cloud Service Status（雲端服務狀態）與Change Records（變更紀錄）。

Synthetic Check（模擬交易檢查）、Transaction Result（交易結果）及客戶回報。

如果兩個來源不一致，我不會挑選比較符合原本假設的數據，而是先找出差異原因，並明確標示目前已知、未知和仍待驗證的部分。

2. 依既有標準建立事件時間線

確認資料可信後，我要求團隊依照既有時間與資料標準建立Incident Timeline（事件時間線），對照：

系統與應用程式Metrics。

Network Traffic和連線狀態。

Logs和Error Messages。

最近的Change Records。

Alert Routing和Escalation紀錄。

人員回應、判斷和交接時間。

我會先找出第一個可以被證實的異常訊號，再檢查異常前後是否有Change（變更）、Capacity（容量）轉折、Error（錯誤）增加或Dependency（相依服務）狀態改變，將「現象」和「可能原因」分開記錄。最早出現的異常訊號不一定是Root Cause，它只是建立調查假設的起點。

3. 用假設驗證，而不是只看Correlation（相關性）

我會根據時間線建立數個可能假設，並依Evidence（證據）逐一驗證：

問題是否只發生在特定Site、Instance、Rack、Network Path或Service Version。

正常與異常對象之間有什麼差異。

異常是否和最近Change或負載變化具有一致時間關係。

Rollback、隔離或修正後，症狀是否按照預期消失。

所提出的Root Cause能否完整解釋所有主要現象，而不只是其中一項Metric。

只有當Evidence（證據）、Failure Mechanism（故障機制）和修正後的驗證結果一致時，我才會將它定義為Root Cause（根本原因）。若只能證明相關性，我會標示為Contributing Factor（促成因素）或Working Hypothesis（待驗證假設）。

4. 將結果轉成可重複機制

我也重新定義SLO（Service Level Objective，服務水準目標）、Error Budget（錯誤預算）、Severity（事件嚴重程度）、Runbook（操作手冊）和Escalation Threshold（升級門檻），減少無效告警，讓工程師優先處理真正可採取行動的告警。

每次RCA完成後，我會保存Data Source（資料來源）、Query（查詢條件）、Time Range（時間範圍）、Dashboard Snapshot（儀表板快照）、Incident Timeline（事件時間線）、Decision Log（決策紀錄）和Evidence（證據），並將Corrective Actions（改善措施）指定Owner（負責人）、期限和驗證方式。文件完成審查與歸檔後向相關部門公告；後續若Metric（指標）、Threshold（門檻值）、Query或Architecture（系統架構）改變，相關文件必須同步更新。

Result

MTTD（平均偵測時間）從15分鐘降低到2分鐘，改善約86.7%；MTTR（平均修復時間）從30分鐘降低到8分鐘，改善約73.3%。

數據口徑：範圍為AXIOM五個站點納入Incident Review的Production Incidents。MTTD從第一個可被監控系統觀察到的異常訊號起算，到產生可採取行動的告警為止；MTTR從事件正式啟動到服務恢復並完成基本驗證為止。Planned Maintenance、演練告警及重複Ticket不納入。實際統計期間與Incident件數必須以Ticket、PagerDuty及RCA紀錄確認後填入，面試時不使用推估件數。

Learning

我學到，Data Center和Infrastructure Monitoring的問題通常不是沒有資料，而是資料太多、缺乏關聯。

我也學到，錯誤或未經驗證的數據可能讓團隊更快走向錯誤方向。因此Data Validation不是RCA之前的行政工作，而是RCA本身的第一個技術步驟。

有效的Monitoring必須形成：

Data Validation → Timeline → Correlation → Hypothesis → Verification → Root Cause → Corrective Action

面試官可能追問

Q1：你如何證明數據是正確的？

我會確認Data Source（資料來源）、Metric Definition（指標定義）、Unit（單位）、Timestamp（時間戳記）、Sampling Frequency（採集頻率）和Aggregation（資料彙總方式），再用Raw Counter（原始計數器）、Logs（日誌）、Equipment Event（設備事件）、Synthetic Check（模擬交易檢查）或另一個獨立系統交叉驗證。單一Dashboard不能自行證明數據正確。

Q2：如果Metrics和Logs顯示不同結果呢？

Metrics（指標數據）和Logs（日誌）在監控建置前就應該有統一的時間、命名、欄位和資料保留標準。因此，事件發生時我不會重新統一格式，而是先確認兩者比較的是不是相同的Time Range（時間範圍）、Service Scope（服務範圍）、Transaction Status（交易狀態）和Metric Definition（指標定義）。

我也會檢查Sampling Interval（採集間隔）、Aggregation Window（彙總時間區間）、Collection Delay（採集延遲）、Missing Data（資料缺失）及Monitoring Pipeline Health（監控資料鏈路健康狀態）。Metrics通常反映一段時間內的數值變化，Logs通常記錄特定事件，兩者可能描述同一事件的不同階段，不應直接判定其中一方錯誤。

如果仍然不一致，我會沿著端到端交易路徑逐段比對數量：

Client Request → Application → Kafka Producer → Kafka Consumer → Database

例如，Application收到的請求數高於Kafka Producer成功送出的訊息數，我會檢查Application到Kafka之間的Timeout（逾時）、Retry（重試）、ACK（確認回應）和送出失敗。如果Kafka收到的訊息數高於Database完成的訂單數，我會繼續檢查Consumer Lag（消費延遲）、處理失敗和Database Write Error（資料庫寫入錯誤）。第一個出現數量差異的處理階段，會成為後續RCA的重要調查方向，但仍需要Failure Mechanism（故障機制）和修復結果加以驗證。

Q3：如何避免把Correlation誤認為Root Cause？

我會要求Root Cause（根本原因）必須能解釋主要症狀、時間順序和Failure Mechanism（故障機制），並透過Rollback（回滾）、隔離、重現或修正後驗證確認。只有時間相近但缺乏機制證據的項目，只能列為Contributing Factor（促成因素）或Hypothesis（假設）。

Q4：如果歷史數據不完整怎麼辦？

我不會自行補齊或推測缺少的數據。我會清楚標示Evidence Gap（證據缺口），使用其他Logs（日誌）、Events（事件）、Configuration（設定資料）、Change Records（變更紀錄）和現場回報交叉確認，並把缺少的Telemetry（遙測資料）列為Corrective Action（改善措施），確保下次能取得必要證據。

Q5：內網平常在5ms內，升到10ms算不算異常？

10ms可能是Anomaly（異常偏移），但不一定是Incident（事故），也不一定代表SLO Breach（違反服務水準目標）。我會先確認比較的是相同Site、VLAN／VRF、Source-Destination Probe Pair（來源與目的探測點）、Route（路由）、Traffic Load（流量負載）和Time Window（時間區間）。

接著比較P50、P95、P99、Packet Loss（封包遺失）、Jitter（延遲抖動）、TCP Retransmission（TCP重傳）、Interface Error（介面錯誤）和Application Response Time（應用程式回應時間）。如果只有單一Sample升到10ms，可能只是Transient Spike（短暫尖峰）；如果P95持續偏離正常Baseline，或同時出現Packet Loss、Route Change及服務影響，就應提高Severity並啟動調查。

所以Baseline只告訴我「平常表現」，SLO則定義「服務可以接受的最低標準」。兩者不能混為一談。

Q6：內部SLO怎麼定義？

我會先定義使用者真正需要的Service Outcome（服務結果），再建立SLI（Service Level Indicator，服務水準指標）、SLO（Service Level Objective，服務水準目標）及OLA（Operational Level Agreement，內部營運協議）。

SLI可以用以下方式計算：

Good Events（符合標準的事件）÷ Valid Events（所有有效事件）

SLO文件必須寫明Service Owner、使用者、SLI定義、資料來源、Good／Bad Event、Measurement Window（統計期間）、目標、排除條件、Error Budget（錯誤預算）、Escalation及Review Date。SLO數字必須由Business、Service Owner和Operations共同確認，不能只根據歷史平均值自行決定。

MTTD、MTTR、Escalation Time等比較適合作為Operational KPI（營運指標）；服務Availability、成功率及Latency達標比例才是使用者導向的SLO。

對應 Leadership Principles：

Dive Deep

Are Right, A Lot

Insist on the Highest Standards

Learn and Be Curious

Deliver Results

6. 請分享一個改善效率的自動化專案

Situation

在Unition，環境佈建原本約需三天，Network Device Changes也包含大量人工操作，容易造成設定差異、審核不一致和Rollback困難。

Task

我要提升速度，但不能犧牲Security、Approval、Audit Trail和Production Stability。

Options／Decision

我們可以維持人工操作、購買大型商業平台，或利用Git、Templates和Ansible建立受控的自動化流程。

我選擇Git加Ansible，因為這個方案可以提供版本控制、Peer Review、可重複執行、Rollback和清楚的Audit Trail。

Action

我建立：

標準化Configuration Templates。

Git Version Control和Peer Review。

Approval Workflow。

Controlled Runners。

Least Privilege。

Pre-check和Post-check。

Rollback Plan。

Pilot和分階段Rollout。

我們先從約30台Network Devices開始，驗證穩定性後再擴大。

Result

環境佈建時間從三天縮短到五分鐘，MTTR從45分鐘降低到12分鐘。以約30台Network Devices的自動化範圍計算，該工作項目的TCO降低35%，每年節省超過30,000美元。

數據口徑：Provisioning Time從需求核准、Configuration產生及部署，到Post-check完成為止；MTTR從Incident啟動到服務恢復並完成驗證為止。TCO與年度節省只計算這項Network Automation工作範圍內的人工工時、工具／授權、維護及重複操作成本，不代表整體公司IT預算節省。實際比較期間、執行次數與Incident件數需以Pipeline、Change Ticket及Incident紀錄確認。

Learning

我學到，自動化不只是讓工作更快。真正有價值的自動化，是把安全、審核、測試、稽核和回復機制直接放進流程。

對應 Leadership Principles：

Invent and Simplify

Insist on the Highest Standards

Frugality

Deliver Results

7. 你如何管理7×24資料中心營運團隊？

我會從People、Process、Technology和Metrics四個方面管理。

People

我會建立Skill Matrix，列出每位工程師在Power、UPS、Cooling、Network、Monitoring、Security和Incident Management的能力。

如果只有一個人了解UPS、網路或監控系統，這個人本身就是Knowledge Single Point of Failure。

因此我會安排：

Cross-training。

Shadow和Reverse Shadow。

Critical Procedure Certification。

公平的On-call Rotation。

One-on-one和Development Plan。

Succession Planning。

Process

我會建立Severity（事件嚴重程度）、Escalation（升級機制）、Shift Handover（班別交接）、SOP（Standard Operating Procedure，標準作業程序）、MOP（Method of Procedure，具體操作程序）、EOP（Emergency Operating Procedure，緊急操作程序）、Runbook（操作手冊）和Stop Work Authority（停止作業權限）。

我會明確區分：SOP用於日常重複作業，MOP用於經過規劃的變更或維護，EOP用於電力、網路、冷卻或關鍵服務異常等緊急情境。每一份Critical Procedure（關鍵程序）必須包含Trigger Condition（啟動條件）、Pre-check（事前檢查）、角色分工、操作步驟、Hold Point（暫停確認點）、Stop Condition（停止條件）、Rollback（回復方式）和Post-check（事後驗證）。

文件完成不代表程序有效。我會透過Peer Review（同儕審查）、Tabletop Exercise（桌上推演）、受控演練、Shadow／Reverse Shadow及Critical Procedure Certification驗證工程師是否能正確執行。

重大事件期間，會分開Incident Command、Technical Recovery、Validation和Stakeholder Communication。

Technology

我會整合Infrastructure、Network、Environmental和Service Monitoring，避免只收到大量無法採取行動的Alarm。

Metrics

我會追蹤：

Availability

MTTD、MTTA、MTTR

Change Failure Rate

Incident Recurrence Rate

Capacity Utilization

SLA Attainment

Backlog Aging

Team Workload

每月異常情境模擬

除了日常排班、On-call、Skill Matrix和Runbook，我每月會安排一次受控的異常情境模擬。

我不會事先告訴團隊完整答案，而是觀察他們如何偵測、判斷、升級、分工、溝通和恢復服務。演練可能涵蓋Network Ring、Server、Storage、Monitoring、Critical Service、Failover、Vendor Support或主要負責人不在場等情境。

演練的目的不是責怪工程師，而是確認人員、程序和系統能否在壓力下正常運作。因此我會採用Blameless Review，但每一項改善仍然需要明確的Accountability。

我會將發現的缺口轉成：

Training與Skill Matrix改善。

Runbook、MOP、SOP或EOP更新。

Monitoring與Escalation Threshold改善。

Cross-training與Succession Planning。

Architecture、Redundancy或Vendor Support改善。

所有問題都會指定Owner和完成時間，修正後再透過下一次演練驗證。

演練、Shift Handover、Critical Procedure及Incident相關文件都必須有明確Owner和版本。每次完成後進行歸檔與部門溝通；若流程、聯絡人、設備或架構改變，文件更新必須和Change一起完成，並視需要重新Training或認證。

以我在Mlytics管理15人SOC和Cloud CDN Operations Team的經驗為例，我將文件覆蓋率從20%提升到90%，新人準備時間從六個月縮短到一個月，內部晉升超過60%，也培養兩位成員在六個月內取得AWS認證。

數據口徑：文件覆蓋率以Critical SOP／Knowledge Base清單中，已完成、通過Review且具備Owner與Version的文件數，除以應建立的文件總數計算；新人準備時間從到職日起算，到通過Critical Procedure、Shadow／Reverse Shadow及獨立值班認證為止；內部晉升率只計算正式晉升，不把一般Training Completion列為晉升。統計期間、符合晉升資格人數及實際晉升人數必須以HR與Training Records確認；AWS認證則為兩位成員在六個月內通過。

對應 Leadership Principles：

Hire and Develop the Best

Strive to be Earth’s Best Employer

Ownership

Insist on the Highest Standards

Earn Trust

8. 請分享一次你培養團隊成員的經驗

Situation

在Mlytics，我管理15人的SOC和Cloud CDN Operations Team。當時文件覆蓋率只有20%，新人需要六個月才能獨立工作。

Task

我要縮短新人準備時間、消除Knowledge SPOF，並培養未來的Team Leads和Technical Specialists。

Action

我先建立Skill Matrix，確認每位成員的技能、經驗和能力缺口。

接著重新設計：

Role Levels和職涯路徑。

Training Plan。

SOP和Knowledge Base。

Shadow與Reverse Shadow。

On-call實作和Incident Simulation。

One-on-one及定期Feedback。

Succession Planning。

我也讓成員負責AWS、Monitoring和Automation等改善專案，使學習和實際責任連結。

Result

文件覆蓋率從20%提升到90%，新人準備時間從六個月縮短到一個月，內部晉升率超過60%，兩位成員在六個月內取得AWS認證。

數據口徑：文件覆蓋率以Critical SOP／Knowledge Base清單中，已完成、通過Review且有Owner與Version的文件數除以應建立的文件總數計算；新人準備時間從到職日起算，到通過Critical Procedure、Shadow／Reverse Shadow及獨立值班認證為止；內部晉升率只計算正式晉升，不把一般Training Completion列為晉升。統計期間、符合晉升資格人數及實際晉升人數需以HR與Training Records確認；AWS認證則為兩位成員在六個月內通過。

Learning

我學到，最有效的Training不是只安排課程，而是讓成員逐步承擔真實責任，再透過觀察、回饋和驗證確認他們能獨立完成工作。

對應 Leadership Principles：

Hire and Develop the Best

Strive to be Earth’s Best Employer

Earn Trust

Ownership

9. 請分享一次你在資訊不完整時做出決策的經驗

Situation

在AXIOM，五個站點的Fortigate Firewall Change原本約需1.5小時，人工操作也存在Configuration Error Risk。

Task

我要決定是否導入自動化，但不能直接讓五個Production Sites承擔未驗證的風險。

Options／Decision

我評估三個選項：

維持人工操作。

一次全面自動化。

先進行小範圍Pilot，再逐站點擴大。

我選擇第三個方案，因為Pilot可以限制Blast Radius，也能取得足夠數據支持下一步決策。

Action

我將流程整合到Jenkins和GitLab CI/CD，加入：

Approval。

OIDC和Private Runner。

Pre-check與Post-check。

Testing。

Audit Trail。

Rollback。

分階段Deployment。

每完成一個階段，我們都檢查Deployment Failure Rate和Configuration Error Rate，再決定是否擴大。

Result

Firewall Change Time從1.5小時縮短到8分鐘，改善約91.1%；Configuration Error Rate降低75%，Deployment Failure Rate低於1%。

數據口徑：Change Time從已核准變更開始執行，到五個站點完成Post-check為止，不包含等待Maintenance Window的時間；Configuration Error Rate以因設定內容錯誤而需要Rollback或Rework的Change數除以Production Change總數計算；Deployment Failure Rate以未達Success Criteria的Deployment數除以所有Production Deployments計算。實際統計期間、Change總數與Failure件數需以Git、Pipeline及Change Ticket紀錄確認。

Learning

我學到，資訊不完整時不需要等待完美答案，但決策必須可逆、Blast Radius可控，而且結果可以量測。

對應 Leadership Principles：

Bias for Action

Are Right, A Lot

Dive Deep

Invent and Simplify

10. 當多項工作同時緊急，但資源有限時，你如何排序？

我不會只按照FIFO處理，而會依照以下順序判斷：

人員與設施安全。

客戶和服務影響。

Severity與SLA Risk。

Power、Cooling、Network或Security風險。

工作之間的Dependency。

是否有Redundancy、Failover或Rollback。

可用人力、備品和供應商支援。

我不會假設不同公司的Severity名稱完全相同，而是依照該公司的Incident Classification執行。以我過去公司的制度為例，最高嚴重等級稱為P0；如果Amazon內部使用不同名稱，我會遵循Amazon既有標準。無論名稱是P0或P1，最高優先順序都是人員與設施安全、已造成重大客戶影響的事件、安全事件、電力或冷卻風險，以及可能造成大範圍服務中斷的問題。

接下來才是重大服務降級、即將違反SLA的工作、一般Incident和Planned Work。

我也會：

保留部分團隊容量處理突發事件。

為每項工作指定Owner。

定義下一次更新時間。

建立Escalation Path。

向Stakeholders說明優先順序和影響。

當風險或服務影響改變時重新排序。

我的目標不是關閉最多Ticket，而是先降低最高的安全、營運和客戶風險。

對應 Leadership Principles：

Customer Obsession

Ownership

Bias for Action

Deliver Results

Are Right, A Lot

11. 請分享一次你在品質與交付速度之間做取捨的經驗

Situation

在Unition約30台Network Devices的自動化管理範圍內，我們需要加快Infrastructure Provisioning和Network Changes，但如果直接減少審核，可能增加Unauthorized Change、Configuration Drift和Rollback風險。

案例一致性註記（面試時不需朗讀）：這與第6題是同一個Network Automation案例，因此設備範圍、時間定義及數據來源必須保持一致。

Task

我要找出不能妥協的品質要求，同時簡化低風險、重複性的操作。

Options／Decision

選項包括：

放寬所有控制以提升速度。

繼續完全手動操作。

自動化標準變更，但保留高風險變更的審核。

我選擇第三個方案。

不能妥協的項目包括Safety、Security、Approval、Testing、Audit Trail和Rollback；可以簡化的是重複性人工輸入與等待時間。

Action

我使用Git、Templates、Ansible、Controlled Runners和Least Privilege，並透過Pilot和Phased Rollout限制Blast Radius。

對高風險變更，我要求：

明確的Success Criteria。

MOP和Rollback Plan。

Pre-check與Post-check。

Owner和Approver。

Maintenance Window。

Stop Work條件。

Result

在約30台Network Devices的工作範圍內，Provisioning從三天縮短到五分鐘，MTTR從45分鐘降低到12分鐘，同時保留變更追蹤、審核和回復能力。

數據口徑：Provisioning Time從需求核准、Configuration產生及部署，到Post-check完成為止；MTTR從Incident啟動到服務恢復並完成驗證為止。此處與第6題使用相同的Pipeline、Change Ticket及Incident Records，不能改用不同的統計期間或分母。實際比較期間、Pipeline執行次數、Production Change數與Incident件數需由原始紀錄確認。

Learning

我學到，品質和速度不一定互相衝突。如果Operating Mechanism設計正確，可以同時提升交付速度和營運品質。

對應 Leadership Principles：

Insist on the Highest Standards

Invent and Simplify

Deliver Results

Ownership

12. 請分享一次降低成本但不降低可靠性的經驗

Situation

在泰偉電子，我管理每年約300萬至500萬美元的整體IT預算與P&L。另一方面，在Unition的Network Automation專案中，我也針對約30台Network Devices評估該工作項目的TCO與年度Recurring Saving。這兩者屬於不同Scope，不能放在同一個分母中比較。公司需要改善成本和預算控制，但不能降低關鍵服務可靠性。

Task

我要區分必要的Reliability Investment，以及可以透過流程、容量、供應商或自動化改善的成本。

Action

我建立Vendor Governance、FinOps和Cost Tracking，檢查：

雲端與Infrastructure使用量。

Capacity和Headroom。

Vendor Contract及Performance。

Critical Spare和Lead Time。

重複性人工工作。

Incident和Maintenance成本。

TCO、Capex和Opex。

我不會為了省錢刪除Backup、Monitoring、DR或Security Controls，而是優先改善資源使用率、自動化、合約和供應商績效。

Result

年度預算Scope： 在整體IT Budget Governance範圍內，透過Monthly Forecast、Variance Review、Approval Gate及Vendor Governance，將Budget Overrun從15%以上控制到約3%。這項數據反映整體預算執行差異，不等同單一自動化專案節省。

單項自動化Scope： 在Unition約30台Network Devices的自動化工作範圍內，環境佈建從三天縮短到五分鐘，並依該工作項目的人工、工具／授權、維護及重複操作成本計算年度節省超過30,000美元。

TCO Scope： TCO降低35%只適用於上述Network Automation工作項目，不代表300萬至500萬美元整體IT預算降低35%。

可靠性Scope： 99.95%以上Availability屬於相關Production Service的可靠性指標，用來確認成本改善沒有造成服務品質下降，不列入Cost Saving計算。

數據口徑：Budget Overrun以實際支出超過核准預算的金額除以核准預算計算；年度節省採Annualized Saving，只計入可由Invoice、工時或維護成本驗證的Recurring Saving；TCO包含導入、工具／授權、人工、維護及Incident相關成本；Availability依該Production Service既定SLI與Measurement Window計算。各項數據的實際年度、比較期間及樣本數應分別由Budget Report、Invoice、Change／Pipeline Record及Monitoring／SLA Report確認，不能共用同一個統計期間或分母。

Learning

Frugality不是購買最便宜的設備，也不是減少必要的備援，而是把資源放在最能降低客戶和營運風險的地方。

對應 Leadership Principles：

Frugality

Ownership

Customer Obsession

Deliver Results

13. 請分享一次失敗或錯誤判斷，以及你學到什麼

Situation

過去管理資料中心和基礎架構時，我曾經太相信Monitoring Dashboard，認為只要監控數值維持在正常範圍，系統就沒有明顯風險。

當時部分監控資料使用一段時間內的平均值。在一個監控週期中，大部分時間的數值正常，但中間可能出現短時間Peak；經過平均計算後，Peak被正常數值稀釋，使Dashboard看起來仍然正常，沒有及時反映現場真正發生的異常。

以CPU為例，OS通常提供累積CPU Time，而不是一個真正零時間的「瞬間CPU使用率」。Monitoring平台需要比較兩次Counter，計算兩個時間點之間的CPU平均使用率。如果CPU只在短時間內達到100%，但計算窗口很長，這段使用量仍會反映在Counter中，卻只會呈現為被稀釋後的區間平均值，無法還原真正的100% Peak。

Task

身為管理者，我需要承認原本的監控設計存在盲點，找出哪些異常被平均值隱藏，並改善技術監控、現場確認和事件處理方式。

我的目標不是單純調低Threshold，因為這可能產生更多Noise和Alert Fatigue；真正的目標是讓Monitoring能反映設備和服務的即時狀態及實際Failure Mode。

Mistake

我當時的錯誤，是把「Dashboard沒有告警」等同於「現場沒有異常」。

另一個錯誤，是沒有先區分Metrics本身的資料型態：

Gauge：讀取當下的狀態，例如Available Memory或Temperature。

Counter：持續累加的數值，例如CPU Time、Network Bytes或Error Count。

Window Metric：OS或設備已經計算好的區間數值，例如1、5、15分鐘Load Average。

Event：某個時間發生的事件，例如OOM、Link Down或Disk Error。

OS、設備或Sensor通常提供原始Counter、狀態值及Event；Average、Maximum、Minimum、P95／P99、Rate of Change和Peak Duration，多半是Monitoring平台根據多個Samples及時間窗口計算出來的。

我過度依賴單一Average，沒有同時檢查：

Maximum Value。

Peak Duration。

P95或P99 Percentile。

短時間內的Rate of Change。

Consecutive Threshold Breaches。

設備Log和Error Event。

現場環境與設備狀態。

使用者實際感受到的服務品質。

後來我了解到，Average適合觀察長期趨勢，但不一定適合偵測短時間異常尖峰。

Action

我先重新檢查監控資料的Collection Interval、Aggregation Window、Threshold和告警條件。

我也檢查完整資料鏈路：

OS／Hardware Sensor → Exporter／Agent → Collection／Scrape → Time-Series Database → Query Step → Dashboard／Alert

真正有效的時間解析度，取決於Sensor更新、Exporter讀取、Scrape Interval及Dashboard Query Step中最慢的一層。如果原始數據已進入Time-Series Database，可能透過短窗口和Maximum找到；如果採集解析度不足，就不能從後續的Average或Maximum還原真正的短時間Peak。

除了Average，我也加入或要求團隊關注：

Maximum Value、Peak和Spike。

P95或P99 Percentile。

Peak Duration和Rate of Change。

Consecutive Threshold Breaches。

Network、Server、Application和Environmental Events的時間關聯。

設備Log、現場巡檢與硬體告警。

Synthetic Check及使用者實際服務狀態。

我不會取消Average，因為Average仍然適合Capacity和Trend Analysis。我的原則是：

High is bad的指標看Maximum，例如CPU、Temperature、Latency及Queue Depth。

Low is bad的指標看Minimum，例如Available Memory、Voltage、Battery Runtime及Success Rate。

使用者體驗看P95／P99，例如Application或Storage Latency。

判斷是否構成事件看Peak Duration及Consecutive Threshold Breaches。

Counter類型先計算Rate或Increase，不能直接解讀原始累積值。

我也注意到，對長時間CPU平均值執行Maximum，得到的只是「多個區間平均值中的最高值」，不是真正的瞬間Maximum。因此，必須先確認底層採集與計算窗口是否足以識別目標Failure Mode。

我要求團隊不能只根據單一Dashboard做判斷，而要交叉確認Metrics、Logs、設備狀態、服務狀態和現場回報。當數據與現場狀況不一致時，必須建立時間線並進一步Dive Deep，而不是直接相信彙總後的圖表。

另外，我開始每月安排受控的異常情境模擬。在非正式或隔離環境中製造短時間資源尖峰、網路異常或服務異常；若涉及正式環境，則必須經過Change Approval，並預先定義Blast Radius、Stop Condition和Rollback Plan。

模擬用來檢查Monitoring是否能及時發現異常、告警是否正確升級，以及團隊是否按照Runbook處理。每次演練後，我們都會找出被忽略的監控節點、告警盲點和程序缺口，指定Owner完成修正，並在後續演練中重新驗證。

每次演練或Incident結束後，我會將監控調整、告警邏輯、Failure Mode、RCA與驗證結果整理歸檔並通知相關團隊。後續若Metric Source、Scrape、Aggregation、Threshold或Escalation有變更，必須同步更新文件和Version History。

AWS Data Center適用性

這種Sampling與Aggregation風險可能存在於任何大型資料中心，但我不會假設AWS內部使用特定Sensor頻率、Aggregation Window或Alarm Threshold，因為這些內部設定並未公開。

在AWS Data Center Operations Manager的工作場景中，我會把相同原則從CPU延伸到：

UPS、PDU及Circuit的Current Spike、Maximum Demand與Phase Imbalance。

Rack Inlet Temperature、Humidity、Cooling及局部Hotspot。

Server的Fan、PSU、Temperature、Hardware Event及Throttling。

Network Interface Error、Packet Drop、Buffer及Microburst。

Storage Latency、Queue、Timeout及Controller Event。

BMS、Electrical Monitoring System及設備告警。

判斷時不能只看機房或設備群組的Average，還要確認單一設備、單一Circuit、單一Rack或單一介面的異常是否被整體平均值掩蓋，並交叉比對Equipment Alarm、Redundancy Status、Hardware Event與現場巡檢。

Result

改善後，團隊能看到以前可能被平均值隱藏的短時間Peak，也能更早識別設備或服務異常。

監控方式不再只依賴Average，而是同時觀察Peak、Duration、Trend、Percentile、Logs和現場狀況。每月情境模擬也讓我們能持續驗證Monitoring、Escalation和Incident Response是否真正有效。

這個案例目前沒有使用未確認的改善百分比或時間數字；正式面試時應以可驗證的實際結果為準。

Learning

我學到，Monitoring是協助決策的工具，不能完全取代現場觀察和工程判斷。

「沒有告警」不代表「沒有風險」，而「平均值正常」也不代表過程中沒有發生異常。身為管理者，我不只要確認Dashboard是否正常，也要確認監控方法是否能偵測真正的Failure Mode。

當Metrics、Logs、現場狀況與使用者體驗不一致時，應該優先深入調查差異，而不是直接相信其中一項資料。

面試結論

這次經驗改變了我的管理方式。現在我會先確認Metric Type、資料來源、採集頻率和Aggregation方式，再同時使用Average、Maximum／Minimum、Percentile、Logs、Equipment Events、現場檢查和情境模擬驗證營運狀態。

我的重點不是認為AWS一定存在某個特定監控問題，而是證明我了解這項普遍的工程風險，知道如何識別、驗證和降低它。

面試官可能追問

Q1：Metrics都是從OS Log取得的嗎？

不是。Metrics主要來自OS Kernel Counter、Hardware Sensor、SNMP、BMC、Exporter或Application Instrumentation。Logs主要記錄特定事件，用來調查當時發生什麼事情。簡單來說，Metrics告訴我數值如何變化，Logs和Events則協助說明變化原因。

Q2：OS或設備提供的是即時數據，還是時間區間數據？

兩種都有。Gauge通常是讀取當下最新狀態；Counter是持續累加值，需要比較兩個時間點才能計算Usage或Rate；有些指標本身已經是時間窗口結果；Event則代表某個時間發生的事情。實際看到的資料通常是Near Real-Time，仍會受到Sensor與採集頻率影響。

Q3：CPU瞬間吃滿100%看得到嗎？

取決於Peak Duration與計算窗口。Linux通常提供累積CPU Time，短時間100%使用會留在Counter差值中，但如果使用60秒或更長的計算窗口，最後只會看到被稀釋的區間平均值。即使再取max_over_time，也可能只是多個區間平均值中的最高值。要看更短Peak，必須提高底層時間解析度，並同時觀察Per-Core CPU、Load、Run Queue、I/O Wait及Application Latency。

Q4：AWS Data Center也會有這種問題嗎？

Sampling與Aggregation是所有Monitoring系統都需要控制的工程風險，但我不會推測AWS未公開的內部設定。我的做法是驗證Sensor Resolution、Polling Interval、Aggregation Window和Alarm Logic，再將Metrics與Equipment Events、Redundancy Status、BMS／Electrical Monitoring及現場狀況交叉比對。

Q5：為什麼不把所有Metrics都設定成一秒？

因為更高頻率會增加設備、網路、儲存與Query負載。正確方式是根據Service Criticality與Failure Mode分層設定。一般Capacity Metric可以使用較長窗口，快速變化或高風險指標則需要更高解析度或Event-based Telemetry。

Q6：如何避免調整後產生大量False Positive？

我不會只降低Threshold，而會組合Peak Duration、Consecutive Breaches、Rate of Change、多個Metrics關聯、Equipment Events、Alert Suppression、Deduplication及Maintenance Window，兼顧Detection Sensitivity與Alert Quality。

AWS官方參考

EC2 CloudWatch Metrics：EC2 Basic Monitoring的Data Point涵蓋5分鐘，Detailed Monitoring涵蓋1分鐘；EC2提供的Minimum、Maximum及Average最低Granularity為1分鐘。

CloudWatch High-resolution Metrics：自訂High-resolution Metrics可使用1秒Granularity。

AWS Data Center Controls：AWS公開說明其使用Building Management及Electrical Monitoring Systems監控電氣、機械、溫度與濕度，並透過Scenario Simulation、Corrective Actions及Lessons Learned持續改善。

對應 Leadership Principles：

Ownership

Dive Deep

Learn and Be Curious

Insist on the Highest Standards

Are Right, A Lot

14. 你認為管理現代資料中心最大的挑戰是什麼？

面試主答案

我認為最大的挑戰不是管理單一設備，而是在Power（電力）、Cooling（冷卻）、Network（網路）、Server（伺服器）、Storage（儲存）、People（人員）和Process（程序）彼此相依的環境中，持續控制風險和Blast Radius（故障影響範圍）。

我的做法是先建立Service Catalog（服務目錄）與Failure Mode Matrix（故障模式矩陣）。對每一項Critical Service和Infrastructure Component，我會定義正常Baseline、SLI、SLO、Degradation Criteria、Failure Criteria、持續時間、Severity、影響範圍、Escalation和Recovery Action。這樣團隊不會因為單一數值升高就直接宣布故障。

例如，市電中斷不一定代表服務中斷。如果UPS和Generator正常接手，它是Utility Power Event（市電事件）；如果A路電力失效但B路仍正常，則是Redundancy Degradation（備援能力下降）；只有當Rack或服務失去供電時，才是Service-impacting Power Failure（影響服務的電力故障）。我的角色是整合IT Operations、Facilities、Electrical、Network和Service Owner的資訊，快速判斷風險及影響範圍，而不是取代專業電力或冷卻工程師。

網路方面，我不會因為單一Latency升高就判斷海纜中斷。我會交叉確認BFD、BGP、Interface、Optical Signal、Packet Loss、Traceroute、不同地區Probe及Carrier資訊，再判斷是Node、Circuit、Carrier還是International Path問題。Carrier正式確認前，只會標示為Suspected Upstream International Path Issue（疑似上游國際路徑異常）。

對於Baseline，我不只看Average，而會按照Site、Path、Traffic Level和Time Window建立P50、P95、P99、Packet Loss和Jitter基準。假設同一條內網路徑的P95平常在5ms內，升到10ms可能是Anomaly，但是否成為Incident，仍要看持續時間、影響範圍、Packet Loss、Route Change和Application SLO。

最後，我透過MOP、SOP、EOP、Critical Procedure Certification和每月受控情境模擬，持續驗證人員、程序、監控、備援和Vendor Support。每次演練或事件後都指定Owner、期限及驗證方式，修正完成後更新文件、審查、歸檔並公告相關部門。

我的Operational Excellence（營運卓越）是一個持續循環：

Define → Measure → Detect → Respond → Review → Correct → Re-test

一、資料中心營運標準架構

管理領域

必須定義的內容

Service Catalog（服務目錄）

Service Owner、Criticality、使用者、Business Impact及Dependency

Failure Mode（故障模式）

主要訊號、佐證資料、失效條件、持續時間及處理方式

Power（電力）

Utility、ATS、UPS、Generator、PDU、A／B Feed、備援及容量

Cooling（冷卻）

溫度、濕度、Hotspot、Airflow、CRAC／CRAH及冷卻備援

Network（網路）

BGP／OSPF／BFD、Latency、Loss、Jitter、Carrier及Path Diversity

Server／Storage

Hardware Health、CPU、Memory、PSU、Disk、IOPS、Latency及Replication

Capacity（容量）

Power、Cooling、Rack、Port、IP、Storage、Spare及Staff Headroom

Observability（可觀測性）

Metrics、Logs、Events、Synthetic Check、資料品質及監控鏈路健康

Incident（事件）

Severity、Incident Commander、Escalation、通報及恢復驗證

Change（變更）

Risk Assessment、MOP、Pre-check、Post-check、Rollback及Approver

DR／BCP

RTO、RPO、Failover、Restore、Dependency及定期演練

People（人員）

Skill Matrix、On-call、Cross-training、Certification及Succession

Vendor／Spare

Vendor SLA、Critical Spare Matrix、到場時間及Escalation Path

Safety／Security

Electrical Safety、Fire、Water Leak、Access Control及Remote Access

Documentation（文件）

SOP、MOP、EOP、Runbook、Owner、Version、Archive及Communication

二、電力事件如何分類？

我會和Facilities及Electrical團隊沿著完整Power Chain（電力鏈路）確認：

Utility → Switchgear → ATS → UPS → PDU → Rack PDU → Server PSU

狀況

營運判定

市電中斷，但UPS與Generator正常接手

Utility Power Event，尚未形成服務中斷

A路失效，但B路正常

Redundancy Degradation，必須評估剩餘風險

UPS進入Bypass、電池能力不足或Generator未Ready

Imminent Risk（即將發生的風險）

A／B Feed同時失效或Rack PDU沒有輸出

Power Failure（電力故障）

Server或Customer-facing Service停止

Service-impacting Incident

我不會只看單一Voltage或Alarm，而會交叉確認Breaker、ATS位置、UPS輸入輸出、Battery、Generator、PDU、Server Dual PSU及服務狀態。事件Severity會根據Customer Impact、Redundancy Loss、Affected Scope及Time to Recover決定。

三、如何區分Node、Circuit與海纜問題？

Network Node Failure（網路節點故障）

Management Interface無法存取。

BFD Session、BGP或OSPF Neighbor中斷。

多個相鄰設備同時回報該節點失聯。

Line Card、Power Module或Interface出現硬體事件。

流量依照設計轉移到備援節點。

Circuit／Carrier Failure（線路／電信商故障）

Physical Interface或Optical Signal異常。

CRC、Input Error、Discard或Loss of Signal增加。

BFD／BGP Session中斷。

同一Carrier的相關Circuit出現共同異常。

備援Carrier仍然正常。

Suspected Submarine Cable Issue（疑似海纜異常）

多個地理位置的Probe同時發現相同國際方向異常。

多家ISP出現相似Latency或Packet Loss變化。

BGP Route或AS Path發生共同改變。

Traceroute顯示流量繞行其他國家或路徑。

國內連線正常，但特定國際方向異常。

Carrier或海纜營運商提供正式確認。

單一站點Latency變高只能視為症狀，不能直接證明海纜中斷。在正式確認前，我會保留Hypothesis（假設），避免因過早下結論而採取錯誤動作。

四、如何快速判斷Blast Radius？

我會事先建立Physical Topology（實體拓撲）和Service Dependency Map（服務相依圖），並為資產加上Region、Site、Room、Power Feed、Carrier、Rack、Cluster、Service和Customer等標籤。

事件發生時依序確認：

是單一Device、Rack、Room、Site還是Region？

是單一Carrier、Circuit還是所有出口？

是單一Service、部分Customer還是全部Customer？

備援路徑和備援電力是否仍可用？

是否失去N+1、A／B Feed或其他Fault Isolation Boundary？

Business KPI，例如成功交易量或服務成功率，是否已受影響？

故障是否可能沿Dependency擴散？

我會要求Incident Dashboard同時呈現「What failed、What is affected、What is still healthy、Where can we fail over」，讓Incident Commander可以快速決定Isolation、Failover、Rollback或Escalation。

五、如何建立內部SLI、SLO與Baseline？

我會先定義Service Outcome（服務結果），再決定如何量測：

SLI = Good Events（符合標準的事件）÷ Valid Events（所有有效事件）

SLO文件必須包含：

Service Owner與使用者。

Service Scope與Dependency。

SLI Definition與Data Source。

Good Event／Bad Event定義。

Measurement Window（統計期間）。

SLO Target與計算方式。

Exclusion（排除條件）。

Error Budget（錯誤預算）。

Alert、Escalation及未達標處理政策。

Reviewer、Approver及Review Date。

Baseline則依照Site、Path、Traffic Load、Route、工作日、尖峰時段和Failover狀態分開建立，並同時觀察Minimum、Maximum、P50、P95、P99、Rate of Change和Peak Duration。

Baseline代表過去的正常行為，SLO代表服務可以接受的最低目標，SLA則是對客戶的正式承諾，三者不能混用。MTTD、MTTR和Escalation Time屬於Operational KPI，不能取代使用者導向的Availability、Success Rate或Latency SLO。

六、5ms升到10ms的面試回答

10ms可能是Anomaly（異常偏移），但不一定是Incident，也不一定是SLO Breach。

我會先確認是否為相同Source-Destination Probe Pair、Site、VLAN／VRF、Route、Traffic Load和Time Window，再比較P50、P95、P99、Packet Loss、Jitter、TCP Retransmission、Interface Error和Application Response Time。

單一Sample變成10ms，沒有其他異常：可能是Transient Spike。

P95持續偏離5ms Baseline，但服務仍正常：Performance Degradation，需要調查。

只發生於特定Path或Rack：Localized Issue。

多條路徑同時升高：檢查Shared Dependency。

同時出現Packet Loss、Route Change、Timeout或Customer Impact：提高Severity並啟動Incident Response。

超過已核准的Latency SLO：SLO Breach。

告警判斷必須同時考慮Absolute Limit（絕對限制）、Relative Deviation（相對偏差）、Persistence（持續性）和Impact（影響），不能只使用一條固定數值。

七、Operational Excellence與持續改善

文件完成不代表程序有效。因此，我每月安排受控的Scenario Simulation（情境模擬），驗證Monitoring、Escalation、Incident Command、Failover、Rollback、Vendor Support和Stakeholder Communication。

每次演練後，我會檢查：

告警是否涵蓋真正的Failure Mode。

採集頻率是否符合RTO及偵測需求。

Runbook是否缺少必要步驟。

備援是否存在未發現的Dependency。

Escalation Contact是否有效。

工程師是否知道Hold Point及Stop Condition。

技術恢復後，是否完成Service及Data Validation。

所有問題都指定Owner、完成時間和驗證方式。修正後同步更新MOP、SOP、EOP、Runbook、Architecture、Contact、SLO和Monitoring Definition，完成審查、歸檔及相關部門公告，再透過下一次演練重新驗證。

公開參考資料說明

以下資料用來支持管理方法，不代表AWS台灣資料中心未公開的內部門檻：

AWS Reliability Pillar：Monitor All Components：監控所有服務層級、商業KPI及外部端點。

AWS Reliability Design Principles：測試Recovery Procedure、限制單點故障及避免猜測容量。

AWS Fault Isolation／Bulkhead Architecture：使用故障隔離邊界限制Blast Radius。

AWS Operational Readiness Review：在上線前審查Operations、Security、People、Rollback及Recovery需求。

Google SRE：Monitoring Distributed Systems：Latency、Traffic、Errors、Saturation及Tail Latency管理。

Google SRE：Implementing SLOs：SLI、SLO、Error Budget及持續改善方法。

IETF RFC 5880：BFD：網路雙向轉送故障偵測機制。

Uptime Institute Tier Classification：Redundant Capacity及Concurrent Maintainability概念。

NIST SP 800-34：Contingency Planning、Recovery需求及演練原則。

對應 Leadership Principles：

Ownership

Dive Deep

Insist on the Highest Standards

Think Big

Success and Scale Bring Broad Responsibility

Learn and Be Curious

Bias for Action
