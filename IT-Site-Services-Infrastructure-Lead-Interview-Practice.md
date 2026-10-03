# IT Site Services & Infrastructure Lead Interview Workbook

## 加拿大商星力達國際有限合夥台灣分支機構｜STAR + Options/Decision + Learning

> Use the conclusion first, then Situation/Task, two to four Actions, Result, and Learning. The English answers below are based on the candidate's resume and the additional operating experience provided.

# 1. Tell me about yourself.

### 請介紹你自己。

**JD Focus：Site infrastructure · End-user support · People leadership**

## Self-Introduction — 自我介紹

**中文：**
我有超過23年企業IT經驗，以及超過14年管理經驗，主要領域包括Site IT、Server、Network、Data Platform、自動化與使用者支援。我曾管理多站點的網路、Windows與Linux伺服器、端點、AD、Firewall、Monitoring與IT服務，支援辦公室、實驗室與製造環境。
我也參與數據中台、紅藍對抗攻防演練、Zero Trust、MFA、指紋驗證與SASE導入。對網路設備變更，我利用Git做設定版控與審核，再以自動化流程執行事前檢查、備份、部署、事後驗證與回復。
在中央與地方據點管理方面，我建立共同架構、安全標準、服務流程與升級方式，同時讓地方團隊處理日常支援、監控與故障排除。我也有管理團隊、供應商、預算、BCP與DR專案的經驗。
**English：**
I have more than 23 years of IT experience and more than 14 years of management experience. My main areas are site IT, servers, networks, data systems, automation, and user support. I have managed networks, Windows and Linux servers, devices, Active Directory, firewalls, monitoring, and IT services for offices, labs, and manufacturing sites.
I have also worked on data systems, Red Team and Blue Team security exercises, Zero Trust, MFA, fingerprint login, and SASE. For IT changes, I use Git for version control and review. We then use automation for pre-checks, backups, rollout, post-checks, and rollback.
For central and local sites, I set common design, security rules, service steps, and escalation paths. Local teams handle daily support, monitoring, and problem fixing. I also have experience with team leadership, suppliers, budgets, BCP, and DR projects.
---

# 2. Why are you interested in this IT Site Services & Infrastructure Lead role?

### 為什麼對 IT Site Services & Infrastructure Lead 職位有興趣？

**JD Focus：Site IT services · Infrastructure · Customer support**

## Answer — 回答

**中文：**
我對這個職位有興趣，因為它同時需要人員管理、Site IT服務與實作型基礎設施能力。這個職位要建立新的台灣Design Center，也要支援其他區域HPS據點，和我過去管理中央與地方網路、Server、端點及使用者服務的經驗很接近。
我可以支援Windows與Linux、Network、Checkpoint Firewall、Silver Peak SD-WAN、SONiC交換器、ClearPass NAC、Active Directory、CrowdStrike、修補與弱點改善。我也能管理供應商、預算、變更、BCP、DR與跨部門專案。我的目標是讓員工能穩定工作，讓IT環境安全、可靠且容易維護。
**English：**
I am interested in this role because it combines people leadership, site IT service, and hands-on infrastructure work. The new Taiwan Design Center and the regional HPS sites need stable support for office, lab, and manufacturing work. This matches my experience with central and local networks, servers, devices, and user IT services.
I can support Windows and Linux, networks, Check Point firewalls, Silver Peak SD-WAN, SONiC switches, ClearPass NAC, Active Directory, CrowdStrike, patching, and vulnerability fixes. I can also manage suppliers, budgets, change work, BCP, DR, and different team projects. My goal is to help people work well and keep IT safe, stable, and easy to support.
---

# 3. Tell me about the most complex site project you led.

### 請分享你帶領過最複雜的資料中心專案。

**JD Focus：New site build · Servers and networks · Project delivery**

## S — Situation｜情境

**中文：**
在泰偉電子，我從零帶領建置約20個機櫃的支付資料中心。這個專案必須支援關鍵服務、嚴格的稽核要求，以及可靠的跨站點連線。網路是設計核心，因為應用程式、儲存、備份、監控與安全流量都需要可預期且受到保護的傳輸路徑。

**English：**
At Tai Wei Electronics, I led the buildout of an about 20-rack payment site from the ground up. The project had to support critical IT services, strict audit needs, and stable connections between sites. The network was central to the design because application, storage, backup, monitoring, and security traffic all needed safe and stable paths.
## T — Task｜任務

**中文：**
身為IT最高主管，我負責架構、預算、供應商、施工、試運轉、驗收與營運交接。我的責任是交付安全且有韌性的網路基礎，明確規劃路由、分段、容量目標與回復方案，同時符合支付機房稽核要求。

**English：**
As the senior IT leader, I owned the design, budget, suppliers, construction, testing, final check, and handover to the daily work team. My responsibility was to deliver a secure and strong network foundation, with clear routing, segmentation, capacity targets, and rollback plans, while meeting payment-site audit needs.
## O / D — Options and Decision｜選項與決策

**中文：**
我們可以沿用既有網路、依賴外部IDC，或建置專用環境。我選擇專用設計，讓電力、連線、防火牆、存取控制、備份與稽核證據一起規劃。如果在這個職位規劃新的網路fabric，我會評估network design架構：伺服器連接leaf交換器，每台leaf再連接每台spine。ECMP等價多路徑路由可為東西向流量提供多條路徑。我會依工作負載驗證超額訂閱比、故障收斂與防火牆部署位置。

**English：**
We could reuse the existing network, depend on an external IDC, or build a dedicated environment. I chose a dedicated design so that power, connectivity, firewalls, access control, backup, and audit evidence could be planned together. For a new fabric in this role, I would evaluate a network design design: servers connect to leaf switches, and each leaf connects to every spine. Equal-cost multipath routing can provide many paths for internal traffic. I would check traffic load, failure recovery speed, and firewall placement against workload needs.
## A — Action｜行動

**中文：**
我把工作分成六個部分。第一是機房電力與冷卻。第二是網路架構與邊界連線，包括10G三點環網、防火牆、負載平衡器、伺服器、儲存與備份。第三是存取控制與安全需求。第四是使用Git、Jenkins、GitLab CI與Ansible進行自動化和部署。第五是監控、日誌、告警與事件操作手冊。第六是供應商治理與7×24營運。每項變更都包含核准、事前檢查、事後檢查、成功標準與回復程序。

**English：**
I divided the work into six areas. First, site power and cooling. Second, the network fabric and edge connectivity, including the 10G three-site ring, firewalls, load balancers, servers, storage, and backup. Third, access control and security needs. Fourth, automation and rollout using Git, Jenkins, GitLab CI, and Ansible. Fifth, monitoring, logging, alerting, and incident runbooks. Sixth, vendor management and 24x7 daily work. Every change used approval, pre-checks, post-checks, success criteria, and rollback procedures.
## R / L — Result and Learning｜結果與學習

**中文：**
我們從零交付機房、網路、平台、部署流程、監控及營運團隊。環境支援300台以上伺服器及後續500個以上服務，並通過相關支付機房稽核。我學到，資料中心網路的正式營運準備，代表路徑可預期、故障情境經過驗證、分段有效，而且營運制度能長期維持可靠性。

**English：**
We delivered the site, network, system, rollout process, monitoring, and daily work team from zero to one. The environment supported more than 300 servers and later more than 500 IT services, while passing the relevant payment-site audit. I learned that production readiness for a site network means predictable paths, tested failure modes, effective segmentation, and an way of working that remains reliable over time.
---

# 4. Describe a major outage and how you handled it.

### 請分享一次重大服務中斷，以及你如何處理。

**JD Focus：Major outage · User support · Recovery**

## S — Situation｜情境

**中文：**
我曾處理遊戲服務正式上線後的P0掉單事件。約5,000人同時在線時正常，超過6,000人開始掉單，接近10,000人時快速惡化。我將它視為跨層的可用性事件，同時檢查基礎設施與應用程式的相依關係。

**English：**
I once handled a P0 order-loss incident after a game service went live. The service was normal with about 5,000 concurrent users, but orders began to fail above 6,000 users and the problem became much worse near 10,000. I treated this as a cross-layer availability incident and checked both systems and application things that depend on each other.
## T — Task｜任務

**中文：**
我的任務是先保護客戶和交易、恢復穩定路徑、確認根因，並每10分鐘更新狀態。我也必須控制變更，避免排查過程擴大網路或安全影響範圍。

**English：**
My task was to protect customers and transactions first, restore a stable path, identify the root cause, and provide a status update every ten minutes. I also had to control changes so that problem fixing did not create a larger network or security area of impact.
## O / D — Options and Decision｜選項與決策

**中文：**
我們可以繼續調查、容錯切換，或回復到已驗證版本。新功能並非必要，而且回復可逆，因此我選擇風險較低的回復方式，同時維持網路路徑與安全控制穩定，取得已知正常的基準後再深入分析。

**English：**
We could continue investigating, fail over, or roll back to a checkd version. Because the new feature was not needed and rollback was easy to undo, I selected the lower-risk rollback while keeping the network path and security controls stable. That gave us a known-good baseline for deeper analysis.
## A — Action｜行動

**中文：**
我啟動War Room，指定基礎設施、網路、應用程式、資料庫、Kafka與客戶溝通負責人。先檢查網路、伺服器、CDN、負載平衡器、防火牆變更與服務狀態，再檢查變更紀錄、版本說明、部署清單及設定差異。恢復後，我建立Client、Application、Producer、Consumer與Database時間線，補上容量、封包遺失、延遲、Producer錯誤、Partition、Broker健康與回復觸發條件的檢查，並用負載測試和每月情境演練驗證。

**English：**
I started a war room and assigned owners for systems, network, application, database, Kafka, and customer communication. I checked the network, servers, CDN, load balancers, firewall changes, and service status first, then reviewed change records, release notes, rollout manifests, and settings changes. After recovery, I built a timeline across client, application, producer, consumer, and database layers. We added checks for capacity, packet loss, latency, producer errors, partitions, broker health, and rollback triggers, and checkd them with load tests and monthly scenarios.
## R / L — Result and Learning｜結果與學習

**中文：**
我們在45分鐘內恢復上一個已驗證版本，並於8小時內完成客戶報告。深入分析發現Kafka容量擴展未正確完成，造成Producer寫入逾時及未收到ACK。我學到，快速恢復後還需要路徑證據、容量驗證，以及網路和應用程式相依關係的永久改善。

**English：**
We restored the previous checkd version within 45 minutes and completed the customer report within eight hours. The deeper review showed that Kafka capacity scaling had not completed correctly, causing producer write timeouts and missing replies. I learned that fast recovery must be followed by path-level evidence, capacity checks, and permanent prevention across both network and application things that depend on each other.
---

# 5. How do you find root cause and use data?

### 你如何找出根本原因並使用數據？

**JD Focus：Troubleshooting · Monitoring · Root cause**

## S — Situation｜情境

**中文：**
在AXIOM，我負責五個站點。平均偵測時間約15分鐘，平均恢復時間約30分鐘，因此團隊需要更早、更可靠地發現連線與服務故障。

**English：**
At AXIOM, I was in charge of five sites. Mean Time to Detect was about 15 minutes and Mean Time to Restore was about 30 minutes, so the team needed earlier and more reliable detection of connectivity and service failures.
## T — Task｜任務

**中文：**
我需要先確認監控資料可信，再透過證據、故障機制及修正後結果確認根因。目標是改善偵測能力，同時避免產生大量無法採取行動的雜訊告警。

**English：**
I needed to check that the monitoring data was trustworthy, then confirm the root cause with evidence, a failure mechanism, and the result after correction. The goal was to improve detection without creating noisy alerts that engineers could not act on.
## A — Action｜行動

**中文：**
我建立可觀測性標準，定義指標來源、單位、時間戳記、採樣頻率、彙總區間、保存期間與負責人。我檢查Agent、Exporter、Collector、告警管線、遺失樣本、延遲、重複與時鐘偏差。我將指標、日誌、變更、網路流量、告警及人員回應時間整合成事件時間線。在這個職位，我也會使用介面錯誤、延遲、封包遺失、NetFlow或sFlow、路由變更及防火牆事件改善網路可視性。我把相關性當成假設，再透過隔離、比較、回復、重現或修正後驗證。

**English：**
I created an monitoring standard covering metric sources, units, timestamps, sampling frequency, time windows, storage time, and ownership. I checked agents, exporters, collectors, alert pipelines, missing samples, delays, duplicates, and clock skew. I combined metrics, logs, changes, network traffic, alerts, and human response times into one incident timeline. In this role, I would also use interface errors, latency, packet loss, NetFlow or sFlow, routing changes, and firewall events to improve network visibility. I treated link as a idea to test, then tested it through isolation, comparison, rollback, repeat test, or check after a fix.
## R / L — Result and Learning｜結果與學習

**中文：**
我整合Prometheus、Grafana、ELK與PagerDuty，將告警連結至指標和操作手冊。MTTD從15分鐘降至2分鐘，MTTR從30分鐘降至8分鐘。我學到，資料驗證是根因分析的第一步，尤其是用網路遙測資料做可用性或安全決策時。

**English：**
I connected Prometheus, Grafana, ELK, and PagerDuty and linked alerts to metrics and runbooks. MTTD decreased from 15 minutes to 2 minutes, and MTTR decreased from 30 minutes to 8 minutes. I learned that data checks is the first technical step in RCA, mainly when network network data is used to make an availability or security decision.
---

# 6. Tell me about an automation project that improved efficiency.

### 請分享一個改善效率的自動化專案。

**JD Focus：Automation · Patch and device management · Efficiency**

## S — Situation｜情境

**中文：**
在AXIOM，五個站點的FortiGate防火牆變更約需1.5小時，人工操作會產生設定錯誤風險。我們知道自動化可能改善效率，但將未驗證流程直接套用所有正式站點，可能造成大範圍安全與連線事件。

**English：**
At AXIOM, a FortiGate firewall change across five sites took about 1.5 hours and manual work created settings-error risk. We knew automation could help, but applying an untested workflow to every production site could create a large security and connectivity incident.
## T — Task｜任務

**中文：**
我需要縮短變更時間，同時保護路由、防火牆政策、存取控制與回復安全。流程必須留下稽核軌跡，也要讓多位工程師能使用。

**English：**
I needed to reduce change time while protecting routing, firewall rule, access control, and rollback safety. The workflow had to produce an audit trail and be usable by more than one engineer.
## O / D — Options and Decision｜選項與決策

**中文：**
我評估維持人工、一次自動化所有站點，或先試行再逐站擴大。我選擇試行，因為它可逆、影響範圍可控，而且能快速取得證據。

**English：**
I considered keeping the manual process, automating every site at once, or running a pilot before expanding site by site. I chose a pilot because it was easy to undo, kept the area of impact controlled, and produced evidence quickly.
## A — Action｜行動

**中文：**
我整合Git、Jenkins、GitLab CI/CD、核准關卡、OIDC、Private Runner與最小權限憑證。管線包含事前檢查、設定驗證、備份、部署、事後檢查、成功標準、停止條件、稽核日誌與回復。我們追蹤變更時間、設定錯誤率與部署失敗率。

**English：**
I connected Git, Jenkins, GitLab CI/CD, approval gates, OIDC, private runners, and least-privilege credentials. The pipeline did pre-checks, settings checks, backup, rollout, post-checks, success criteria, stop conditions, audit logging, and rollback. We tracked change time, settings-error rate, and rollout-failure rate.
## R / L — Result and Learning｜結果與學習

**中文：**
防火牆變更由1.5小時縮短至8分鐘，設定錯誤率降低75%，部署失敗率維持低於1%。我學到，網路自動化應讓安全流程可重複執行；完善核准與驗證可以提升速度，同時維持安全性與可靠性。

**English：**
Firewall change time decreased from 1.5 hours to 8 minutes, settings-error rate decreased by 75%, and rollout-failure rate stayed below 1%. I learned that network automation should make the safe path repeatable: strong approvals and checks allow speed without weakening security or reliability.
---

# 7. How do you manage a 24x7 site daily work team?

### 你如何管理7×24資料中心營運團隊？

**JD Focus：Regional HPS team · Service desk · Operations**

## Answer — 回答

**中文：**
在這個職位，我會從人員、流程、技術與指標四個面向管理7×24資料中心網路與安全團隊。技能矩陣涵蓋路由、交換、network design、防火牆、VPN、監控、事件管理與變更控制。透過交叉訓練、跟班、反向跟班、關鍵程序認證與接班規劃降低知識單點風險。我會定義事件等級、升級、交接、work steps、change plan、emergency plan、Runbook與停止作業權限，整合基礎設施、網路、環境、安全及服務監控，讓告警可採取行動。指標包含可用性、MTTD、MTTA、MTTR、變更失敗率、事件復發、容量與團隊負荷。每月演練包含環網、spine或leaf、路由切換、防火牆、監控及關鍵人員缺席情境。每次無責備檢討後，都為缺口指定負責人、期限與重測計畫。

**English：**
For this role, I would manage a 24x7 site network and security team through four areas: people, process, technology, and metrics. I use a skill matrix covering routing, switching, network design fabrics, firewalls, VPN, monitoring, incident support, and change rules. Cross-training, shadowing, reverse shadowing, critical-procedure certification, and backup leader planning reduce risk from one person. I define severity, escalation, handover, work steps, change plan, emergency plan, runbooks, and stop-work authority. Technology includes systems, network, environmental, security, and service monitoring, with actionable alerts rather than noise. I track availability, MTTD, MTTA, MTTR, change-failure rate, incident recurrence, capacity, and team workload. Monthly exercises test ring failure, spine or leaf failure, routing failover, firewall failure, monitoring loss, and the absence of a key owner. After each no-blame review, every gap receives an owner, deadline, and retest plan.
---

# 8. Tell me about a time you developed or coached your team.

### 請分享一次你培養或指導團隊成員的經驗。

**JD Focus：Coaching · Documentation · Cross-training**

## S — Situation｜情境

**中文：**
在Mlytics，我管理15人的SOC與Cloud CDN營運團隊。文件覆蓋率只有20%，新人需要六個月才能獨立工作，重要網路與安全知識集中在少數人身上。

**English：**
At Mlytics, I managed a 15-person SOC and Cloud CDN Operations Team. Documentation coverage was only 20%, new hires needed six months to work on their own, and important network and security knowledge was concentrated in a few people.
## T — Task｜任務

**中文：**
我需要縮短新人準備時間、消除知識單點風險，並培養能獨立操作網路與安全控制的組長和技術專家。

**English：**
I needed to shorten new-hire readiness, remove risk from one person, and develop team leads and technical specialists who could operate networks and security controls on their own.
## A — Action｜行動

**中文：**
我建立技能矩陣與職級，重新設計訓練計畫、work steps、知識庫、跟班、反向跟班、值班實作與事件演練。成員負責AWS、監控與自動化改善專案；透過關鍵程序認證確認能安全執行變更、容錯切換與回復。演練後，我將缺口轉為訓練、操作手冊、監控、升級或架構改善。

**English：**
I created a skill matrix and role levels, then redesigned the training plan, work stepss, knowledge base, shadowing, reverse shadowing, on-call practice, and incident simulations. Team members owned AWS, monitoring, and automation improvement projects. Critical-procedure certification confirmed that they could execute changes, failover, and rollback safely. After each exercise, I converted gaps into training, runbook, monitoring, escalation, or design improvements.
## R / L — Result and Learning｜結果與學習

**中文：**
文件覆蓋率從20%提升至90%，新人準備時間從六個月縮短至一個月，內部晉升超過60%，兩位成員在六個月內取得AWS認證。我學到，技術訓練連結真實網路責任和可量測營運成果時，效果最好。

**English：**
Documentation coverage increased from 20% to 90%, new-hire readiness decreased from six months to one month, internal promotion exceeded 60%, and two team members earned AWS certifications within six months. I learned that IT training is most effective when it is connected to real network responsibility and clear daily results.
---

# 9. Tell me about a decision you made with incomplete information.

### 請分享一次你在資訊不完整時做出決策的經驗。

**JD Focus：Business decision · Risk · Vendor choice**

## S — Situation｜情境

**中文：**
在AXIOM，五個站點的FortiGate防火牆變更約需1.5小時。自動化看起來可行，但當時還沒有足夠證據直接套用所有正式站點，而且錯誤可能影響連線與安全控制。

**English：**
At AXIOM, a FortiGate firewall change across five sites took about 1.5 hours. Automation appeared promising, but we did not yet have enough evidence to apply it to every production site, and an error could affect connectivity and security controls.
## T — Task｜任務

**中文：**
我需要在資訊不完整時取得證據，控制影響範圍與回復風險，同時保留核准、可稽核性及最小權限。

**English：**
I needed to gather evidence while information was incomplete and control the area of impact and rollback risk. The decision also had to preserve approvals, auditability, and least-privilege access.
## O / D — Options and Decision｜選項與決策

**中文：**
我評估維持人工、一次全面自動化，或先試行再逐站擴大。我選擇試行，因為它可逆、範圍可控，而且能快速產生新證據。

**English：**
I considered keeping the manual process, automating everything at once, or running a pilot before expanding site by site. I chose a pilot because it was easy to undo, controlled the scope, and produced new evidence quickly.
## A — Action｜行動

**中文：**
我先選擇低風險站點及標準化變更，整合Jenkins、GitLab CI/CD、核准、OIDC、Private Runner、最小權限、事前與事後檢查、稽核軌跡、回復、成功標準與停止條件。每階段追蹤變更時間、設定錯誤率、部署失敗率、路由可達性與防火牆健康。若事後檢查失敗，必須停止部署並評估回復。

**English：**
I selected a lower-risk site and a standardized change, then connected Jenkins and GitLab CI/CD with approval, OIDC, private runners, minimum access, pre-checks, post-checks, audit trails, rollback, success criteria, and stop conditions. We tracked change time, settings-error rate, rollout-failure rate, route reachability, and firewall health at each stage. If a post-check failed, the rollout had to stop and we would assess rollback.
## R / L — Result and Learning｜結果與學習

**中文：**
防火牆變更由1.5小時縮短至8分鐘，設定錯誤率降低75%，部署失敗率低於1%。我學到，資訊不完整不代表一定要等待完美答案，但決策必須可逆、可控且可量測。

**English：**
Firewall change time decreased from 1.5 hours to 8 minutes, settings-error rate decreased by 75%, and rollout-failure rate stayed below 1%. I learned that incomplete information does not always require waiting for a perfect answer; the decision should be easy to undo, controlled, and clear.
---

# 10. How do you choose first when many tasks are urgent and resources are limited?

### 多項工作同時緊急，但資源有限時如何排序？

**JD Focus：Urgent incidents · Customer impact · Site priorities**

## Answer — 回答

**中文：**
我不會只按誰催得最急來排序，而是先降低最高的人員安全、客戶、資安與營運風險。我會檢查人員和機房安全、客戶影響、事件等級與SLA風險，再看電力、冷卻、路由、相依性、備援、回復選項、備品與供應商支援。網路工作也要考量影響範圍、東西向流量暴露、路由收斂、防火牆政策與安全切換路徑。我保留部分團隊容量處理突發事件，指定負責人、下次更新時間與升級路徑，並在影響或恢復選項改變時重新排序。例如一般佈建需求與不穩定的spine連線同時發生，我會先處理連線風險，並保留清楚交接讓低風險工作安全恢復。

**English：**
I do not choose first only by who asks the loudest. I first reduce the highest safety, customer, security, and daily risk. I check personnel and site safety, customer impact, severity and SLA risk, then power, cooling, routing, things that depend on each other, redundancy, rollback options, spares, and supplier support. For IT work, I consider area of impact, east-west exposure, route recovery speed, firewall rule, and whether a safe failover path exists. I reserve part of the team's capacity for incidents, assign an owner, define the next update time and escalation path, and re-choose first when impact or recovery options change. For example, if a normal provisioning request and an unstable spine link occur together, I handle the link risk first and preserve a clear handover so lower-risk work can resume safely.
---

# 11. Tell me about a time you balanced quality and delivery speed.

### 請分享一次你在品質與交付速度之間做取捨的經驗。

**JD Focus：Change management · Testing · Service quality**

## S — Situation｜情境

**中文：**
在Unition，我們需要加快基礎設施佈建與網路變更，但直接減少審查會增加未授權變更、設定漂移及回復風險。

**English：**
At Unition, we needed faster systems provisioning and network changes, but just reducing reviews could increase unauthorized changes, settings drift, and rollback risk.
## T — Task｜任務

**中文：**
我需要確認不可妥協的品質與安全要求，同時簡化低風險、可重複工作。流程必須保留可追溯性與安全恢復路徑。

**English：**
I needed to identify non-negotiable quality and security needs while simplifying low-risk, repeatable work. The process had to preserve traceability and a safe recovery path.
## O / D — Options and Decision｜選項與決策

**中文：**
我選擇自動化標準變更，對高風險變更保留核准人、change plan、維護時段、測試、稽核軌跡、回復與停止作業條件，區分可加速的工作與需要深入審查的決策。

**English：**
I chose to automate standardized changes while keeping an approver, change plan, maintenance window, testing, audit trail, rollback, and stop-work conditions for high-risk changes. This separated speed improvements from decisions that required deeper review.
## A — Action｜行動

**中文：**
我使用Git、範本、Ansible、受控Runner與最小權限。透過試行與分階段部署限制影響範圍，開發、測試及正式環境使用相同的已驗證產出。事後檢查確認可達性、路由、防火牆政策與服務健康；未達成功標準就停止部署或回復。

**English：**
I used Git, templates, Ansible, controlled runners, and minimum access. A pilot and phased rollout limited the area of impact, and development, staging, and production used the same checkd artifact. Post-checks checked reachability, routing, firewall rule, and service status; if success criteria were not met, we stopped the rollout or rolled it back.
## R / L — Result and Learning｜結果與學習

**中文：**
佈建由三天縮短至五分鐘，MTTR從45分鐘降至12分鐘，同時保留變更追蹤、審查與恢復能力。我學到，當營運制度讓安全流程容易重複執行時，品質與交付速度可以一起提升。

**English：**
Provisioning decreased from three days to five minutes, and MTTR decreased from 45 minutes to 12 minutes while change tracking, review, and recovery remained available. I learned that quality and delivery speed can improve together when the way of working makes the safe path easy to repeat.
---

# 12. Tell me about a time you reduced cost without reducing reliability.

### 請分享一次降低成本但不降低可靠性的經驗。

**JD Focus：Budget · Business case · Supplier management**

## S — Situation｜情境

**中文：**
我曾管理每年約300萬至500萬美元的IT預算，也在Unition管理約150萬美元預算。我們希望利用規模降低網路與雲端成本，同時維持安全、可用性、備份、災難復原與資安。

**English：**
I have managed annual IT budgets of about three to five million US dollars and a budget of about 1.5 million dollars at Unition. We needed to use scale to reduce network and cloud cost without weakening safety, availability, backup, disaster recovery, or security.
## T — Task｜任務

**中文：**
我需要區分必要的可靠性投資，以及可透過架構、容量規劃、自動化及供應商治理改善的成本。

**English：**
I needed to separate necessary reliability investments from costs that could be improved through design, capacity checks, automation, and vendor management.
## A — Action｜行動

**中文：**
我整合需求、流量使用量、合約日期、計費單位、SLA與支援等級，用一致假設比較供應商TCO。我談判用量級距、承諾用量、價格保護、續約上限、支援範圍、服務抵扣與驗收條件。連線與安全服務也需記錄可用性、回應和解決時間、容量承諾、資料可攜性、退出計畫、DR支援、關鍵備品及移轉方案，並保留必要備援。

**English：**
I combined needs, traffic usage, contract dates, billing units, SLAs, and support levels, then compared vendor TCO using the same assumptions. I negotiated volume tiers, committed usage, price protection, renewal caps, support coverage, service credits, and final check conditions. For connectivity and security IT services, I documented availability, response and resolution times, capacity commitments, ability to move data, leaving plans, DR support, important spares, and migration options while retaining required redundancy.
## R / L — Result and Learning｜結果與學習

**中文：**
Google Cloud有效價格從牌價80%降至60%，以原實付價格計算，相對成本降低25%，在相同範圍及合約期間約節省50,000美元。我學到，成本管理應透過規模與治理降低TCO，同時避免增加集中及營運風險。

**English：**
We reduced the effective Google Cloud price from 80% of list price to 60%. Based on the original paid price, that was a 25% cost reduction and about 50,000 US dollars in savings under the same scope and contract time. I learned that cost control means reducing TCO through scale and management without increasing concentration or daily risk.
---

# 13. Tell me about a time you made a wrong judgment and what you learned.

### 請分享一次錯誤判斷，以及你從中學到什麼。

**JD Focus：Learning · Monitoring · Problem solving**

## S — Situation｜情境

**中文：**
過去管理資料中心時，我曾太相信監控儀表板，把沒有告警當成沒有異常。較長的彙總區間稀釋了短時間CPU、網路與服務尖峰，所以儀表板正常，但使用者已遇到問題。

**English：**
Earlier in my site daily work experience, I trusted a monitoring dashboard too much and treated no alert as no abnormality. Long time windows diluted short CPU, network, and service peaks, so the dashboard looked normal while users experienced a real problem.
## T — Task｜任務

**中文：**
我需要承認監控盲點，找出被平均值隱藏的網路與服務故障，改善遙測、現場驗證與事件應變。

**English：**
I needed to acknowledge the monitoring blind spot, identify which network and service failures were hidden by averages, and improve network data, field check, and incident support.
## A — Action｜行動

**中文：**
我檢查資料來源、採樣頻率、彙總區間、門檻與告警條件，加入最大值、P95、P99、變化率、尖峰持續時間及連續超標，再比對介面計數器、設備事件、應用程式日誌、交易結果、路由變更及現場狀況。我要求確認監控管線本身健康，不能依賴單一儀表板。每月測試短時間尖峰、網路異常與服務故障，並指定負責人、期限及重測。

**English：**
I reviewed data sources, sampling frequency, time windows, thresholds, and alert conditions. We added maximum values, P95 and P99, rate of change, peak duration, and consecutive breaches, then correlated them with interface counters, equipment events, application logs, transaction results, route changes, and field conditions. I also required the team to check that the monitoring pipeline itself was healthy instead of relying on one dashboard. Monthly scenarios tested short peaks, network abnormalities, and service failures, followed by an owner, deadline, and retest.
## R / L — Result and Learning｜結果與學習

**中文：**
團隊能看到以前被平均值隱藏的短時間尖峰，更早發現設備與服務問題。我學到，平均值適合長期趨勢，但可能遺漏短暫故障。監控是決策工具，必須搭配日誌、流量證據、現場觀察與工程判斷。

**English：**
The team could see short peaks that had previously been hidden by averages and detect equipment or service problems earlier. I learned that averages are useful for long-term trends but may miss a short failure mode. Monitoring is a decision tool and must be combined with logs, traffic evidence, field observation, and engineering judgment.
---

# 14. What are the biggest challenges in managing a modern site?

### 你認為管理現代資料中心最大的挑戰是什麼？

**JD Focus：Manufacturing IT · BCP/DR · Infrastructure risks**

## Answer — 回答

**中文：**
我認為最大挑戰是管理電力、冷卻、容量、network design連線、路由、安全、人員、變更、供應鏈與供應商之間的相依關係。網路主管必須了解南北向連線及東西向流量，並在故障時控制影響範圍。我使用故障模式矩陣定義電力、冷卻、網路設備、路由、防火牆、VPN與服務的主要訊號、佐證、基準、故障判定、持續時間、嚴重度及應對方式。我會觀察延遲、封包遺失、抖動、路由變更、NetFlow或sFlow、P95、P99與服務影響。變更管理包含change plan、事前與事後檢查、核准、回復與停止作業權限；人員管理包含技能矩陣、交叉訓練、跟班及關鍵程序認證；供應鏈則維護關鍵備品與供應商SLA計畫。每月演練監控、事件指揮、路由切換、防火牆回復、供應商支援與溝通，再修正缺口並重測。我的管理原則是讓相互依賴的系統保持安全、可觀測、有韌性，並遵守營運紀律。

**English：**
I believe the biggest challenge is managing things that depend on each other across power, cooling, capacity, network connectivity, routing, security, people, change, suppliers. A site network lead must understand both user connections and internal traffic, then control the area of impact when something fails. I use a failure-mode matrix for power, cooling, network equipment, routing, firewalls, VPN, and IT services. It defines primary signals, supporting evidence, baselines, failure criteria, persistence, severity, and response actions. I do not rely only on averages: I check latency, packet loss, jitter, route changes, NetFlow or sFlow, P95 and P99, and effect on users. For change work, I require a change plan, pre-checks, post-checks, an approver, rollback, and stop-work authority. For people, I use skill matrices, cross-training, shadowing, and critical-procedure certification. For suppliers, I keep critical-spare and vendor-SLA plans. Every month, we exercise monitoring, incident command, routing failover, firewall rollback, supplier support, and communication, then correct gaps and retest. My management principle is to keep coupled systems secure, observable, strong, and well managed.
---


## How to use these answers

**中文：**
每題先說結論，再用STAR-L展開。清楚區分我與團隊的貢獻，並說明每個指標的範圍、期間、分母與資料來源。機密資訊可以用區間、比例、服務等級與決策原則說明，避免提供客戶名稱或敏感架構細節。

**English：**
Start with the conclusion, then use STAR-L. Make the difference between ‘I’ and ‘we’ clear, and explain scope, period, denominator, and data source for every metric. If information is confidential, use ranges, percentages, service levels, and decision principles instead of customer names or sensitive design details.
