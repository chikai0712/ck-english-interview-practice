好，既然你選 **A**，我就把剛才建議的數據視為你已確認，直接整合進正式版本。下面這版會把 `〔請確認〕` 全部拿掉，並統一成可以直接練習的 Amazon DCOM Interview Workbook。

# Amazon Data Center Operations Manager Interview Workbook

## TOEIC 約 600 分｜STAR + Options/Decision + 中英對照跟讀版

> `/` = 短停頓約 0.3–0.5 秒
> **粗體** = 建議面試時稍微加重
> 建議主回答：約 2–3 分鐘
> 核心原則：**WHY → I → DATA → RESULT → LEARNING**

---

# 1. Tell me about a time you took ownership of a serious problem.

### 請分享一次你主動承擔重大問題的經驗。

**Primary LP：Ownership**
**Secondary LP：Bias for Action / Dive Deep / Deliver Results / Customer Obsession**

## S — Situation｜情境

**中文：**
我曾經負責一個需要 24x7 運作的 IT 環境。有一次發生重大系統異常，同時影響 3 到 5 個重要服務，大約 20% 到 30% 的使用者受到影響。

一開始，我們無法確認問題是在 Network、System 還是 Application，但服務影響持續擴大。

我的想法是，對使用者而言，他們不在意問題到底是哪一個 Team 負責，他們只在意服務什麼時候恢復。

**English｜跟讀版：**

I was responsible for /
a **24x7 IT environment**.

One time, /
we had a major system incident.

It affected /
about **three to five important services**, /
and around **20 to 30 percent of users** /
were impacted.

At the beginning, /
we did not know /
whether the problem came from Network, /
System, /
or Application.

But the service impact /
was getting worse.

From the user’s point of view, /
it did not matter /
which team owned the problem.

They needed the service /
to be restored.

---

## T — Task｜任務

**中文：**
我的責任是快速確認 Business Impact、建立 Incident Command、協調所有技術團隊，並在控制風險的情況下盡快恢復服務。

同時，我必須避免因為急著恢復服務，而造成 Data Loss、Security Risk 或更大的 Production Impact。

**English：**

My task was /
to understand the business impact quickly, /
create one incident command point, /
and coordinate all technical teams.

I needed to restore the service /
as quickly as possible, /
but with **controlled risk**.

I also needed to make sure /
our recovery action /
would not cause data loss, /
security risk, /
or a larger Production impact.

---

## O — Options / Trade-off｜選項與取捨

**中文：**
當時有三個選擇。

第一是繼續調查，直到完全確認 Root Cause。這個方式技術風險較低，但 Outage 可能持續更久。

第二是 Failover 到 Backup Environment，但必須先確認 Backup Status 和 Data Synchronization。

第三是 Rollback 最近的 Change。這個方案是可逆的，而且我們已經有測試過的 Rollback Plan。

**English：**

At that time, /
I had three main options.

The first option /
was to continue the investigation /
until we fully understood /
the root cause.

This had lower technical risk, /
but the outage could continue longer.

The second option /
was to fail over /
to the backup environment.

But we first needed /
to confirm the backup status /
and data synchronization.

The third option /
was to roll back /
the most recent change.

The rollback was **reversible**, /
and we already had /
a tested rollback plan.

---

## D — Decision｜決策

**中文：**
因為問題開始時間與最近一項 Change 高度相關，而且 Rollback 已經測試過，所以我決定先 Rollback。

原因很簡單：在當時的條件下，這是速度最快、風險較低，而且可以逆轉的方案。

**English：**

The data showed /
that the incident started /
soon after a recent change.

We also had /
a tested rollback plan.

So I decided /
to perform the rollback.

I chose this option /
because it was the fastest, /
lowest-risk, /
and most reversible solution.

---

## A — Action｜行動

**中文：**
我主動建立 Incident Bridge，召集 Network、System、Application 和 Vendor Team。

我先要求確認受影響服務、使用者、Business Impact、Security Risk 和 Data Risk。

接著把 Investigation 拆成不同 Workstream，讓不同 Engineer 同時檢查 Monitoring Data、Log、Network Traffic 和 Change Record。

Rollback 前，我再次確認 Backup、Rollback Command、Data Status、Owner 和 Validation Step。

Incident 期間，我固定向 Management 更新 Impact、Risk、Progress 和 Next Action。

服務恢復後，我帶領團隊完成初步 RCA，並在 3 到 5 個工作天內完成正式 RCA，同時更新 Monitoring Alert、SOP、Change Review 和 Corrective Action。

**English：**

I took ownership /
and created an **Incident Bridge**.

I invited the Network, /
System, /
Application, /
and Vendor teams.

First, /
I asked the teams to confirm /
the affected services, /
users, /
business impact, /
security risk, /
and data risk.

Then, /
I divided the investigation /
into different workstreams.

Different engineers checked /
monitoring data, /
logs, /
network traffic, /
and recent change records /
at the same time.

Before the rollback, /
I confirmed /
the backup, /
rollback commands, /
data status, /
owners, /
and validation steps.

During the incident, /
I gave regular updates /
to management.

After recovery, /
I led the initial RCA /
within 24 hours.

We completed /
the formal RCA /
within three to five business days.

---

## R — Result｜結果

**中文：**
我們在大約 45 到 60 分鐘內恢復主要服務，而且沒有發生 Data Loss。

初步 RCA 在 24 小時內完成，後續三個月沒有再發生相同類型問題。

**English：**

We restored /
the main services /
within about **45 to 60 minutes**.

There was **no data loss**.

We completed /
the initial RCA /
within **24 hours**.

For the next three months, /
we did not see /
the same type of incident again.

---

## L — Learning｜學習

**中文：**
我學到 Ownership 並不是所有事情都自己做，而是即使問題跨越多個 Team，我仍然要對 Final Service Result 負責。

如果再遇到類似 Incident，我會更早建立 Incident Commander、Timeline 和 Decision Log。

**English：**

I learned /
that Ownership does not mean /
doing everything by myself.

It means /
I am responsible /
for the final service result, /
even when the problem /
crosses several teams.

If I faced /
the same type of incident again, /
I would create /
the incident command, /
timeline, /
and decision log /
even earlier.

### Amazon 可能追問

* How did you know rollback was the right decision?
* What would you have done if rollback failed?
* How did you communicate with management?
* What did you personally do?
* How did you prevent recurrence?

---

# 2. Tell me about a time you had to dive deep into a technical problem.

### 請分享一次你深入技術問題的經驗。

**Primary LP：Dive Deep**
**Secondary：Are Right, A Lot / Highest Standards**

## S — Situation

**中文：**
我們有一個重要服務在 Peak Hours 會間歇性變慢，每天約發生 2 到 3 次，每次大約持續 10 到 15 分鐘。

但 CPU、Memory 和一般 Infrastructure Metrics 看起來都正常。

**English：**

We had /
an important service /
that sometimes became slow /
during peak hours.

The problem happened /
about **two or three times a day**.

Each event lasted /
about **10 to 15 minutes**.

CPU, /
memory, /
and normal infrastructure metrics /
all looked healthy.

---

## T — Task

**中文：**
我要找出真正 Root Cause，而不是簡單增加 Server Capacity 或 Restart Service。

**English：**

My task was /
to help the team find /
the **real root cause**.

I did not want /
to simply add more servers /
or restart the service.

---

## O / D — Options & Decision

**中文：**
我們可以增加 CPU / Memory、Restart Service，或深入分析 Application、Network 和 Database Dependency。

前兩個方法可能暫時改善，但無法證明 Root Cause。

所以我決定 Dive Deep。

**English：**

We could add /
more CPU and memory.

We could restart /
the service.

Or, /
we could analyze /
the Application, Network, /
and Database dependencies /
in more detail.

The first two options /
were faster, /
but they did not prove /
the root cause.

So I chose /
to **Dive Deep**.

---

## A — Action

**中文：**
我要求團隊建立統一 Timeline，把 Application Log、Network Traffic、Database Connection、Monitoring Data 放在一起比較。

再深入分析 Connection Pool、Timeout、Query 和 Traffic Pattern。

最後發現部分 Connection 在 Peak Traffic 沒有正常釋放。

我們先在 Test Environment 重現問題，再調整 Connection Pool 和 Timeout，並增加 Connection Usage 和 Failed Request Alert。

**English：**

First, /
I asked the team /
to build one timeline.

We compared /
application logs, /
network traffic, /
database connections, /
and monitoring data.

Then, /
we checked /
connection pools, /
timeout settings, /
database queries, /
and traffic patterns.

We found /
that some connections /
were not released correctly /
during peak traffic.

Before changing Production, /
we reproduced the problem /
in a test environment.

Then, /
we adjusted the settings /
and added new alerts.

---

## R — Result

**中文：**
改善前約每天會發生 2 到 3 次異常，後來降低到每週 1 次以下。

Average Response Time 約改善 30% 到 40%。

**English：**

Before the improvement, /
the issue happened /
about two or three times /
every day.

After the change, /
it dropped /
to less than **one incident per week**.

Average response time /
also improved /
by about **30 to 40 percent**.

---

## L — Learning

**中文：**
Manager 不需要自己完成所有 Troubleshooting，但一定要能深入到足以挑戰假設、理解數據，並確認團隊真的找到 Root Cause。

**English：**

A manager does not need /
to do all technical work.

But I need /
to understand the technical details /
deeply enough /
to challenge assumptions, /
understand the data, /
and confirm the real root cause.

---

# 3. Tell me about a process you improved or simplified.

### 請分享一次你改善或簡化流程的經驗。

**Primary LP：Invent and Simplify**
**Secondary：Highest Standards / Frugality / Ownership**

## S

**中文：**
我管理多地 Infrastructure 時，發現 Network Device Configuration 不一致，而且很多 Change 是 Engineer 手動直接登入設備完成。

**English：**

When I managed /
IT infrastructure /
across several locations, /
I found that network configurations /
were not standardized.

Many engineers /
made changes manually /
by logging directly /
into network devices.

---

## T

**中文：**
我要建立標準化、可追蹤、可稽核、可以 Rollback，而且能 Scale 的 Configuration Management。

**English：**

My task was /
to create a process /
that was standardized, /
traceable, /
auditable, /
reversible, /
and scalable.

---

## O / D

**中文：**
選項包括購買 Commercial Platform、繼續人工操作，或利用 Git + Ansible。

考量 Cost、既有 Skill 和導入速度，我決定採用 Git + Ansible。

**English：**

We could buy /
a commercial management platform.

We could continue /
with manual operations.

Or, /
we could use /
our existing Git /
and Ansible skills.

I selected /
Git and Ansible /
because it was lower cost, /
faster to implement, /
and easier for the team /
to maintain.

---

## A

**中文：**
我先完成 Device Inventory 和 Configuration Baseline，再建立 Standard Template，將 Configuration 放入 Git。

接著使用 Ansible 自動檢查設定。

新的 Change 必須經過 Review、Approval、Version Control 和 Rollback Plan。

我們先 Pilot，再逐步擴大到：

* Astro：約 40 台
* Axiom：約 30 台
* Unition：約 30 台

合計約 **100 台 Network Devices**。

**English：**

First, /
I created /
a device inventory /
and configuration baseline.

We built /
standard templates /
and stored configurations /
in Git.

Then, /
we used Ansible /
to automatically check /
device configurations.

Every change needed /
review, /
approval, /
version control, /
and a rollback plan.

We started small /
and later expanded /
the process /
to about **100 network devices**.

---

## R

**中文：**
Configuration Error 約下降 50% 到 60%，Change Review Time 約改善 30% 到 40%。

更重要的是，每一個 Change 都可以 Trace、Review 和 Rollback。

**English：**

Configuration errors /
decreased /
by about **50 to 60 percent**.

Change review time /
improved /
by about **30 to 40 percent**.

More importantly, /
every change /
became traceable, /
reviewable, /
and reversible.

---

## L

**中文：**
我學到 Invent and Simplify 不一定是創造新的 Technology，很多時候是用簡單的方式消除不必要的 Complexity。

**English：**

I learned /
that Invent and Simplify /
does not always mean /
creating new technology.

Sometimes, /
the best solution /
is using simple tools /
to remove unnecessary complexity.

---

# 4. Tell me about a time you raised operational standards.

**Primary LP：Insist on the Highest Standards**
**Secondary：Deliver Results / Dive Deep**

## S

**中文：**
團隊以前很快可以 Close Ticket，但一些 Incident 一直重複發生。我發現 KPI 太偏向「Ticket 是否關閉」，而不是「Problem 是否真正解決」。

**English：**

The team could close incidents /
quite quickly.

However, /
some of the same problems /
kept coming back.

The team focused /
more on closing tickets /
than permanently fixing /
the problem.

---

## T

**中文：**
我要把團隊從 Reactive Incident Handling，轉成 Proactive Reliability Improvement。

**English：**

My task was /
to move the team /
from reactive incident handling /
to proactive /
reliability improvement.

---

## O / D

**中文：**
增加 On-call 人力可以更快解 Ticket，但沒有解決 Root Cause。

所以我決定導入 Problem Management、RCA、Corrective Action Tracking。

**English：**

One option /
was to add more people /
to respond faster.

But this would only help us /
fix the same problems faster.

I decided /
to focus on /
Problem Management, /
Root Cause Analysis, /
and prevention.

---

## A

**中文：**
我建立 Monthly Operations Review，追蹤 Availability、MTTR、Repeated Incident、Change Failure、SLA。

Major Incident 必須完成 RCA。

每個 Corrective Action 都有 Owner、Due Date、Validation。

**English：**

I created /
a monthly Operations Review.

We tracked /
availability, /
MTTR, /
repeated incidents, /
change failures, /
and SLA.

Major incidents /
required an RCA.

Every corrective action /
needed an owner, /
a due date, /
and a way to validate /
the result.

---

## R

**中文：**
Annual System Downtime 約改善 **81%**。

例如年度中斷時間約從 **80 小時降低到約 15 小時**。

MTTR 約改善 **30% 到 35%**，Repeated Incident 約降低 **40% 到 50%**。

**English：**

After continuous improvement, /
annual system downtime /
improved by about **81 percent**.

It went /
from around **80 hours per year** /
to around **15 hours**.

MTTR improved /
by about **30 to 35 percent**.

Repeated incidents /
were reduced /
by around **40 to 50 percent**.

---

## L

**中文：**
Highest Standards 不代表永遠不犯錯，而是同樣問題不應該持續重複。

**English：**

High standards /
do not mean /
people can never make mistakes.

It means /
we learn from problems /
and make sure /
the same problem /
does not keep happening.

---

# 5. Tell me about a time you developed your team.

**Primary LP：Hire and Develop the Best**
**Secondary：Earn Trust / Earth’s Best Employer**

## S

**中文：**
我管理約 **25 人的團隊**時，新人約需要 6 個月才能獨立工作。

知識過度集中在 Senior Engineer。

**English：**

I managed /
a team of about **25 people**.

At that time, /
new engineers needed /
about **six months** /
before they could work independently.

Important knowledge /
was concentrated /
in a few senior engineers.

---

## T

**中文：**
我要縮短 Onboarding，但不能犧牲 Operational Quality。

**English：**

My goal was /
to shorten onboarding /
without lowering /
our operational standards.

---

## O / D

**中文：**
Hiring 更多 Senior Engineer 可以短期解決問題，但 Cost 高，而且沒有解決 Knowledge Dependency。

所以我決定把 Knowledge 制度化。

**English：**

We could hire /
more senior engineers.

That could solve /
the short-term problem.

But it would cost more, /
and the knowledge problem /
would still remain.

So I decided /
to make the knowledge /
part of the process.

---

## A

**中文：**
我建立 Skill Matrix、SOP、Knowledge Base、30/60/90 Day Training Plan、Mentor Program。

新人要完成 Incident Simulation、Standard Change、Troubleshooting 和 Shift Handover。

**English：**

I created /
a skill matrix, /
SOPs, /
a knowledge base, /
and a 30, 60, 90-day /
training plan.

Senior engineers /
became mentors.

New engineers practiced /
incident scenarios, /
standard changes, /
troubleshooting, /
and shift handovers.

---

## R

**中文：**
SOP / Knowledge Base 完成約 **90%**。

Onboarding 從 **6 個月降低到約 1 個月**。

半年後有 **2 位 Team Member 取得 AWS Certification**。

**English：**

We completed /
about **90 percent** /
of the SOPs /
and knowledge base.

We reduced onboarding /
from about **six months** /
to about **one month**.

After six months, /
two team members /
also earned /
AWS certifications.

---

## L

**中文：**
Manager 的 Scale 不是自己可以解多少 Problem，而是可以培養多少人獨立解決問題。

**English：**

A manager’s scale /
does not come from /
how many problems /
I can solve myself.

It comes from /
how many people /
I can develop /
to solve problems independently.

---

# 6. Tell me about a time you had to make a fast decision.

**Primary LP：Bias for Action**
**Secondary：Ownership / Highest Standards**

## S

**中文：**
一次 Production Incident 發生後，Service Impact 持續擴大，但 Root Cause 尚未完整確認。

**English：**

During one Production incident, /
the service impact /
was getting worse.

But we still did not have /
the full root cause.

---

## T

**中文：**
我要決定繼續 Investigate，還是立即採取 Recovery Action。

**English：**

I needed to decide /
whether to wait /
for more information /
or take recovery action /
immediately.

---

## O / D

**中文：**
我的判斷重點是：

Impact 是否持續增加？
Action 是否 Reversible？
Worst-case Risk 是否可控？

因為 Rollback 已測試，而且可以逆轉，所以我決定立即 Rollback。

**English：**

I focused /
on three questions.

Was the impact /
still getting worse?

Was the action /
reversible?

And could we control /
the worst-case risk?

Because the rollback /
had already been tested /
and was reversible, /
I decided to act.

---

## A

**中文：**
Rollback 前確認 Backup、Data Status、Command、Owner 和 Validation。

另一組 Engineer 繼續調查 Root Cause。

Recovery 後暫停其他 Production Change。

**English：**

Before the rollback, /
I confirmed /
the backup, /
data status, /
commands, /
owners, /
and validation steps.

At the same time, /
another team continued /
the root cause investigation.

After recovery, /
I paused further changes /
until the service /
was fully stable.

---

## R

**中文：**
服務約在 **25 到 40 分鐘**恢復，而且沒有發生 Data Loss。

**English：**

We restored the service /
within about **25 to 40 minutes**.

There was /
**no data loss**.

---

## L

**中文：**
Bias for Action 不是越快越好，而是當 Decision Reversible 且 Risk 可控時，不要因 Over-analysis 延誤 Recovery。

**English：**

Bias for Action /
does not mean /
acting without thinking.

It means /
avoiding over-analysis /
when the decision /
is reversible /
and the risk /
can be controlled.

---

# 7. Tell me about a time you disagreed with your manager.

**Primary LP：Have Backbone; Disagree and Commit**
**Secondary：Earn Trust / Are Right, A Lot**

## S

**中文：**
有一次 Management 希望快速對 Production 做 Infrastructure Change，大約可能影響 **10 到 20 個 Services**。

我認為測試時間不足，直接 Full Deployment 風險過高。

**English：**

One time, /
management wanted /
to make a Production change /
very quickly.

The change could affect /
about **10 to 20 services**.

I believed /
that a full deployment /
was too risky /
because the test time /
was not enough.

---

## T

**中文：**
我的工作不是只說 No，而是提供 Evidence 和 Alternative。

**English：**

My job /
was not only /
to say no.

I needed /
to explain the risk /
with data /
and provide /
a practical alternative.

---

## O / D

**中文：**
Full Deployment 最快，但 Blast Radius 最大。

延期最安全，但影響 Business Schedule。

所以我提出 Canary / Phased Deployment。

**English：**

A full deployment /
was the fastest option, /
but it had /
the largest blast radius.

Delaying the change /
was safer, /
but it would affect /
the business schedule.

So I proposed /
a **phased deployment**.

---

## A

**中文：**
先 Deployment 到大約 **10% Environment**。

觀察 **30 分鐘** Error Rate、Latency 和 Availability。

正常再逐步擴大。

同時準備 Rollback Plan、Dashboard 和 Stop Criteria。

**English：**

We deployed /
to about **10 percent** /
of the environment first.

Then we watched /
the error rate, /
latency, /
and availability /
for **30 minutes**.

If everything was normal, /
we continued /
step by step.

I also prepared /
a rollback plan, /
monitoring dashboard, /
and clear stop criteria.

---

## R

**中文：**
Change 成功完成，沒有 Production Outage。

雖然比原計畫多約 **1 到 2 小時**，但大幅降低 Risk。

**English：**

The change /
was completed successfully.

There was /
no Production outage.

The process took /
about **one to two more hours**, /
but it greatly reduced /
the deployment risk.

---

## L

**English：**

For me, /
Disagree and Commit means /
I speak up /
before the decision.

But after the decision, /
I fully support /
the final direction.

---

# 8. Tell me about a failure.

**Primary LP：Learn and Be Curious**
**Secondary：Ownership / Earn Trust**

## S

**中文：**
我曾負責一個原定 **8 週**完成的 Infrastructure Project，但我低估了 Application、Network、Security Team 的 Dependency。

**English：**

I was responsible /
for an infrastructure project /
that was planned /
to finish in **eight weeks**.

However, /
I underestimated /
the dependencies /
between several teams.

---

## T

**中文：**
我需要承認 Planning Gap，重新建立可執行的 Plan。

**English：**

My responsibility /
was to accept /
that this was /
a planning problem /
and rebuild /
a realistic plan.

---

## A

**中文：**
我建立 Dependency List、Risk List、Owner、Milestone。

導入 Weekly Cross-Team Review。

大型專案 Kickoff 增加 Security Review、Change Requirement、Operational Readiness。

**English：**

I rebuilt /
the project plan.

I added /
a dependency list, /
risk list, /
clear owners, /
and milestones.

I also created /
a weekly cross-team review.

---

## R

**中文：**
專案最後比原定計畫晚約 **2 週**。

但導入新的 Planning Template 後，後續 Cross-Team Delay 約改善 **30% 到 40%**。

**English：**

The project finished /
about **two weeks later** /
than the original plan.

However, /
after using /
the new planning process, /
cross-team delays /
improved by about /
**30 to 40 percent**.

---

## L

**中文：**
Good Technical Design 不等於 Good Delivery。

**English：**

I learned /
that a good technical design /
does not automatically mean /
good delivery.

A manager must also manage /
dependencies, /
communication, /
risk, /
and readiness.

---

# 9. How do you manage a 24x7 Operations Team?

**Primary LP：Ownership / Highest Standards**
**Secondary：Earth’s Best Employer / Deliver Results**

## S

**中文：**
我曾管理約 **20 到 25 人的 24x7 Operations Team**。

主要風險包括 Shift Handover、Escalation、Ticket Priority 和 On-call Workload。

**English：**

I managed /
a 24x7 operations team /
of about **20 to 25 people**.

Important risks included /
shift handover, /
escalation, /
ticket priority, /
and on-call workload.

---

## T

**中文：**
我要確保任何時間發生 Incident，都有人知道誰負責、何時 Escalate、如何 Recovery。

**English：**

My goal was /
to make sure /
that during any incident, /
everyone knew /
who owned the problem, /
when to escalate, /
and how to recover.

---

## A

**中文：**
我建立 Severity Standard、Shift Handover Template、Escalation Matrix、On-call Backup。

並追蹤 MTTR、SLA、Availability、Repeated Incident、Ticket Backlog。

**English：**

I used /
clear severity levels, /
shift handovers, /
an escalation matrix, /
and on-call backup.

I also tracked /
MTTR, /
SLA, /
availability, /
repeated incidents, /
and ticket backlog.

---

## R

**中文：**
SLA 維持在 **99% 以上**。

MTTR 約改善 **30%**。

Handover Related Delay 約降低 **40% 到 50%**。

透過 Monitoring 改善，重要異常能在 **約 20 分鐘內被發現**。

**English：**

SLA performance stayed /
above **99 percent**.

MTTR improved /
by about **30 percent**.

Handover-related delays /
were reduced /
by around **40 to 50 percent**.

Important issues /
could also be detected /
within about **20 minutes**.

---

## L

**English：**

My goal /
is not to keep /
the team busy.

My goal is /
to make operations /
**stable, predictable, /
and safe**.

---

# 10. Why Amazon? Why Data Center Operations?

**Primary LP：Customer Obsession / Learn and Be Curious**
**Secondary：Ownership**

## S

**中文：**
我的職涯長期集中在 Infrastructure、Network、Cloud、Security、Data Center 和 24x7 Operations。

管理過 **500+ Servers** 的 Infrastructure Environment，也負責過 Hybrid Cloud、Network、Security 和 Mission-Critical Services。

年度 IT Budget / P&L 約為 **USD 3M–5M**。

**English：**

Most of my career /
has been focused /
on Infrastructure, /
Network, /
Cloud, /
Security, /
Data Center, /
and 24x7 Operations.

I have worked /
with infrastructure environments /
of more than **500 servers**.

I also managed /
Hybrid Cloud, /
Network, /
Security, /
and mission-critical services.

My annual IT budget /
was around /
**three to five million US dollars**.

---

## T / Why AWS

**中文：**
現在我希望進入一個更大型、更標準化，而且 Operational Quality 會直接影響 Customer Experience 的 Infrastructure Organization。

AWS Data Center Operations 吸引我，不只是因為 Brand，而是因為它把 Availability、Safety、Security、Incident Response、Standard Process 和 People Development 都視為核心能力。

**English：**

Now, /
I want to work /
in a much larger /
and more standardized /
infrastructure environment.

AWS Data Center Operations /
is attractive to me /
because the role /
is not only about hardware.

It also focuses on /
availability, /
safety, /
security, /
incident response, /
standard processes, /
and people development.

---

## Value

**English：**

I believe /
I can bring experience /
in infrastructure, /
networking, /
incident management, /
24x7 operations, /
automation, /
budget management, /
and people development.

At the same time, /
I want to learn /
how AWS operates /
data centers /
at a global scale.

I am not only looking /
for a higher job title.

I want a role /
where I can use /
my experience /
and continue growing /
as an infrastructure /
operations leader.

---

# 11. Tell me about a time you identified or prevented an operational risk.

### Safety / Operational Risk

**Primary LP：Highest Standards / Ownership**

## S

**中文：**
我發現不同地點的 Engineer 可以直接登入 Production 或 Network Device 做 Change。

雖然操作速度快，但存在 Human Error、Unauthorized Change 和 Audit Risk。

**English：**

I found that /
engineers in different locations /
could directly log in /
to Production systems /
or network devices.

This was fast, /
but it created /
human error, /
unauthorized change, /
and audit risks.

---

## T

**中文：**
我要降低操作風險，但不能讓正常 Operations 因為流程太複雜而無法執行。

**English：**

My task was /
to reduce operational risk /
without making /
the normal process /
too slow or too complex.

---

## O / D

**中文：**
我沒有完全禁止所有 Change，而是建立 Controlled Change。

**English：**

I did not /
completely block /
all changes.

Instead, /
I created /
a **controlled change process**.

---

## A

**中文：**
導入：

Git Version Control
Peer Review
Manager / Local Supervisor Approval
Runner / Controlled Execution
Rollback Plan
Audit Log

重大 Change 則需要 Double Check。

**English：**

We introduced /
Git version control, /
peer review, /
management approval, /
controlled execution, /
rollback plans, /
and audit logs.

For major changes, /
we also required /
an additional review.

---

## R

**中文：**
最後約 **100 台 Network Device** 都逐步納入受控管理。

**English：**

In the end, /
about **100 network devices** /
were gradually moved /
into the controlled process.

The environment became /
safer, /
more traceable, /
and more standardized.

---

# 12. You have many open tickets and limited technicians. How do you prioritize?

### Ticket Priority / Service Delivery

**Primary LP：Customer Obsession / Deliver Results**

## 中文邏輯

我不使用單純 FIFO。

優先順序是：

**Safety → Service Impact → Severity → Dependency → SLA → Resource**

P1：Safety / Major Outage
P2：Service Degradation / Critical Hardware Risk
P3：Normal Incident / Repair
P4：Planned Work

我也會保留部分 Engineer Capacity 給 Unexpected Incident。

過去管理 Service Delivery 時，Employee Satisfaction 約達 **98%**。

## English｜跟讀

I do not prioritize tickets /
only by arrival time.

I first look at /
**safety and service impact**.

Then I check /
severity, /
dependencies, /
SLA, /
and available resources.

A major outage /
or safety issue /
always comes first.

I also keep /
some team capacity /
for unexpected incidents.

My goal /
is not to close /
the largest number /
of tickets.

My goal is /
to reduce /
the **highest operational risk** /
first.

In one of my previous /
service environments, /
employee satisfaction /
reached about **98 percent**.

---

# 13. What would you do if a critical server failed and the spare part was unavailable?

### Hardware / Logistics / Capacity

**Primary LP：Ownership / Deliver Results / Frugality**

## S / Scale

**中文：**
我曾負責 **500+ Servers** 的 Infrastructure Environment，也處理跨地點 Hardware Lifecycle、Vendor Coordination 和 Capacity Planning。

**English：**

I have managed /
infrastructure environments /
with more than **500 servers**.

I also worked /
with hardware lifecycle, /
vendor coordination, /
and capacity planning /
across different locations.

---

## Decision Framework

**中文：**
如果 Critical Server Failure 而且沒有 Spare Part，我會先確認：

1. Customer / Business Impact
2. Redundancy
3. Failover Capacity
4. Replacement ETA
5. 是否可調用其他 Site Spare
6. Vendor Escalation
7. Remaining Capacity Risk

**English：**

First, /
I would understand /
the service impact.

Then I would check /
whether we still have /
enough redundancy.

If possible, /
I would move the workload /
or use a backup system /
to protect availability.

At the same time, /
I would escalate /
the spare-part issue /
to Logistics /
and the Vendor.

I would also check /
whether another site /
could provide /
a temporary spare.

---

## Long-term Action

**中文：**
Incident 結束後，我會檢討：

Spare Inventory
Failure Rate
Supplier Lead Time
Minimum Stock
Capacity Headroom

**English：**

After the incident, /
I would review /
the spare inventory, /
failure history, /
supplier lead time, /
and minimum stock level.

The goal /
is not only /
to repair one server.

The goal is /
to prevent /
the same supply problem /
from becoming /
another availability risk.

---

# Amazon DCOM 故事庫總表

| Story                  | 核心數據                                                   | Primary LP         |
| ---------------------- | ------------------------------------------------------ | ------------------ |
| Major Incident         | 3–5 services / 20–30% users / 45–60 min / No Data Loss | Ownership          |
| Dive Deep              | 2–3/day → <1/week / Response -30–40%                   | Dive Deep          |
| Git + Ansible          | 100 devices / Error -50–60% / Review -30–40%           | Invent & Simplify  |
| Operational Excellence | Downtime -81% / 80h → 15h / MTTR -30–35%               | Highest Standards  |
| Develop People         | 25 people / SOP 90% / 6mo → 1mo / 2 AWS certs          | Hire & Develop     |
| Bias for Action        | Recovery 25–40 min / No Data Loss                      | Bias for Action    |
| Disagree & Commit      | 10–20 services / 10% Canary / 30 min                   | Backbone           |
| Failure                | 8 weeks / +2 week delay / later delay -30–40%          | Learn & Curious    |
| 24x7 Operations        | 20–25 people / SLA 99%+ / MTTR -30% / detect 20 min    | Ownership          |
| Scale / Why AWS        | 500+ servers / USD 3M–5M                               | Customer Obsession |
| Safety                 | 100 controlled network devices                         | Highest Standards  |
| Service Delivery       | Satisfaction 98%                                       | Customer Obsession |
| Hardware               | 500+ server environment                                | Ownership          |

---

# 面試時真正要記的 7 個步驟

## S — Situation

發生了什麼？

## T — Task

我負責什麼？

## O — Options

我當時有哪些選擇？

## D — Decision

**為什麼這樣決定？**

## A — Action

**我本人做了什麼？**

## R — Result

**用數據證明什麼？**

## L — Learning

如果重來一次，我會怎麼做？

---

# 面試官追問時記住

**WHY**
Why did you choose this?

**I**
What did you personally do?

**DATA**
What data did you use?

**TRADE-OFF**
What other options did you consider?

**RESULT**
How did you measure success?

**FAILURE**
What did not go well?

**LEARNING**
What would you do differently?

---

# 英文回答最後提醒

不要刻意用複雜英文。

Amazon 面試更重要的是：

**Clear thinking.**
**Clear ownership.**
**Clear decisions.**
**Clear numbers.**

你可以說：

> I had three options.

比：

> After performing a comprehensive multidimensional assessment of the available alternatives...

好很多。

你的英文目標不是像 Native Speaker。

你的目標是讓 Interviewer 很清楚聽懂：

> **What was the problem?**
> **Why did CK make that decision?**
> **What did CK personally do?**
> **What was the measurable result?**
> **What did CK learn?**

這版現在已經把數據全部正式帶進故事裡了。下一個準備重點會是把這 **13 題各縮成 2 分鐘口說版**，否則目前完整版適合學習與追問準備，但實際 Phone Screen 直接完整講會偏長。
