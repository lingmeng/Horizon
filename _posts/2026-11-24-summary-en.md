---
layout: default
title: "Horizon Summary: 2026-11-24 (EN)"
date: 2026-11-24
lang: en
---

> From 39 items, 20 important content pieces were selected

---

**Technology News**
1. [NVIDIA board reinstates Jensen Huang as CEO](#item-tech-news-1) ⭐️ 9.0/10
2. [GLM-5.4: first loop transformer](#item-tech-news-2) ⭐️ 8.0/10
3. [NariQ: BF16-level Qwen3.8-27B in a 10 GB file](#item-tech-news-3) ⭐️ 8.0/10
4. [Codex2api suspected supply-chain compromise](#item-tech-news-4) ⭐️ 8.0/10
5. [Alpöge/Claude Lean &\#x27;proof&\#x27; of Riemann criticized](#item-tech-news-5) ⭐️ 8.0/10
6. [45,000 EU Groups Ask EU to Challenge Apple&\#x27;s iPhone Browser Rules](#item-tech-news-6) ⭐️ 8.0/10
7. [Singapore Won&\#x27;t Be Conduit for Evading U.S. Chip Controls](#item-tech-news-7) ⭐️ 8.0/10
8. [Anthropic: Claude claims VP ≠ VNP \(Lean 4 formalization\)](#item-tech-news-8) ⭐️ 8.0/10
9. [Arm requests community mirror takedown \(Dec 4, 2026\)](#item-tech-news-9) ⭐️ 7.0/10
10. [Stalwart: drop-in replacement for Microsoft Exchange](#item-tech-news-10) ⭐️ 7.0/10
11. [Ladybird browser alpha release](#item-tech-news-11) ⭐️ 7.0/10
12. [Meta AI head warns superintelligence is arriving](#item-tech-news-12) ⭐️ 7.0/10
13. [HarmonyOS terminals surpass 100 million devices](#item-tech-news-13) ⭐️ 7.0/10
14. [Shenzhou-24 set for Nov 25 launch with Pakistani astronaut](#item-tech-news-14) ⭐️ 7.0/10

**Technology Blog**
1. [vLLM Day-0 Support for ERNIE 5.5 Flash](#item-tech-blog-1) ⭐️ 8.0/10

**Financial News**
1. [NY Fed&\#x27;s Williams Signals Further Rate Action &\#x27;Over Time&\#x27;](#item-finance-news-1) ⭐️ 8.0/10
2. [Nvidia reinstates Jensen Huang, prompting relief rally](#item-finance-news-2) ⭐️ 8.0/10
3. [Anthropic IPO triggers selloff, clouds Chinese AI listings](#item-finance-news-3) ⭐️ 8.0/10
4. [Shanghai raises metro fares after 21 years](#item-finance-news-4) ⭐️ 8.0/10
5. [SpaceX reportedly renting compute capacity to Anthropic and Google](#item-finance-news-5) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [NVIDIA board reinstates Jensen Huang as CEO](https://nvidianews.nvidia.com/news/nvidia-board-reinstates-jensen-huang-as-president-ceo-and-board-director) ⭐️ 9.0/10

NVIDIA&\#x27;s board unanimously reinstated Jensen Huang as president, chief executive officer, and board director effective immediately after consulting senior U.S. government officials. The board said it is confident Huang&\#x27;s return poses no national-security risk, named Colette Kress to resume the chief financial officer role \(she had served as interim CEO\), and announced an independent investigation committee made up of independent directors. The board also created a national-security and export-control committee and has begun recruiting a chief compliance officer; Huang said he will fully cooperate with the investigation.

telegram · zaihuapd · Nov 23, 14:02

**「Background」** The board previously placed Colette Kress in the interim CEO role while reports circulated that Huang had been targeted by foreign intelligence activity, a development that prompted the board to consult U.S. officials. The new actions are framed as responses to those reports and to the board&\#x27;s review of any potential national-security implications.

**「Impact」** Because the board has created a national-security and export-control committee and is hiring a chief compliance officer, NVIDIA partners, customers, and vendors should expect more formalized export-control and compliance processes and should review their documentation and approval workflows for shipments or licensing tied to NVIDIA products. Investors and corporate governance watchers should also expect the independent investigation to drive further disclosure or governance changes depending on its findings.

**「Community discussion」** Commenters highlighted the board&\#x27;s statement that consultations with senior U.S. officials were decisive in concluding there is no national-security risk, and some argued that legal standards \(citing Delaware Caremark precedent\) plus any non-prosecution advice reduce board liability. Others noted surprise at the board&\#x27;s unanimous reversal after quickly installing an interim CEO and raised concerns about perceived inconsistencies in how export controls and enforcement are applied.

**Tags**: `#nvidia`, `#leadership`, `#national-security`, `#ai`, `#corporate-governance`

---

<a id="item-tech-news-2"></a>
### [GLM-5.4: first loop transformer](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai published GLM-5.4, their first model using a loop transformer: a group of weight‑shared layers runs for multiple iterations per forward pass to refine hidden states, producing a deeper effective network without increasing parameter count. GLM-5.4 weights are not public; the model is available through Z.ai&\#x27;s hosted API but currently requires the Coding Plan subscription \(the Coding Plan API key worked with Z.ai&\#x27;s OpenAI‑compatible Responses API at https://api.z.ai/api/v1\). Independent tests in the post show GLM-5.4&\#x27;s generated images/text \(the author&\#x27;s &quot;pelican&quot; examples\) look similar in quality to GLM-5.3 and comparable to outputs from OpenAI and Anthropic models.

hackernews · foohis · Nov 23, 10:06 · [Discussion](https://news.ycombinator.com/item?id=50609685)

**「Why loop transformers matter」** In a standard Transformer each layer is computed once per forward pass; a loop transformer repeats a group of weight‑shared layers across multiple iterations to iteratively refine hidden states, yielding greater effective depth without adding parameters. The post also notes a recent similar looped‑transformer claim from Thinking Machines Lab&\#x27;s Inkling 2 Mini.

**「Concrete consequence for users and integrators」** Because GLM-5.4&\#x27;s weights are not released, organizations cannot run it locally and must use Z.ai&\#x27;s hosted endpoint; developers who want access need the Coding Plan subscription and should update clients/plugins to request the new model via Z.ai&\#x27;s OpenAI‑compatible Responses API at https://api.z.ai/api/v1, since existing plugins \(for example, llm-zai\) did not yet support the model at the time of the post.

**「What commenters focused on」** Readers praised Z.ai&\#x27;s technical transparency and said loop transformers are a natural direction, while some reported that Chinese models can exhibit slower, &quot;second‑guessing&quot; behavior in practice. Other commenters highlighted the engineering rationale: loop transformers can reduce inference memory‑bandwidth pressure by reusing weights and computing deeper representations without transferring more parameters.

**Tags**: `#loop-transformer`, `#LLM-release`, `#model-architecture`, `#API-access`

---

<a id="item-tech-news-3"></a>
### [NariQ: BF16-level Qwen3.8-27B in a 10 GB file](https://huggingface.co/nari-labs/Qwen3.8-27B-NariQ-GGUF) ⭐️ 8.0/10

NariQ presents 3-bit-and-lower quantizations of Qwen3.8-27B claiming near-BF16 quality on multiple benchmarks and context lengths, with provided numeric comparisons and a required llama.cpp fork.

hackernews · toebee · Nov 23, 13:42 · [Discussion](https://news.ycombinator.com/item?id=50611402)

**Tags**: `#quantization`, `#model-compression`, `#inference-performance`, `#benchmarks`, `#Qwen3.8`

---

<a id="item-tech-news-4"></a>
### [Codex2api suspected supply-chain compromise](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 8.0/10

A community report alleges a supply‑chain compromise of the Codex2api project: the maintainer account was reportedly breached and an attacker pushed a tagged release that produced a backdoored build. The report says release v3.1.11 removed authentication \(allegedly allowing unauthenticated remote command execution\) and that a malicious GitHub Actions workflow exfiltrated 16 Actions secrets, impacting at least 21 repositories under the same account. Users who installed or updated versions 3.1.10–3.1.12 are urged to disable those installs, roll back to v3.1.9, and rotate credentials. This account is based on community/Telegram reporting and has not been independently verified here.

telegram · zaihuapd · Nov 23, 11:21

**「Background」** Codex2API is a high‑performance reverse proxy and management system that converts pools of upstream Codex/OpenAI accounts into a unified, OpenAI‑compatible API gateway and is offered as deployable releases and self‑hosted gateway software. Because those releases and any bundled GitHub Actions workflows run code on install or in the repository context, a malicious tagged release or injected workflow can both introduce server backdoors \(including remote execution\) and exfiltrate Actions secrets such as tokens, SSH keys, or upstream credentials.

**「Immediate action」** If you used Codex2api v3.1.10–3.1.12 or store secrets in repositories using the same account, assume potential credential compromise: disable or remove the affected releases and workflows, roll back to v3.1.9, rotate GitHub tokens, SSH keys, database credentials and other service keys \(the report specifically mentions DeepSeek\), and audit repository settings and recent workflow runs for unauthorized activity.

<details><summary>References</summary>
<ul>
<li><a href="https://codex2api.net/">Codex2API .net</a></li>
<li><a href="https://deepwiki.com/james-6-23/codex2api">james-6-23/ codex2api | DeepWiki</a></li>

</ul>
</details>

**Tags**: `#supply-chain`, `#security`, `#RCE`, `#GitHub Actions`, `#open-source`

---

<a id="item-tech-news-5"></a>
### [Alpöge/Claude Lean &\#x27;proof&\#x27; of Riemann criticized](https://x.com/i/web/status/2124987173439209561) ⭐️ 8.0/10

Alpöge and Claude released a Lean formalization claiming proofs of the Riemann hypothesis and a generalized version but published only a massive codebase—about 17 million lines across roughly 175,000 files—without a human‑readable proof. The Lean/Mathlib community reportedly said the next day they had &quot;sufficient confidence&quot; that the code verifies the stated propositions. Researchers then flagged that key definitions appear written as tautologies and some geometric conditions are effectively vacuous, prompting doubts the formalization contains substantive mathematics; on the 23rd Alpöge reportedly admitted the repository is &quot;full of garbage but compiles&quot; and called the criticism reasonable. This account comes from a social‑media report and does not include independent verification.

telegram · zaihuapd · Nov 24, 01:29

**「Why a Lean archive matters」** Proof assistants such as Lean represent mathematical statements and arguments as machine-checkable code, so a claimed proof can be distributed as a formal development that the verifier accepts. Levent Alpöge published an online Lean archive of roughly 175,187 files \(about 17.4 million lines\); observers report that at least one group compiled the archive without errors and that two organizations were reported to have inspected or verified the development.

**「Impact」** The episode shows that a proof assistant build that compiles is not by itself proof of meaningful mathematics: reviewers and maintainers should audit definitions and the intent behind encodings rather than equating compilation with a correct, human‑interpretable proof. Responsible release and review practices prompted by this case should include publishing a concise, human‑readable proof sketch, curated minimal reproducible files that demonstrate the core argument, and explicit checks that key definitions are non‑trivial.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=aDl7-MWFLVc">17 Million Lines Claim to Prove Riemann . We Ran Them. - YouTube</a></li>
<li><a href="https://www.theguardian.com/technology/2026/nov/21/anthropic-riemann-hypothesis-solved-claude-ai">Two groups verify mathematician’s claim that Claude ... | The Guardian</a></li>
<li><a href="https://math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/">Alpöge / Claude proof of the Generalized Riemann Hypothesis</a></li>

</ul>
</details>

**Tags**: `#formal-verification`, `#AI-assisted-proof`, `#reproducibility`, `#open-source`, `#math-foundations`

---

<a id="item-tech-news-6"></a>
### [45,000 EU Groups Ask EU to Challenge Apple&\#x27;s iPhone Browser Rules](https://appleinsider.com/articles/26/11/23/eu-urges-to-challenge-apples-grip-on-iphone-browsers?utm_source=rss) ⭐️ 8.0/10

About 45,000–55,000 EU organisations, including Mozilla and Shopify, have jointly petitioned the European Commission to open a case challenging Apple’s iPhone browser restrictions. The signatories say that although the Digital Markets Act \(DMA\) technically permits third‑party browsers to use non‑WebKit engines in the EU, technical and legal requirements still effectively lock users to WebKit and keep businesses reliant on the App Store. The petitioners estimate that if many native iOS apps moved to the web, EU organisations could save roughly €11 billion per year in development costs and €1.3 billion per year in App Store fees; the signatures were gathered through December 3, 2026. These figures and claims come from the petitioning organisations and have not been independently verified.

telegram · zaihuapd · Nov 24, 03:02

**「Why the DMA matters here」** The EU&\#x27;s Digital Markets Act obliged designated gatekeepers such as Apple to permit alternative browser engines and to open app-distribution options within the EU, and Apple revised its policies to reflect those obligations. The petitioners say those policy changes have not eliminated practical WebKit lock‑in or the App Store&\#x27;s central role, because remaining technical and contractual requirements still make it difficult for developers and users to shift away from WebKit and App Store reach.

**「Likely immediate consequence」** The coordinated petition increases pressure on the Commission to consider enforcement or an investigation under the DMA and competition rules; affected developers and browser vendors should monitor proceedings, document technical compatibility and migration costs, and test web‑first strategies on iOS because any regulatory remedy could require technical changes or create new compatibility obligations.

**Tags**: `#regulation`, `#Apple`, `#iOS`, `#web browsers`, `#EU DMA`

---

<a id="item-tech-news-7"></a>
### [Singapore Won&\#x27;t Be Conduit for Evading U.S. Chip Controls](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 8.0/10

Singapore&\#x27;s prime minister Lawrence Wong said the city-state will not be used as a conduit to circumvent U.S. chip export controls, and authorities are investigating Megaspeed&\#x27;s purchases of NVIDIA chips. The U.S. Commerce Department has placed Megaspeed and six other Southeast Asian firms on a trade blacklist over a described &quot;significant risk&quot; of transferring advanced computing products to unauthorized users; the list reportedly includes affiliates in Malaysia and Thailand and names Apex Enterprise Solutions, a Singapore unit of Alibaba, which denies transferring regulated chips. These statements describe an ongoing investigation and policy enforcement stance rather than a completed enforcement action by Singaporean authorities.

telegram · zaihuapd · Nov 24, 05:03

**「Background」** U.S. export controls on advanced computing chips are enforced in part through Commerce Department entity listings and trade blacklists that restrict which companies can receive sensitive processors.  The Commerce Department recently added Singapore-based Megaspeed and several Southeast Asian affiliates to a blacklist over alleged risks of transferring advanced computing products to unauthorized users, which is the immediate context for the Singapore prime minister&\#x27;s statement that the city‑state will not be used to evade those controls.

**「Impact」** Companies that route or broker advanced computing chips through Singapore should expect increased export-control scrutiny and possible disruption to supply chains: firms named on the U.S. trade blacklist may face limits on acquiring U.S.-origin advanced compute products, and partners in Singapore can expect enquiries or audits. Organizations handling high-performance GPUs or other controlled semiconductors should review end-use screening, preserve export-compliance documentation, and seek required U.S. export licenses before transfers to avoid enforcement risk.

<details><summary>References</summary>
<ul>
<li><a href="https://www.indiatoday.in/world/story/megaspeed-us-blacklist-nvidia-export-control-espionage-probe-3045532-2026-11-24">Megaspeed US blacklist : Nvidia customer faces export control and...</a></li>
<li><a href="https://www.ft.com/content/ce6d292e-eaaa-4c23-b909-34276e1a1e8d?syn-25a6b1a6=1">Bessent blames Lutnick’ s commerce department for failure to...</a></li>

</ul>
</details>

**Tags**: `#export-controls`, `#semiconductors`, `#supply-chain`, `#AI-hardware`, `#geopolitics`

---

<a id="item-tech-news-8"></a>
### [Anthropic: Claude claims VP ≠ VNP \(Lean 4 formalization\)](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 8.0/10

Anthropic published a paper titled “VP ≠ VNP over every field” and a Lean 4 formalization on 2026-11-24, saying the result was discovered and written by an internal Claude model and is available in the Anthropic/formal-math repository. The paper presents a superpolynomial arithmetic-circuit lower bound for the Hamiltonian-cycle polynomial and uses that to conclude VP is a proper subset of VNP \(the algebraic analogue of Valiant’s 1979 conjecture\); the claim applies to arithmetic circuits only and does not address P vs NP. The repository reports that the formalization passed three standard axiom audits and an independent kernel review \(named nanoda\), contains no remaining sorrys except reserved files, but has not been read and validated by human mathematicians; Lean itself cannot confirm that the formal statements exactly match the informal claimed theorem, and Appendix Q lists the discrepancies pending independent review.

telegram · zaihuapd · Nov 24, 06:02

**「Background」** VP and VNP are classes in algebraic complexity theory; Valiant&\#x27;s 1979 conjecture that VP ≠ VNP \(for arithmetic circuits\) is an algebraic analogue of the P versus NP question but applies only to arithmetic circuits, so a proof about VP ≠ VNP would not itself resolve P versus NP. Anthropic says the claimed proof and the accompanying Lean 4 formalization were produced by an internal Claude model; Claude is a family of large language models developed by Anthropic.

**「Immediate consequence」** Researchers and reviewers should treat the claim as provisional: if the formalization is correct it would resolve Valiant’s algebraic complexity conjecture for arithmetic circuits, but independent human verification is required before the community accepts the result or cites it as established. The practical action is for complexity theorists and Lean users to pull the Anthropic/formal-math repository, run the Lean 4 checks, inspect Appendix Q’s reported mismatches, and perform independent formal and informal verification rather than relying solely on the repository’s automated audits.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Anthropic">Anthropic - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#algebraic-complexity`, `#formal-verification`, `#AI-generated-research`, `#VP-vs-VNP`

---

<a id="item-tech-news-9"></a>
### [Arm requests community mirror takedown \(Dec 4, 2026\)](https://arm.jonpalmisc.com/) ⭐️ 7.0/10

A Hacker News thread reports that Arm has asked the operator of a community-hosted mirror of its documentation \(https://arm.jonpalmisc.com/\) to discontinue the site on 4 December 2026. The site owner says Arm&\#x27;s request cites use of Arm trademarks and intellectual property in the hosted documentation; the owner reports offers from volunteers to host mirrors, and is considering legal advice or publishing the site&\#x27;s source without Arm IP as options. This account is from the public discussion and has not been independently verified.

hackernews · tech234a · Nov 23, 19:17 · [Discussion](https://news.ycombinator.com/item?id=50617499)

**「Why a community mirror matters」** The Hacker News thread is about a community-hosted mirror of Arm&\#x27;s architecture documentation that the site operator reports Arm has asked to be removed; developers rely on consolidated archives like this because they make multiple ISA documents and historical versions easier to search, cross-reference, and cite. Commenters note that Arm publishes a machine-readable architecture spec \(MRAS\) and that some MRAS releases are described as having a BSD-style license, which is why participants in the discussion say the legal basis for the takedown \(trademark, copyright on conversions, or other IP\) appears ambiguous.

**「Impact」** Developers and projects that rely on the consolidated, community-hosted copy of Arm documentation may lose that convenient access after 4 December 2026 and should plan to obtain needed references from official Arm channels, local copies, or an alternative mirror. The report indicates maintainers and volunteers are exploring mirrors and legal options, so short-term continuity may depend on whether alternative hosts appear and on license or trademark constraints asserted by Arm.

**「Community discussion」** Comments in the thread debate the legality and fairness of the takedown request: some say documenting publicly released hardware should be fair use, while others note Arm&\#x27;s trademark and IP claims. Participants suggested hosting mirrors, consulting lawyers, or releasing the site&\#x27;s source without Arm IP, and also criticized the company&\#x27;s enforcement as harmful to developers; those are opinions from the discussion, not independent findings.

<details><summary>References</summary>
<ul>
<li><a href="https://www.autozone.com/">AutoZone - Official Site</a></li>

</ul>
</details>

**Tags**: `#arm`, `#documentation`, `#legal`, `#developer-tools`, `#open-source`

---

<a id="item-tech-news-10"></a>
### [Stalwart: drop-in replacement for Microsoft Exchange](https://stalw.art/blog/microsoft-exchange-replacement/) ⭐️ 7.0/10

Stalwart&\#x27;s team published a blog post presenting Stalwart as a drop-in, open-source replacement for Microsoft Exchange aimed at organizations running on-prem Exchange. The post asserts interoperability with Exchange protocols and management workflows, but those are vendor claims rather than independently verified, shipped capabilities. Public evidence of full Outlook compatibility and enterprise features such as regulatory-proof immutable archiving is limited, so administrators should treat the &quot;drop-in&quot; characterization cautiously. The announcement is most relevant to sysadmins and organizations evaluating on-prem Exchange alternatives, but compatibility and compliance testing will be required before any migration.

hackernews · shaunpud · Nov 23, 22:32 · [Discussion](https://news.ycombinator.com/item?id=50620349)

**「Why Exchange compatibility matters」** For more than twenty years, many organizations treated Microsoft Exchange as their standard on‑premises mail server and Outlook as the default mail client; Stalwart 1.2.0 is announced as a &quot;drop‑in replacement&quot; for that pair. Understanding this matters because being a drop‑in replacement implies substituting the server role Exchange filled in existing Outlook‑centric deployments without requiring a wholesale client or workflow change.

**「Test Outlook integration and compliance archiving before replacing Exchange」** Administrators should not assume Stalwart is a seamless, production-ready swap for on‑premises Exchange: commenters flagged real compatibility and compliance gaps \(notably Outlook MAPI/calendar/contacts/search behavior and the absence of immutable archiving in some plans, with GoBD cited as an example\). Before migrating, run a pilot with the representative Outlook versions your users run, verify mailbox, calendar, GAL, search, and delegation features, and ensure you have an independent, tamper‑proof archiving/retention solution if your jurisdiction requires it; otherwise you risk functional regressions or regulatory noncompliance that negate the claimed operational or licensing benefits.

**「Community reaction」** Hacker News commenters raised concrete concerns: Outlook&\#x27;s evolving handling of Exchange and IMAP could limit client compatibility, a commenter noted German regulatory archiving requirements \(GoBD\) that Stalwart&\#x27;s standard or OSS plans reportedly do not meet, and others argued that supporting Exchange protocols perpetuates Microsoft-centric lock-in. Some users also made operational claims \(for example, that Mozilla&\#x27;s Thunderbird uses Stalwart as its mail server\); those are user reports from the thread and were not independently confirmed there.

<details><summary>References</summary>
<ul>
<li><a href="https://stalw.art/blog/microsoft-exchange-replacement/">Stalwart is now a drop - in replacement for Microsoft Exchange</a></li>
<li><a href="https://en.wikipedia.org/wiki/Microsoft">Microsoft - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#email`, `#open-source`, `#sysadmin`, `#interoperability`, `#compliance`

---

<a id="item-tech-news-11"></a>
### [Ladybird browser alpha release](https://ladybird.org/posts/alpha/) ⭐️ 7.0/10

Ladybird published its first alpha with downloadable builds for macOS and Linux so users can install without compiling. The browser is largely implemented from scratch — including HTML parsing, a CSS engine, layout, JavaScript, and WebAssembly — while reusing components such as HarfBuzz \(text shaping\), Skia \(2D graphics\), ffmpeg \(video\), and SQLite. The project reports large web-platform-tests gains in October and early reviewers report broad site compatibility, but the release is explicitly alpha: some sites won’t work and crashes are expected; the browser includes in-product bug reporting and optional crash reports.

hackernews · janvdberg · Nov 23, 16:13 · [Discussion](https://news.ycombinator.com/item?id=50614249)

**「Prerequisite context」** Ladybird is a from‑scratch, open‑source web browser that implements its own HTML parser, CSS engine, layout system, JavaScript engine and WebAssembly support while relying on external libraries for text shaping \(HarfBuzz\), 2D graphics \(Skia\), video \(ffmpeg\) and SQLite. Earlier in 2026 the project ported parts of its JavaScript engine to Rust and used AI coding agents to land large numbers of fixes to the web‑platform‑tests suite, and the alpha release now provides downloadable macOS and Linux builds so users can install without compiling.

**「Immediate consequence for users and testers」** Anyone on macOS or Linux can now try a from‑scratch browser implementation and submit bug reports or crash reports directly from the product; maintainers are explicitly soliciting testing and security inspection. Testers should avoid relying on Ladybird as a daily driver yet, expect occasional crashes and incomplete features \(for example, a reported service-worker startMessages error broke one Pyodide-based app\), and treat it cautiously for sensitive browsing until privacy and fingerprinting behaviors are audited and hardened.

**「What people are saying」** Early commenters praised Ladybird’s surprising web-compatibility and lightweight UI but reported issues like slightly jerky scrolling; others urged stronger anti‑fingerprinting and finer permission controls, and emphasized caution while it remains alpha.

**Tags**: `#browser`, `#open-source`, `#web-compatibility`, `#systems`, `#privacy`

---

<a id="item-tech-news-12"></a>
### [Meta AI head warns superintelligence is arriving](https://thenextweb.com/news/metas-ai-chief-says-superintelligence-is-arriving-and-control-is-at-risk) ⭐️ 7.0/10

Alexandr Wang, Meta’s chief AI officer and head of its Superintelligence Lab, posted on X saying superintelligence is no longer a distant concern. He pointed to a reported Claude-assisted proof of the Riemann hypothesis—attributed to mathematician Levent Alpöge and said to have been machine-checked by the Lean/Mathlib community—as evidence that AI capabilities now approach top human mathematicians, while noting the proof currently has no human-readable version. Wang warned that systems capable of unbounded self-improvement or those &quot;1000x&quot; smarter than humans would be difficult to control and called for urgent investment in safety, alignment, and defensive research. These remarks are a public claim by Wang and have not been shown here to have independent technical verification.

telegram · zaihuapd · Nov 23, 12:49

**「Proof assistants and the Claude-assisted Riemann claim」** Formal proof assistants such as Lean let mathematicians write definitions and arguments as machine-checkable code, producing a certificate that a computer can verify even when the exposition is long or differs from a human-readable paper.  According to reporting that verified the event, mathematician Levent Alpöge said he worked with Anthropic’s Claude to produce a proof of the Riemann hypothesis and a Lean formalization of that solution was independently checked by two organizations, which is the verification step commentators cite as evidence of machine-checked correctness.

**「Impact」** For AI developers, funders, and policy makers, Wang’s statement implies a need to reprioritize resources toward interpretable verification, alignment research, and defensive measures; reviewers and organizations should require human-readable proofs and independent checks before treating machine-generated, machine-checked results as definitive evidence of new capabilities.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theguardian.com/technology/2026/nov/21/anthropic-riemann-hypothesis-solved-claude-ai">Two groups verify mathematician’s claim that Claude ... | The Guardian</a></li>

</ul>
</details>

**Tags**: `#AI safety`, `#superintelligence`, `#AI capabilities`, `#formal verification`, `#industry news`

---

<a id="item-tech-news-13"></a>
### [HarmonyOS terminals surpass 100 million devices](https://www.xinhuanet.com/20261124/68842538167d4e59a875056d5eb885ad/c.html) ⭐️ 7.0/10

Huawei announced that devices running HarmonyOS 5, 6, and 7 — including phones, tablets, and PCs — have exceeded 100 million units in active terminals. The company says the HarmonyOS ecosystem now offers more than 460,000 apps and services and has over 12 million registered developers. Huawei also reported open-source figures of about 14,000 contributors, more than 120 industry distributions, over 160 partner-contributed features integrated into 1,600+ apps, and that related feature usage rose about 90× in one year; these are company-reported milestone figures and are not independently verified.

telegram · zaihuapd · Nov 24, 01:46

**「Context on HarmonyOS」** HarmonyOS is Huawei’s cross-device operating system first published in 2019; Huawei released a &quot;native Harmony&quot; variant in October 2024 and now ships OS versions labeled HarmonyOS 5–7 for phones, tablets, and PCs. The project has an open-source upstream that the company reports includes more than 14,000 contributors and over 120 industry distribution builds, which helps explain the ecosystem-focused metrics in the announcement.

**「Immediate consequence」** For developers and hardware partners, the announcement increases the platform&\#x27;s apparent reach inside Huawei&\#x27;s ecosystem and strengthens the incentive to support HarmonyOS, but it also means teams should explicitly verify SDK/API and behavior compatibility across HarmonyOS 5–7 before broadly targeting apps or integrations. The company&\#x27;s claim of a 90× increase in usage for integrated features suggests partner-provided capabilities may see rapid adoption, so testing and certification of integrations is a practical next step.

**Tags**: `#operating-systems`, `#mobile`, `#open-source`, `#ecosystem`, `#developer-community`

---

<a id="item-tech-news-14"></a>
### [Shenzhou-24 set for Nov 25 launch with Pakistani astronaut](https://www.news.cn/20261124/3b116eb35c404cd7b897b23a50099b5b/c.html) ⭐️ 7.0/10

China announced that Shenzhou-24 is aimed for launch on November 25 at 08:18, with a crew of Tang Hongbo \(commander\), Wu Yi, and Pakistan&\#x27;s Muhammad Qishan Ali. The flight is reported to be the first Chinese crewed mission to include a foreign astronaut, and Ali would be the first foreign visitor to the Tiangong space station. The spacecraft is slated to perform an autonomous 3.5-hour fast rendezvous and dock at the forward port of the Tianhe core module; Ali is reported to return later aboard Shenzhou-23 with Zhang Zhiyuan and Li Jiaying.

telegram · zaihuapd · Nov 24, 04:08

**「Fast rendezvous and docking explained」** A &quot;3.5-hour autonomous fast rendezvous and docking&quot; refers to a launch-to-dock profile in which the crewed Shenzhou spacecraft performs automated orbital phasing and approach maneuvers after ascent so it can reach and attach to the Tiangong core module&\#x27;s forward \(axial\) docking port within roughly three and a half hours. This short, automated profile reduces the time crew spend in the spacecraft compared with traditional multi-orbit or multi-day rendezvous procedures and requires precise launch timing and onboard guidance, navigation, and control to execute the final approach and soft/dynamic capture sequences.

**「Operational impact」** A 3.5-hour autonomous fast-rendezvous profile gives mission control little margin for timing or manual intervention, so precise launch-window execution, prelaunch orbital phasing, and readiness of automated docking systems and ground support are required; the international crew rotation also requires coordinated training, medical, and reentry arrangements for Pakistan and Chinese mission planners.

**Tags**: `#spaceflight`, `#aerospace`, `#China`, `#international-cooperation`, `#launch`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [vLLM Day-0 Support for ERNIE 5.5 Flash](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 8.0/10

rss · vLLM Blog · Nov 24, 00:00

**「Background」** The authors describe day‑0 integration of Baidu&\#x27;s ERNIE 5.5 Flash — a sparse MoE model \(280B total, 14B activated per token\) with a 1M‑token context — into vLLM so users can run the preview immediately. They argue that naively implementing ERNIE&\#x27;s new attention, gating and MoE structures results in many intermediate tensors, extra kernel launches and heavy memory traffic, which motivated fused kernels and other runtime changes.

**「Solution」** vLLM-ERNIE implements a plugin that supplies model code plus a set of dedicated fused kernels and runtime hooks while relying on vLLM core for attention, KV management, scheduling and serving; the plugin is discovered via vllm.general\_plugins so it loads only when an ERNIE config is used. The teams fused several hotspots \(VHA cross‑head mixing, Multi‑Router Latent MoE routing, the MultiMax output head, gated attention and others\), folding fixed transforms into weight load and reducing memory traffic — per‑kernel speedups range from about 1.55× up to 6.53× in their measurements. For sparse indexing they ship FlashIndexer, a lightweight head router trained by distillation \(authors say ~1B tokens of short fine‑tuning\) plus threshold pre‑filtering that yields roughly a 1.4× \(≈40%\) speedup at 1M context; routed experts are stored in MXFP4 \(W4A8\) with quantization‑aware training to match inference numerics, while other weights and the KV cache use FP8. They also provide a DSpark draft model for speculative decoding \(up to 7 tokens drafted, mean acceptance length &gt;4.0 on reported workloads\) and describe attention/parallelism strategies \(data‑parallel attention with expert parallelism, TP2/4/8, prefill‑decode disaggregation and KV offload\) to accelerate end‑to‑end inference.

**「Takeaway」** The post argues that a lightweight plugin plus targeted kernel fusions, FlashIndexer routing, QAT for W4A8, and DSpark speculative decoding together deliver substantial end‑to‑end inference acceleration for ERNIE 5.5 Flash on day‑0; however, the reported gains are high‑level and lack full reproducible benchmark methodology, so practitioners should validate the improvements on their own hardware and workloads.

**Tags**: `#inference-acceleration`, `#kernel-fusion`, `#quantization`, `#sparse-attention`, `#vLLM-plugin`

---

## Financial News

<a id="item-finance-news-1"></a>
### [NY Fed&\#x27;s Williams Signals Further Rate Action &\#x27;Over Time&\#x27;](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 8.0/10

New York Fed President John Williams said further interest-rate action is likely &quot;over time&quot; to return inflation to the Fed&\#x27;s 2% target, and markets are fully pricing a 25-basis-point \(0.25 percentage point\) increase from the current federal funds target range of 3.75%–4.00% at the Dec. 8–9 FOMC meeting. Williams projected inflation would move closer to 2% in 2027 and reach the 2% target in 2028 \(his forecast\).

rss · CNBC Finance · Nov 23, 21:02

**「background」** John Williams, president of the New York Federal Reserve and an influential FOMC participant, spoke ahead of the Dec. 8–9 Fed meeting and said the Fed still has work to return inflation to its 2% target, expecting it to move closer to that level in 2027.

**「Impact」** Those comments increase the odds of higher short-term borrowing costs for households and businesses and can push up short-term Treasury yields by raising market expectations of further Fed tightening.

<details><summary>References</summary>
<ul>
<li>Fed&#x27;s John Williams indicates higher interest rates likely &#x27;over ... - CNBC</li>
<li>Williams keeps December Fed hike in play as inflation seen above 2 ...</li>

</ul>
</details>

**Tags**: `#monetary policy`, `#Federal Reserve`, `#interest rates`, `#inflation`, `#US economy`

---

<a id="item-finance-news-2"></a>
### [Nvidia reinstates Jensen Huang, prompting relief rally](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo-market-rally.html) ⭐️ 8.0/10

Nvidia reinstated Jensen Huang as CEO; the S&amp;P 500 had fallen more than 9% from Nov. 12 through Friday before Monday&\#x27;s rally \(actual\).

rss · CNBC Finance · Nov 23, 18:00

**「background」** The report follows Nvidia&\#x27;s reinstatement of CEO Jensen Huang after his removal on Nov. 12, an episode that coincided with a broad U.S. equity sell-off that left the S&amp;P 500 more than 9% lower through Friday. Nvidia is a leading maker of GPUs used in AI data centers, which helps explain why its leadership moves can drive the AI trade and overall market sentiment.

**「Impact」** CNBC reports Wall Street strategists said the reinstatement triggered a relief rally and may have &quot;established a bottom&quot; for AI-exposed stocks by restoring confidence in Nvidia&\#x27;s central role in AI infrastructure, though they warned unresolved risks on data-center approvals and hyperscaler capital spending remain.

<details><summary>References</summary>
<ul>
<li><a href="https://en.m.wikipedia.org/wiki/Nvidia">Nvidia - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#Market rally`, `#AI trade`, `#Equities correction`, `#CEO reinstatement`

---

<a id="item-finance-news-3"></a>
### [Anthropic IPO triggers selloff, clouds Chinese AI listings](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 8.0/10

Anthropic&\#x27;s record $119.5 billion IPO, Bloomberg reports, triggered a global tech selloff that has clouded planned IPOs for Chinese AI firms including DeepSeek, 月之暗面 and 阶跃星辰.

telegram · zaihuapd · Nov 23, 09:31

**「background」** Bloomberg reported that Anthropic’s record $119.5 billion IPO triggered a global tech selloff that the article says erased about $1.7 trillion from Chinese tech stocks since late June and has clouded planned listings by DeepSeek, 月之暗面 and 阶跃星辰.

**「Impact」** Bloomberg says the selloff has reduced investor appetite for China tech IPOs, raising the risk of weaker pricing or delays for those Chinese AI listings and affecting investors targeting that pipeline.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bloomberg.com/">Bloomberg - Business News, Stock Markets, Finance, Breaking &amp;...</a></li>

</ul>
</details>

**Tags**: `#AI IPO`, `#market selloff`, `#China tech IPOs`, `#investor sentiment`

---

<a id="item-finance-news-4"></a>
### [Shanghai raises metro fares after 21 years](https://weibo.com/1699432410/5368461393397183) ⭐️ 8.0/10

Shanghai adjusted metro fares for the first time in 21 years: the new starting fare is ¥3 for 0–4 km, then adds ¥1 after successive distance bands of 4,4,4,7,7,10,10 km and ¥1 per 15 km beyond 50 km, according to Xinhua. Multi‑ride tickets \(35/45/60/90 rides\) are priced at ¥190/¥210/¥270/¥390 and go on sale Nov 26, with the new fares and a 10% monthly cumulative discount after ¥90 in the same payment channel taking effect Dec 1.

telegram · zaihuapd · Nov 23, 10:45

**「background」** Shanghai Metro is the city&\#x27;s urban rail transit system; the item reports that Shanghai is implementing its first metro fare adjustment in 21 years.

**「impact」** Frequent commuters and households in Shanghai will face higher per‑ride costs but may partly offset them via the new multi‑ride tickets and the 10% discount once monthly spending in one payment channel exceeds ¥90.

<details><summary>References</summary>
<ul>
<li><a href="https://zh.wikipedia.org/wiki/%E4%B8%8A%E6%B5%B7%E5%9C%B0%E9%93%81%E8%BD%A6%E7%AB%99%E5%88%97%E8%A1%A8">上海地铁 车站列表 - 维基百科，自由的百科全书</a></li>

</ul>
</details>

**Tags**: `#public-transport`, `#fare-change`, `#Shanghai`, `#consumer-impact`, `#policy-change`

---

<a id="item-finance-news-5"></a>
### [SpaceX reportedly renting compute capacity to Anthropic and Google](https://www.nytimes.com/2026/11/23/business/elon-musk-ai-anthropic-google.html) ⭐️ 8.0/10

The New York Times reports that since May 2026 SpaceX has been renting large amounts of its data‑center compute to Anthropic and Google and is &\#x27;reportedly&\#x27; earning tens of billions of US dollars per month \(claim attributed to three unnamed sources; figure unconfirmed\).

telegram · zaihuapd · Nov 24, 02:06

**「Background」** The New York Times reported that, beginning in May, SpaceX began leasing data‑center compute to Anthropic and Google after Elon Musk told staff SpaceX was behind on AI and reportedly renamed an engineering group chat “Sell compute because we can&\#x27;t compete.”

**「impact」** If accurate, the deal would increase GPU capacity available to major AI developers and — if the revenue estimate is true — materially boost SpaceX&\#x27;s monthly income, but the report&\#x27;s extraordinary revenue claim and its anonymous sourcing remain unverified.

<details><summary>References</summary>
<ul>
<li>Grace Kay (@graceihle) / X</li>
<li>SPCX Stock Gets A &#x27;Buy&#x27; Rating From Jefferies For Its Engineering Edge ...</li>

</ul>
</details>

**Tags**: `#SpaceX`, `#AI infrastructure`, `#Cloud compute`, `#Elon Musk`, `#Anthropic/Google`

---