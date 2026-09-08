以下我把整份統一成完整的 **STAR 中英逐段對照 + 英文跟讀格式**。你可以直接從第 1 題一路練到第 10 題。

# Amazon Data Center Operations Manager 面試回答

## TOEIC 約 600 分｜STAR 逐段中英對照｜英文跟讀版

> `/` = 短停頓約 0.3～0.5 秒
> **粗體** = 面試時建議稍微加重語氣
> 建議語速：每分鐘約 100～120 字

---

# 1. Tell me about a time you took ownership of a serious problem.

### 請分享一次你主動承擔重大問題的經驗。

**Leadership Principles：Ownership / Bias for Action / Deliver Results**

## S — Situation｜情境

**中文：**
我曾經負責一個需要 24 小時運作的 IT 環境。有一次，系統發生嚴重異常，影響多個服務，約有 30% 的內部使用者無法正常使用系統。雖然問題不完全屬於我的團隊，但我認為恢復服務、保護系統可用性，以及安全地處理 Incident 是最重要的事情。

**English｜跟讀版：**

I was responsible for an IT environment /
that needed to run **24 hours a day**.

One time, /
we had a serious system problem.

Several services were affected, /
and about **30% of internal users** /
could not use the system normally.

The problem was not fully owned by my team, /
but I believed **restoring the service** /
was the first priority.

I also wanted to protect availability /
and manage the incident safely.

---

## T — Task｜任務

**中文：**
我的任務是快速確認影響範圍、協調相關團隊，並在風險可控的情況下恢復服務。同時，我也需要確保所有決策、處理步驟和溝通內容都有清楚紀錄，方便後續進行 RCA 和流程改善。

**English｜跟讀版：**

My task was to understand the impact quickly /
and coordinate the right teams.

I needed to restore the service /
with **controlled risk**.

I also needed to keep clear records /
of our decisions, actions, and communication.

These records were important /
for the later Root Cause Analysis /
and process improvement.

---

## A — Action｜行動

**中文：**
我主動建立 Incident Bridge，邀請 Network、System、Application 和 Vendor 團隊加入。我先確認影響範圍，再把調查工作分開，讓工程師平行檢查 Monitoring、Log、Network Traffic 和 Change Record。

當我們發現最近的一項 Change 可能是原因後，我沒有立刻要求 Rollback，而是先確認 Rollback Plan、資料保護和可能風險。確認安全之後才執行回復。

Incident 期間，我每 30 分鐘向管理層更新一次影響、處理進度、風險和下一步。服務恢復後，我帶領團隊完成 RCA，並改善 SOP、Monitoring Alert 和 Change Review。

**English｜跟讀版：**

I took ownership /
and created an **Incident Bridge**.

I invited the Network, System, Application, /
and Vendor teams.

First, /
I asked the teams to confirm /
the affected services, /
the number of users, /
and the start time.

Then, /
I divided the investigation /
into different areas.

Some engineers checked monitoring data. /
Some checked logs.

Others checked network traffic /
and recent change records.

When we found that a recent change /
could be the cause, /
I did not roll it back immediately.

First, /
I asked the team to confirm /
the **rollback plan**, /
data protection, /
and possible risks.

After we confirmed it was safe, /
we started the rollback.

During the incident, /
I gave management an update /
every **30 minutes**.

After the service was restored, /
I led the Root Cause Analysis.

We updated the SOP, /
monitoring alerts, /
and change review process.

---

## R — Result｜結果

**中文：**
我們在 45 分鐘內恢復主要服務，並在 24 小時內完成初步 RCA。後續三個月沒有再發生相同問題，相關 Change Failure Rate 下降約 30%。

這個經驗讓我學到，重大 Incident 發生時，Manager 必須主動承擔責任，在資訊不完整的情況下，也要快速做出安全而合理的決定。

**English｜跟讀版：**

We restored the main services /
within **45 minutes**.

We completed the first RCA /
within **24 hours**.

We did not see the same problem again /
for the next three months.

The related change failure rate /
also decreased by about **30%**.

This experience taught me /
that during a major incident, /
a manager should not just wait.

I need to **take ownership**, /
coordinate resources, /
and make a safe and reasonable decision.

---

# 2. Tell me about a time you had to dive deep into a technical problem.

### 請分享一次你深入技術細節解決問題的經驗。

**Leadership Principles：Dive Deep / Are Right, A Lot**

## S — Situation｜情境

**中文：**
我們曾經發現一個重要系統在尖峰時間偶爾變慢。問題每天大約發生兩到三次，每次持續 10 到 15 分鐘。CPU 和 Memory 使用率都正常，因此只看 Dashboard 找不到真正原因。

**English｜跟讀版：**

We found that an important system /
sometimes became slow /
during **peak hours**.

The problem happened /
about two or three times a day.

Each event lasted /
around **10 to 15 minutes**.

CPU and memory usage looked normal, /
so the dashboard did not show /
the real cause.

---

## T — Task｜任務

**中文：**
我的任務是帶領團隊找出真正的 Root Cause，而不是只增加 Server 資源或重新啟動服務。我也需要確認解決方案不會造成新的 Availability、Capacity 或 Operational Risk。

**English｜跟讀版：**

My task was to help the team /
find the **real root cause**.

I did not want the team /
to only add more server resources /
or restart the service.

I also needed to make sure /
our solution would not create /
new availability, capacity, /
or operational risks.

---

## A — Action｜行動

**中文：**
我先要求團隊整理問題發生的確切時間，再把 Application Log、Network Traffic、Database Connection 和 Monitoring Data 放在同一時間軸比較。

接著，我請工程師檢查 Connection Pool、Timeout Setting 和 Database Query。我們最後發現部分 Connection 在尖峰時段沒有正常釋放。

我要求先在測試環境重現問題，再調整 Connection Pool 和 Timeout Setting，同時增加 Connection Usage 和 Failed Request Alert。

**English｜跟讀版：**

First, /
I asked the team to record /
the exact time of every problem.

Then, /
we compared application logs, /
network traffic, /
database connections, /
and monitoring data /
on the same timeline.

I also asked the engineers /
to check the connection pool, /
timeout settings, /
and database queries.

After several checks, /
we found that some connections /
were not released correctly.

I asked the team /
to reproduce the problem /
in a test environment first.

After that, /
we changed the connection pool /
and timeout settings.

I also added new alerts /
for connection usage /
and failed requests.

---

## R — Result｜結果

**中文：**
調整後，系統在尖峰時間沒有再出現相同延遲。相關 Incident 從每週約 10 件下降到每週 1 件以下，平均 Response Time 改善約 40%。

**English｜跟讀版：**

After the change, /
the system did not have /
the same delay during peak hours.

Related incidents decreased /
from about **10 per week** /
to less than **one per week**.

Average response time /
also improved by about **40%**.

This experience taught me /
that a manager should understand /
the data and technical details /
deeply enough /
to ask the right questions.

---

# 3. Tell me about a process you improved or simplified.

### 請分享一次你改善或簡化流程的經驗。

**Leadership Principles：Invent and Simplify / Insist on the Highest Standards**

## S — Situation｜情境

**中文：**
在管理多個地點的 IT Infrastructure 時，我發現不同地點的 Network Device 設定不一致，而且很多變更都是工程師手動完成，因此容易產生 Human Error，也難以追蹤 Change History。

**English｜跟讀版：**

When I managed IT infrastructure /
in several locations, /
I found that network device settings /
were different between sites.

Many changes /
were also done manually.

This could cause **human errors**, /
and it was difficult to track /
who changed what and when.

---

## T — Task｜任務

**中文：**
我的任務是建立標準、可追蹤而且可以擴展的 Configuration Management 流程，同時提升 Change Quality、Security 和服務穩定性。

**English｜跟讀版：**

My task was to create /
a standard and traceable /
configuration management process.

The process also needed /
to support more devices /
in the future.

I wanted to improve /
change quality, /
security, /
and service stability.

---

## A — Action｜行動

**中文：**
我先盤點所有 Network Device，整理各地點設定差異。接著使用 Git 管理 Network Configuration、建立 Standard Template，並使用 Ansible 自動檢查設定。

我也重新設計 Change Process，工程師需要 Peer Review 和 Approval 才能執行變更，而且每次 Change 都必須保留 Version、Audit Record 和 Rollback Plan。

為降低風險，我先從 10 台設備做 Pilot，確認穩定後，再逐步擴大。

**English｜跟讀版：**

First, /
I reviewed all network devices.

Then, /
I proposed using **Git** /
to manage network configurations.

We created standard templates /
and used **Ansible** /
to check settings automatically.

I also changed /
the change management process.

Engineers needed /
a peer review and approval /
before making a change.

Every change had /
a version, /
an audit record, /
and a rollback plan.

To reduce risk, /
I started with a pilot /
on **10 devices**.

After the pilot was stable, /
we expanded the process /
step by step.

---

## R — Result｜結果

**中文：**
最後約 100 台 Network Device 納入這套流程。設定錯誤下降約 60%，Change Review 時間縮短約 40%，每一次變更都可以被追蹤和 Rollback。

**English｜跟讀版：**

In the end, /
we included about **100 network devices** /
in the new process.

Configuration errors decreased /
by about **60%**.

Change review time decreased /
by about **40%**.

Every change /
could also be tracked /
and rolled back.

This experience taught me /
that automation is not only /
about saving time.

It is also about /
reducing human error /
and building a process /
that is standard and scalable.

---

# 4. Tell me about a time you improved operational quality.

### 請分享一次你提升營運品質的經驗。

**Leadership Principles：Insist on the Highest Standards / Deliver Results**

## S — Situation｜情境

**中文：**
我以前管理 Infrastructure 和 IT Operations 時，發現工程師通常可以快速解決 Incident，但同類型問題會重複發生。當時團隊比較重視 Ticket Closure，卻沒有系統性追蹤 Repeated Incident 和 Root Cause。

**English｜跟讀版：**

When I managed Infrastructure /
and IT Operations, /
the engineers could usually /
solve incidents quickly.

However, /
the same types of problems /
happened again and again.

At that time, /
we focused more /
on closing tickets.

We did not have /
a clear process /
to track repeated incidents /
and root causes.

---

## T — Task｜任務

**中文：**
我的任務是讓團隊從單純處理 Incident，轉變成主動改善 Service Reliability，並建立可以量化的 Operational Quality 指標。

**English｜跟讀版：**

My task was to move the team /
from only fixing incidents /
to improving **service reliability**.

I also wanted to create /
clear and measurable /
operational quality metrics.

---

## A — Action｜行動

**中文：**
我建立每月 Operations Review，開始追蹤 Repeated Incident、MTTR、Change Failure、SLA 和 Availability。

我要求所有 Sev-1，以及重複出現的 Sev-2 Incident，都必須完成 RCA。每一項 Follow-up Action 都需要 Owner 和 Due Date。

改善措施可能包括增加 Monitoring、更新 SOP、Automation 或修改 System Architecture。

我每週追蹤改善進度，並在月會確認這些改善是否真的降低 Incident。

**English｜跟讀版：**

First, /
I created a monthly /
**Operations Review**.

We tracked /
repeated incidents, /
MTTR, /
change failures, /
SLA, /
and availability.

I required an RCA /
for every Sev-One incident /
and repeated Sev-Two incidents.

Every follow-up action /
needed a clear owner /
and a due date.

The actions could include /
better monitoring, /
updated SOPs, /
more automation, /
or changes to system design.

I checked the progress /
every week.

In the monthly review, /
we checked whether /
the actions really reduced /
the number of incidents.

---

## R — Result｜結果

**中文：**
經過持續改善，年度系統中斷時間降低約 81%，MTTR 下降約 35%，重複 Incident 下降約 50%。團隊也逐漸從「解決問題」轉變成「預防問題」。

**English｜跟讀版：**

After continuous improvement, /
annual system downtime decreased /
by about **81%**.

MTTR decreased /
by about **35%**.

Repeated incidents decreased /
by about **50%**.

The team changed /
from only **fixing problems** /
to **preventing problems**.

This experience taught me /
that high standards /
do not mean people /
can never make mistakes.

It means /
we should learn from mistakes /
and prevent the same problem /
from happening again.

---

# 5. Tell me about a time you developed someone on your team.

### 請分享一次你培養團隊成員的經驗。

**Leadership Principles：Hire and Develop the Best / Earn Trust**

## S — Situation｜情境

**中文：**
在我之前的一個團隊，新進工程師通常需要大約六個月才能獨立工作。主要原因是很多重要知識只存在資深工程師的經驗裡，文件和訓練流程不完整。

**English｜跟讀版：**

In one of my previous teams, /
new engineers usually needed /
about **six months** /
before they could work independently.

A lot of important knowledge /
was only in the experience /
of senior engineers.

Our documents /
and training process /
were not complete.

---

## T — Task｜任務

**中文：**
我的任務是縮短新人 Onboarding 時間，同時確保新人能夠安全而獨立地處理日常 Incident、基本 Change 和標準 Operations 工作。

**English｜跟讀版：**

My task was to reduce /
the onboarding time.

At the same time, /
I needed to make sure /
new engineers could safely /
handle daily incidents, /
basic changes, /
and standard operations /
by themselves.

---

## A — Action｜行動

**中文：**
我先建立 Skill Matrix，把不同職位需要的能力整理清楚。接著帶領團隊建立 SOP、Knowledge Base、System Architecture 文件和 Troubleshooting Guide。

我設計 30、60、90 天 Training Plan，也安排 Senior Engineer 擔任 Mentor。新人需要實際處理 Test Incident、Standard Change 和 Knowledge Sharing。

我每月與新人進行 One-on-One，了解學習問題，並根據 Skill Matrix 調整訓練。

**English｜跟讀版：**

First, /
I worked with the team /
to create a **skill matrix**.

We listed the skills /
needed for each role.

Then, /
we created SOPs, /
a knowledge base, /
system architecture documents, /
and troubleshooting guides.

I also created /
a **30, 60, and 90-day** /
training plan.

Senior engineers /
became mentors.

New engineers needed /
to practice real tasks, /
such as handling test incidents, /
performing standard changes, /
and sharing knowledge.

I also had /
a one-on-one meeting /
with each new engineer /
every month.

I used their feedback /
and the skill matrix /
to improve the training.

---

## R — Result｜結果

**中文：**
我們完成約 90% 的 SOP 和 Knowledge Base，把新人獨立工作的時間從六個月縮短到約一個月。後來有兩位團隊成員取得 AWS Certification，也有工程師成為新的 Mentor。

**English｜跟讀版：**

We completed /
about **90%** /
of the SOPs /
and knowledge base.

We reduced the time /
for new engineers /
to work independently /
from **six months** /
to about **one month**.

Later, /
two team members received /
AWS certifications.

Some engineers also became /
mentors for new employees.

This experience taught me /
that a good manager /
does not only manage today's work.

A good manager /
also builds the future capability /
of the team.

---

# 6. Tell me about a time you had to make a decision quickly.

### 請分享一次你必須快速做決定的經驗。

**Leadership Principles：Bias for Action / Ownership**

## S — Situation｜情境

**中文：**
在一次 24x7 Operations Incident 中，一個重要服務突然發生異常，約 40% 使用者受到影響。當時我們還沒有完整確認 Root Cause，但問題持續擴大，Availability 不斷下降。

**English｜跟讀版：**

During a 24x7 /
operations incident, /
an important service /
suddenly had a serious problem.

About **40% of users** /
were affected.

We did not know /
the full root cause yet.

However, /
the problem was getting worse, /
and service availability /
was continuing to decrease.

---

## T — Task｜任務

**中文：**
我的任務是在資訊不完整的情況下，找到一個能快速恢復服務、風險可控，而且可以 Rollback 的方案，同時避免 Data Loss 或更大的 Production Impact。

**English｜跟讀版：**

My task was to make a decision /
with limited information.

I needed a solution /
that could restore the service quickly, /
control the risk, /
and be rolled back if needed.

I also needed to avoid /
data loss /
and a larger production impact.

---

## A — Action｜行動

**中文：**
我先確認三件事情：影響範圍、問題是否繼續擴大，以及有哪些安全的 Recovery Option。

團隊發現近期一項 Change 可能有關，而且我們已經有測試過的 Rollback Plan。

我要求工程師先確認 Backup、Rollback Command、Data Status 和 Owner，確認後才批准 Rollback。同時讓另一組工程師繼續調查 Root Cause。

我要求每 15 分鐘更新 Error Rate、Availability 和服務狀態。

**English｜跟讀版：**

First, /
I checked three things.

How big was the impact?

Was the problem /
still getting worse?

And what safe recovery options /
did we have?

The team found /
that a recent change /
could be related to the problem.

We also had /
a tested rollback plan.

I asked the engineers /
to confirm the backup, /
rollback commands, /
data status, /
and owners.

After that, /
I approved the rollback.

At the same time, /
another group continued /
the root cause investigation.

I asked for an update /
every **15 minutes** /
on error rate, /
availability, /
and service status.

---

## R — Result｜結果

**中文：**
我們在 25 分鐘內恢復服務，沒有 Data Loss，也沒有產生新的重大問題。後續 RCA 確認該 Change 是主要原因，因此我們進一步更新 Change Validation Checklist。

**English｜跟讀版：**

We restored the service /
within **25 minutes**.

There was **no data loss** /
and no new major problem.

The RCA later confirmed /
that the recent change /
was the main cause.

We also updated /
the change validation checklist.

This experience taught me /
that **Bias for Action** /
does not mean /
making a decision without thinking.

It means /
understanding the risk /
and taking quick action /
with a safe /
and reversible solution.

---

# 7. Tell me about a time you disagreed with your manager or another team.

### 請分享一次你和主管或其他團隊意見不同的經驗。

**Leadership Principles：Have Backbone; Disagree and Commit / Earn Trust**

## S — Situation｜情境

**中文：**
有一次管理層希望在週末快速執行一項 Production Infrastructure Change。但我認為一次部署到所有 Production Environment 風險過高，因為測試時間不足，而且可能影響約 20 個服務。

**English｜跟讀版：**

One time, /
management wanted to complete /
a Production infrastructure change /
quickly during the weekend.

However, /
I believed deploying the change /
to all Production environments /
at the same time /
was too risky.

The test time was not enough, /
and the change could affect /
about **20 services**.

---

## T — Task｜任務

**中文：**
我的任務不是單純反對，而是清楚說明 Risk，並提出一個既能完成 Business Goal、又能降低 Production Risk 的替代方案。

**English｜跟讀版：**

My task was not /
to simply say no.

I needed to explain /
the risk clearly /
and provide another solution.

The new solution needed /
to support the business goal /
and also reduce /
the Production risk.

---

## A — Action｜行動

**中文：**
我整理 Business Impact、Rollback Risk、Monitoring Data 和 Test Result，並向管理層提出 Canary Deployment。

我建議先部署到 10% 的環境，觀察 30 分鐘。如果 Error Rate、Latency 和 Availability 都正常，再逐步增加部署比例。

同時，我準備 Rollback Plan、Monitoring Dashboard 和明確的 Stop Criteria。

**English｜跟讀版：**

I prepared information /
about the business impact, /
rollback risk, /
monitoring data, /
and test results.

Then, /
I proposed a **canary deployment**.

I suggested deploying /
to only **10%** /
of the environment first.

We would watch it /
for **30 minutes**.

If the error rate, /
latency, /
and availability /
were normal, /
we could continue.

I also prepared /
a rollback plan, /
a monitoring dashboard, /
and clear stop criteria.

Management agreed /
to use this approach.

---

## R — Result｜結果

**中文：**
變更最後順利完成，沒有 Production Outage，也沒有重大 Incident。雖然比原計畫多花約兩小時，但大幅降低部署風險。

我也認為如果最後公司做出不同決定，只要沒有安全或法規問題，我仍然會完全支持最後決定，這就是 Disagree and Commit。

**English｜跟讀版：**

The change was completed /
successfully.

There was /
**no Production outage** /
and no major incident.

The process took /
about two more hours /
than the original plan.

However, /
it greatly reduced /
the deployment risk.

For me, /
**Disagree and Commit** means /
I should speak up /
before the decision.

But after the final decision, /
I will fully support it /
and help the team /
deliver the result.

---

# 8. Tell me about a failure or mistake and what you learned from it.

### 請分享一次失敗或犯錯的經驗，以及你學到了什麼。

**Leadership Principles：Learn and Be Curious / Earn Trust / Ownership**

## S — Situation｜情境

**中文：**
我曾經負責一個 Infrastructure Project，原本預計八週完成。技術方案已經準備好，但到第四週才發現 Application、Network 和 Security Team 還有多個重要 Dependency 尚未完成。

**English｜跟讀版：**

I was responsible /
for an infrastructure project /
that was planned /
to finish in **eight weeks**.

The technical solution /
was ready.

However, /
in week four, /
I found that the Application, /
Network, /
and Security teams /
still had several important dependencies.

---

## T — Task｜任務

**中文：**
我的任務是重新評估 Project Schedule、降低 Delay Impact，同時找出我在 Planning 上做錯的地方，而且不能為了趕進度而省略 Security、Network 或 Operational Review。

**English｜跟讀版：**

My task was /
to review the project schedule /
and reduce the delay.

I also needed /
to understand /
what was wrong /
with my project planning.

At the same time, /
I did not want to skip /
important Security, /
Network, /
or Operational Reviews.

---

## A — Action｜行動

**中文：**
我先承認自己低估了 Cross-Team Dependency，而沒有責怪其他團隊。

我重新召集所有 Owner，建立 Dependency List、Risk List、Owner 和新的 Milestone。

接著把專案拆成較小階段，先執行不依賴其他團隊的部分，並建立每週一次 Cross-Team Review。

從那之後，我也把 Security Review、Change Approval、Operational Readiness 和 Dependency Review 納入專案初期規劃。

**English｜跟讀版：**

First, /
I accepted that /
I had underestimated /
the cross-team dependencies.

I did not blame /
the other teams.

Instead, /
I brought all the owners /
together again.

We created /
a dependency list, /
a risk list, /
clear owners, /
and new milestones.

I also divided the project /
into smaller phases.

We completed the work /
that did not depend /
on other teams first.

Then, /
I created a weekly /
cross-team review.

For future projects, /
I also added /
Security Review, /
Change Approval, /
Operational Readiness, /
and Dependency Review /
to the early planning stage.

---

## R — Result｜結果

**中文：**
專案最後比原定計畫晚兩週完成，但所有必要的 Security 和 Network Review 都有完成，也沒有再出現重大 Blocking Issue。

後來我把這套 Planning Template 應用到其他大型專案，Cross-Team Delay 約下降 40%。

**English｜跟讀版：**

The project finished /
**two weeks later** /
than the original plan.

However, /
we completed all required /
Security and Network reviews.

We also did not have /
any more major blockers.

Later, /
I used the new planning template /
for other large projects.

Cross-team delays decreased /
by about **40%**.

This experience taught me /
that a good technical solution /
does not always mean /
a good project.

A manager also needs /
to manage communication, /
risk, /
and dependencies.

---

# 9. How do you manage a 24x7 operations team?

### 你如何管理一個 24x7 Operations Team？

**Leadership Principles：Ownership / Insist on the Highest Standards / Strive to be Earth’s Best Employer**

## S — Situation｜情境

**中文：**
在管理 24x7 Operations Team 時，我曾經遇過 Shift Handover 資訊不完整、Incident Escalation 標準不一致，以及少數工程師 On-Call 負擔過重的問題。

這不只會影響 Incident Response，也容易造成 Engineer Burnout。

**English｜跟讀版：**

When I managed /
a **24x7 operations team**, /
we had several problems.

Some shift handovers /
were not complete.

Escalation decisions /
were not always consistent.

And some engineers /
had too much on-call work.

These problems /
could delay incident response /
and also cause /
engineer burnout.

---

## T — Task｜任務

**中文：**
我的任務是建立清楚的 Ownership、Handover 和 Escalation Process，同時維持 Service Quality、快速 Incident Response 和合理的團隊工作負荷。

**English｜跟讀版：**

My task was to create /
clear ownership, /
handover, /
and escalation processes.

At the same time, /
I needed to maintain /
service quality, /
fast incident response, /
and a reasonable workload /
for the team.

---

## A — Action｜行動

**中文：**
我先定義 Sev-1、Sev-2 和 Sev-3 標準，為每個等級設定 Response Time、Escalation Owner 和 Communication Rule。

接著建立 Shift Handover Template，要求記錄 Incident、Change、Risk、Pending Ticket 和 Next Action。Sev-1 Incident 則必須進行口頭交接。

我也持續追蹤 Ticket Backlog、MTTR、SLA、Availability、Repeated Incident 和 On-Call Hours。

在排班方面，我確保每位工程師都有 Backup，也定期檢查 Workload、休息和 Training Need。

**English｜跟讀版：**

First, /
I defined the standards /
for Sev-One, /
Sev-Two, /
and Sev-Three.

For each level, /
I defined /
the response time, /
escalation owner, /
and communication rules.

Then, /
I created a **shift handover template**.

Each shift needed /
to record incidents, /
changes, /
risks, /
pending tickets, /
and next actions.

For a Sev-One incident, /
we also required /
a verbal handover.

I tracked /
ticket backlog, /
MTTR, /
SLA, /
availability, /
repeated incidents, /
and on-call hours.

When creating schedules, /
I made sure /
every engineer /
had backup support.

I also reviewed /
workload, /
rest time, /
and training needs.

---

## R — Result｜結果

**中文：**
交接遺漏造成的 Incident Delay 下降約 50%，MTTR 改善約 30%，SLA 達成率維持 99% 以上。

透過重新安排 On-Call 和 Backup，團隊加班時間也下降約 25%。

**English｜跟讀版：**

Incident delays /
caused by missing handover information /
decreased by about **50%**.

MTTR improved /
by about **30%**.

SLA performance stayed /
above **99%**.

After we improved /
the on-call schedule /
and backup support, /
team overtime decreased /
by about **25%**.

My goal /
is not to keep the team /
busy all the time.

My goal is /
to make operations /
**stable and predictable**.

---

# 10. Why do you want to join AWS Data Center Operations?

### 為什麼你想加入 AWS Data Center Operations？

**Leadership Principles：Customer Obsession / Ownership / Learn and Be Curious**

## S — Situation｜情境

**中文：**
我的職涯主要集中在 Infrastructure、Network、Cloud、Security 和 IT Operations。我管理過跨國團隊，也負責過需要 24x7 運作的 Mission-Critical Environment。

**English｜跟讀版：**

Most of my career /
has been in Infrastructure, /
Network, /
Cloud, /
Security, /
and IT Operations.

I have also managed /
international teams /
and mission-critical environments /
that needed to run /
**24 hours a day**.

---

## T — Task｜目標

**中文：**
現在我希望加入一個更大規模的 Infrastructure Operations 組織，把 Reliability、Incident Management、Automation 和 People Management 經驗應用在更高標準的環境。

**English｜跟讀版：**

Now, /
I want to join /
a larger infrastructure /
operations organization.

I want to use /
my experience in reliability, /
incident management, /
automation, /
and people management /
in an environment /
with very high standards.

---

## A — Action｜為什麼是 AWS

**中文：**
我研究 AWS Data Center Operations 後，了解到這個角色不只是管理設備。

它也很重視 Safety、Standard Process、Operational Excellence、Incident Response、Availability 和 Team Development。

這些和我過去的經驗非常相關。我曾經改善 Operations Process、建立 Automation、降低 Downtime，也培養工程師處理複雜問題。

另外，我希望了解 AWS 如何在全球規模管理 Data Center、建立一致標準，並把 Operations Quality 轉化成 Customer Experience。

**English｜跟讀版：**

I studied /
AWS Data Center Operations.

I understand that /
this role is not only /
about managing equipment.

It also focuses on /
safety, /
standard processes, /
operational excellence, /
incident response, /
availability, /
and team development.

These areas are closely related /
to my previous experience.

I have improved /
operations processes, /
built automation, /
reduced downtime, /
and developed engineers /
to handle complex problems.

At the same time, /
I want to learn /
how AWS manages data centers /
at a global scale.

I also want to learn /
how AWS builds standards /
and improves /
the customer experience.

---

## R — Result｜我希望帶來的價值

**中文：**
我希望能為 AWS 帶來更穩定的 Operations、更快的 Incident Response、更強的 Team Capability，以及持續改善的 Operational Standards。

我不是單純在找更高的 Job Title。我希望加入一個可以讓我運用過去經驗，同時繼續學習大型 Infrastructure Operations 的團隊。

**English｜跟讀版：**

I hope I can bring /
more stable operations, /
faster incident response, /
stronger team capability, /
and higher operational standards /
to AWS.

I am not only looking /
for a higher job title.

I want to join a team /
where I can use /
my previous experience /
and continue learning /
about large-scale /
infrastructure operations.

Most importantly, /
I want to help AWS /
provide **safe, reliable, /
and highly available services** /
to customers.

---

# 面試跟讀練習方式

### 第一階段：慢速跟讀

先按照 `/` 停頓。

例如：

I took ownership /
and created an Incident Bridge.

不要急著講快。先確保每個字都說清楚。

### 第二階段：拿掉部分停頓

熟悉之後變成：

I took ownership and created an Incident Bridge.

讓句子逐漸變自然。

### 第三階段：只看中文回答英文

看到：

「我先確認三件事情：影響範圍、問題是否持續擴大，以及安全的 Recovery Option。」

嘗試自己說：

First, I checked three things. /
How big was the impact? /
Was the problem getting worse? /
And what safe recovery options did we have?

### 第四階段：記 STAR，不背全文

真正 Amazon 面試時，不建議逐字背答案。

你只需要記：

**S：發生什麼事情？**
**T：我要解決什麼？**
**A：我本人做了什麼？**
**R：數據結果是多少？**

尤其 Action 要多使用：

**I found...**
**I decided...**
**I asked...**
**I created...**
**I changed...**
**I reviewed...**
**I learned...**

而不是一直說：

**We did...**

因為 Amazon 面試官非常在意：

**What did YOU do?**

---

# 最重要的數字記憶表

面試前至少記住這些數據：

| 題目                  | 關鍵數字                                                             |
| ------------------- | ---------------------------------------------------------------- |
| Ownership Incident  | 30% users / 45 minutes / 24-hour RCA / 30% improvement           |
| Dive Deep           | 2–3 times/day / 10–15 minutes / incidents 10 → less than 1 / 40% |
| Automation          | 100 devices / errors -60% / review time -40%                     |
| Operational Quality | downtime -81% / MTTR -35% / repeated incidents -50%              |
| Develop People      | onboarding 6 months → 1 month / SOP 90% / 2 AWS certifications   |
| Bias for Action     | 40% users / recovery in 25 minutes / no data loss                |
| Disagree & Commit   | 20 services / 10% canary / 30-minute observation                 |
| Failure             | 8-week project / 2-week delay / later delays -40%                |
| 24x7 Team           | handover delay -50% / MTTR -30% / SLA 99%+ / overtime -25%       |

**注意：面試前請把其中不是你真實紀錄的數字換掉。Amazon 很可能針對數字深入追問，所以只使用你能解釋來源與計算方式的數據。**

這一版已經全部統一成你要的跟讀方式。你實際準備時，我會建議先攻 **1、4、5、6、7、8**，因為這六個故事可以交叉覆蓋 Amazon 很多 Leadership Principles，不需要硬背 16 套不同故事。
