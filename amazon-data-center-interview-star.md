# Amazon Data Center Operations Manager Interview Workbook

## Resume-based STAR answers | TOEIC 600-friendly English

> These answers are based on the experience and metrics in CK Chiu's current resume. Use ranges or principles when a detail is confidential.

# 1. Tell me about yourself.

### 請介紹你自己。

**Primary Leadership Principles：Ownership · Deliver Results · Learn and Be Curious**

## Answer — 回答

**中文：**
我有超過 23 年企業 IT 經驗，以及超過 14 年的人員管理經驗。我曾管理最多 60 人的跨國團隊與每年 300 到 500 萬美元的預算。我從零建置 20-rack payment data center，管理 500 多台伺服器與約 300 個服務，支援超過 17 萬同時在線使用者，維持 99.95% 以上可用性。現在我專注於資料中心、雲端、7×24 服務、事件管理、自動化和團隊發展。

**English：**
I have more than 23 years of enterprise IT experience and more than 14 years of people-management experience. I have led up to 60 people across countries and managed annual budgets of three to five million US dollars. I built a 20-rack payment data center from the ground up, managed more than 500 servers and about 300 services, supported more than 170,000 concurrent users, and maintained availability above 99.95 percent. My strengths are data center operations, cloud, 24x7 services, incident management, automation, and developing people. I want to bring this practical experience to AWS and improve safety, reliability, and customer experience at global scale.

---

# 2. Why Amazon and why Data Center Operations?

### 為什麼選 Amazon？為什麼是資料中心營運？

**Primary Leadership Principles：Customer Obsession · Ownership · Think Big**

## Answer — 回答

**中文：**
AWS 把營運品質直接連結到客戶體驗，這與我的工作方式一致。資料中心營運結合實體基礎架構、伺服器、網路、電力、冷卻、雲端、事件指揮、DR/BCP、供應商與人員管理。我曾建置 payment data center 並通過 VISA validation，也曾在 2022 FIFA World Cup 期間協調 WAF、AWS Shield、traffic scrubbing 和 DDoS vendors，維持 99.9% 以上可用性且零停機。

**English：**
I am interested in Amazon because AWS connects operational quality directly to customer experience and expects high, measurable standards. Data Center Operations matches my background in physical infrastructure, servers, networks, power, cooling, cloud, incident command, disaster recovery, vendors, and people leadership. I built a payment data center and passed VISA validation. I also coordinated WAF, AWS Shield, traffic scrubbing, and DDoS vendors during the 2022 FIFA World Cup. We maintained availability above 99.9 percent with zero downtime. I can bring practical operations experience and learn how AWS runs data centers safely at global scale.

---

# 3. Tell me about the most complex infrastructure project you led.

### 請分享你帶領過最複雜的基礎架構專案。

**Primary Leadership Principles：Ownership · Think Big · Deliver Results**

## S — Situation｜情境

**中文：**
在 Astro Corp.，公司需要一個支援 payment services 的新資料中心。我負責從零規劃，範圍包含約 20 個機櫃、雙路電力、UPS、配電、冷卻、環境監控、消防、網路、防火牆、伺服器、儲存、備份與監控。

**English：**
At Astro Corp., the company needed a new data center for payment services. I led the project from the beginning. The scope included about 20 racks, dual power, UPS, power distribution, cooling, environmental monitoring, fire protection, network, firewalls, servers, storage, backup, and monitoring.

## T — Task｜任務

**中文：**
我的任務是協調供應商與內部團隊，完成 commissioning、asset handover、VISA validation，並交給 24×7 團隊穩定營運。

**English：**
My task was to coordinate vendors and internal teams, complete commissioning and asset handover, pass VISA validation, and transition the environment to stable 24x7 operations.

## O / D — Options and Decision｜選項與決策

**中文：**
我們可以完全外包、沿用現有機房，或建立專用環境。我選擇專用設計，因為電力、網路、存取控制、備份和稽核要求可以從設計階段整合。

**English：**
We could outsource the environment, reuse an existing facility, or build a dedicated design. I chose the dedicated design because power, network, access control, backup, and audit requirements could be integrated from the start.

## A — Action｜行動

**中文：**
我建立 architecture、採購、施工、測試和 handover 計畫，定義供應商責任與驗收標準，並要求測試電力、網路、備份、監控和故障情境。

**English：**
I created architecture, procurement, construction, testing, and handover plans. I defined vendor responsibilities and acceptance criteria, and required tests for power, network, backup, monitoring, and failure scenarios.

## R / L — Result and Learning｜結果與學習

**中文：**
我們完成資料中心並通過 VISA validation，後續維持 99.95% 以上可用性、RTO 小於一小時、RPO 小於 15 分鐘。我學到，專案完成不只是設備上線，而是設計、驗證、交接和日常營運都有清楚控制。

**English：**
We delivered the data center and passed VISA validation. It later maintained availability above 99.95 percent, with an RTO under one hour and an RPO under 15 minutes. I learned that a data center project is complete only when design, validation, handover, and daily operations all have clear controls.

---

# 4. Describe a major outage and how you handled it.

### 請分享一次重大服務中斷，以及你如何處理。

**Primary Leadership Principles：Ownership · Bias for Action · Deliver Results**

## S — Situation｜情境

**中文：**
在 Gamania，我負責 500 多台伺服器和 24×7 高流量遊戲服務。年度累計服務中斷達 4,998 小時，影響玩家體驗與營運。

**English：**
At Gamania, I was responsible for more than 500 servers and 24x7 high-traffic game services. Annual cumulative service interruption was 4,998 hours, which affected player experience and operations.

## T — Task｜任務

**中文：**
我不只要處理單一事件，也要找出重複原因，建立偵測、分級、復原和預防機制。

**English：**
My task was not only to handle individual incidents. I needed to find recurring causes and build better detection, severity management, recovery, and prevention mechanisms.

## O / D — Options and Decision｜選項與決策

**中文：**
我們可以增加 on-call 人力、逐一處理事件，或改善 DR/BCP、集中監控、容量管理、預防性維護和 RCA。我選擇系統性改善，因為問題是營運控制不足，而不只是人手不足。

**English：**
We could add on-call staff, handle incidents one by one, or improve disaster recovery, centralized monitoring, capacity management, preventive maintenance, and root-cause analysis. I chose the system-wide approach because the problem was weak operational control, not only a lack of people.

## A — Action｜行動

**中文：**
我建立集中監控、容量管理和 severity-based alerts，改善 incident/problem escalation，並推動 DR/BCP、backup/restore、RCA 和 preventive actions。

**English：**
I established centralized monitoring, capacity management, and severity-based alerts. I improved incident and problem escalation and drove disaster recovery, backup and restore, root-cause analysis, and preventive actions.

## R / L — Result and Learning｜結果與學習

**中文：**
年度中斷由 4,998 小時降到 952 小時，改善 81%。我學到，每次故障都必須轉化成監控、流程或架構改善。

**English：**
Annual interruption fell from 4,998 hours to 952 hours, an 81 percent improvement. I learned that every major failure should become an improvement in monitoring, process, or architecture.

---

# 5. How do you find root cause and use data?

### 你如何找出根本原因並用數據解決問題？

**Primary Leadership Principles：Dive Deep · Are Right, A Lot**

## S — Situation｜情境

**中文：**
在 AXIOM，五個站點的事件偵測與恢復需要改善。MTTD 是 15 分鐘，MTTR 是 30 分鐘。

**English：**
At AXIOM, operations across five sites needed faster detection and recovery. Mean Time to Detect, or MTTD, was 15 minutes and Mean Time to Restore, or MTTR, was 30 minutes.

## T — Task｜任務

**中文：**
我需要找出延遲原因，並用可量測方式改善，而不是只增加人力。

**English：**
I needed to find the causes of the delays and improve them with measurable methods, rather than simply adding people.

## A — Action｜行動

**中文：**
我整合 Prometheus、Grafana、ELK 和 PagerDuty，建立 SLO、Error Budget 和 runbooks，並用 logs、metrics 和 change records 建立 incident timeline。

**English：**
I integrated Prometheus, Grafana, ELK, and PagerDuty. I defined Service Level Objectives, Error Budgets, and runbooks, and built incident timelines from logs, metrics, and change records. I also verified corrective actions in post-incident reviews.

## R / L — Result and Learning｜結果與學習

**中文：**
MTTD 由 15 分鐘降到 2 分鐘，MTTR 由 30 分鐘降到 8 分鐘。我的學習是，數據必須直接連結到 alert、決策、責任人和下一個改善動作。

**English：**
MTTD decreased from 15 minutes to 2 minutes, and MTTR decreased from 30 minutes to 8 minutes. I learned that data must connect directly to alerts, decisions, owners, and the next improvement action.

---

# 6. Tell me about an automation project that improved efficiency.

### 請分享一個改善效率的自動化專案。

**Primary Leadership Principles：Invent and Simplify · Frugality**

## S — Situation｜情境

**中文：**
在 Unition，環境佈建需要三天，網路變更也容易受到人工操作與審核差異影響。

**English：**
At Unition, environment provisioning took about three days. Network changes were also exposed to manual work and inconsistent reviews.

## T — Task｜任務

**中文：**
我要加速流程，同時保留審核、最小權限、稽核紀錄和 rollback。

**English：**
My goal was to make the process faster while keeping review, least privilege, audit trails, and rollback.

## O / D — Options and Decision｜選項與決策

**中文：**
我們可以維持手動、購買大型平台，或使用 Git、templates 和 Ansible。我選擇 Git 加 Ansible，因為它可版本控制、重複執行且容易追蹤。

**English：**
We could keep the manual process, buy a large platform, or use Git, templates, and Ansible. I chose Git and Ansible because they provided version control, repeatable execution, and a clear history.

## A — Action｜行動

**中文：**
我設計 templates、peer review、approval workflow、controlled runners、pre-check、post-check 和 rollback，先從約 30 台 network devices 開始。

**English：**
I designed templates, peer review, an approval workflow, controlled runners, pre-checks, post-checks, and rollback. I started with approximately 30 network devices, validated the process, and then expanded it.

## R / L — Result and Learning｜結果與學習

**中文：**
佈建由三天縮短到五分鐘，MTTR 由 45 分鐘降到 12 分鐘，TCO 降低 35%，每年節省超過 30,000 美元。我學到，自動化要把正確控制直接放進流程。

**English：**
Provisioning decreased from three days to five minutes, MTTR decreased from 45 minutes to 12 minutes, TCO decreased by 35 percent, and we saved more than 30,000 US dollars annually. I learned that good automation builds the right controls directly into the workflow.

---

# 7. How do you manage a 24x7 operations team?

### 你如何管理 24×7 營運團隊？

**Primary Leadership Principles：Hire and Develop the Best · Earth’s Best Employer**

## S — Situation｜情境

**中文：**
我管理過 24×7 cloud CDN、IDC、Service Desk 和 infrastructure operations，團隊從 9、12、15、20 人到跨國最多 60 人。

**English：**
I have managed 24x7 cloud CDN, IDC, Service Desk, and infrastructure operations. My teams ranged from 9 to 20 people, and I also managed up to 60 people across countries.

## T — Task｜任務

**中文：**
我的責任是維持服務穩定，同時讓輪班、on-call、交接、升級和人員發展可以長期運作。

**English：**
My responsibility was to keep services stable while making shift coverage, on-call rotations, handoffs, escalation, and development sustainable.

## A — Action｜行動

**中文：**
我使用 skill matrix、cross-training、severity 定義、runbooks、handoff 標準和 one-on-ones。事件中分開 incident command、technical recovery、validation 和 communication，並透過 coaching、SOP 和 succession planning 建立團隊深度。

**English：**
I use skill matrices, cross-training, severity definitions, runbooks, handoff standards, and one-on-ones. During incidents, I separate incident command, technical recovery, validation, and communication. I also use coaching, SOPs, and succession planning to build team depth.

## R / L — Result and Learning｜結果與學習

**中文：**
在 Mlytics，文件覆蓋率由 20% 提升到 90%，新人準備時間由六個月降到一個月，內部晉升超過 60%，兩位成員六個月內取得 AWS 認證。

**English：**
At Mlytics, documentation coverage increased from 20 percent to 90 percent, new-hire readiness decreased from six months to one month, internal promotion exceeded 60 percent, and two team members earned AWS certifications within six months. I learned that stable 24x7 operations require investment in both process and people.

---

# 8. Tell me about a time you developed or coached your team.

### 請分享一次培養或教練團隊的經驗。

**Primary Leadership Principles：Hire and Develop the Best · Earn Trust**

## S — Situation｜情境

**中文：**
在 Mlytics，我管理 15 人 SOC 和 cloud CDN team。文件覆蓋率只有 20%，新人需要六個月才能獨立工作。

**English：**
At Mlytics, I managed a 15-person SOC and cloud CDN team. Documentation coverage was only 20 percent, and new hires needed six months to work independently.

## T — Task｜任務

**中文：**
我需要建立可重複的訓練與 coaching，並為未來 team leads 和 specialists 建立成長路徑。

**English：**
I needed to create repeatable training and coaching and build a growth path for future team leads and specialists.

## A — Action｜行動

**中文：**
我重新設計 role levels、training、knowledge base 和 succession plan，把常見事件寫成 SOP，安排 shadowing、實作演練、one-on-one 和 feedback，也鼓勵成員負責 AWS 學習與改善專案。

**English：**
I redesigned role levels, training, the knowledge base, and succession planning. I converted common incidents into SOPs and used shadowing, practical exercises, one-on-ones, and regular feedback. I encouraged people to own AWS learning and improvement projects.

## R / L — Result and Learning｜結果與學習

**中文：**
文件覆蓋率達 90%，新人準備時間降到一個月，內部晉升超過 60%，兩位成員六個月內取得 AWS 認證。我學到，coaching 最有效時，學習會連結到真實責任和可量測成果。

**English：**
Documentation coverage reached 90 percent, new-hire readiness decreased to one month, internal promotion exceeded 60 percent, and two team members earned AWS certifications within six months. I learned that coaching is most effective when learning is connected to real responsibility and measurable results.

---

# 9. Tell me about a decision you made with incomplete information.

### 請分享一次資訊不完整時做決策的經驗。

**Primary Leadership Principles：Bias for Action · Are Right, A Lot**

## S — Situation｜情境

**中文：**
在 AXIOM，五個站點的 firewall change 約需 1.5 小時，人工操作也造成 configuration error 風險。

**English：**
At AXIOM, a firewall change across five sites took about 1.5 hours, and manual work created configuration-error risk.

## T — Task｜任務

**中文：**
我需要決定是否自動化，但不能直接讓五個 production sites 承擔未知風險。

**English：**
I needed to decide whether to automate without exposing five production sites to unknown risk.

## O / D — Options and Decision｜選項與決策

**中文：**
選項是維持手動、一次全面自動化，或先做小範圍 pilot。我選擇 pilot，先驗證 templates、OIDC、private runner、testing 和 rollback。

**English：**
The options were to keep the manual process, automate everything at once, or run a small pilot. I chose the pilot to validate templates, OIDC, a private runner, testing, and rollback.

## A — Action｜行動

**中文：**
我把流程放進 Jenkins 和 GitLab CI/CD，加入 approval、pre-check、post-check、audit trail 和 rollback，每次只擴大一個受控範圍。

**English：**
I placed the workflow in Jenkins and GitLab CI/CD with approval, pre-checks, post-checks, audit trails, and rollback. We expanded only one controlled scope at a time and measured failure and error rates.

## R / L — Result and Learning｜結果與學習

**中文：**
變更時間由 1.5 小時縮短到 8 分鐘，configuration error rate 降低 75%，deployment failure rate 低於 1%。我學到，資訊不完整時，決策要可逆、範圍要可控、結果要可量測。

**English：**
Change time decreased from 1.5 hours to 8 minutes, configuration error rate decreased by 75 percent, and deployment failure rate stayed below 1 percent. I learned that with incomplete information, the decision should be reversible, the scope controlled, and the result measurable.

---

# 10. How do you prioritize when many tasks are urgent?

### 當許多工作同時緊急時，你如何排優先順序？

**Primary Leadership Principles：Customer Obsession · Ownership · Deliver Results**

## Answer — 回答

**中文：**
我不只按照 FIFO 排 ticket。我會看 safety、service impact、severity、customer impact、SLA risk、dependencies、recovery options 和 available resources。P1、安全問題或可能造成大範圍中斷的硬體風險優先，接著是重大服務降級與 SLA 風險，正常 request 放入 backlog。我保留部分 capacity 給突發事件，指定 owner、下一次更新時間和 escalation path，並在影響改變時重新排序。

**English：**
I do not prioritize only by first in, first out. I look at safety, service impact, severity, customer impact, SLA risk, dependencies, recovery options, and available resources. A P1 incident, a safety issue, or a hardware risk that could cause a broad outage comes first. Next are major service degradation and SLA risk. Normal requests go into a clear backlog. I reserve part of the team’s capacity for unexpected incidents, assign an owner and next update time, and re-prioritize when the impact changes. My goal is to reduce the highest operational risk first, not simply close the most tickets.

---

# 11. Tell me about a time you balanced quality and delivery speed.

### 請分享一次你在品質與交付速度之間做取捨的經驗。

**Primary Leadership Principles：Highest Standards · Disagree and Commit**

## S — Situation｜情境

**中文：**
在 Unition，我們要加快多環境佈建與變更，但直接放寬 controls 會增加權限、稽核、configuration drift 和 rollback 風險。

**English：**
At Unition, we needed faster provisioning and changes across environments. Relaxing controls could increase privilege, audit, configuration-drift, and rollback risks.

## T — Task｜任務

**中文：**
我的任務是找出不能妥協的品質標準，同時讓低風險、重複性工作更快交付。

**English：**
My task was to protect non-negotiable quality standards while delivering low-risk, repeatable work faster.

## O / D — Options and Decision｜選項與決策

**中文：**
我選擇自動化標準化變更，保留高風險變更的 review。Safety、security、approval、audit trail、testing 和 rollback 不能妥協，非必要手動步驟則簡化。

**English：**
I chose to automate standardized changes while keeping review for high-risk changes. Safety, security, approval, audit trails, testing, and rollback could not be compromised. Unnecessary manual steps could be simplified.

## A — Action｜行動

**中文：**
我使用 Git、templates、Ansible、controlled runners、least privilege 和 deployment validation，並透過 pilot、分階段 rollout、success criteria 和 rollback plan 控制 blast radius。

**English：**
I used Git, templates, Ansible, controlled runners, least privilege, and deployment validation. We controlled the blast radius with a pilot and phased rollout, clear success criteria, and rollback plans.

## R / L — Result and Learning｜結果與學習

**中文：**
佈建由三天降到五分鐘，MTTR 由 45 分鐘降到 12 分鐘。我學到，品質與速度不一定衝突，好的 operating mechanism 可以同時提升兩者。

**English：**
Provisioning decreased from three days to five minutes, and MTTR decreased from 45 minutes to 12 minutes. I learned that quality and speed are not always opposites. A strong operating mechanism can improve both.

---

# 12. Tell me about a time you reduced cost without reducing reliability.

### 請分享一次降低成本但沒有犧牲可靠性的經驗。

**Primary Leadership Principles：Frugality · Ownership · Deliver Results**

## S — Situation｜情境

**中文：**
我曾管理每年 300 到 500 萬美元的 IT budget，也在 Unition 管理 150 萬美元預算。團隊需要控制超支，同時維持 99.95% 以上可用性。

**English：**
I have managed annual IT budgets of three to five million US dollars and a 1.5-million-dollar budget at Unition. We needed to control overrun while maintaining availability above 99.95 percent.

## T — Task｜任務

**中文：**
我需要找出真正的成本驅動因素，不能為了省錢刪除 backup、monitoring 或 DR controls。

**English：**
I needed to identify the real cost drivers. We could not reduce cost by removing backup, monitoring, or disaster-recovery controls.

## A — Action｜行動

**中文：**
我建立 vendor governance、FinOps 和 cost tracking，檢查使用量、合約、供應商績效、容量和重複工作，並優先改善 provisioning、網路變更和監控流程。

**English：**
I introduced vendor governance, FinOps, and cost tracking. I reviewed usage, contracts, vendor performance, capacity, and repeated manual work. I improved provisioning, network changes, and monitoring instead of removing reliability controls.

## R / L — Result and Learning｜結果與學習

**中文：**
預算超支由 15% 以上降到 3%，TCO 降低 35%，每年節省超過 30,000 美元，同時維持 99.95% 以上可用性。我學到，Frugality 是把資源放到真正降低客戶風險的地方。

**English：**
Budget overrun decreased from more than 15 percent to 3 percent, TCO decreased by 35 percent, and we saved more than 30,000 US dollars annually while maintaining availability above 99.95 percent. I learned that Frugality means putting resources where they reduce the greatest customer risk.

---

# 13. Tell me about a failure or a lesson you learned.

### 請分享一次失敗，或你從中學到的經驗。

**Primary Leadership Principles：Learn and Be Curious · Highest Standards**

## S — Situation｜情境

**中文：**
在早期跨國 IT 專案中，我低估了跨地點相依性與供應商 lead time，造成專案時程需要重新調整。這不是 production outage，但影響了交付信心。

**English：**
Earlier in my cross-country IT project experience, I underestimated dependencies between locations and a vendor’s lead time. The schedule had to be re-planned. It was not a production outage, but it affected delivery confidence.

## T — Task｜任務

**中文：**
我需要承擔責任、透明溝通影響，並建立機制避免同樣的 planning gap 再發生。

**English：**
I needed to take responsibility, communicate the impact transparently, and prevent the same planning gap from happening again.

## A — Action｜行動

**中文：**
我重新拆分 dependency、supplier lead time、testing、commissioning 和 handover milestones，加入 risk register、contingency、design review、vendor review 和 escalation checkpoint，並納入後續 reusable deployment standards。

**English：**
I broke the plan into dependency, supplier lead-time, testing, commissioning, and handover milestones. I added a risk register, contingency, earlier design reviews, vendor reviews, and escalation checkpoints. I also added these checks to later reusable deployment standards.

## R / L — Result and Learning｜結果與學習

**中文：**
後續的 factory IT、data center 和跨國部署專案都能更早暴露風險、改善 handover 品質。我學到，好的領導不是假裝每次預估都正確，而是快速承認偏差、透明溝通，並把教訓轉成 operating mechanism。

**English：**
Later factory IT, data center, and cross-country deployment projects exposed risks earlier and had stronger handovers. I learned that good leadership is not pretending every estimate is correct. It is acknowledging a gap quickly, communicating transparently, and turning the lesson into a better operating mechanism.

---

# Interview follow-up reminders

## How to use these answers

**中文：**
面試時先講結論，再用 STAR-L 展開。回答個人貢獻時使用 I identified、I decided、I implemented、I led。若被問到機密資料，可以使用範圍、比例、服務等級與決策原則，不必揭露客戶名稱或敏感架構細節。

**English：**
Start with the conclusion, then use STAR-L. Make your contribution clear with phrases such as I identified, I decided, I implemented, and I led. If an interviewer asks for confidential details, use ranges, percentages, service levels, and decision principles instead of customer names or sensitive architecture details.

