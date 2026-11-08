---
layout: default
title: "Horizon Summary: 2026-11-08 (EN)"
date: 2026-11-08
lang: en
---

> From 39 items, 18 important content pieces were selected

---

**Technology News**
1. [Claude Code &\#x27;Don&\#x27;t Ask Again&\#x27; exposed 1,122 GitHub files](#item-tech-news-1) ⭐️ 8.0/10
2. [Coldframe honeypot mimics supermarket fridge controllers](#item-tech-news-2) ⭐️ 8.0/10
3. [Asahi Linux progress report 7.3](#item-tech-news-3) ⭐️ 8.0/10
4. [Galaxy AI datacenter campus in Inner Mongolia](#item-tech-news-4) ⭐️ 8.0/10
5. [Claude Code may leak users&\#x27; login email](#item-tech-news-5) ⭐️ 8.0/10
6. [Apple reveals humanoid robot HALO using two Qwen models](#item-tech-news-6) ⭐️ 8.0/10
7. [GitHub Rubicon: 7200 pushes/s Git storage](#item-tech-news-7) ⭐️ 8.0/10
8. [Microsoft Research &\#x27;AI Frontiers&\#x27; group reportedly ends](#item-tech-news-8) ⭐️ 7.0/10
9. [MaxxBench questions DeepSWE benchmark validity](#item-tech-news-9) ⭐️ 7.0/10
10. [Macs reportedly run undocumented family-member classifier](#item-tech-news-10) ⭐️ 7.0/10
11. [Discord Windows 11 client uses ~70% less RAM](#item-tech-news-11) ⭐️ 7.0/10
12. [Need for Speed Underground 2 in the browser](#item-tech-news-12) ⭐️ 7.0/10
13. [Turkey uses TraceART AI to recover looted antiquities](#item-tech-news-13) ⭐️ 7.0/10
14. [Judge Allows Suit Over Anthropic&\#x27;s Claude Max Usage Claims](#item-tech-news-14) ⭐️ 7.0/10
15. [Lawmaker urges ban on AI recursive self‑improvement](#item-tech-news-15) ⭐️ 7.0/10

**Financial News**
1. [SoftBank and ABB weigh China carve‑out to rescue $5.4bn robotics deal](#item-finance-news-1) ⭐️ 8.0/10
2. [Nationwide financial inspection launched for temples and Daoist sites](#item-finance-news-2) ⭐️ 8.0/10
3. [Berkshire accelerates buybacks as earnings fall](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Claude Code &\#x27;Don&\#x27;t Ask Again&\#x27; exposed 1,122 GitHub files](https://apiiro.com/blog/coding-agents-leaking-secrets-github-dont-ask-again) ⭐️ 8.0/10

A report alleges that local Claude Code configuration and approved agent commands resulted in secrets appearing in 1,122 public GitHub files. The exposure reportedly involved committed .claude files \(notably .claude/settings.local.json\) that contained manually approved commands or embedded credentials; pressing the agent UI&\#x27;s “Don&\#x27;t Ask Again” control alone is not identified as a direct leak vector, but committing those local files published the secrets. A Claude Code team member acknowledged the product historically does not perform secret-scrubbing and said .claude/settings.local.json is intended to remain local and is automatically gitignored when created, implying the affected repositories had the files manually added to source control. Commenters and the report highlighted mitigations such as secret-scrubbing, ensuring .claude is ignored from source control, and using secret managers or scripts that fetch credentials at runtime instead of embedding them in agent approvals.

hackernews · shmulc · Nov 7, 20:45 · [Discussion](https://news.ycombinator.com/item?id=50407882)

**「Coding agents and local execution」** Coding agents are language models adapted to developer workflows and automation; recent models such as Mellum2.1 are explicitly built for coding agents and fast sub-agents and can run on users&\#x27; own hardware. That local execution model means agent behavior is controlled by local code and configuration as well as the model, which helps explain why local settings or files can influence what an agent outputs or persists.

**「Concrete consequence and recommended action」** Developers who commit a .claude directory or settings.local.json risk publishing API keys, passwords, or other secrets and should treat exposed credentials as compromised: search repos for committed .claude files, remove them from source control, rotate any credentials found, add .claude entries to .gitignore, and avoid embedding credentials in approved agent commands in future. Community-recommended practices with supporting comments include using a password manager or CLI token retrieval \(so the agent calls a local script instead of storing secrets\), running agents in isolated ephemeral VMs, and applying secret-scrubbing tools before publishing code.

**「What the community said」** A Claude Code team member \(Boris\) noted the product does not currently scrub secrets and that the settings file is intended to stay local and is auto-gitignored when created; other commenters emphasized that the issue arises when users commit their .claude files, not from clicking “Don&\#x27;t Ask Again” alone, and suggested mitigations such as using password managers, scripted credential retrieval, ephemeral VMs, and manual editing of AI outputs before publishing.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.jetbrains.com/ai/2026/10/mellum2-1-gets-to-work-a-fast-open-model-for-coding-agents/">Mellum2.1 Gets to Work: A Fast Open Model for Coding Agents - The...</a></li>

</ul>
</details>

**Tags**: `#secrets`, `#security`, `#AI-agents`, `#github`, `#developer-tools`

---

<a id="item-tech-news-2"></a>
### [Coldframe honeypot mimics supermarket fridge controllers](https://github.com/hedgerow-dev/coldframe) ⭐️ 8.0/10

Coldframe is an open-source, single-file Python honeypot that impersonates supermarket refrigeration controllers \(Danfoss AK-SM 800A and Dixell XWEB\). The author says it matches device fingerprints observed on Shodan \(header order, TLS/certificate fields, and exact page size — the Dixell persona pads pages to 8,202 bytes and omits a Server header; the Danfoss persona reproduces nginx header order\), recognizes exploit attempts including CVE-2025-41450 \(tracking whether the submitted &quot;code of the day&quot; is correct\), and tags attempts against several other Danfoss and XWEB issues. Two instances have been live for about a day and, so far, have only attracted generic scanners and Shodan&\#x27;s refrigerator.census.shodan.io crawler; default logins present a fake store dashboard with defrost controls, but no real backend functions.

hackernews · hedgerow-dev · Nov 7, 17:27 · [Discussion](https://news.ycombinator.com/item?id=50406292)

**「Honeypots and recent refrigeration-controller issues」** Honeypots are deliberate fake services that imitate real devices or applications so researchers can observe reconnaissance and exploitation attempts without exposing production systems. Coldframe was built to emulate Danfoss AK-SM 800A and Dixell XWEB refrigeration UIs by matching observable fingerprints \(headers, TLS, page size\) and draws on prior decoy work \(eppser/danfoss-ak-sm-decoy\) and public research from Synacktiv, Claroty, and Ironhackers; it was motivated by recent incidents targeting industrial refrigeration and specifically detects attempts such as the Danfoss CVE-2025-41450 &quot;code of the day&quot; login bypass.

**「Immediate consequence」** Researchers and defenders can deploy a very small, standard-library Python honeypot to capture both initial scanning activity and post-login behavior against fridge-controller UIs, because Coldframe logs exploit probes and lets actors interact with a fake dashboard. Operators should note early telemetry shows only generic scanning and Shodan indexing so far, and that Coldframe&\#x27;s fidelity depends on Shodan-derived fingerprints — therefore teams should validate the mimicry against real hardware before treating findings as representative of targeted attacker behavior.

**「Community reactions」** Commenters cautioned against relying on Shodan as the sole source for device fingerprints, arguing many internet-visible pages can be honeypots or altered devices and recommending testing against real hardware where possible. The author and others also raised practical concerns about nontechnical operators \(for example, supermarkets\) lacking security teams and noted related targets such as blood‑bank refrigeration were suggested in discussion as potentially higher-risk.

**Tags**: `#honeypot`, `#industrial-control-systems`, `#security-research`, `#open-source`

---

<a id="item-tech-news-3"></a>
### [Asahi Linux progress report 7.3](https://asahilinux.org/2026/11/progress-report-7-3/) ⭐️ 8.0/10

Asahi Linux published Progress Report 7.3, updating the project’s Apple Silicon Linux work and current gaps. The report highlights recent release momentum \(the team shipped a Fedora Asahi Remix on the same day as upstream Fedora\), ongoing hardware support shortfalls such as USB‑C external‑display support, concerns about attempts to exploit permissive licensing for aggressive monetization, and continued graphics and driver development effort. The update describes work in progress rather than claiming finished, supported features for all Apple Silicon models.

hackernews · ackyshake · Nov 7, 05:20 · [Discussion](https://news.ycombinator.com/item?id=50401867)

**「Background」** Asahi Linux is a community project that ports the Linux kernel, device drivers, and an installer to run on Apple Silicon Macs; its progress reports track which drivers have been upstreamed and which hardware gaps remain. Earlier Asahi work included merging support for M3-series machines into the installer, which helps explain the current report’s focus on upstreaming SoC drivers and finishing remaining device support around the Linux 7.3 cycle.

**「Impact」** Users who depend on USB‑C external displays should expect that external monitor support remains incomplete and should not treat Asahi as a drop‑in replacement until that hardware gap is closed. Conversely, the team’s ability to ship a Fedora Asahi Remix alongside upstream releases reduces the lag for users and packagers who want up‑to‑date Fedora images for Apple Silicon.

**「Community discussion」** Comments emphasize two recurring points: end users frequently call out the missing USB‑C display support as a blocker for everyday use, and others raise questions about past decisions around permissive licensing after reports of attempts to hijack work for monetization. Some community members also point to alternate projects and contributions \(for example, work on Vulkan and newer CPU support\) as complementary efforts advancing Apple Silicon Linux support.

<details><summary>References</summary>
<ul>
<li><a href="https://asahilinux.org/2026/11/progress-report-7-3/">Progress Report: Linux 7.3 - Asahi Linux</a></li>
<li><a href="https://asahilinux.org/2026/09/m2-episode-1/">M2: Episode 1 (or, Asahi Linux on M3)</a></li>

</ul>
</details>

**Tags**: `#asahi-linux`, `#apple-silicon`, `#linux`, `#device-drivers`, `#open-source`

---

<a id="item-tech-news-4"></a>
### [Galaxy AI datacenter campus in Inner Mongolia](https://newsletter.semianalysis.com/p/we-visited-chinas-stargate-in-inner) ⭐️ 8.0/10

On-site reporting from Inner Mongolia describes Galaxy, an Envision-owned AI datacenter campus in Ulanqab planned for up to 800 MW of IT capacity, with its first 120 MW phase delivered within a year and reportedly built at roughly one-fifth the cost of comparable U.S. projects. The report says all four phases are being built-to-suit for two internet giants and that the campus is about the same size as the core of the U.S. &quot;Stargate Abilene&quot; buildout. Reporters observed extensive vertical integration: Envision reportedly builds nearby wind farms and a dedicated power line, operates a blade factory adjacent to the campus, manufactured battery storage to smooth load, co-designed a prefabricated substation, and implemented an 800 V low-voltage power system inside the site.

rss · Semianalysis · Nov 7, 19:01

**「Background」** Modern AI services are often hosted in purpose-built datacenter campuses that combine multiple high-density halls to deliver hundreds of megawatts up to gigawatt-scale IT capacity — a category exemplified by Stargate Abilene, the gigawatt-scale campus built for OpenAI. These projects depend on integrated power delivery \(on-site generation or dedicated transmission, substations, and battery smoothing\) and rapid, large‑scale construction, so deep vertical integration across energy, manufacturing, and building operations can materially reduce per‑megawatt costs and deployment time.

**「Impact」** If the reported speed and one-fifth cost are accurate, Chinese operators with vertically integrated energy-to-datacenter models can scale AI compute capacity faster and cheaper than many international peers, which may put pricing and capacity pressure on Western cloud and hyperscale providers; infrastructure planners and procurement teams should therefore update cost and timeline assumptions and monitor Chinese capacity additions when planning colocations or global deployments.

**Tags**: `#datacenter`, `#AI infrastructure`, `#China`, `#cloud`, `#industry-trends`

---

<a id="item-tech-news-5"></a>
### [Claude Code may leak users&\#x27; login email](https://github.com/anthropics/claude-code/issues/107757) ⭐️ 8.0/10

Multiple developers reported that Claude Code sometimes inserted users&\#x27; login email into outbound web requests, causing the address to be sent to external sites \(reports named Wikipedia and the U.S. Securities and Exchange Commission\) and triggering increased phishing messages. An Anthropic engineer said the login email had been added into the model context earlier to prevent the model from inventing author names; the issue was reported in July. Anthropic released a partial mitigation in version 2.1.317 that intercepts such leaks but users report it can be bypassed via Python scripts, and the company plans to remove the login email from the model context in a future release.

telegram · zaihuapd · Nov 7, 08:09

**「Background」** Claude Code is an automated coding agent that can perform web searches and make HTTP requests; multiple user reports say the agent placed the signed-in account email into the model context and sometimes transmitted it in request headers \(reported sent to sites such as Wikipedia and the U.S. SEC\), which users say led to a spike in scam messages. Anthropic has shipped a partial interception in version 2.1.317 to block the immediate leak and says it will remove the login email from the model context in a future release.

**「Immediate consequence and recommended action」** Teams using Claude Code&\#x27;s browsing or network features should assume login emails may have been exposed and take precautions: avoid using primary or production accounts with the feature until the context removal ships, monitor and filter incoming mail for targeted phishing, and rotate or restrict any credentials tied to exposed addresses if suspicious activity appears.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/anthropics/claude-code/issues/107757">Bug Report: Privacy violation in User-Agent header · Issue ...</a></li>
<li><a href="https://dev.to/axrisi/claude-code-email-in-user-agent-headers-how-it-happened-and-what-the-fix-covers-4i0p">Claude Code email in User-Agent headers: how it happened and ...</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#security`, `#AI-models`, `#Anthropic`, `#bug`

---

<a id="item-tech-news-6"></a>
### [Apple reveals humanoid robot HALO using two Qwen models](https://weibo.com/1642634100/RqjjGllvw) ⭐️ 8.0/10

An Apple research team submitted an arXiv paper \(reported Nov 4\) describing HALO, a three-layer humanoid-robot control system that combines two Qwen language models with a reinforcement‑learning motion tracker. The top layer uses Qwen3.6-35B-A3B for task orchestration, the middle layer uses Qwen3.5-2B to generate actions, and the bottom layer is an RL-trained action tracker; the authors report sim-to-real validation on a Yushu G1 robot executing tasks in unfamiliar real rooms. The paper reportedly includes the data-generation pipeline, model training, and deployment code and assets, according to the submission summary.

telegram · zaihuapd · Nov 7, 13:35

**「Conceptual background」** HALO&\#x27;s three-layer design—an LLM-based high-level planner, an LLM-based mid-level action generator, and a low-level controller trained with reinforcement learning—follows an emerging pattern in robotics that separates long-horizon task sequencing from precise motor tracking to aid sim-to-real transfer. The larger Qwen variant cited for HALO&\#x27;s top layer, Qwen 3.6-35B-A3B, is a Mixture-of-Experts family model reported to provide very large native context windows \(about 262,144 tokens\) and native function-calling capabilities, features that make it suitable for context-rich task orchestration.

**「Impact」** If the code and data are available as reported, robotics researchers and practitioners can examine and attempt to reproduce HALO&\#x27;s sim-to-real pipeline, but reproducing the results will require access to the specific Qwen models \(including the 35B variant\) and compatible hardware and compute; readers should check the arXiv paper and linked repository for license, model access requirements, and exact training/deployment details before attempting replication.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/empero-ai/Qwen3.8-35B-A3B-Distill">empero-ai/ Qwen 3 .8- 35 B - A 3 B -Distill · Hugging Face</a></li>

</ul>
</details>

**Tags**: `#robotics`, `#sim-to-real`, `#LLM-for-robotics`, `#reinforcement-learning`, `#Apple`

---

<a id="item-tech-news-7"></a>
### [GitHub Rubicon: 7200 pushes/s Git storage](https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/) ⭐️ 8.0/10

GitHub announced Rubicon, a new Git storage architecture designed for high-concurrency, agent-driven workloads; Rubicon stores Git objects in Azure Blob Storage, manages reference state with a Ref-CAS, and uses virtual replicas with background node-side compression. In internal tests GitHub reports supporting 5,000 concurrent agents and sustaining 7,200 pushes per second while keeping read latency low. Rubicon is currently in a limited private preview and is not yet generally available.

telegram · zaihuapd · Nov 7, 14:12

**「Technical background」** Rubicon separates Git&\#x27;s components across services: pack data are moved into Azure Blob Storage, refs and the pack manifest are managed by a Ref‑CAS, and API/Web requests are routed through Spokes to groups of virtual replicas that hold only cached state. This split \(durable pack storage + a reference CAS + lightweight, cache‑only replicas\) is the architectural change that enables many ephemeral replicas to serve a repository without each storing full pack files.

**「Impact」** Teams and organizations that run many concurrent automated agents or need very high push throughput should plan to request preview access and test representative workloads, because the reported scalability could reduce push contention and support larger agent-driven workflows, but the capability is not broadly available yet so you should not assume the numbers apply to your production repositories until you can validate them in preview or general availability.

<details><summary>References</summary>
<ul>
<li><a href="https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/">Inside GitHub &#x27;s new Git storage architecture - The GitHub Blog</a></li>

</ul>
</details>

**Tags**: `#git`, `#scalability`, `#distributed-storage`, `#ai-agents`, `#infrastructure`

---

<a id="item-tech-news-8"></a>
### [Microsoft Research &\#x27;AI Frontiers&\#x27; group reportedly ends](https://hunch.net/?p=13764006) ⭐️ 7.0/10

A community-posted report on Hacker News claims that Microsoft Research&\#x27;s &\#x27;AI Frontiers&\#x27; group — a unit described as focused on fundamental AI research — has been ended. The claim comes from community sources and is not confirmed by Microsoft or independent reporting, so the organizational change remains unverified. If correct, the change would remove an internal MSR team explicitly organized around exploratory, foundational AI work rather than product-driven scale projects.

hackernews · srean · Nov 7, 18:02 · [Discussion](https://news.ycombinator.com/item?id=50406563)

**「Background」** AI Frontiers was a Microsoft Research group that organized coherent, fundamental AI work and reportedly focused on efficient language models and agentic systems. A personal blog post archived on hunch.net and subsequent reporting say a researcher declared the AI Frontiers group over, while Microsoft’s lab page lists AI Frontiers as now part of “Microsoft AI,” which together suggest an internal re‑alignment rather than only an informal rumor.

**「Immediate consequence」** If the report is accurate, affected MSR researchers working on exploratory or non-transformer research could face reassignment, reduced internal support, or the need to seek roles elsewhere, shifting hiring and project funding toward scale-focused work; researchers and collaborators should monitor official Microsoft communications and job listings and consider contacting their MSR contacts for clarity or to preserve continuity of ongoing projects.

**「Community reactions」** Commenters argued this fits a broader industry trend favoring transformer-scale engineering over exploratory methods \(AnotherGoodName\), noted the report refers specifically to the &\#x27;AI Frontiers&\#x27; group rather than all MSR work \(smokel\), and described the development as evidence of changing internal culture and a broken research contract at Microsoft \(rhyperior\). These are community opinions and not independent confirmation of the organizational change.

<details><summary>References</summary>
<ul>
<li><a href="https://www.microsoft.com/en-us/research/lab/ai-frontiers/">Microsoft Research AI Frontiers - Microsoft Research</a></li>
<li><a href="https://businessexaminer.ca/victoria-articles/item/microsoft-researcher-john-langford-exits-as-ai-frontiers-group-is-declared/">Microsoft Researcher John Langford Exits as AI Frontiers Group Is...</a></li>
<li><a href="https://hunch.net/?p=13764006">The End of AI Frontiers – Machine Learning (Theory)</a></li>

</ul>
</details>

**Tags**: `#microsoft-research`, `#ai-research`, `#industry-news`, `#organizational-change`

---

<a id="item-tech-news-9"></a>
### [MaxxBench questions DeepSWE benchmark validity](https://maxxbench.unlap.ai/research/why-maxxbench/) ⭐️ 7.0/10

A MaxxBench analysis posted and discussed on Hacker News argues that DeepSWE scores for large language models can be unstable and may not reflect true generalization. The analysis recommends systematically varying task specifications \(prompt phrasing, scoring mode, input distributions\) as a basic robustness check, and reports that model-family differences appear — smaller models tend to &quot;collapse&quot; more — while also surfacing possible DeepSWE benchmark implementation bugs and odd API behavior \(for example around a reported &quot;max&quot; scoring mode\). These are analysis and community observations rather than independent, formal rebenchmarks, so they are best read as methodological warnings for benchmark users and model developers.

hackernews · antiuniverse · Nov 7, 17:19 · [Discussion](https://news.ycombinator.com/item?id=50406222)

**「Background」** DeepSWE is a coding-task benchmark whose leaderboard has been used to compare code-capable LLMs; MaxxBench is a targeted follow-up that systematically mutates 89 DeepSWE tasks \(changing instructions or starting code\) while keeping the median patch growth small \(17 lines, about 3.5%\) to test whether leaderboard scores generalize. MaxxBench reports that models which looked similar on DeepSWE can separate on these variants \(for example, reported score gaps of roughly 23 points and specific pairs moving to 71.9% vs. 63.5%\), which motivates its critique of DeepSWE-style evaluations.

**「Concrete consequence for practitioners」** Practitioners who rely on DeepSWE scores should not treat single-run numbers as definitive: they should run sensitivity tests that vary task specs and scoring modes, check for benchmark implementation issues \(including reported &\#x27;max&\#x27; mode quirks\), and compare family-level behavior because smaller models may fail qualitatively differently than larger ones.

**「Notable points from the Hacker News thread」** Commenters \(for example kqr and peri-cl\) endorsed varying a single parameter as a first-order generalization test and flagged consistent model-family patterns \(smaller models collapsing more\). Other contributors \(Systemerror7A69 and rao-v\) raised concerns about DeepSWE bugs and about labs&\#x27; training environments needing broader, intentionally varied RL-style tasks to avoid overfitting to simple benchmark scenarios.

<details><summary>References</summary>
<ul>
<li><a href="https://daily.dev/posts/maxxbench-nice-deepswe-score-but-is-it-true--ue9ulip60">MaxxBench – &quot;Nice DeepSWE score. But is it true?&quot;</a></li>
<li><a href="https://maxxbench.unlap.ai/research/why-maxxbench/">Introducing MaxxBench: Benchmarking Task Adaptation and ...</a></li>

</ul>
</details>

**Tags**: `#benchmarks`, `#LLM-evaluation`, `#robustness`, `#model-comparison`, `#AI-systems`

---

<a id="item-tech-news-10"></a>
### [Macs reportedly run undocumented family-member classifier](https://8rank.ai/game/apple-intelligence-personal-knowledge-graph) ⭐️ 7.0/10

A researcher posting on Hacker News and linking to 8rank.ai alleges that macOS on every Mac since 2022 includes undocumented background daemons whose purpose is to build a personal knowledge graph and a family-member classifier \(mapping people, relationships, communications, locations and events\). The claim is based on the author&\#x27;s analysis and follow-up research but is not independently verified in the discussion; the report frames the capability as an on-device machine‑learning feature that was not clearly documented to end users. The allegation has prompted privacy and on-device‑ML concerns among reviewers and administrators because it describes persistent, system‑level data collection and inference running without apparent explicit user consent or public documentation.

hackernews · infwhispers · Nov 7, 09:46 · [Discussion](https://news.ycombinator.com/item?id=50403097)

**「What a personal knowledge graph and on‑device classifier are」** A personal knowledge graph is a structured, local representation that links people, places, events and interactions inferred from device signals \(for example: contacts, communications, photos, calendar entries and location\); on‑device machine learning can use such a graph to disambiguate names, identify relationships \(like family members\), and make assistants or apps more context-aware. Vendors often implement those features as background services or small classifiers so the work is fast and private‑by‑design, but if such processes are undocumented or uncommunicated they create practical and policy questions about visibility, user control, and consent.

**「Immediate consequence for users and administrators」** Until the report is independently verified, security teams and privacy‑conscious users should treat the claim as a risk signal and audit macOS installations for unexpected daemons and data flows, review privacy permissions \(Photos, Contacts, Siri, and system analytics\), and monitor process and network activity for undocumented system services. Developers and operators of local LLMs or assistant integrations should avoid assuming undocumented OS behavior and explicitly document any reliance on system‑derived personal graphs, because such hidden capabilities can create compatibility, consent, and compliance complications.

**「What commenters are saying」** Some commenters argued such a graph would be useful if clearly opt‑in, while others pointed out Apple already builds contextual models \(for example, Photos face recognition and Siri features\) and suggested the suspected daemons would plausibly support natural‑language tasks like identifying which &quot;James&quot; a user means. Those statements are opinions and interpretations of observed Apple features rather than independent confirmation of the researcher&\#x27;s claims.

**Tags**: `#privacy`, `#apple`, `#macos`, `#on-device-ml`, `#personal-data`

---

<a id="item-tech-news-11"></a>
### [Discord Windows 11 client uses ~70% less RAM](https://www.windowslatest.com/2026/11/06/every-windows-11-app-should-kill-electron-and-discord-just-showed-why-no-starting-screen-and-70-less-ram-even-with-two-accounts-signed-in/) ⭐️ 7.0/10

A WindowsLatest report claims Discord&\#x27;s new Windows 11 client removes the startup splash and uses about 70% less RAM than the previous desktop app, even with two accounts signed in. The article and a strong Hacker News discussion present this as a shipped improvement to Discord&\#x27;s Windows 11 build, but the report provides limited technical detail and the memory and startup figures are not independently measured in the supplied account. The coverage frames the result as evidence in the ongoing debate about replacing Electron-based apps with more native or platform‑specific implementations.

hackernews · thunderbong · Nov 7, 11:11 · [Discussion](https://news.ycombinator.com/item?id=50403507)

**「Context on Discord&\#x27;s client change」** Discord has been rebuilding its desktop client using Rust, and an early Windows 11 build was reported to use about 290 MB of RAM, a substantial reduction compared with the widely used Electron-based client. Independent native-client projects demonstrate even smaller footprints \(one community project reports roughly 130 MB\), which is why reports of Discord&\#x27;s new build have reignited debate about replacing Electron with more native alternatives.

**「Practical consequence」** Engineering teams that ship cross‑platform desktop apps should treat this report as a prompt to benchmark their own clients: if a Windows‑specific build can materially cut memory use and startup time, teams should consider prototyping per‑platform UIs, optimizing packaging, or adding a Windows‑native codepath. The claim does not prove Electron is unusable for all projects, but it does support the concrete action of measuring live performance on target OS builds before committing to a single framework.

**「Community takeaways」** Commenters noted that Electron&\#x27;s main advantage remains a single web‑based codebase and good out‑of‑the‑box accessibility/IME support, while others pointed out Discord&\#x27;s history of switching frameworks \(desktop, mobile\) and argued teams should weigh code reuse, developer velocity, and platform features \(and suggested alternatives like Qt or Kotlin Multiplatform\). These are opinions about tradeoffs rather than independent verification of the reported memory reductions.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/RshaCuDeVidro/larperCord">GitHub - RshaCuDeVidro/larperCord: A native Discord client of about...</a></li>
<li><a href="https://wccftech.com/discord-is-ditching-electron-for-rust-with-early-windows-build-using-just-290mb-of-ram/">Discord Is Ditching Electron For Rust, With Early Windows Build...</a></li>

</ul>
</details>

**Tags**: `#electron`, `#desktop`, `#performance`, `#discord`, `#windows-11`

---

<a id="item-tech-news-12"></a>
### [Need for Speed Underground 2 in the browser](https://nfsu2.xyz/) ⭐️ 7.0/10

An unofficial browser port of Need for Speed: Underground 2 is live at https://nfsu2.xyz/ and runs the mid-2000s PC build with multiplayer in modern browsers. The project uses web-based emulation and reportedly leverages WebGPU and other modern web APIs to render and run the game, producing playable sessions on phones and desktops. The release is unofficial and legally uncertain, and some users report needing to enable unsafe WebGPU flags on Chromium/Linux to get it working.

hackernews · fluxusars · Nov 7, 09:36 · [Discussion](https://news.ycombinator.com/item?id=50403052)

**「How browser ports run old PC games」** Modern browser ports typically recompile native PC game code to WebAssembly and use WebGPU for rendering so the game can run at near-native speed in a tab, while a separate server or backend implements multiplayer and matchmaking. The nfsu2.xyz project follows that pattern: the game is rebuilt for WebAssembly/WebGPU and a hosted server provides online free‑roam and races, and users have reported platform-specific workarounds such as enabling unsafe WebGPU flags on Chromium/Linux.

**「Immediate consequence」** Players who want to use the site should be prepared to enable unsafe WebGPU flags on some platforms \(for example, Chromium on Linux\), and operators should expect copyright takedown risk—so avoiding soliciting donations or paid access is a prudent precaution.

**「Community reaction」** Commenters report strong nostalgia and surprise that the game runs smoothly in-browser, with users noting chaotic but fun multiplayer sessions and phone compatibility \(comments by macNchz and birdsongs\). Others highlighted legal and ethical concerns about distributing copyrighted games and warned against accepting donations for unofficial ports \(comments by popcar2 and rustyhancock\).

<details><summary>References</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50403052">Need for Speed Underground 2 online in the browser | Hacker News</a></li>
<li><a href="https://www.inxanitylabs.com/games/need-for-speed-underground-2-online">NFS Underground 2 Online: Browser Multiplayer , Free</a></li>
<li><a href="https://portedgames.com/need-for-speed-underground-2-browser/">NFS Underground 2 Browser Game: Play NFSU 2 Online at nfsu 2 . xyz</a></li>

</ul>
</details>

**Tags**: `#browser`, `#emulation`, `#webgpu`, `#game-preservation`, `#multiplayer`

---

<a id="item-tech-news-13"></a>
### [Turkey uses TraceART AI to recover looted antiquities](https://www.artnews.com/art-news/news/turkey-uses-ai-tech-100-looted-antiquities-us-1234804634/) ⭐️ 7.0/10

Turkey&\#x27;s Ministry of Culture used an AI platform called TraceART, together with lead‑isotope analysis and mold‑shape comparisons, to help identify and repatriate roughly 200 antiquities recovered from the United States now on display at the Istanbul Archaeology Museum. The exhibit highlights items including bronze statues looted in the 1960s from the ancient site labeled in the report as &quot;布尔本古城&quot; and 44 fired architectural slabs dated to about 700–480 BCE. According to the report, TraceART began scanning global auction sites and social media in 2025; Turkey has recovered more than 26,700 cultural objects since 1980.

telegram · zaihuapd · Nov 7, 03:43

**「Background」** Contemporary repatriation workflows often combine large-scale digital searches with physical-forensic verification: TraceART, an AI platform put into use in 2025, scans auction sites and social media for candidate matches to trafficked objects, while lead‑isotope analysis and mould‑shape comparison provide material and manufacturing evidence that can tie an item to a specific archaeological context. This two-step approach lets investigators find likely matches in online listings and then corroborate those leads with laboratory and comparative‑morphology tests.

**「Immediate consequence」** Museums, auction houses, and collectors should expect greater provenance scrutiny: national heritage authorities are increasingly combining online AI monitoring \(TraceART\) with scientific forensics, so institutions handling antiquities may need to review acquisition records and be prepared for repatriation claims based on online matches plus isotope or mold evidence.

<details><summary>References</summary>
<ul>
<li><a href="https://www.artnews.com/art-news/news/turkey-uses-ai-tech-100-looted-antiquities-us-1234804634/">Turkey Uses AI to Claw Back 100 Looted Antiquities from the US</a></li>

</ul>
</details>

**Tags**: `#AI for cultural heritage`, `#computer vision / image matching`, `#digital forensics`, `#artifact repatriation`

---

<a id="item-tech-news-14"></a>
### [Judge Allows Suit Over Anthropic&\#x27;s Claude Max Usage Claims](https://thenextweb.com/news/anthropic-claude-max-lawsuit-ruling-usage-claims) ⭐️ 7.0/10

A federal judge in the Northern District of California ruled that Anthropic must defend a lawsuit alleging its Claude Max pricing and usage marketing was misleading. The plaintiff says the $100 and $200 Claude Max tiers were advertised as providing 5× and 20× the usage of Pro, but when converted to a weekly basis the multipliers are about 3.5× and 6×. The court said the explanation that limits were session-based was located behind two hyperlinks on the sales page while customers pay monthly and could reasonably expect monthly-based figures. The judge allowed negligent misrepresentation and breach claims to proceed while dismissing California unfair competition and false advertising counts.

telegram · zaihuapd · Nov 7, 12:44

**「Claude Max pricing and prior complaint」** Anthropic marketed Claude Max as higher‑usage monthly tiers — a $100 &\#x27;Max 5x&\#x27; and a $200 &\#x27;Max 20x&\#x27; — billed as giving multiples of the usage available on the Pro plan. A class‑action complaint filed in June alleges those advertised multipliers and claimed savings were overstated, asserting Max 5x yields about 3.5× Pro and Max 20x only about 6–8× Pro, which is the factual basis for the litigation the judge allowed to proceed.

**「Immediate consequence」** Anthropic must litigate the surviving negligent misrepresentation and breach claims, which will likely trigger discovery into how Claude Max usage and session-based limits were presented and may impose legal costs or settlement risk. Product and marketing teams for AI services should review how usage multipliers and per-session versus per-month calculations are disclosed, because burying session-based details behind links while advertising monthly prices can be the basis for consumer-side claims.

<details><summary>References</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/anthropic-faces-class-action-over-claude-max-usage-limits">Anthropic faces class action over Claude Max usage limits | AI Weekly</a></li>
<li><a href="https://runtimewire.com/article/anthropic-faces-class-action-claim-over-claude-max-20x-limits">Anthropic faces class-action claim over Claude Max 20 x limits</a></li>

</ul>
</details>

**Tags**: `#legal`, `#AI companies`, `#pricing transparency`, `#product claims`

---

<a id="item-tech-news-15"></a>
### [Lawmaker urges ban on AI recursive self‑improvement](https://x.com/AlexBores/status/2118494668769878037) ⭐️ 7.0/10

U.S. Democratic representative Alex Bores publicly called on Congress to pass legislation this year banning AI recursive self‑improvement \(RSI\) — systems that automatically design or build the next generation of AI. Bores cited industry forecasts and a METR report he says show rapid AI R&amp;D acceleration, and referenced OpenAI’s stated goal to reach an automated “AI researcher” by March 2028 and an Anthropic employee prediction that AI could handle roughly 80% of frontier model development by the end of 2027. His statement is a policy appeal, not a law or formal proposal, and the post is a short repost of a tweet with limited technical detail or enforceability language.

telegram · zaihuapd · Nov 8, 01:30

**「What is recursive self‑improvement \(RSI\) and why it matters」** Recursive self‑improvement \(RSI\) refers to AI systems that autonomously design or build successive, more capable AI systems, which can in principle accelerate capabilities generation beyond human direction. Major AI labs have publicly discussed progress toward automating parts of AI research and published projections that such automation could handle substantial portions of model development in the late 2020s, which is the forecasting Bores cited in urging legislative action.

**「Immediate consequence」** The call increases pressure on congressional staff and regulators to define RSI clearly and consider verification and enforcement mechanisms; stakeholders \(legislative offices, agencies, and AI labs\) should be prepared to supply technical definitions, timelines, and evidence about development capabilities if hearings or draft bills follow. Because the statement rests on cited forecasts and a report rather than enacted rules, labs may face reputational and political scrutiny but not new legal requirements until legislation is proposed and passed.

<details><summary>References</summary>
<ul>
<li><a href="https://www.anthropic.com/institute/recursive-self-improvement">Our progress toward recursive self - improvement , and its implications.</a></li>
<li><a href="https://time.com/article/2026/08/07/ai-recursive-self-improvement-anthropic-openai/">time.com/article/2026/08/07/ ai - recursive - self - improvement ...</a></li>

</ul>
</details>

**Tags**: `#ai-policy`, `#ai-safety`, `#governance`, `#recursive-self-improvement`, `#legislation`

---

## Financial News

<a id="item-finance-news-1"></a>
### [SoftBank and ABB weigh China carve‑out to rescue $5.4bn robotics deal](https://www.bloomberg.com/news/articles/2026-11-07/softbank-abb-weigh-china-carve-out-to-salvage-robotics-deal) ⭐️ 8.0/10

SoftBank and ABB are considering carving out ABB’s China robotics operations to try to salvage a $5.4 billion takeover that China’s investment review office has halted; the China unit is estimated at $2–3 billion, Bloomberg reports \(estimate and reported halt\).

telegram · zaihuapd · Nov 7, 11:24

**「background」** China’s foreign investment security review office this week stopped the original $5.4 billion deal, and ABB is reportedly assessing other options including finding a different buyer, with both companies declining to comment.

**「impact」** If used to salvage the transaction, a China-only carve-out would directly affect SoftBank and ABB by shrinking the assets sold and changing the deal’s valuation and ownership of the China robotics operations.

**Tags**: `#M&amp;A`, `#China investment review`, `#Robotics industry`, `#SoftBank`, `#ABB`

---

<a id="item-finance-news-2"></a>
### [Nationwide financial inspection launched for temples and Daoist sites](https://www.163.com/dy/article/LB2VSRQD0556HNS1.html) ⭐️ 8.0/10

A nationwide financial inspection has been launched covering 33,500 temples and more than 9,000 Daoist sites, the NetEase report says; the report says already‑contracted commercial operations must be returned and financing/listing channels must be cut \(reported\).

telegram · zaihuapd · Nov 7, 15:02

**「background」** A nationwide financial inspection has been launched across 33,500 temples and more than 9,000 Daoist sites to curb commercialization of religious venues; reported measures include returning contracted operations, cutting listing and financing channels, requiring third‑party audits for higher‑revenue sites, centralizing and publicly disclosing donation and account handling, and checking clergy members&\#x27; external investments and commercial ties.

**「impact」** The measures directly affect religious institutions, clergy, and firms or investors tied to temples by forcing contract rollbacks, cutting financing/listing routes and imposing audits and tighter controls on donations and clergy business ties \(reported\).

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/1992513/djy/blob/master/gb/26/11/5/n14883359.md">djy/gb/26/11/5/n14883359.md at master · 1992513/djy · GitHub</a></li>

</ul>
</details>

**Tags**: `#regulatory action`, `#religious sector`, `#compliance`, `#audit`, `#China`

---

<a id="item-finance-news-3"></a>
### [Berkshire accelerates buybacks as earnings fall](https://www.cnbc.com/2026/11/07/berkshire-hathaway-q3-2026-earnings-buybacks.html) ⭐️ 7.0/10

Berkshire Hathaway said it repurchased $9.6 billion of stock in Q3 2026, more than double the $4.5 billion repurchased in Q2 \(company report\). Operating earnings fell 5.8% year‑over‑year to $12.705 billion and overall earnings fell 28% to $22.112 billion \(company report\).

rss · CNBC Finance · Nov 7, 15:23

**「Context」** The buybacks lift Berkshire&\#x27;s 2026 total repurchases to about $14.4 billion and followed a 43% year‑over‑year drop in insurance underwriting to $1.352 billion, which largely drove the profit decline \(company report\).

**「Direct market effect」** Investors are the most directly affected: the $9.6 billion repurchase program reduces shares outstanding and coincided with Berkshire Class A shares rising more than 12% over the past month while the S&amp;P 500 fell 5.5% \(company report\).

**Tags**: `#Berkshire Hathaway`, `#share buybacks`, `#earnings`, `#insurance`, `#cash holdings`

---