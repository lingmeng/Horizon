---
layout: default
title: "Horizon Summary: 2026-11-23 (EN)"
date: 2026-11-23
lang: en
---

> From 28 items, 10 important content pieces were selected

---

**Technology News**
1. [Perplexity and Intelligence](#item-tech-news-1) ⭐️ 8.0/10
2. [FT alleges Nvidia‑chip smuggling tied to Cambodian &\#x27;Prince&\#x27; group](#item-tech-news-2) ⭐️ 8.0/10
3. [China Objects to U.S. Ban on Direct Access to U.S. Phone Numbers](#item-tech-news-3) ⭐️ 8.0/10
4. [Windows Server 2028 drops WoW64 by default](#item-tech-news-4) ⭐️ 8.0/10
5. [What Happened to Silicon Valley?](#item-tech-news-5) ⭐️ 7.0/10
6. [Mirror Dimension: Google’s simulated internet for Chrome AI agent](#item-tech-news-6) ⭐️ 7.0/10

**Technology Blog**
1. [When in doubt, flail about](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [US tech sell-off prompts Asian market interventions](#item-finance-news-1) ⭐️ 9.0/10
2. [Record-strength &\#x27;super&\#x27; El Niño and WFP warning on food insecurity](#item-finance-news-2) ⭐️ 8.0/10
3. [Ant Group leads $100M pre‑A in Simplexity Robotics at $1.6B valuation](#item-finance-news-3) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Perplexity and Intelligence](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 8.0/10

OpenAI published an essay titled &quot;Perplexity and Intelligence&quot; arguing that a model&\#x27;s perplexity \(cross-entropy / prediction surprise\) closely correlates with general intelligence and therefore can serve as a simple, powerful benchmark for language-model progress. The piece frames log‑perplexity on held-out pretraining data as predictive of downstream capabilities and has triggered active discussion among researchers and practitioners. The article advances a strong empirical claim but appears to be an argument rather than independently verified proof; commenters noted the article omits a formal definition of perplexity and that measurement details \(held-out set, tokenization, evaluation protocol\) are critical to interpreting any reported numbers.

hackernews · acossta · Nov 22, 17:06 · [Discussion](https://news.ycombinator.com/item?id=50601525)

**「What perplexity measures」** Perplexity is a probabilistic measure of how surprised a language model is when predicting the next token: formally it is the exponential of the model&\#x27;s average negative log‑probability \(cross‑entropy\), so lower perplexity means the model assigns higher probability to the observed tokens. By definition a perfect predictor has perplexity 1, while a uniformly random predictor reaches about the vocabulary size, so changes in perplexity reflect changes in the model&\#x27;s average per‑token confidence and compression of the training distribution.

**「Immediate consequence」** If the community accepts the correspondence, vendors and researchers are likely to resume publishing held-out log‑perplexities on common evaluation sets to compare base models — a step commenters report is already starting \(one thread notes Microsoft adding MAI models to a shared chart and reporting a log‑perplexity claim\). To make such comparisons reproducible, practitioners should require matched evaluation conditions \(identical held‑out data, tokenization, vocabulary and reporting conventions\) and report raw cross‑entropy or bits‑per‑token alongside any perplexity figures.

**「Discussion highlights」** Commenters argued the idea is both surprising and intuitively plausible: some praised having a single simple benchmark instead of proliferating task suites, while others pointed out omissions — notably no formal definition of perplexity — and referenced prior theoretical work linking prediction/compression to intelligence. Opinions about historical model milestones and how RL-based fine‑tuning interacts with pretraining perplexity were debated but remain unresolved in the discussion.

**Tags**: `#evaluation-metrics`, `#language-models`, `#benchmarks`, `#AI-research`

---

<a id="item-tech-news-2"></a>
### [FT alleges Nvidia‑chip smuggling tied to Cambodian &\#x27;Prince&\#x27; group](https://www.ft.com/content/f3ad8a81-3890-4a8a-8853-ff0a94b08ba9?syn-25a6b1a6=1) ⭐️ 8.0/10

The Financial Times reports that Hu Xiaowei \(胡小伟\), described by the US Treasury as the &quot;number two&quot; figure in Cambodia&\#x27;s Prince Group, has been accused by sources of participating in a network that moved Nvidia chips toward China. The report says the group used shell companies, underground financing and private aircraft and routed shipments through a Malaysian affiliate, Megaspeed, whose declared imports from December 2024 to December 2025 totaled about $4.6 billion; some chips are alleged to have reached China’s black market. The Prince Group denies Hu worked for it and rejects the specific smuggling and private‑plane allegations; the FT story is an allegation, not an adjudicated finding.

telegram · zaihuapd · Nov 22, 04:34

**「Why export controls and gray‑market routes matter」** U.S. export controls on advanced AI accelerators have restricted legal sales of some high‑end Nvidia chips to China, creating incentives for gray‑market and smuggling networks. Recent reporting has identified Megaspeed and related intermediaries as implicated in moving restricted Nvidia chips toward China, which explains why investigators and journalists trace trade‑data, shell companies and intermediary subsidiaries in these stories.

**「Impact」** If true, the scale and mechanics alleged \(use of shell firms and a Malaysian trading affiliate\) increase legal and compliance risk for suppliers, distributors and freight intermediaries handling advanced chips: affected companies should immediately review counterparties, shipment documentation and sanctions/export‑control screening procedures and be prepared for possible regulatory inquiries.

<details><summary>References</summary>
<ul>
<li><a href="https://asiatimes.com/2026/11/daigou-the-gray-market-that-moves-nvidias-chips-to-china/">Daigou: the gray market that moves Nvidia &#x27;s chips to... - Asia Times</a></li>

</ul>
</details>

**Tags**: `#hardware`, `#supply-chain`, `#export-controls`, `#security`, `#investigation`

---

<a id="item-tech-news-3"></a>
### [China Objects to U.S. Ban on Direct Access to U.S. Phone Numbers](https://www.bloomberg.com/news/articles/2026-11-22/china-objects-to-us-curbs-on-telecoms-access-to-phone-numbers) ⭐️ 8.0/10

China&\#x27;s Ministry of Commerce on Nov 22 urged the United States to revoke a measure that prevents China Mobile, China Telecom and China Unicom from directly obtaining U.S. telephone numbers, saying the restriction violates non‑discrimination and fair‑competition principles. The U.S. Federal Communications Commission voted on Nov 19 to tighten security requirements for internet‑voice providers seeking direct access to U.S. numbering, adding a national‑security certification intended to stop entities, devices or services on the FCC&\#x27;s Covered List from connecting to U.S. networks. The ministry said the FCC cited national‑security risks without factual basis and warned the move risks pushing the two countries toward telecom and testing/certification decoupling; it said China will take necessary measures to protect its interests.

telegram · zaihuapd · Nov 22, 06:44

**「Why U.S. numbering access matters」** Direct access to U.S. telephone numbers means non‑U.S. carriers or internet‑voice service providers obtain the ability to use or assign U.S. numbering resources so they can present U.S. caller IDs or offer services that rely on U.S. numbers; regulators control that access and can impose security, certification, and operational conditions on applicants. On November 19 the FCC voted to tighten security requirements for applicants seeking direct access to U.S. numbers, adding a national‑security certification intended to keep entities on its Covered List from connecting to U.S. networks.

**「Immediate consequence」** Operators and voice‑service providers affected by the FCC change should assume parties on the Covered List cannot request direct U.S. numbering and will likely need to either pursue the FCC&\#x27;s new national‑security certification or arrange numbering and interconnection through U.S. intermediaries or partners to preserve service continuity.

**Tags**: `#telecom`, `#policy`, `#China-US`, `#national-security`, `#regulatory`

---

<a id="item-tech-news-4"></a>
### [Windows Server 2028 drops WoW64 by default](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 8.0/10

Microsoft announced at Ignite 2026 that Windows Server 2028 will ship without the WoW64 \(Windows-on-Windows 64\) compatibility subsystem enabled by default, so 32‑bit applications will not run out of the box. WoW64 will remain available as a Feature on Demand \(FoD\) that administrators can reinstall, and Server Core installations typically add it with PowerShell or DISM. Microsoft said the change aims to reduce attack surface and block 32‑bit malware; Windows 11 will continue to include WoW64 and no removal plan there was announced.

telegram · zaihuapd · Nov 23, 03:03

**「Background」** WoW64 is the compatibility layer that lets 32‑bit Windows binaries run on 64‑bit Windows systems. Historically, 64‑bit Windows Server editions included WoW64 by default so legacy 32‑bit server applications ran without extra configuration.

**「Impact」** Administrators who rely on 32‑bit server applications must either install the WoW64 Feature on Demand on Windows Server 2028 deployments or migrate those applications to 64‑bit builds; otherwise the 32‑bit binaries will not execute. Actionable steps are to audit server images and automated provisioning \(unattend/DISM/PowerShell\) to include WoW64 where required and to test compatibility before upgrading production servers.

**Tags**: `#windows-server`, `#compatibility`, `#security`, `#sysadmin`, `#wow64`

---

<a id="item-tech-news-5"></a>
### [What Happened to Silicon Valley?](https://www.oreilly.com/radar/what-happened-to-silicon-valley/) ⭐️ 7.0/10

O’Reilly Radar published a long-form essay titled &quot;What Happened to Silicon Valley?&quot; that argues Silicon Valley’s incentive structures and mechanism design produced perverse outcomes and should be redesigned to prioritize human flourishing rather than primarily optimizing for shareholder profit. The piece frames mechanism design as a form of reverse game theory—asking what game we ought to be playing—and urges engineers, product leaders, and policymakers to rethink metrics, governance, and reward systems. This is an analytical prescription presented as argument and normative guidance, not a report of new measurements or engineering changes.

hackernews · greenyouse · Nov 22, 19:20 · [Discussion](https://news.ycombinator.com/item?id=50602947)

**「Conceptual background」** The O’Reilly Radar piece frames recent problems in Silicon Valley as a shift from broad value creation toward value extraction and evaluates that shift through the lens of mechanism design — treating incentive structures as the rules that determine collective outcomes. Readers should be familiar with mechanism-design thinking \(reverse game theory\) and the distinction between creating surplus value and capturing it to follow the article’s proposals for redesigning incentives toward human flourishing.

**「Impact」** Practitioners and organizations should treat the essay as a practical prompt to review incentives and evaluation systems: consider adding human-centered KPIs, conducting mechanism-design or ethics audits of product flows, and reassessing compensation and success metrics that currently reward growth or engagement irrespective of social effects. These are actionable governance changes readers can pilot internally, but they require process changes and stakeholder alignment rather than a single technical fix.

**「Community discussion」** HN commenters echoed the essay’s central theme: one noted Hal Varian’s anecdote that only a small share of Google results were monetized to illustrate an earlier era of abundance, while others argued we need to &quot;tear down and rebuild the machine&quot; and hold mechanism designers accountable. A separate thread pointed to macro causes—ZIRP-era incentives and recent interest-rate and AI-driven shifts—as proximate factors that amplified the problems the article describes; these observations were presented as opinion rather than settled fact.

<details><summary>References</summary>
<ul>
<li><a href="https://www.oreilly.com/radar/posts/">All Articles – O’Reilly</a></li>
<li><a href="https://www.oreilly.com/radar/">Radar – O’Reilly</a></li>

</ul>
</details>

**Tags**: `#tech-industry`, `#mechanism-design`, `#governance`, `#AI-ethics`

---

<a id="item-tech-news-6"></a>
### [Mirror Dimension: Google’s simulated internet for Chrome AI agent](https://www.landian.news/archives/128701.html) ⭐️ 7.0/10

Google is reported to have built a simulated internet called Mirror Dimension to run isolated, large-scale tests of a Chrome AI agent’s browsing behavior. The report says the environment contains thousands of synthetic websites and that engineers run their tests in isolated instances, with more than 1,000 test cases executed daily covering actions such as opening pages, searching, logging in, adding items to a cart, and completing tasks. The testbed reportedly focuses on evaluating defenses against malicious webpages and prompt‑injection attacks. This account comes from a single report and lacks independent technical corroboration.

telegram · zaihuapd · Nov 23, 01:30

**「Why this matters」** AI agents that perform web browsing and account actions face threats from malicious sites and prompt‑injection, so evaluating agent behavior against hostile content at scale requires an isolated, controllable environment. A simulated internet lets engineers run many automated scenarios without exposing real users, live websites, or production credentials.

**「Concrete consequence」** If Mirror Dimension functions as reported, Chrome and other browser‑agent teams gain a way to stress‑test browsing workflows and prompt‑injection defenses at scale in isolation, which can reduce the risk of accidental exposure of accounts or browsers to live malicious content; teams building similar agents should consider comparable isolated testbeds and include explicit prompt‑injection test scenarios in their QA process.

**Tags**: `#Chrome`, `#AI agent`, `#sandboxing`, `#security`, `#prompt-injection`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [When in doubt, flail about](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 23, 00:00

**「Background」** Sean Goedecke argues that when a problem lacks clear guidance, the fastest route to understanding is often to ‘flail’—run lots of small experiments—rather than wait for certainty, though he cautions this can damage your reputation if done poorly.

**「Solution」** His practical prescription is threefold: try many different approaches, pay very close attention to feedback, and ruthlessly drop anything that doesn’t show clear positive signals. He frames this across product, engineering, and organizational contexts: in product work he describes trying many feature ideas while on GitHub Models until one—allowing AI inference from a GitHub Actions token—proved sticky and seeded “Continuous AI”; in engineering he recommends speculative, measurable changes \(and notes AI agents can help generate options\) so you can observe what actually improves the system; and in organizational problems he suggests a menu of low-cost interventions while stressing extreme sensitivity to social feedback so you don’t make things worse. The common mechanics are small bets, rapid observation of real outcomes, and low sunk cost per experiment so you can abandon failures quickly and concentrate effort on the few things that work.

**「Takeaway」** Goedecke’s core thesis is that deliberate, well-monitored flailing is an effective way to discover what works under uncertainty—if you accept the temporary discomfort and immediately drop experiments that fail to produce convincing feedback.

**Tags**: `#experimentation`, `#engineering-culture`, `#product-management`, `#organizational-change`

---

## Financial News

<a id="item-finance-news-1"></a>
### [US tech sell-off prompts Asian market interventions](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

US AI and tech stocks suffered a sharp sell-off: the Nasdaq fell 5.28% in a single day and the Philadelphia Semiconductor Index dropped about 11% \(actual results\); Asian authorities responded with market-stability measures — mainland China cut the minimum financing margin ratio to 80%, South Korea will loosen daily buyback order limits from Nov. 24 for three months, and Taiwan will ban short-selling below the previous close and raise securities‑lending margin from 130% to 150% \(reported by Xinhua, Yonhap and CNA\).

telegram · zaihuapd · Nov 22, 13:24

**「background」** On Nov 20 US tech stocks plunged: the Nasdaq Composite fell 5.28% to 22,617.73 \(turning 2026 year‑to‑date performance negative\) while the VIX spiked above 35, signaling acute market stress.

**「impact」** These measures directly affect margin traders, short sellers and listed issuers conducting buybacks and are intended to alter regional equity market liquidity by restricting selling and changing financing requirements.

<details><summary>References</summary>
<ul>
<li><a href="https://www.gate.com/zh/news/detail/us-stocks-crash-nasdaq-turns-negative-for-2026-vix-surges-past-40-25797766">美股暴跌：纳斯达克指数2026年迄今转为负收益，VIX飙升至40以上 | Gat...</a></li>

</ul>
</details>

**Tags**: `#market turmoil`, `#regulatory response`, `#US tech sell-off`, `#Asia markets`

---

<a id="item-finance-news-2"></a>
### [Record-strength &\#x27;super&\#x27; El Niño and WFP warning on food insecurity](https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/) ⭐️ 8.0/10

A record-strength &quot;super&quot; El Niño has warmed the central tropical Pacific by 3.5°C as of October and is forecast to peak near 4°C in early winter \(Berkeley Earth&\#x27;s Zeke Hausfather\). The UN World Food Programme estimates the event could push about 49 million more people into acute food insecurity by end-2027 \(WFP estimate\).

telegram · zaihuapd · Nov 22, 14:09

**「background」** Berkeley Earth scientist Zeke Hausfather reports the 2026 “super” El Niño has warmed the central tropical Pacific by about 3.5°C as of October, and climate-model analyses project a peak near 4°C.

**「impact」** Humanitarian response capacity is at risk because global aid funding fell about 30% in 2025 versus the 2022 peak, constraining the WFP&\#x27;s ability to cover affected populations \(WFP reported example: Somalia coverage fell from 10 million to under 1 million in a comparable drought\).

<details><summary>References</summary>
<ul>
<li><a href="https://www.wired.com/story/2026-el-nino-the-strongest-in-150-years/">The 2026 El Niño Is on Track to Be the Strongest on Record</a></li>
<li><a href="https://www.carbonbrief.org/simply-staggering-rapidly-developing-super-el-nino-on-track-to-peak-in-december">‘Simply staggering’: Rapidly developing ‘super El Niño’ on ...</a></li>

</ul>
</details>

**Tags**: `#El Niño`, `#Food security`, `#Humanitarian aid`, `#Climate`, `#Agriculture`

---

<a id="item-finance-news-3"></a>
### [Ant Group leads $100M pre‑A in Simplexity Robotics at $1.6B valuation](https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race) ⭐️ 8.0/10

Bloomberg reports Ant Group led a $100 million pre‑A financing in Simplexity Robotics at a $1.6 billion post‑money valuation.

telegram · zaihuapd · Nov 23, 02:02

**「background」** The International Federation of Robotics reported global shipments of professional service robots rose 24% to almost 250,000 units in 2025, showing rapid industry growth.

**「Impact」** Bloomberg says the proceeds will be used to compete with more mature Chinese humanoid‑robot makers such as 宇树 and 优必选, strengthening Simplexity’s position in China’s humanoid‑robot market and intensifying competition for industry investors and suppliers.

<details><summary>References</summary>
<ul>
<li><a href="https://ifr.org/">International Federation of Robotics</a></li>

</ul>
</details>

**Tags**: `#private financing`, `#robotics`, `#China tech`, `#valuation`, `#corporate investors`

---