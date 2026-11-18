---
layout: default
title: "Horizon Summary: 2026-11-18 (EN)"
date: 2026-11-18
lang: en
---

> From 43 items, 27 important content pieces were selected

---

**Technology News**
1. [Java4Shell: RCE in OpenJDK Base64 handling \(CVE-2026-114938\)](#item-tech-news-1) ⭐️ 8.0/10
2. [Quad9 withdraws from France, raising DNS policy concerns](#item-tech-news-2) ⭐️ 8.0/10
3. [Nvidia stops disclosing Singapore sales after $104B bookings](#item-tech-news-3) ⭐️ 8.0/10
4. [OpenAI releases GPT‑6.2 Astra and Sol](#item-tech-news-4) ⭐️ 8.0/10
5. [Microsoft/onnxruntime GitHub repository disappears](#item-tech-news-5) ⭐️ 8.0/10
6. [Classified US national-security communications network outage](#item-tech-news-6) ⭐️ 8.0/10
7. [Solid 2.0](#item-tech-news-7) ⭐️ 8.0/10
8. [Microsoft MAI Code 2 and Code 2 Flash](#item-tech-news-8) ⭐️ 8.0/10
9. [Datasette Lite runs full Datasette in the browser](#item-tech-news-9) ⭐️ 8.0/10
10. [EU preliminarily finds Temu breached Digital Services Act](#item-tech-news-10) ⭐️ 8.0/10
11. [Jensen Huang says he&\#x27;d return as NVIDIA CEO if board asks](#item-tech-news-11) ⭐️ 8.0/10
12. [IRS sign-in requires ID.me terms](#item-tech-news-12) ⭐️ 7.0/10
13. [Claim: Google AI answers cut search traffic 40%](#item-tech-news-13) ⭐️ 7.0/10
14. [Phrack Issue 73 Released](#item-tech-news-14) ⭐️ 7.0/10
15. [Apple Services Down](#item-tech-news-15) ⭐️ 7.0/10
16. [Claude Code verification practices](#item-tech-news-16) ⭐️ 7.0/10
17. [External sandboxes for coding agents](#item-tech-news-17) ⭐️ 7.0/10
18. [China demonstrates 27 Gbps Q/V‑band wireless link](#item-tech-news-18) ⭐️ 7.0/10
19. [NVIDIA board creates national security and export‑control oversight committee](#item-tech-news-19) ⭐️ 7.0/10
20. [Study: U.S. hyperscale data centers used about 2% of electricity](#item-tech-news-20) ⭐️ 7.0/10
21. [Telegram requires Telegram Stars for bot and mini‑app purchases](#item-tech-news-21) ⭐️ 7.0/10
22. [UK court rejects £1.97bn PlayStation Store class action](#item-tech-news-22) ⭐️ 7.0/10
23. [South Korea proposes emergency alerts and AI data disclosure to block exam cheating](#item-tech-news-23) ⭐️ 7.0/10

**Financial News**
1. [MIIT asks CAAM to assess 17 carmakers&\#x27; 60‑day supplier payment term](#item-finance-news-1) ⭐️ 8.0/10
2. [APEC: Trump, Xi and Putin meet in Shenzhen](#item-finance-news-2) ⭐️ 7.0/10
3. [JPMorgan and Hyundai Card test AI agents to transact on blockchain](#item-finance-news-3) ⭐️ 7.0/10
4. [U.S. tech firms confront tighter U.S. chip export and remote-access rules](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Java4Shell: RCE in OpenJDK Base64 handling \(CVE-2026-114938\)](https://calif.io/java4shell/) ⭐️ 8.0/10

A remote code-execution vulnerability labelled Java4Shell \(CVE-2026-114938, CVSS 9.2\) was reported in OpenJDK&\#x27;s Base64 processing. The report says HotSpot-based JVMs \(OpenJDK builds, Oracle JDK, GraalVM\) are affected when running on x86-64 servers that support the AVX-512 VBMI instruction set; cited impacted Java releases include Java 17 \(17.0.6 and later in the 17 line\), 21, 25, and 27, while standard Java 8/11 are generally not affected except for Oracle Java 8 Performance Pack. The disclosure and published exploit work \(called out by Calif\) note the bug appears to have existed for about four years and that reliable exploitation depends on specific runtime and network conditions.

hackernews · werrett · Nov 17, 21:11 · [Discussion](https://news.ycombinator.com/item?id=50538240)

**「Why an AVX‑512 Base64 path matters」** OpenJDK ships a vectorized Base64 decoder that uses AVX‑512/VBMI instructions on supported x86‑64 CPUs; HotSpot-based builds \(OpenJDK, Oracle JDK and similar HotSpot VMs\) can select that fast path at runtime. Vendor and research writeups for CVE‑2026‑114938 say exploitation depends on those CPU/vector conditions and that administrators can mitigate by disabling AVX‑512 \(for example with -XX:UseAVX=2\), at the cost of potential performance impact on Base64- or vector-heavy workloads.

**「Immediate consequence and actionable mitigations」** Organizations running HotSpot JVMs on AVX-512 VBMI–capable x86-64 servers \(roughly Intel Ice Lake and newer Xeons, and AMD Zen 4 and newer EPYC/Ryzen\) should treat exposed Java services that accept Base64 inputs as high-risk and inventory affected hosts. While vendors may publish patches, immediate steps supported by the report include using published detection checks \(for example, the Semgrep detection scripts called out by community responders\) and reducing network exposure of vulnerable processes; a community-sourced workaround — running the JVM with -XX:UseAVX=2 to alter AVX usage — has been suggested but is unconfirmed in the disclosure and should be tested before deployment.

**「Notable discussion points from the community」** Researchers noted the exploit is sensitive to network conditions \(RTT and jitter\) and requires careful remote heap grooming for reliability \(comment by lucasluitjes\). Others praised the disclosure and published detection scripts \(comment by ievans referencing Semgrep\). Some users suggested disabling AVX features with -XX:UseAVX=2 as a possible mitigation \(attributed as unconfirmed by AgentME\), and commenters warned of rapid exploitation risk to poorly maintained infrastructure \(comment by leca\).

<details><summary>References</summary>
<ul>
<li><a href="https://orca.security/resources/research/java4shell-critical-openjdk-base64-decoder-flaw-could-allow-unauthenticated-remote-code-execution/">Java 4 Shell CVE - 2026 - 114938 : Affected Versions &amp; Mitigation</a></li>
<li><a href="https://www.cyberkendra.com/2026/11/cve-2026-114938-pre-auth-rce-flaw-in-java-17-puts-servers-at-risk.html">Java 4 Shell ( CVE - 2026 - 114938 ): Java Base 64 Flaw... - Cyber Kendra</a></li>
<li><a href="https://thehackernews.com/2026/11/oracle-to-patch-11-java-flaws-today-as.html">Oracle to Patch 11 Java Flaws Today as Critical OpenJDK RCE...</a></li>

</ul>
</details>

**Tags**: `#security`, `#vulnerability`, `#java`, `#openjdk`, `#rce`

---

<a id="item-tech-news-2"></a>
### [Quad9 withdraws from France, raising DNS policy concerns](https://blog.cloudflare.com/quad9-withdrawal-from-france/) ⭐️ 8.0/10

Coverage reports that Quad9 has withdrawn its public DNS resolver service from France, citing regulatory pressure; the change affects users and networks in France that relied on Quad9 for DNS resolution and privacy-focused filtering. The write-up frames the withdrawal as a broader signal about rising legal demands on public DNS operators and the possible impact on resolver availability and privacy, but the coverage does not include full legal or technical detail nor explicit long-term commitments from other vendors.

hackernews · subset · Nov 17, 22:13 · [Discussion](https://news.ycombinator.com/item?id=50538994)

**「Why DNS resolver rulings matter」** Public DNS resolvers convert domain names to IP addresses and can be used to block or alter responses for particular domains, so court orders that require resolvers to block access effectively ask infrastructure providers to enforce content restrictions.  French and related Belgian court orders have recently targeted public resolvers—leading Quad9 to announce it will stop serving users in France and prompting orders that would require Cloudflare, Google, and Cisco to begin blocking certain sites under penalty—making DNS operators direct targets of content‑blocking litigation.

**「Concrete consequence」** French users and administrators who relied on Quad9 will need to reconfigure to other resolvers or run their own recursive service, which may reduce available privacy protections or change filtering behavior; resolver operators should assess their legal exposure in affected jurisdictions, review geofencing and transparency-reporting options, and prepare operational or legal responses if regulations force similar withdrawals.

**「Notable comments from the discussion」** Quad9’s CTO reported broad sympathy and support for Quad9’s position at IETF 127 and described widespread concern among DNS engineers about the developments; other commenters criticized growing internet regulation and called on vendors such as Cloudflare to state clearer commitments rather than vague opposition.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.cloudflare.com/quad9-withdrawal-from-france/">Quad9’s withdrawal from France: A canary in the coal mine</a></li>
<li><a href="https://quad9.net/news/blog/au-revoir-france/">Farewell, France | Quad9</a></li>
<li><a href="https://www.eff.org/deeplinks/2026/10/french-courts-site-blocking-orders-drive-quad9-out-france">French Court’s Site-Blocking Orders Drive Quad9 Out Of France</a></li>

</ul>
</details>

**Tags**: `#dns`, `#internet-policy`, `#security`, `#infrastructure`

---

<a id="item-tech-news-3"></a>
### [Nvidia stops disclosing Singapore sales after $104B bookings](https://www.ft.com/content/dbde7a30-548c-4f9d-a4be-7898a0c24dcf) ⭐️ 8.0/10

The Financial Times reported that Nvidia&\#x27;s Singapore subsidiary booked roughly $104 billion in external revenue for 2025 and that Nvidia has stopped separately disclosing Singapore sales in its investor reporting. The FT story and subsequent coverage focus on how GPU orders are routed through corporate entities, whether revenue booking aligns with where chips are physically shipped, and whether that routing raises exposure to export controls or other regulatory probes. Public details remain incomplete and disputed; the report and online discussion describe reported inquiries and open questions rather than a definitive finding about chip shipments or illegal conduct.

hackernews · louiereederson · Nov 17, 17:12 · [Discussion](https://news.ycombinator.com/item?id=50534631)

**「Prior disclosures and the Megaspeed issue」** Nvidia previously disclosed that its Singapore subsidiary \(reported externally as Megaspeed\) generated roughly $104 billion of external revenue in 2025, and the company later stopped reporting Singapore sales separately. Nvidia has said it added Megaspeed to an internal “block list” in June 2025 prohibiting further sales or shipments, and U.S. authorities have been reported to be investigating whether the unit diverted chips to China amid leadership changes including the appointment of the CFO as interim CEO.

**「Practical consequence」** The disclosure change and reported routing of large revenue through a Singapore entity increase regulatory and compliance risk: customers, resellers, and corporate compliance teams should review contracts, end‑use and export‑control obligations, and supply‑chain routing because legal entity booking can affect export‑control compliance and shipment approvals. Investors and analysts should treat Singapore revenue attribution as a change in disclosure that complicates revenue analysis and may affect near‑term visibility into where sales are booked versus where products are delivered.

**「What commenters said」** Some commenters emphasized that the $104 billion figure is the subsidiary&\#x27;s external revenue — meaning many orders may simply be routed through that legal entity rather than proving chips were physically shipped to or sold from Singapore. Other commenters argued this looks like an accounting or routing issue rather than definitive evidence of smuggling, while a minority raised speculative links to sanctions evasion or executive conduct; those remain opinions and are not established facts.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ft.com/content/65ff066f-a81c-4d24-95da-73c2d7b83a27?syn-25a6b1a6=1">How Jensen Huang’s family shaped Nvidia ’s Singapore dealings</a></li>
<li><a href="https://www.cnbc.com/2026/11/15/bessent-nvidia-ceo-lutnick-megaspeed.html">Bessent calls for ‘dramatic shakeup’ at Nvidia , urges outside CEO</a></li>

</ul>
</details>

**Tags**: `#ai-hardware`, `#supply-chain`, `#trade-compliance`, `#geopolitics`

---

<a id="item-tech-news-4"></a>
### [OpenAI releases GPT‑6.2 Astra and Sol](https://openai.com/index/introducing-gpt-6-2-astra-sol/) ⭐️ 8.0/10

OpenAI announced GPT‑6.2 Astra and GPT‑6.2 Sol, available in the API as gpt-6.2-astra and gpt-6.2-sol and supported in recent tooling such as Codex and ChatGPT Work. GPT‑6.2 Astra is priced at $8 per million input tokens and $40 per million output tokens \(about 20% cheaper than GPT‑6 Astra\), with a cached price quoted as $0.40/million versus $1/million for the prior model; GPT‑6.2 Sol keeps the $2/$10 per‑million input/output pricing used by GPT‑6.1/6 Sol. Early reports say both models deliver substantial cost and latency improvements for many tasks while producing mixed quality tradeoffs on specific benchmarks and office-style outputs, and Astra shows different evaluation-awareness and chain‑of‑thought behavior compared with GPT‑6 Astra.

hackernews · jasondavies · Nov 17, 17:46 · [Discussion](https://news.ycombinator.com/item?id=50535230)

**「What GPT‑6.2 Astra and Sol build on」** OpenAI&\#x27;s GPT‑6.x family separates a higher‑capability &\#x27;Astra&\#x27; line for complex, professional tasks from a lower‑latency, lower‑cost &\#x27;Sol&\#x27; line for everyday work; GPT‑6.2 is a point release that updates both variants. For users the most relevant technical context is the token‑priced API model \(input/output per‑million‑token rates\) and cached pricing, which are the primary levers that change deployment cost and make direct comparisons to prior GPT‑6 and GPT‑6.1 releases meaningful.

**「Impact」** Teams running cost- or latency-sensitive workloads can materially reduce per-task costs and runtime: community testers reported examples where Astra reduced a data-analytics exam run from roughly $20 to $4 and Sol from about $2.6 to $1.2, while also making fewer tool calls and returning faster results—however, practitioners should run task-specific validation because some creative and office-document outputs and some benchmark scores regressed versus competing models.

**「Community discussion」** Commenters praised the price and speed improvements but reported mixed quality: some saw similar accuracy at much lower cost, others found poorer outputs for slides, memos, and certain creative prompts, and reviewers noted Astra exhibits more evaluation‑awareness and some changes in chain‑of‑thought behavior compared with the previous Astra.

**Tags**: `#large-language-models`, `#model-performance`, `#cost-reduction`, `#benchmarks`, `#openai`

---

<a id="item-tech-news-5"></a>
### [Microsoft/onnxruntime GitHub repository disappears](https://github.com/microsoft/onnxruntime) ⭐️ 8.0/10

Microsoft&\#x27;s ONNX Runtime repository \(github.com/microsoft/onnxruntime\) reportedly disappeared from GitHub as of reports on Nov 17, 2026, removing a widely used source and delivery point \(a commenter noted the repo had about 22k stars\). Users said evals and CI/pipelines began failing when their workflows tried to pull the repo, and no confirmed explanation or vendor statement is available in the supplied reports. Community discussion has raised supply‑chain and security concerns — including compromised packages, telemetry/exfiltration, or backdoored models — but those possibilities are unverified.

hackernews · nvader · Nov 17, 23:18 · [Discussion](https://news.ycombinator.com/item?id=50539610)

**「Why ONNX Runtime matters」** ONNX Runtime is Microsoft’s cross‑platform inference engine for ONNX models, published from the microsoft/onnxruntime GitHub repository and distributed through package registries such as PyPI. A March 2026 report flagged a parser flaw that could let an ONNX model cause ORT to read arbitrary file paths or memory without validation, which helps explain why the repository’s sudden disappearance has immediate supply‑chain and security relevance.

**「Immediate consequence and mitigation」** Organizations that rely on cloning the repository or automatically pulling code can experience broken evaluations and pipeline failures; affected teams should immediately vendor or pin a vetted copy of ONNX Runtime, consider using an alternate maintained fork \(a commenter pointed to github.com/intel/onnxruntime\), and audit any automated dependency pulls and package registries while awaiting clarification from Microsoft. If telemetry or compromised-packages are suspected, rebuilding from source with telemetry disabled or blocking related network endpoints was suggested by community members as a precaution, though those steps address specific risks that remain unconfirmed.

**「Notable community reactions」** Commenters suggested the removal might follow a package compromise and raised concerns about ONNX telemetry that some say can only be disabled by building from source; others warned about attack vectors that could backdoor models. One user reported discovering the outage when evals started failing and noted the lack of prior warning for a repository of this size.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/microsoft/onnxruntime/">GitHub - microsoft / onnxruntime : ONNX Runtime: cross-platform...</a></li>
<li><a href="https://news.ycombinator.com/item?id=50539610">Microsoft &#x27;s ONNX Runtime has disappeared from GitHub</a></li>

</ul>
</details>

**Tags**: `#onnxruntime`, `#supply-chain-security`, `#open-source`, `#machine-learning`

---

<a id="item-tech-news-6"></a>
### [Classified US national-security communications network outage](https://www.cnn.com/2026/11/17/politics/highly-classified-national-security-communications-network-goes-down) ⭐️ 8.0/10

A highly classified U.S. national-security communications network went down, according to media reports published on Nov 17, 2026. The reports do not name the specific system, affected agencies, or a technical cause; officials have said the cause, scope, and operational impact are currently unclear. There is no independently verified information in the supplied account about outage duration, data loss, or whether classified traffic was compromised.

hackernews · monkeydust · Nov 17, 15:38 · [Discussion](https://news.ycombinator.com/item?id=50532849)

**「What the NSA&\#x27;s classified communications network is」** The National Security Agency maintains a highly classified internal communications network used for agency messaging and operational communications that is kept separate from public internet services. Reuters and CNN report that the network experienced a temporary degradation or outage while the agency worked to determine scope, and there was no immediate evidence of a cyberattack; the cause and operational impact remain unclear.

**「Immediate implication」** Until authorities provide details, users and operators of classified communications should assume reduced or no access and follow agency contingency procedures, including using pre-approved alternate channels and verifying system integrity before resuming classified exchanges. Organizations that depend on those links for command, control, or time-sensitive reporting should await official guidance and avoid moving classified material to unvetted commercial or public systems.

**「Community reactions」** Some commenters attributed the event to long-term staffing and operational cuts, while others questioned why a normally quiet, internal outage was publicly announced. A subset of responses speculated about attacker activity or AI-assisted exploits, framed as unverified hypotheses rather than established facts.

<details><summary>References</summary>
<ul>
<li><a href="https://www.reuters.com/technology/highly-classified-us-national-security-communications-network-is-down-cnn-2026-11-17/">Classified US national security communications network hit by ...</a></li>
<li><a href="https://witness.usatoday.com/story/news/nation/2026/11/17/nsa-classified-network-outage-cnn/92827090007/">NSA classified communications network is down, CNN reports</a></li>

</ul>
</details>

**Tags**: `#security`, `#national-security`, `#infrastructure`, `#incident`, `#operations`

---

<a id="item-tech-news-7"></a>
### [Solid 2.0](https://www.solidjs.com/blog/solid-2-0-the-long-hold/) ⭐️ 8.0/10

Solid 2.0 was announced \(blog post linked from the Hacker News item published 2026-11-17\) as a major new release of the Solid frontend framework that introduces agent-focused ergonomics under the tagline &quot;Built to Be Written by Agents&quot; and adds built-in server RPC plus &\#x27;live&\#x27; and &\#x27;broadcast&\#x27; primitives for server-driven, real-time updates. The announcement emphasizes tighter frontend–backend integration and debugging/diagnostic improvements, but the supplied item does not include full technical details about runtime requirements, breaking changes, or platform compatibility.

hackernews · pier25 · Nov 17, 18:56 · [Discussion](https://news.ycombinator.com/item?id=50536387)

**「Background」** SolidJS is a fine‑grained reactive frontend framework that emphasizes minimal runtime and precise reactivity rather than a virtual DOM. Solid 2.0 reached a stable release after a multi‑year effort and follows release candidates that shipped ecosystem pieces such as Solid Router 2.0 and built‑in head/meta primitives.

**「Concrete consequence」** Frontend teams building interactive or real-time UIs can potentially replace custom websocket or ad-hoc sync layers with Solid&\#x27;s server RPC and live/broadcast primitives, so teams should review Solid 2.0&\#x27;s documentation and server/runtime compatibility and evaluate migration effort before adopting it in production.

**「What people said」** Commenters praised Solid 2.0&\#x27;s ergonomics and said the server RPC and live/broadcast primitives feel more natural than some alternatives \(users compared it to Remix, LiveView, and htmx\). Others noted the &quot;Built to Be Written by Agents&quot; framing may be marketing — several observed the same developer-facing diagnostics and ergonomics also help human authors — and congratulated the Solid team on a significant release.

<details><summary>References</summary>
<ul>
<li><a href="https://www.solidjs.com/blog/solid-2-0-rc-the-big-reveal">Solid 2.0 RC: The Big | SolidJS</a></li>
<li><a href="https://www.solidjs.com/blog/solid-2-0-the-long-hold/">Solid 2.0 - The Long Hold</a></li>

</ul>
</details>

**Tags**: `#frontend-frameworks`, `#web-development`, `#server-rpc`, `#agent-integration`, `#open-source`

---

<a id="item-tech-news-8"></a>
### [Microsoft MAI Code 2 and Code 2 Flash](https://microsoft.ai/news/introducing-mai-code-2-and-mai-code-2-flash/) ⭐️ 8.0/10

Microsoft announced two new code-focused models, MAI Code 2 and MAI Code 2 Flash, aimed at developer tooling and code generation. Community reports say at least some users can select MAI Code 2 inside GitHub Copilot and that the model handled real-world tasks such as resolving Python build issues in WSL, generating passing tests, and fixing Azure Bicep deployment problems. The announcement and community reports are the primary evidence provided; technical details, model sizes, benchmarks, or Microsoft’s published performance claims were not included in the supplied material, and independent validation is still needed. Availability appears to be rolling to some Copilot users rather than a guaranteed platform-wide release based on the supplied commentary.

hackernews · lemonish97 · Nov 17, 18:25 · [Discussion](https://news.ycombinator.com/item?id=50535885)

**「Background」** MAI Code 2 and MAI Code 2 Flash are Microsoft’s new code-focused models: MAI Code 2 is presented as a higher‑capacity model becoming a workhorse across Microsoft products, while Code 2 Flash is a lightweight, cost‑efficient variant tuned for routine edits, explanations, and rapid iteration. GitHub’s changelog documents Code 2 Flash’s availability in GitHub Copilot for everyday development workflows, reflecting the ongoing trend of specialized coding models tailored to generation, targeted edits, and testing rather than general-purpose chat models.

**「Immediate consequence for developers and teams」** Developers using GitHub Copilot should test MAI Code 2 on representative repositories before adopting it broadly, since community reports show practical wins but independent benchmarks and security/quality reviews are lacking; teams evaluating tooling should require reproducible comparisons \(A/B testing\) and inspect generated code for correctness and supply-chain risks. Organizations considering migration or tighter integration should also verify pricing, API/IDE compatibility, and governance controls once Microsoft publishes formal availability and technical documentation.

**「What commenters are saying」** Some commenters \(pseudosavant, origini\) suggested the models narrow OpenAI/Anthropic’s lead and speculated about techniques such as distillation for rapid progress, while a user \(chopete3\) reported hands-on success with Copilot using MAI Code 2 on Python/WSL, tests, and Azure Bicep; others questioned product lineage \(SillyUsername\) or the value of current Copilot subscriptions \(LaurensBER\). These are user reports and opinions, not independent benchmarks or vendor confirmations.

<details><summary>References</summary>
<ul>
<li><a href="https://microsoft.ai/news/introducing-mai-code-2-and-mai-code-2-flash/">MAI Code 2 and Code 2 Flash : Everyday coding at... | Microsoft AI</a></li>
<li><a href="https://github.blog/changelog/2026-11-17-mai-code-2-and-mai-code-2-flash-in-github-copilot/">MAI Code 2 and MAI Code 2 Flash in GitHub... - GitHub Changelog</a></li>

</ul>
</details>

**Tags**: `#code-generation`, `#models`, `#microsoft`, `#developer-tools`, `#ai-competition`

---

<a id="item-tech-news-9"></a>
### [Datasette Lite runs full Datasette in the browser](https://simonwillison.net/2026/Nov/17/datasette-lite/) ⭐️ 8.0/10

Simon Willison reports that Datasette Lite has been rewritten to run the full server-side Datasette Python application entirely in the browser using WebAssembly \(Pyodide\) and a service-worker–based architecture, and is available at lite.datasette.io. The rewrite lets users load SQLite databases, JSON, CSV or SQL scripts; choose a released Datasette version from PyPI or a specific Git commit, tag, or branch; pick from over 100 SQLite builds; and install additional Datasette plugins from PyPI or wheel URLs \(including JavaScript visualization tools\). Remote data files must be served with open CORS headers, and the author says the service-worker approach restores JavaScript plugin behavior that the earlier innerHTML/web-worker hack could not execute.

rss · Simon Willison · Nov 17, 16:48

**「Background」** Pyodide compiles Python to WebAssembly so Python applications can run in the browser. Willison initially released a Datasette Lite proof-of-concept in 2022 that ran Datasette inside a Pyodide web worker and injected HTML via innerHTML, which prevented client-side JavaScript from running; the new service-worker rewrite addresses that limitation.

**「Impact」** Developers can create shareable, versioned, URL-addressable demos and bug reproductions that run entirely in a visitor&\#x27;s browser — for example by pinning a Datasette ref, SQLite build, and plugins in a lite.datasette.io URL — removing the need to deploy a server to demonstrate issues or features; the author already uses it to show a real pagination bug and its fix. To use it in practice, hosts of example database or metadata files must provide open CORS headers so the browser-based Datasette can fetch them, and plugin installations happen client-side via PyPI or wheel URLs.

**Tags**: `#WebAssembly`, `#Pyodide`, `#Datasette`, `#Browser-based apps`, `#SQLite`

---

<a id="item-tech-news-10"></a>
### [EU preliminarily finds Temu breached Digital Services Act](https://www.reuters.com/legal/litigation/eu-preliminarily-finds-temu-breaches-regulation-failing-tackle-illegal-good-2026-11-17/) ⭐️ 8.0/10

On Nov. 17 the European Commission preliminarily found that Temu failed to take &quot;reasonable, proportionate and effective&quot; measures to prevent the sale of illegal goods, concluding the company breached obligations under the Digital Services Act. The Commission specifically identified weaknesses in Temu&\#x27;s product compliance checks, content-moderation processes and sanctioning/penalty mechanisms. The finding is preliminary rather than a final sanction and may lead to further regulatory steps under the DSA.

telegram · zaihuapd · Nov 17, 14:11

**「Digital Services Act obligations」** The EU&\#x27;s Digital Services Act requires online marketplaces to take reasonable, proportionate and effective measures to prevent the sale of illegal goods—measures that typically include product compliance checks, content moderation and sanctions for repeat offenders. That regulatory framework is the basis for the European Commission&\#x27;s preliminary finding against Temu reported in this item.

**「Immediate consequence for platforms」** Marketplaces operating in the EU should review and strengthen product-compliance checks, automated and human content-moderation workflows, and their sanctioning frameworks to meet the DSA&\#x27;s &quot;reasonable, proportionate and effective&quot; standard; compliance teams can expect detailed scrutiny from regulators and potential follow-up enforcement if deficiencies persist.

**Tags**: `#regulation`, `#content-moderation`, `#platform-compliance`, `#EU`, `#marketplaces`

---

<a id="item-tech-news-11"></a>
### [Jensen Huang says he&\#x27;d return as NVIDIA CEO if board asks](https://x.com/JensenHuang/status/2122726005219737649) ⭐️ 8.0/10

Former NVIDIA CEO Jensen Huang made his first public comment since resigning, saying he would be honored to resume the CEO role if NVIDIA&\#x27;s board determines that his return would serve shareholders, employees, the company and U.S. interests. He said he has received pleas from employees, investors, partners and customers, apologized for personal misconduct, and accepted responsibility for failing to meet the company&\#x27;s management standards. The NVIDIA board, however, is not currently considering rehiring him, so his statement is a personal offer rather than an active corporate plan.

telegram · zaihuapd · Nov 17, 16:14

**「Corporate‑governance context」** A public company&\#x27;s chief executive is appointed and can be reappointed only by its board of directors, so any return of Jensen Huang would require board approval and would be judged against shareholder, employee and regulatory interests. Huang&\#x27;s statement comes after his recent departure and his own apology for personal misconduct, which makes the board&\#x27;s current decision not to consider rehiring him the operative constraint on an immediate comeback.

**「Impact」** Because the board has stated it is not considering Huang&\#x27;s rehiring, stakeholders should treat the company&\#x27;s current leadership arrangement as unchanged and rely on official board communications for any governance changes rather than Huang&\#x27;s personal statement.

**Tags**: `#NVIDIA`, `#leadership`, `#industry news`, `#AI hardware`

---

<a id="item-tech-news-12"></a>
### [IRS sign-in requires ID.me terms](https://consumerrights.wiki/w/ID.me_terms_required_for_IRS_sign-in) ⭐️ 7.0/10

Hacker News commenters report that signing in to some IRS online services now requires accepting ID.me&\#x27;s terms and completing ID.me&\#x27;s identity verification flow. Multiple commenters say the ID.me flow enforces smartphone-based steps \(camera or mobile number\), which prevents users without a smartphone from completing verification; other commenters point to login.gov as an alternative sign-in path. These are community reports from the discussion and not an independent confirmation of an official IRS policy change.

hackernews · DeepLogin · Nov 18, 00:51 · [Discussion](https://news.ycombinator.com/item?id=50540437)

**「Authentication options for federal services」** Many federal online services use third-party identity-verification vendors \(such as ID.me\) to let users access accounts and benefits, and those vendor flows can require smartphone-based proof and raise accessibility and privacy concerns. Commenters on the item noted a federal plan that aims to require agencies to offer login.gov, a government-run single sign-on alternative, within two years as an intended fallback for users who cannot complete vendor-based verification.

**「Impact」** At least one commenter reports a concrete access loss: a person unable to use a smartphone could not redeem TreasuryDirect bonds because they could not complete ID.me verification, indicating that smartphone-only verification can block access to financial and tax services. A practical step for affected users is to try signing in via login.gov where available or contact IRS support, while organizations relying on ID.me should consider accessibility and alternative-authentication options for users without mobile devices.

**「Community discussion」** Commenters argued over whether a private affiliate-marketing company \(ID.me\) should handle government authentication, with some calling the arrangement inappropriate and others noting login.gov works for them; others reported login.gov rejects prepaid or VOIP numbers, so experiences vary. These points are reported opinions and experiences from the Hacker News thread rather than verified facts about agency policy or vendor behavior.

**Tags**: `#authentication`, `#identity-verification`, `#government`, `#accessibility`, `#privacy`

---

<a id="item-tech-news-13"></a>
### [Claim: Google AI answers cut search traffic 40%](https://revscope.co/blog/search-seo-geo-2026/) ⭐️ 7.0/10

A single blog post surfaced on Hacker News claims Google’s AI-powered answers have reduced publisher referral traffic from Google Search by about 40%. The report is a claim from one source and is not an independently verified measurement; the post attributes the drop to Google showing direct AI answers instead of linking to sites. Because the evidence is limited, the size and permanence of any traffic change remain uncertain.

hackernews · slashdev · Nov 18, 00:17 · [Discussion](https://news.ycombinator.com/item?id=50540178)

**「What the report measured」** Google&\#x27;s AI Overviews \(AI-generated answers displayed directly in search results\) can satisfy queries without users clicking through to websites; RevScope&\#x27;s post describes a randomized experiment that hid those Overviews for a subset of US desktop users to compare referral traffic. The experiment&\#x27;s contrast between &\#x27;AI shown&\#x27; and &\#x27;AI hidden&\#x27; groups is the key methodological premise behind the blog&\#x27;s claim that AI answers reduced clicks by roughly 40%.

**「Consequence for publishers」** If the claim is accurate, publishers and sites that depend on Google referrals could see materially lower pageviews and ad revenue and should immediately monitor Search Console and analytics for changes in click-throughs. A practical response is to diversify traffic sources \(social, newsletters, direct\), evaluate subscription or reader-revenue models, and update SEO and structured data so content can still be surfaced or monetized when search presents summarized answers.

**「Community reaction」** Commenters argued that direct answers improve user experience but reduce discovery and may harm the open web, while others said users might simply go to other LLM services. Several remarks were anecdotal \(for example, personal reductions in Google use after adopting ChatGPT\) and reflect opinion rather than independent data.

<details><summary>References</summary>
<ul>
<li><a href="https://revscope.co/blog/search-seo-geo-2026/">Google&#x27;s AI Overviews cut clicks to websites by 40% - RevScope</a></li>

</ul>
</details>

**Tags**: `#search`, `#AI`, `#SEO`, `#web-economy`, `#Google`

---

<a id="item-tech-news-14"></a>
### [Phrack Issue 73 Released](https://phrack.org/issues/73/introduction_md) ⭐️ 7.0/10

Phrack issue 73 was published on Phrack&\#x27;s site and collects technical writeups and historical analyses aimed at security researchers and systems engineers. Community discussion around the issue highlights a writeup described as a docker escape and a history piece on an SSH remote code‑execution \(RCE\) incident. The public record supplied with this notice is limited and does not establish whether any exploit described has been responsibly disclosed, assigned a CVE, or been fixed by affected vendors. Readers should treat exploit claims as potentially sensitive until disclosure and remediation status can be confirmed.

hackernews · notmine1337 · Nov 17, 18:31 · [Discussion](https://news.ycombinator.com/item?id=50535992)

**「Why Phrack matters」** Phrack is a long-running, community-published hacker magazine known for in-depth technical papers and historical retrospectives on exploits, system internals, and offensive research. Issue 73, posted to the Phrack archives, is the third issue curated by the project&\#x27;s new staff and collects 23 main papers and eight &quot;Line Noise&quot; pieces that span topics such as vDSO/container escapes, use-after-free exploitation, QNX userland shellcode, Linux kernel research, a Chromium renderer sandbox escape, Windows smart card architecture, Binary Ninja taint analysis, and backdoors in machine learning.

**「Immediate action for practitioners」** Security teams should review the issue&\#x27;s container and SSH‑related writeups, verify whether any referenced vulnerabilities have public advisories or CVEs, and, if necessary, test mitigations in isolated environments rather than production. If an organization uses affected container runtimes or SSH implementations, prioritize checking vendor bulletins and applying patches or mitigating controls rather than relying on the magazine&\#x27;s account alone.

**「Discussion highlights」** Commenters raised a key practical question about responsible disclosure and CVE assignment for the docker escape writeup \(comment by ashleyn\), and others pointed readers to the SSH RCE history article as useful context for how quickly remote‑code exploits can evolve. Several responses also expressed nostalgia for older Phrack issues and appreciation for the magazine&\#x27;s unvarnished technical style, which some readers find valuable for candid technical detail.

<details><summary>References</summary>
<ul>
<li><a href="https://archives.phrack.org/dl/73/">Phrack | 73</a></li>
<li><a href="https://zeli.app/story/50535992">Phrack 73 Arrives With 23 Papers · 28 HN comments | Zeli</a></li>

</ul>
</details>

**Tags**: `#security`, `#exploits`, `#containers`, `#historical-analysis`, `#hacker-magazine`

---

<a id="item-tech-news-15"></a>
### [Apple Services Down](https://developer.apple.com/system-status/) ⭐️ 7.0/10

Multiple Apple services were reported unavailable on Apple&\#x27;s system-status pages \(developer.apple.com/system-status\), with community reports of disrupted Apple Store operations and failures activating new devices. Reported impacts include in-store systems unable to process orders or returns and some newly purchased iPhones failing activation; the cause was not identified in the supplied reports. Affected parties should treat this as an active availability incident and watch Apple&\#x27;s official status pages for updates.

hackernews · willy\_k · Nov 17, 17:47 · [Discussion](https://news.ycombinator.com/item?id=50535238)

**「Why Apple service outages affect devices and stores」** Many End-User and retail functions — including App Store purchases, iCloud sign-ins, Apple Pay transactions and iPhone activation — depend on Apple’s cloud back ends, so failures can stop purchases, prevent new-device activations and block account access. Apple publishes incident information on separate public and developer status pages and has confirmed multiple service issues while retail stores and corporate offices also reported disruptions.

**「Concrete consequence」** Retail staff, device-provisioning teams, and IT administrators should delay non‑urgent in‑store purchases or mass device activations until Apple lists services as restored, and ensure offline or manual fallback procedures are ready for customer transactions and device enrollment.

**「What commenters said」** At least one commenter reported firsthand confirmation from an Apple Store that orders, returns, and activations were failing, which is presented as an observed fact. Other commenters speculated without evidence about causes — including broader cloud dependency concerns and unverified theories that AI exploit tools \(for example, references to &\#x27;ARTEX&\#x27;\) could be involved — and those claims should be treated as opinions until confirmed by Apple or independent analysis.

<details><summary>References</summary>
<ul>
<li><a href="https://9to5mac.com/2026/11/17/icloud-app-store-and-other-apple-services-hit-by-ongoing-outage/">iCloud, App Store, and other Apple services hit by ongoing outage</a></li>
<li><a href="https://www.theguardian.com/technology/2026/nov/17/gmail-apple-outage-major-disruption">Gmail and Apple ’s apps suffer outages days after... | The Guardian</a></li>

</ul>
</details>

**Tags**: `#outage`, `#apple`, `#incident-response`, `#cloud-dependency`, `#security-speculation`

---

<a id="item-tech-news-16"></a>
### [Claude Code verification practices](https://claude.dev/blog/how-the-claude-code-team-thinks-about-verification/) ⭐️ 7.0/10

Anthropic’s Claude Code team published a practical write-up describing how they verify their LLM-based developer product. The post explains per-change verification using &quot;skill files,&quot; invoking a chrome-for-Claude tool to exercise UI flows, running dozens or hundreds of checks in parallel, and using automated failures to decide what needs human review. The team presents these as operational practices rather than benchmarked performance claims. Commenters noted the approach can be token‑heavy and costly and pointed out that existing non‑LLM tools \(for example, Playwright\) can accomplish many of the same checks without high token usage.

hackernews · craigmart · Nov 17, 10:20 · [Discussion](https://news.ycombinator.com/item?id=50529612)

**「Verification for LLM coding agents」** The article assumes readers understand that LLM-based coding assistants must produce machine-checkable evidence of correct behavior rather than only human-written claims; in practice this is done with automated end-to-end tests, property tests, and differential tests that exercise generated code. Those verifier outputs — test results, assertions, and recorded environment interactions — are used to decide whether an agent&\#x27;s change can be accepted automatically or requires human review, and the Claude Code post outlines patterns to make those verifiers reliable.

**「Impact」** Organizations considering LLM-driven verification should quantify projected token spend before replicating these practices, prototype equivalent flows with traditional automation \(such as Playwright\) as a cost baseline, and reserve parallel LLM checks for high‑value end‑to‑end scenarios to control costs and latency.

**「Community discussion」** Several commenters described the described practices as impractically expensive—characterizing them as feasible only with &quot;unlimited tokens&quot;—and urged use of existing automation tools instead. Other responses questioned Claude Code’s product stability and suggested that keeping changes small so humans can review diffs remains a practical alternative to broad LLM verification.

<details><summary>References</summary>
<ul>
<li><a href="https://claude.dev/blog/how-the-claude-code-team-thinks-about-verification/">How the Claude Code team thinks about verification</a></li>

</ul>
</details>

**Tags**: `#verification`, `#LLM-assisted-development`, `#testing`, `#developer-tools`, `#cost`

---

<a id="item-tech-news-17"></a>
### [External sandboxes for coding agents](https://simonwillison.net/2026/Nov/17/external-sandboxes-for-coding-agents/) ⭐️ 7.0/10

Simon Willison and Prime Radiant introduced the &quot;external sandbox&quot; pattern and published three sandbox server implementations that let an agent invoke code which actually runs inside a dedicated sandbox while the agent process remains outside. The three released implementations are external-sandbox-v86 \(Node.js server running Alpine Linux in v86/WebAssembly\), external-sandbox-container \(Python server running Alpine inside an Apple Containers instance\), and external-sandbox-quicksand \(Python server using Microsoft&\#x27;s Quicksand library bundling QEMU and Alpine\). Each offers the same localhost API so you can point models such as Pi, Claude Code, or Codex at the sandbox, and the sandboxes include an optional HTTP/HTTPS allow-list proxy plus a credential-replacement mechanism to limit network access and keep secrets out of the agent. The write-up is a practical demo for safer experimentation rather than a formal threat-model or evaluation of security guarantees.

rss · Simon Willison · Nov 17, 22:52

**「Why an external sandbox helps with coding agents」** Sandboxing runs untrusted code in a restricted environment to limit what it can do on the host; the external sandbox pattern specifically keeps the agent process outside that sandbox and executes only the agent‑requested code inside a dedicated sandbox. Prime Radiant&\#x27;s post and repositories demonstrate this pattern with three backends \(v86, Apple Containers, and Quicksand\) that present a common localhost API and include an optional allow‑list proxy plus credential‑replacement to control network and secret access.

**「Concrete consequence」** Developers experimenting with coding agents can reduce risk from prompt-injection or unintended host actions by routing code execution to one of these sandbox servers and enforcing network allow-lists and credential mediation; to adopt it you must configure your agent to send execution requests to the sandbox&\#x27;s localhost API and choose the implementation that matches your host environment \(the options use WebAssembly/v86, Apple Containers, or Quicksand/QEMU\).

<details><summary>References</summary>
<ul>
<li><a href="https://blog.primeradiant.com/external-sandboxes-for-coding-agents/">External sandboxes for coding agents - blog.primeradiant.com</a></li>

</ul>
</details>

**Tags**: `#sandboxing`, `#AI-safety`, `#coding-agents`, `#local-models`

---

<a id="item-tech-news-18"></a>
### [China demonstrates 27 Gbps Q/V‑band wireless link](https://www.news.cn/tech/20261117/d6323540dccf4e2a976c48a762795956/c.html) ⭐️ 7.0/10

A Chinese research team including the Aerospace Information Innovation Institute of the Chinese Academy of Sciences reported a Q/V‑band wireless experiment at the Lijiang China Remote Sensing Satellite Ground Station that achieved bidirectional 27 Gbps. The system tested modulation formats from 64QAM up to 512QAM, with a single 512QAM channel delivering 6.75 Gbps and throughput aggregated to 27 Gbps using dual‑carrier and polarization multiplexing. The announcement describes this as the highest coded data rate achieved in China for Q/V‑band and states the key indicators are domestically leading and internationally advanced; the team says it will pursue beyond 50 Gbps. The report is a press account and does not publish independent, peer‑reviewed measurements or full test conditions \(for example, bandwidth, link distance, SNR, or hardware details\).

telegram · zaihuapd · Nov 17, 08:45

**「Technical context」** Q‑ and V‑band are millimeter‑wave frequency ranges of interest for high‑capacity satellite links and future 6G wireless research because they offer large contiguous bandwidths. Using higher‑order QAM \(64QAM→512QAM\) increases spectral efficiency but requires substantially higher signal‑to‑noise ratio, better RF linearity and lower phase noise; aggregating capacity through multiple carriers and polarization multiplexing is a common method to reach multi‑gigabit aggregate rates. The announcement therefore represents a system‑level demonstration of those techniques in the Q/V band rather than publication of detailed, independently verified link measurements.

**「Immediate consequence」** For researchers, satellite operators, and 6G development teams this result indicates practical feasibility of tens‑of‑Gbps links in Q/V bands if hardware can meet tighter SNR, phase‑noise, and linearity requirements; groups planning to adopt similar modulations should validate link budgets, ADC/DAC and RF chain linearity, and alignment/pointing performance under real operational conditions. For productization and standards work, the absence of published test parameters means vendors and regulators should treat the claim as an experimental demonstration until independent measurements and interoperability tests are available.

**Tags**: `#wireless-communications`, `#6G`, `#satellite`, `#mmWave`, `#modulation`

---

<a id="item-tech-news-19"></a>
### [NVIDIA board creates national security and export‑control oversight committee](https://nvidianews.nvidia.com/news/nvidia-board-of-directors-establishes-national-security-and-export-control-oversight-committee) ⭐️ 7.0/10

NVIDIA&\#x27;s board of directors has established a three‑member National Security and Export Control Oversight Committee to supervise the company&\#x27;s national security policy, export‑control compliance, and global trade risk, according to an NVIDIA Newsroom announcement. Existing national security and global trade compliance teams will report directly to the new committee and to the company&\#x27;s interim CEO. The committee will meet at least quarterly and will engage independent external experts in law and trade compliance; the board chair framed the move as a response to risks from advanced silicon and AI developments.

telegram · zaihuapd · Nov 17, 10:57

**「Why board-level export-control oversight matters」** A board committee is a governance body that gives directors direct responsibility for overseeing company policy, risk, and compliance and for receiving reports from management teams. For companies that design and sell advanced silicon used in AI, elevating national-security and export-control oversight to a dedicated board committee recognizes that export-control compliance and global trade risk are material governance issues that require regular director-level review and access to external legal and trade expertise.

**「Immediate consequence」** Product, procurement, and legal teams should expect centralized, board‑level oversight of export and trade decisions, which may lead to tighter controls and additional review steps for transactions involving restricted technologies or jurisdictions; organizations that buy, integrate, or resell NVIDIA hardware or software should review their compliance processes and timelines accordingly.

**Tags**: `#nvidia`, `#export-controls`, `#corporate-governance`, `#national-security`, `#ai-hardware`

---

<a id="item-tech-news-20"></a>
### [Study: U.S. hyperscale data centers used about 2% of electricity](https://arstechnica.com/science/2026/11/hyperscale-data-centers-use-2-of-us-electricity/) ⭐️ 7.0/10

A study reported by Ars Technica estimates that 403 U.S. hyperscale data centers consumed between 68 and 99 TWh of electricity in May 2024–April 2025, equal to roughly 1.5%–2.2% of U.S. electricity use. The researchers selected those 403 sites from a commercial list of 675 candidates, requiring verifiable power-capacity data; the selected facilities have an average capacity of about 40 MW. The paper presents this range as a baseline for tracking data‑center energy use but notes it is an estimate and cannot distinguish AI compute from other services.

telegram · zaihuapd · Nov 17, 12:54

**「Why the study can estimate hyperscale power use」** Estimating electricity consumption for hyperscale facilities depends on assembling a verified list of large data-center sites and their power capacities; the study drew from a commercial database to select 403 sites \(from 675 candidates\) with an average capacity of about 40 MW. Because the underlying data do not identify workloads, the reported 68–99 TWh total for May 2024–Apr 2025 serves as a baseline for aggregate energy tracking but cannot attribute usage specifically to AI versus traditional services.

**「Practical consequence」** Because the estimated load is comparable to the total electricity use of a mid‑sized state \(the study likens it to Wisconsin or Indiana\), grid planners and policymakers should treat hyperscale campuses as material, system‑level demand when doing capacity and resilience planning; the study also implies a need for more granular metering and public reporting so researchers and regulators can attribute consumption to AI versus other workloads.

**Tags**: `#data-centers`, `#energy`, `#ai-infrastructure`, `#sustainability`, `#research`

---

<a id="item-tech-news-21"></a>
### [Telegram requires Telegram Stars for bot and mini‑app purchases](https://telegram.me/zaihuapd/45189) ⭐️ 7.0/10

Telegram notified developers that, citing Apple and Google in‑app purchase rules, digital goods sold inside Telegram bots and mini‑apps must be sold via Telegram Stars. The policy covers bot subscriptions, paid tools, access to third‑party AI models, and virtual points or tokens; where cryptocurrency trading is involved, Telegram says GRAM is the only permitted crypto. Telegram stated it will begin active checks this week and that violators can be banned without further warning.

telegram · zaihuapd · Nov 17, 14:46

**「Background」** Apple and Google enforce rules that require apps to use their in‑app purchase systems for selling digital goods consumed inside the app, which extends to embedded content such as mini‑apps and bot interfaces running in a mobile client. Because Telegram bots and mini‑apps operate inside Telegram’s mobile apps distributed through those stores, Telegram must adopt a compliant payment flow for those purchases.

**「Developer impact and required action」** Developers who sell digital content or grant paid access inside bots or mini‑apps need to migrate their payment flows to Telegram Stars \(and use GRAM for allowed crypto trades\) or risk account bans and removal; Telegram&\#x27;s announcement implies immediate enforcement. Teams should audit bot/mini‑app billing, update integration and UI to use Stars/GRAM, and stop relying on external in‑app payment flows for covered goods or services.

**Tags**: `#platform-policy`, `#monetization`, `#chatbots`, `#ai-access`

---

<a id="item-tech-news-22"></a>
### [UK court rejects £1.97bn PlayStation Store class action](https://www.reuters.com/world/sony-defeats-2-billion-uk-claim-over-playstation-store-pricing-2026-11-17/) ⭐️ 7.0/10

The UK Competition Appeal Tribunal on November 17 dismissed a £1.97 billion class action against Sony brought on behalf of roughly 12.2 million UK consumers, finding Sony did not abuse market power to raise prices on the PlayStation Store. Plaintiffs had alleged Sony used exclusivity and bundling and that store prices were about 20% too high. The tribunal concluded that competition between consoles constrained Sony&\#x27;s ability to set higher prices.

telegram · zaihuapd · Nov 17, 16:02

**「Background」** The UK Competition Appeal Tribunal handles collective competition-law claims that seek damages for alleged overcharging by dominant firms or platforms; these cases turn on whether the defendant possessed actionable market power or was constrained by competitive alternatives, such as rival consoles and their stores. The PlayStation Store pricing claim was a typical platform-market dispute framed as a class action alleging systemic overcharges for digital content.

**「Impact」** As a direct consequence, the proposed £1.97 billion damages claim will not proceed and class members will not receive compensation from Sony under this claim. The tribunal&\#x27;s reliance on inter-console competition as a constraint on PlayStation Store pricing raises the evidentiary bar for similar UK platform-pricing claims, meaning future plaintiffs will need to show platform-specific market power that is not offset by competition between device ecosystems.

<details><summary>References</summary>
<ul>
<li><a href="https://www.eurogamer.net/playstation-store-pricing-uk-class-action-lawsuit-result">PlayStation defeats £ 2 billion UK lawsuit that alleged Sony forced...</a></li>

</ul>
</details>

**Tags**: `#antitrust`, `#digital-platforms`, `#gaming`, `#legal`

---

<a id="item-tech-news-23"></a>
### [South Korea proposes emergency alerts and AI data disclosure to block exam cheating](https://x.com/Jaemyung_Lee/status/2122664216578424918) ⭐️ 7.0/10

A social-media post claims the South Korean government plans new measures to prevent AI-assisted cheating on university entrance exams, including repeatedly issuing highest-level disaster alerts before and during exams to force communications devices to ring and requiring AI companies to submit records of photographed test questions and the queries users sent \(with a push to legislate mandatory compliance\). The post also says AI-assisted cheating could be criminalized with penalties up to five years&\#x27; imprisonment, that reports of high-technology cheating would carry rewards of at least 100 million KRW per report \(additive by number of people involved\), and that whistleblowers could receive reduced penalties for co-conspirators. These claims come from a single social-media account and are unverified here; the post did not provide legal text, implementation details, or independent confirmation.

telegram · zaihuapd · Nov 17, 23:48

**「Background」** The measures follow a public confession that the top scorer on this year’s certified tax accountant exam admitted using generative AI and digital devices to cheat, which prompted police attention and media coverage. That revelation, reported domestically and internationally just days before large university entrance exams, has intensified calls for stricter anti–AI-cheating rules and surveillance during tests.

**「Impact」** If implemented as described, AI companies would face new privacy and compliance obligations to retain and produce user-submitted images and query logs on government request, and exam authorities would need to coordinate with emergency-alert systems — organizations handling personal data should review retention, access controls, and legal-response procedures in case mandatory disclosure requirements are enacted.

<details><summary>References</summary>
<ul>
<li><a href="https://en.yna.co.kr/view/AEN20261118003200315">S. Korea considering unannounced disaster alerts during CSAT to...</a></li>
<li><a href="https://www.theguardian.com/world/2026/nov/18/south-korea-university-entrace-exams-ai-cheating-measures">Sleeve checks and no smartglasses: South Korea ... | The Guardian</a></li>

</ul>
</details>

**Tags**: `#AI governance`, `#privacy`, `#education`, `#legal`

---

## Financial News

<a id="item-finance-news-1"></a>
### [MIIT asks CAAM to assess 17 carmakers&\#x27; 60‑day supplier payment term](http://www.caam.org.cn/chn/5/cate_68/con_5237404.html) ⭐️ 8.0/10

China&\#x27;s Ministry of Industry and Information Technology \(MIIT\) has commissioned the China Association of Automobile Manufacturers \(CAAM\) to evaluate whether 17 major carmakers have implemented a 60‑day supplier payment term, according to a CAAM notice on Nov 16.

telegram · zaihuapd · Nov 18, 01:15

**「background」** This review follows a June 2025 public pledge by 17 major automakers to cap supplier payment terms at 60 days, after media investigations found many suppliers still waiting three to nine months for payment.

**「Impact」** The review affects auto suppliers—especially small and medium-sized enterprises \(SMEs\)—by enforcing checks that SME payment windows do not exceed 60 days and that payments to non‑SMEs are at least 80% cash or bank‑accepted bills, directly influencing supplier cash flow and payment methods.

<details><summary>References</summary>
<ul>
<li><a href="https://www.dzwww.com/news/hlcjnews/202611/t20261117_18310304.htm">60天账期从承诺走向核查，17家重点车企迎来首次“账期大考”</a></li>
<li><a href="http://www1.xinhuanet.com/fortune/20260907/bcb7af93659b40379b42466c32f0ea0b/c.html">权威人士解读规范车企供应商账款支付新规-新华网</a></li>

</ul>
</details>

**Tags**: `#automotive`, `#regulation`, `#supply-chain`, `#SMEs`

---

<a id="item-finance-news-2"></a>
### [APEC: Trump, Xi and Putin meet in Shenzhen](https://www.cnbc.com/2026/11/18/apec-trump-xi-putin-shenzhen.html) ⭐️ 7.0/10

APEC leaders—including U.S. President Donald Trump, China&\#x27;s Xi Jinping and Russia&\#x27;s Vladimir Putin—meet in Shenzhen; the U.S. and China in September said they would lower tariffs on $30 billion of goods, with no effective date specified.

rss · CNBC Finance · Nov 18, 03:25

**「background」** This is the first-ever summit to bring Trump, Xi and Putin together and follows a 2025 U.S.-China trade truce that temporarily lowered tariffs and eased rare-earth flows.

**「impact」** Chinese technology companies face tighter U.S. AI export controls that could reduce access to American AI technology, while exporters of goods covered by the $30 billion tariff commitment would gain if those tariff cuts take effect.

**Tags**: `#APEC`, `#U.S.-China relations`, `#Trade/tariffs`, `#Technology/AI export controls`, `#Geopolitics`

---

<a id="item-finance-news-3"></a>
### [JPMorgan and Hyundai Card test AI agents to transact on blockchain](https://www.cnbc.com/2026/11/18/jpmorgan-hyundai-card-ai-agents-payments.html) ⭐️ 7.0/10

JPMorgan’s Kinexys unit and Hyundai Card completed a simulated blockchain-based foreign-exchange proof-of-concept where AI agents negotiated and executed transactions, and they are targeting a multi-agent phase in the first half of 2027 \(target\).

rss · CNBC Finance · Nov 18, 03:17

**「background」** Kinexys is JPMorgan’s rebranded unit for blockchain-based institutional payments and tokenized deposits, operating a permissioned payments rail that the bank used for the reported AI-agent proof‑of‑concept.

**「Impact」** If scaled, corporate treasuries and payments providers could see operational change because blockchain-linked AI agents would negotiate and execute FX and payments, raising the importance of automated transaction limits and governance controls.

<details><summary>References</summary>
<ul>
<li><a href="https://www.jpmorgan.com/insights/payments/blockchain-digital-assets/introducing-kinexys">Introducing Kinexys | J . P . Morgan</a></li>
<li><a href="https://rareevo.io/news/t/enterprise-blockchain">Rare Evo 2026 Blockchain AI Conference Vegas</a></li>

</ul>
</details>

**Tags**: `#AI payments`, `#blockchain`, `#corporate treasury`, `#fintech innovation`, `#governance and controls`

---

<a id="item-finance-news-4"></a>
### [U.S. tech firms confront tighter U.S. chip export and remote-access rules](https://www.cnbc.com/2026/11/17/us-tech-firms-china-ties-political-pressure.html) ⭐️ 7.0/10

The U.S. tightened restrictions on Chinese firms&\#x27; remote access to advanced U.S. chips on Monday \(a policy move intended to prevent bypassing export controls\), forcing companies such as Nvidia and Apple to weigh continued China market access against national-security and supply‑chain risks.

rss · CNBC Finance · Nov 17, 08:52

**「background」** This follows recent U.S. steps tightening export and remote‑access rules for advanced chips and a multilateral &\#x27;San Francisco Declaration&\#x27; to protect sensitive technologies, measures that have intensified the trade‑off U.S. tech firms face between China market access and national‑security and supply‑chain risks.

**「Impact」** U.S. technology companies with sales or manufacturing ties to China may face reduced market access and higher supply‑chain disruption risk as export controls limit chip sales and Beijing&\#x27;s control of critical minerals raises the prospect of retaliatory restrictions.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/17/nvidia-china-cloud-ai-chip-access.html">Nvidia warns chip buyers of legal risks tied to China access : sources</a></li>

</ul>
</details>

**Tags**: `#US-China tech tensions`, `#export controls`, `#supply chains`, `#big tech`, `#geopolitical risk`

---