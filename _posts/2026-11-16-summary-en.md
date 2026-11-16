---
layout: default
title: "Horizon Summary: 2026-11-16 (EN)"
date: 2026-11-16
lang: en
---

> From 36 items, 18 important content pieces were selected

---

**Technology News**
1. [datasette 0.65.6: security backport](#item-tech-news-1) ⭐️ 8.0/10
2. [Meta FAIR + NYU: Pretraining optional for multimodal vision encoding](#item-tech-news-2) ⭐️ 8.0/10
3. [Rubio, Anthropic Allegedly Linked to Campaign Targeting Jensen Huang](#item-tech-news-3) ⭐️ 8.0/10
4. [Meituan open-sources LongCat-2.5 \(Ascend-trained claim\)](#item-tech-news-4) ⭐️ 8.0/10
5. [Judge Denies Dismissal in DRAM Price‑Fixing Suit Against Micron, Samsung, SK Hynix](#item-tech-news-5) ⭐️ 8.0/10
6. [Apple N50 smart glasses target 2027 release](#item-tech-news-6) ⭐️ 8.0/10
7. [Reports: Old Bitly links hijacked](#item-tech-news-7) ⭐️ 7.0/10
8. [Understanding Positional Embeddings in Modern LLMs](#item-tech-news-8) ⭐️ 7.0/10
9. [Microsoft 365 outage tied to hotel chlorine incident](#item-tech-news-9) ⭐️ 7.0/10
10. [Protomaps: Self-hosting map tiles is now cheap and easy](#item-tech-news-10) ⭐️ 7.0/10
11. [MacBook Pro OLED PWM flicker](#item-tech-news-11) ⭐️ 7.0/10
12. [datasette 1.0a43: streaming output renderers, security fix](#item-tech-news-12) ⭐️ 7.0/10
13. [Tool boosts cudaMemcpy pageable transfers up to 5× on a B300](#item-tech-news-13) ⭐️ 7.0/10
14. [3C certification suspensions block e‑bike registrations](#item-tech-news-14) ⭐️ 7.0/10
15. [Huawei Cloud launches openPangu-2.1-Pro on MaaS](#item-tech-news-15) ⭐️ 7.0/10

**Financial News**
1. [Cantor Fitzgerald&\#x27;s Nvidia ties raise questions for Commerce Secretary Lutnick](#item-finance-news-1) ⭐️ 9.0/10
2. [Report: Jensen Huang in talks to return as Nvidia CEO](#item-finance-news-2) ⭐️ 8.0/10
3. [US, China and Russia leaders to hold first trilateral meeting at APEC on Nov 19](#item-finance-news-3) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [datasette 0.65.6: security backport](https://simonwillison.net/2026/Nov/15/datasette-2/) ⭐️ 8.0/10

datasette 0.65.6 was released with a backported security fix that prevents databases from being downloaded via their route when the route differs from the registered database name. The bug allowed a database registered with add\_database\(db, name=..., route=...\) to be downloaded from /&lt;route&gt;.db by actors who should have been denied access; this fix was backported from 1.0a43. Administrators running Datasette should upgrade to 0.65.6 to obtain the patch.

rss · Simon Willison · Nov 15, 23:18

**「How Datasette routes and database downloads work」** Datasette exposes registered databases at HTTP endpoints and lets operators register a database with add\_database\(db, name=..., route=...\) so the URL route can differ from the database name. That arrangement creates a downloadable .db endpoint \(/&lt;route&gt;.db\), and if routing and name-based access checks don&\#x27;t align a route mismatch can permit downloading a database even when access controls would otherwise deny it.

**「Concrete impact and recommended action」** Deployments that register databases with a route different from the database name may have been exposing .db downloads to unauthorized users; operators should promptly upgrade to datasette 0.65.6 \(or to a release that includes the same fix\) and audit any add\_database\(...\) calls where name and route differ to confirm access controls are correct.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/Happ-proxy/happ-desktop/releases">Releases · Happ-proxy/happ-desktop · GitHub</a></li>

</ul>
</details>

**Tags**: `#security`, `#datasette`, `#release`, `#open-source`

---

<a id="item-tech-news-2"></a>
### [Meta FAIR + NYU: Pretraining optional for multimodal vision encoding](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 8.0/10

A large-scale empirical study from Meta FAIR and NYU that trained 200+ multimodal models on the same data and matched lifetime compute finds that separate encoder pretraining is not necessary for VQA and related multimodal tasks provided the model keeps vision-dedicated parameters. The experiments compare Qwen3-based backbones \(1.7B and 4B\) with ~0.4B vision parameters and a scaling ladder from 0.6B to 6.4B, and evaluate on 16 VQA benchmarks \(at 448 px\) plus 12 language benchmarks. Key findings: encoders pretrained under four objectives at matched compute at best tie encoders trained from scratch; removing vision-only parameters \(encoder-free designs\) trails at every size and requires about 3× the compute to match performance; placing vision branches “in-fusion” inside the LLM \(zero-initialized vision-only weights in the first 8 layers\) matches separate encoders while reducing time-to-first-token by ~13%. The paper also reports that much longer pretraining \(MetaCLIP\) raised ImageNet linear-probe accuracy but did not improve VQA. The study was run with encoder pretraining counted against the same compute budget as multimodal training, and the submitter notes they are one of the paper’s authors.

reddit · r/MachineLearning · /u/trungh98 · Nov 15, 17:38

**「Why a vision encoder matters for multimodal LLMs」** Multimodal large language models need a component that converts image pixels into token-like representations for the LLM; the common solution is a pretrained vision encoder, though some recent models instead train that component jointly with the LLM or omit it entirely. The paper treats a vision encoder as three separate design choices—upstream pretraining, parameters dedicated only to vision tokens, and placement before fusion into the language model—and tests those choices independently to see which actually drive downstream multimodal performance.

**「Consequence and recommended action」** For practitioners designing multimodal LLMs, the evidence suggests you should prioritize allocating compute and parameters to vision-dedicated capacity rather than to a separate encoder pretraining stage, and avoid architectures that remove vision-only parameters entirely. If latency or integration is a concern, consider the in-fusion placement \(vision-only branches in early LLM layers\) to match encoder performance with lower time-to-first-token; however, ensure vision-specific parameters remain separate from text token parameters and account any encoder pretraining against your overall compute budget because longer pretraining did not improve VQA in these experiments.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.17334">[2611.17334] Unbundling Multimodal Vision Encoding - arXiv.org</a></li>
<li><a href="https://huggingface.co/papers/2611.17334">Paper page - Unbundling Multimodal Vision Encoding</a></li>

</ul>
</details>

**Tags**: `#multimodal`, `#vision-encoders`, `#empirical-study`, `#model-training`

---

<a id="item-tech-news-3"></a>
### [Rubio, Anthropic Allegedly Linked to Campaign Targeting Jensen Huang](https://www.washingtonpost.com/technology/2026/11/13/behind-jensen-huangs-spy-scandal-shadow-war-trumps-ear-china/) ⭐️ 8.0/10

The Washington Post reports allegations that Sen. Marco Rubio and executives at Anthropic were involved in a coordinated campaign that pressured Nvidia founder Jensen Huang and contributed to his departure. The reporting says Rubio used CIA-sourced intelligence to write a hardline memo to influence the president, while investigators trace an initial anonymous tip about a Singapore company called Megaspeed to a ‘‘technology industry contact’’ that some in the press and tech community suspect came from Anthropic; neither the reporters nor Anthropic responded to those suspicions. The article also highlights Huang&\#x27;s earlier lobbying of the Trump administration to loosen chip-export controls and his public opposition to firmware-based tracking or backdoors in GPUs, and notes that lawmakers are now pushing three specific measures into an end-of-year defense bill: further limits on high-end AI chip exports, mandatory anti-diversion/tracking technology built into chips, and restrictions on exports of chipmaking equipment. These allegations are investigative and contested and have not been independently verified in the reporting.

telegram · zaihuapd · Nov 15, 08:08

**「Policy and lobbying context」** The article sits within an ongoing U.S. policy debate over restricting high‑end AI chips and adding firmware‑level tracking or anti‑diversion measures — proposals that lawmakers are seeking to fold into a major defense bill.  Reportedly, Jensen Huang had lobbied for loosening chip export limits and opposed embedding tracking or backdoor functionality in GPUs, while some AI companies have been publicly pushing for stricter export controls and technical measures to prevent unauthorized model use, making those opposing lobbying efforts central to the reported dispute.

**「Practical consequence」** If the cited legislative proposals are adopted, GPU and AI-hardware vendors, cloud providers, and equipment manufacturers should expect tighter export licensing, possible requirements to include firmware-level tracking or anti-diversion features, and new limits on supplying chipmaking tools; affected organizations should begin auditing export compliance, firmware and supply-chain designs, and engage with policymakers because implementation would create technical, legal, and deployment implications.

<details><summary>References</summary>
<ul>
<li><a href="https://www.washingtonpost.com/technology/2026/11/13/behind-jensen-huangs-spy-scandal-shadow-war-trumps-ear-china/">Behind Jensen Huang’s spy scandal, a shadow war for Trump’s ...</a></li>

</ul>
</details>

**Tags**: `#AI policy`, `#hardware`, `#export-controls`, `#investigative journalism`

---

<a id="item-tech-news-4"></a>
### [Meituan open-sources LongCat-2.5 \(Ascend-trained claim\)](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

Meituan&\#x27;s LongCat team published LongCat-2.5 weights under an MIT license one week after the model&\#x27;s initial release. The model is presented as an agent-capable multimodal system \(text, image, and video inputs\) designed for long, multi-step tasks—especially programming—and the team says it activates about 48 billion parameters per token. LongCat-2.5 scored 88.4 on Terminal Bench v2.1 \(compared with Claude Opus 5 at 89.1\), and the team asserts the model was trained using Huawei Ascend accelerators only, not NVIDIA GPUs; that hardware claim is reported by the team in the release and is not independently verified in the source.

telegram · zaihuapd · Nov 15, 11:08

**「Background」** Mixture-of-experts \(MoE\) architectures report very large total parameter counts while routing computation through a small subset of experts for each token; Meituan&\#x27;s LongCat-2.5 is described as an MoE multimodal model with 1.6 trillion total parameters and about 48 billion activated parameters per token. That total-vs-activated distinction matters for comparing training and inference compute, memory, and benchmark results because the activated-parameters figure drives per-token work and resource requirements.

**「Impact」** The MIT commercial license and released weights let companies and researchers deploy or fine-tune LongCat-2.5 without restrictive licensing barriers. Organizations that need to reproduce training or run large-scale training should verify hardware compatibility and request training logs or reproduction details, since the Ascend-only training claim in the announcement is not corroborated by independent evidence in the source; users should also validate model performance on their own workloads despite the reported benchmark score.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/meituan-longcat/LongCat-2.5">meituan - longcat / LongCat - 2 . 5 · Hugging Face</a></li>
<li><a href="https://lmspeed.net/model/longcat-2-5">LongCat - 2 . 5 API Pricing &amp; Benchmarks | LMSpeed</a></li>

</ul>
</details>

**Tags**: `#open-source`, `#model-release`, `#hardware-acceleration`, `#multimodal`, `#benchmarks`

---

<a id="item-tech-news-5"></a>
### [Judge Denies Dismissal in DRAM Price‑Fixing Suit Against Micron, Samsung, SK Hynix](https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge) ⭐️ 8.0/10

U.S. District Judge Noël Wise denied motions by Micron, Samsung, and SK Hynix to dismiss a collective antitrust lawsuit alleging DRAM price‑fixing, finding the plaintiffs presented new evidence and describing the defendants&\#x27; synchronized conduct as “more like formation flying.” The plaintiffs—17 individuals and small businesses—allege the three firms took four parallel actions within a year that restricted DRAM supply and drove prices up as much as 500%. The denial keeps the case alive rather than resolving liability, and the defendants were ordered to file responses by December 7 with a case management conference set for January 2027.

telegram · zaihuapd · Nov 15, 16:39

**「Antitrust pleading and motions-to-dismiss」** Under U.S. antitrust practice, a motion to dismiss tests whether plaintiffs have pleaded sufficient factual detail to make claims of coordinated conduct plausible; if a judge denies that motion the case can proceed to discovery. The plaintiffs here allege Micron, Samsung, and SK hynix carried out parallel production cuts that coincide with large DRAM price increases, a pattern the court found plausibly consistent with collusion rather than independent decision‑making.

**「Immediate consequence」** Because the court declined to dismiss the complaint, the litigation proceeds and the companies must prepare substantive responses and potential discovery starting before the December 7 deadline and the January 2027 case management conference; affected buyers and OEMs should monitor the case for possible impacts on pricing, damage claims, or supply‑chain disclosures. 

<details><summary>References</summary>
<ul>
<li><a href="https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge">Judge denies motion to dismiss DRAM price - fixing lawsuit against...</a></li>

</ul>
</details>

**Tags**: `#antitrust`, `#DRAM`, `#memory-market`, `#hardware`, `#supply-chain`

---

<a id="item-tech-news-6"></a>
### [Apple N50 smart glasses target 2027 release](https://www.bloomberg.com/news/newsletters/2026-11-15/apple-siri-ai-app-integrations-power-smart-glasses-iphone-duo-2-face-id-plan) ⭐️ 8.0/10

Bloomberg reports Apple is targeting a 2027 launch for its first smart glasses, internal code name N50, with a planned reveal at Apple’s June developer conference and shipments by year‑end. The reported first‑generation device will not include an AR display, must pair with a newer iPhone \(no Android support\), and will run third‑party apps on the phone rather than on the glasses while offering deep Siri and iPhone integration. Prototypes are described as slightly thinner than Meta’s second‑generation Ray‑Ban, use a three‑pin magnetic charging connector that can charge while worn, and Bloomberg warns software and AI readiness could delay the schedule \(including uncertainty about adding Face ID via a second‑generation iPhone Duo\).

telegram · zaihuapd · Nov 16, 02:13

**「Context: self-contained AR headsets vs. phone-hosted glasses」** Smart glasses typically split into self-contained AR headsets \(with onboard displays and local compute\) and lighter, phone-hosted companions that surface notifications and run apps on a paired smartphone. That distinction clarifies why a first-generation device without an AR display but with deep iPhone/Siri integration would be framed as a companion accessory rather than a standalone mixed‑reality headset.

**「Impact for developers and partners」** Developers should design experiences as phone‑hosted apps that integrate with Siri and recent iPhone models rather than assuming on‑device AR rendering, and partners should not expect Android compatibility or a first‑gen AR display when planning integrations or accessories.

**Tags**: `#apple`, `#wearables`, `#smart-glasses`, `#hardware`, `#ai-integration`

---

<a id="item-tech-news-7"></a>
### [Reports: Old Bitly links hijacked](https://ransomnews.com/burger-king-tweet-bitly-link-hijack-2026/) ⭐️ 7.0/10

Hacker News threads report that old Bitly short URLs are being hijacked, with community members saying previously created links now resolve to different — and in some reports potentially malicious — destinations. The supplied item contains no primary source content or independent verification, and it does not specify the scale, timeline, or mechanism \(for example, account takeover, Bitly policy/contract change, or domain reissue\) behind the reassignments. Readers should treat these reports as anecdotal until confirmed by Bitly or independent measurements.

hackernews · hspeiser · Nov 15, 22:11 · [Discussion](https://news.ycombinator.com/item?id=50511395)

**「How URL shorteners and re-registration work」** URL shorteners like Bitly issue short, opaque endings that the shortener’s service resolves to a destination URL; that resolution is controlled by the shortener’s registry rather than by the original linking page. Recent reports say some of those old Bitly endings were allowed to be re-registered and repointed, causing historic X posts from corporate and political accounts to redirect to different pages and effectively ‘hijacking’ the old links.

**「Immediate consequence and recommended actions」** If the reports are accurate, archived citations, documentation, emails, and social-media posts that rely on Bitly shortlinks can now send users to incorrect or harmful pages, undermining web integrity and creating phishing or malware risk. Affected organizations and authors should, when practical, inventory critical short links and replace them with permanent, canonical URLs or vanity short domains; add redirect-monitoring for important shortlinks; and consider using a self-hosted shortener or archive snapshots for preservable references. These steps are precautionary and should be prioritized for links used in security-sensitive or long-lived contexts.

**「What commenters said」** Commenters argued that outsourced URL shorteners are fragile for web permanence and that reassignable shortlinks are a known risk; some expressed surprise that larger shortener services maintain Trust &amp; Safety teams. Suggestions included using self-managed shortlinks \(for example, via vanity domains or services like shorter.dev\) and relying on web archives or institutional tracking to preserve the original content.

<details><summary>References</summary>
<ul>
<li><a href="https://nypost.com/2026/11/15/lifestyle/corporate-social-media-hacked-in-bizarre-bitly-link-hijacking-scheme/">Corporate social media hacked in bizarre Bitly link-hijacking ...</a></li>
<li><a href="https://ransomnews.com/burger-king-tweet-bitly-link-hijack-2026/">Old Bitly links hijacked in Burger King, McDonald’s and Trump ...</a></li>

</ul>
</details>

**Tags**: `#web-security`, `#link-shorteners`, `#web-infrastructure`, `#digital-preservation`

---

<a id="item-tech-news-8"></a>
### [Understanding Positional Embeddings in Modern LLMs](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 7.0/10

An implementation-focused explainer titled &quot;Understanding Positional Embeddings in Modern LLMs&quot; provides practical, code-oriented guidance for engineers who build or modify transformer-based models, concentrating on how positional embeddings are implemented and used in modern LLMs. The article emphasizes implementation trade-offs and examples rather than formal mathematical derivations. Community feedback indicates the piece does not provide a deeper theoretical framing—such as the group-representation view of positional encodings—and so is less suitable as a standalone source for theoretical understanding.

hackernews · vismit2000 · Nov 15, 12:14 · [Discussion](https://news.ycombinator.com/item?id=50506376)

**「Positional embeddings basics」** Transformer architectures do not by themselves encode token order, so positional embeddings are applied to give tokens a notion of position for attention mechanisms. Modern variants such as rotary positional embeddings \(RoPE\) have been widely adopted in open-weight LLMs since the original LLaMA model, and the choice of positional method materially affects a model’s ability to handle long prompts and long-context inputs.

**「Concrete consequence for engineers」** Engineers can directly apply the article&\#x27;s implementation guidance to RoPE-style positional embeddings because RoPE has been a staple in most open-weight LLMs since LLaMA, making the walkthrough immediately relevant for many current models. Before fine-tuning, merging, or replacing model weights, explicitly check which positional-embedding scheme each model uses—proprietary models may differ—since mismatches in positional formats can require conversion steps or alter model behavior.

**「Community discussion」** A commenter \(programjames\) argued the article focuses on implementation but omits essential theory, stating that positional embeddings are best understood as group representations and that rotary positional embeddings in particular correspond to representations of the translation group; the commenter recommended a group-representation perspective for finding and parameterizing positional encodings.

<details><summary>References</summary>
<ul>
<li><a href="https://magazine.sebastianraschka.com/p/understanding-positional-embeddings">Understanding Positional Embeddings in Modern LLMs</a></li>
<li><a href="https://dev.to/zeromathai/why-positional-embeddings-matter-ape-rpe-and-rope-explained-for-developers-27gn">Why Positional Embeddings Matter — APE, RPE... - DEV Community</a></li>
<li><a href="https://magazine.sebastianraschka.com/p/understanding-positional-embeddings">Understanding Positional Embeddings in Modern LLMs</a></li>
<li><a href="https://readmedium.com/rope-a-detailed-guide-to-rotary-position-embedding-in-modern-llms-fde71785f152">RoPE: A Detailed Guide to Rotary Position Embedding in Modern ...</a></li>

</ul>
</details>

**Tags**: `#positional-embeddings`, `#transformers`, `#LLMs`, `#tutorial`, `#theory-vs-implementation`

---

<a id="item-tech-news-9"></a>
### [Microsoft 365 outage tied to hotel chlorine incident](https://www1.wdr.de/nrw/rheinland/rhein-erft-kreis/technischer-defekt-chlor-phantasialand-100.html) ⭐️ 7.0/10

Local reports say a Microsoft 365 email outage coincided with a malfunction in a hotel&\#x27;s automated chlorine-dosing system, and that the outage prevented monitoring alerts from being delivered. The reporting alleges 13–15 guests complained of respiratory irritation and four were taken to hospital \(one described as a moderate injury\), but the exact causal chain between the dosing failure, the missed notifications, and the health effects is unclear and not independently confirmed. Available accounts describe a dual failure—an operational fault in the dosing equipment plus an interruption of email-based alerts—but do not establish whether the Microsoft outage alone caused or significantly worsened the incident. Until investigators publish a technical incident report, responsibility and specific system failures remain uncertain.

hackernews · DeepLogin · Nov 15, 18:36 · [Discussion](https://news.ycombinator.com/item?id=50509411)

**「Why automated pool monitoring matters」** Commercial pool chemistry is typically managed by automated dosing and monitoring systems that both adjust chlorine levels and raise alarms when concentrations leave safe ranges; hardware or sensor faults can cause over‑ or under‑dosing and rely on timely human notification to limit harm. German news reports say a technical defect in a hotel&\#x27;s chlorination unit produced excessive chlorine and that staff did not receive timely alerts because email/notification delivery was affected by a Microsoft 365 outage, delaying the response to the dosing failure.

**「Avoid relying on cloud email as a single safety-alert path」** If reports that a Microsoft 365 outage coincided with a hotel chlorine-dosing failure are correct, organizations that use cloud email as the sole channel for safety or alarm notifications face a real risk of delayed detection of hazardous failures, with direct harm to people. Actionable steps are to audit any safety‑critical alerts that depend on Microsoft 365/Exchange, add independent redundant notification channels \(local audible/visual alarms, cellular/SMS alerts, separate monitoring services\), and implement hardware fail‑safe interlocks that move systems to a safe state when sensors or communications fail rather than relying only on SLA credits or post‑incident remediation.

**「Discussion highlights」** Commenters argued the root cause may be the hotel&\#x27;s operational and design choices: one commenter with chlorination experience warned such dosing systems can fail in ways that overdispense chlorine, while others \(including a commenter identifying as an Azure employee\) emphasized that relying solely on cloud email for safety-critical alerts is poor design and the hotel&\#x27;s responsibility. Several commenters also noted translation gaps in the coverage and cautioned against blaming Microsoft without a clear technical link between the outage and the hardware fault.

<details><summary>References</summary>
<ul>
<li><a href="https://www.spiegel.de/panorama/phantasialand-in-bruehl-wegen-microsoft-ausfall-chlorpanne-zu-spaet-entdeckt-15-verletzte-a-6e70b4ec-9e3e-4c52-aae5-28beaa2fef62">Phantasialand in Brühl: Chlor-Ausfall durch Microsoft-Panne ...</a></li>
<li><a href="https://www.tagesschau.de/inland/regional/nordrheinwestfalen/verletzte-phantasialand-chlor-100.html">Zu viel Chlor im Pool: 15 Gäste im Phantasialand verletzt</a></li>
<li><a href="https://www.npr.org/2026/11/12/nx-s1-6039343/is-outlook-down-widespread-outage-hits-microsoft-email-and-other-apps">Widespread outage hits Microsoft email and other apps : NPR</a></li>
<li><a href="https://lazyadmin.nl/office-365/microsoft-365-outage-november-2026/">Microsoft 365 Outage - Current Status and SLA Credits — LazyAdmin</a></li>

</ul>
</details>

**Tags**: `#cloud-outage`, `#safety-critical-systems`, `#monitoring`, `#reliability`, `#incident-response`

---

<a id="item-tech-news-10"></a>
### [Protomaps: Self-hosting map tiles is now cheap and easy](https://bruceroettgers.eu/blog/protomaps/) ⭐️ 7.0/10

A practical write-up argues that self‑hosting map tiles has become inexpensive and straightforward for engineers building map-backed apps. The piece highlights community tooling and examples—PMTiles \(a tiled archive format\), gloss \(PMTiles viewer/CLI\), Cloudflare R2 \(object storage\), ntmaps \(a Go library\), and projects such as OpenFreeMap—that together make storing and serving vector and raster basemaps from cheap object storage and edge workers a viable alternative to hosted tile services. The author emphasizes cost and privacy benefits while noting that very large or high-resolution satellite imagery remains an outlier use case with different storage and bandwidth needs.

hackernews · bcye · Nov 15, 19:26 · [Discussion](https://news.ycombinator.com/item?id=50509837)

**「Protomaps &\#x27;map‑in‑a‑file&\#x27; concept」** Protomaps treats a map as a single file that frontend code can read over plain HTTP using range requests, so clients can fetch vector tiles without running a traditional tile server. The PMTiles format and associated tools and integrations \(for example, Grid&\#x27;s Custom Provider configured for PMTiles\) are the practical building blocks that make self‑hosting tiles from object storage or simple static hosts feasible for applications.

**「Impact」** Developers can materially reduce hosting costs and external dependence by packaging tiles \(for example with PMTiles\), placing them on affordable object storage like Cloudflare R2, and serving them at the edge; teams should evaluate PMTiles tooling and worker integration before migrating. Community reports show practical limits for very high‑resolution satellite imagery—developers should test tile sizes and raster formats \(some viewers report failures for very large tiles\) and plan storage/zoom cutoffs accordingly because storage needs can grow to many terabytes for wide, high‑zoom coverage.

**「Community discussion」** Commenters pointed to OpenFreeMap as a public instance and described real projects that became feasible once hosting costs dropped, while other contributors noted tooling gaps such as gloss failing on very large tiles or some raster formats and mentioned ntmaps as an alternative library to integrate with local infrastructure. These comments mix practical experience and opinion, and they underline testing formats, tile sizes, and expected storage before committing to self‑hosting.

<details><summary>References</summary>
<ul>
<li><a href="https://protomaps.com/">Protomaps - The open source map in a file</a></li>
<li><a href="https://github.com/Rezivure/Grid-Protomaps">Rezivure/Grid- Protomaps : The Protomaps &quot;serverless&quot; map tile ...</a></li>
<li><a href="https://thejeshgn.com/2021/05/25/protomaps-self-hosted-maps-and-map-tiles/">Protomaps – Self Hosted Maps and Map Tiles – Thejesh GN</a></li>

</ul>
</details>

**Tags**: `#maps`, `#geospatial`, `#infrastructure`, `#open-source`, `#privacy`

---

<a id="item-tech-news-11"></a>
### [MacBook Pro OLED PWM flicker](https://macanorak.com/the-macbook-pros-oled-pwm-problem-when-a-better-display-becomes-worse-to-use/) ⭐️ 7.0/10

Reports have highlighted that the MacBook Pro&\#x27;s new OLED displays use pulse‑width modulation \(PWM\) dimming that can produce perceptible flicker for some users. Testers and community measurers disagree on the PWM rates — the published coverage cited a 240 Hz reading while other participants suggested higher harmonics or combined‑panel behavior at 480 Hz or an effective 960 Hz — and the measurements remain contested rather than independently confirmed. Users and accessibility advocates have reported eye strain and difficulty concentrating tied to the displays&\#x27; dimming behavior, and the coverage emphasizes that these effects vary by individual sensitivity and by the test method used. The situation is therefore a report of user‑facing flicker risks, not an authoritative, manufacturer‑published specification change.

hackernews · MacAnorak · Nov 15, 13:15 · [Discussion](https://news.ycombinator.com/item?id=50506719)

**「PWM basics and why OLED differs」** Pulse‑width modulation \(PWM\) controls brightness by rapidly switching a light source on and off; on OLED screens that switching is applied at the pixel level because pixels themselves emit light rather than using a separate backlight. The PWM frequency matters for perceived flicker — lower rates can be visible or cause discomfort for sensitive users — and early measurements cited for the MacBook Pro OLED \(around 240 Hz\) contrast with much higher reported PWM rates for the mini‑LED model \(reported around 14,880 Hz\).

**「Impact」** Anyone who is sensitive to display flicker \(for example, people prone to migraines, concussion patients, or those with documented photosensitivity\) may experience increased eye strain or headaches on affected MacBook Pro OLED units; the practical action is to test the specific laptop at the brightness levels you use in person before buying, and employers or procurement teams should avoid assuming the OLED model is suitable for all users until Apple or independent labs publish consistent PWM measurements or offer a DC‑dimming option. 

**「Community discussion」** Commenters focused on two disputes: whether the scope and test rigs reported the correct base PWM frequency \(some quoted 240 Hz while others argued for 480 Hz or an effective 960 Hz when two OLED subpanels operate out of phase\), and strong anecdotal reports from flicker‑sensitive people who say the screen causes real discomfort. These points are opinions and measured claims from community members rather than settled, independently verified facts.

<details><summary>References</summary>
<ul>
<li><a href="https://macanorak.com/the-macbook-pros-oled-pwm-problem-when-a-better-display-becomes-worse-to-use/">The MacBook Pro ’ s OLED PWM Problem : When a ‘Better’ Display...</a></li>
<li><a href="https://www.youtube.com/watch?v=sGgowKoztzk">Is the PROLED ( OLED ) MacBook Pro a Disaster? Flicker ... - YouTube</a></li>

</ul>
</details>

**Tags**: `#displays`, `#OLED`, `#hardware`, `#user-experience`, `#health`

---

<a id="item-tech-news-12"></a>
### [datasette 1.0a43: streaming output renderers, security fix](https://simonwillison.net/2026/Nov/15/datasette/) ⭐️ 7.0/10

datasette 1.0a43 was released with streaming support for output renderers: the built-in CSV and TSV exports now use a new Response.stream\(\) API so a renderer \(including plugins\) can stream every row of a table in one response. The release also includes a couple of security fixes, one documented with a GitHub advisory \(private stored queries could expose a query&\#x27;s title and SQL, but not permit execution\). The author notes the 1.0 milestone is 53% complete and that Claude Fable 5.2 was used to help with development, and adds CSS multi-page view transitions to improve navigation feel in Safari and Chrome \(Firefox support is expected in Firefox 162\).

rss · Simon Willison · Nov 15, 23:20

**「Background」** Datasette publishes SQLite databases as web APIs and supports extensible output renderers for things like CSV and TSV exports. The release adds a Response.stream\(\) API that lets renderers emit rows progressively instead of assembling the entire output before sending, which is the mechanism that enables streaming CSV/TSV exports and streaming-capable plugins.

**「Impact」** For users and operators: upgrade to this release to receive the stored-query exposure fix \(the issue is tracked in a GitHub advisory\). For plugin authors and deployments serving large tables: implement or adopt the Response.stream\(\) output-renderer API so CSV/TSV and similar exports can be streamed rather than materialized in memory, reducing memory usage and improving export reliability for very large result sets.

**Tags**: `#datasette`, `#streaming`, `#plugins`, `#security`

---

<a id="item-tech-news-13"></a>
### [Tool boosts cudaMemcpy pageable transfers up to 5× on a B300](https://www.reddit.com/r/MachineLearning/comments/1xx2n25/making_cudamemcpy_5x_faster_on_a_b300_p/) ⭐️ 7.0/10

A Reddit post links to a blog and a GitHub project \(cudamemcpy-tuner by Maknee\) that claims to speed up cudaMemcpy pageable host-to-device transfers by up to about 5× on a &quot;B300&quot; machine. The author reports a microbenchmark copying a 1 GB torch.uint8 tensor five times where CPU→GPU throughput increases from 10.2 GB/s to 51.5 GB/s after running the tool&\#x27;s tuning command \(&\#x27;cmt tune&\#x27;\). The code and writeup are available on GitHub and the blog, but the reported improvement comes from the author&\#x27;s single-machine tests and has not been independently verified.

reddit · r/MachineLearning · /u/makneeee · Nov 15, 18:20

**「Background on CUDA host↔device copies」** In CUDA, cudaMemcpy is the primary API for copying memory between host and device, and it has synchronous and asynchronous variants \(for example, cudaMemcpy vs cudaMemcpyAsync\) that change whether transfers can overlap with computation. Transfer throughput also depends on how the host memory is allocated and the chosen transfer mode, which is why community tools sometimes tune host-to-device copy behavior to raise effective memcpy throughput on particular machines.

**「Consequence and recommended action」** Developers who depend on pageable cudaMemcpy transfers and have similar hardware could see large runtime improvements by trying the tuner&\#x27;s autotuning, but they should first benchmark the tool on their own workloads and compare against alternatives like pinned \(page‑locked\) host memory plus asynchronous transfers. Results may be highly environment-specific \(machine model, GPU, CUDA driver/version, and OS\), so review the project&\#x27;s code and validate correctness and stability before adopting it in production.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.csdn.net/Bruce_0712/article/details/73477126">cudaMemcpy 与cudaMemcpyAsync的区别-CSDN博客</a></li>

</ul>
</details>

**Tags**: `#cuda`, `#gpu-performance`, `#memory-transfer`, `#tools`, `#benchmarking`

---

<a id="item-tech-news-14"></a>
### [3C certification suspensions block e‑bike registrations](https://www.peopleapp.com/column/30053564254-500007786629) ⭐️ 7.0/10

Multiple electric‑bicycle 3C certificates have been suspended, leaving buyers in cities such as Guangzhou and Wuhan unable to complete vehicle registration; the report names brands including 九号, 雅迪, 爱玛, 新日 and 台铃. Certification bodies began pausing certificates after market supervision checks of 201 companies found issues such as replacement of key components and reserved &quot;unlocking&quot; space in designs, and data anomalies were noticed from late September onward. A new set of post‑certification rules that took effect on November 1—summarised as “one vehicle, one battery, one charger, one code”—has tightened post‑market verification and contributed to the suspensions. Brand customer services say there is no timetable for certificate restoration, and vehicle‑registration offices report the registration data are pushed by the national accreditation authority \(国家认监委\) and cannot be changed locally.

telegram · zaihuapd · Nov 15, 06:08

**「Context」** Starting in late September, certification databases in multiple regions showed anomalies and the State Administration for Market Regulation inspected 201 companies, finding changed key components and reserved “unlock” spaces; certification bodies have used those findings to suspend some e‑bike 3C certificates. A new rule effective November 1 — the “one vehicle one battery one charger one code” requirement — tightened post‑certification oversight, and vehicle registration offices say certification data are pushed by the National Certification and Accreditation Administration and cannot be modified, so suspended certificates block registrations.

**「Immediate consequence and recommended actions」** Affected consumers cannot obtain registration plates for impacted models until the suspended 3C certificates are reinstated, creating potential problems for legal use and transfer; dealers who promised immediate registration are delaying or refusing returns. Buyers should verify a model&\#x27;s current 3C status and get written confirmation about registration before completing a purchase, while manufacturers and suppliers should avoid unreported component changes and work with certification bodies and the national accreditation authority to correct submitted product and data records to restore certificates.

**Tags**: `#regulation`, `#hardware`, `#certification`, `#supply-chain`, `#e-bikes`

---

<a id="item-tech-news-15"></a>
### [Huawei Cloud launches openPangu-2.1-Pro on MaaS](https://mp.weixin.qq.com/s/8JfFmscBTDl_mPQMycD8Nw) ⭐️ 7.0/10

Huawei Cloud&\#x27;s MaaS \(Model-as-a-Service\) platform has gone live with the open-source model openPangu-2.1-Pro, announced on November 15, making the model available to MaaS users. The release says the model is upgraded for Agent development, AI coding, and inference optimization, and was tuned with over 100,000 specialist data items to improve Skills triggering and tool invocation. Huawei describes adaptations for HarmonyOS ArkTS development and Ascend operator generation and lists integrations with AgentArts, CodeArts, and OfficeAce; the announcement also publishes inference pricing of 0.8 CNY per million input tokens, 3.2 CNY per million output tokens, and 0.016 CNY per million tokens for cache hits. The notice does not publish model size, architecture details, or independent benchmark results.

telegram · zaihuapd · Nov 15, 16:03

**「Context」** openPangu is Huawei&\#x27;s open-source family of large language models offered through Huawei Cloud&\#x27;s MaaS \(Model-as-a-Service\) platform. Huawei Cloud previously stopped selling openPangu-2.0 Flash and Pro on MaaS on Nov 6 and scheduled their retirement for Nov 30, directing users toward DeepSeek‑V4.1‑Flash‑1017 and GLM‑5.3 as alternatives.

**「Impact」** Developers and teams working in the Huawei/HarmonyOS/Ascend ecosystem gain a hosted, integrated model option that is explicitly positioned for agent workflows and code-related tasks, so they can prototype with MaaS and the listed product integrations without self-hosting. They should, however, confirm model size and performance with their own benchmarks before production use and factor the published token pricing and the much-lower cache-hit rate \(0.016 CNY per million tokens\) into cost estimates and caching strategy.

<details><summary>References</summary>
<ul>
<li><a href="https://pandaily.com/huawei-cloud-maas-openpangu-2-0-flash-pro-offline-nov-30-deepseek-v4-1-flash-glm-5-3">Huawei Cloud to Retire openPangu - 2 .0 Models From MaaS ...</a></li>

</ul>
</details>

**Tags**: `#model-release`, `#cloud-ai`, `#inference-pricing`, `#agent-development`, `#hardware-integration`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Cantor Fitzgerald&\#x27;s Nvidia ties raise questions for Commerce Secretary Lutnick](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 9.0/10

CNBC reports Cantor Fitzgerald, once run by Commerce Secretary Howard Lutnick and now led by his sons, maintained close business and financing ties to Nvidia while U.S. officials raised intelligence and export‑control concerns about chip transfers to China. The firm&\#x27;s reported Nvidia holdings fell about 49% to 1.78 million shares between September 2025 and March 2026, CNBC found.

rss · CNBC Finance · Nov 15, 19:58

**「background」** Howard Lutnick, who ran Cantor Fitzgerald before recusing himself as commerce secretary, has been the subject of reporting that he received classified warnings about Nvidia CEO Jensen Huang’s ties to a suspected Chinese spy while Cantor—now led by his sons—kept sizable financing and investment ties to Nvidia even as U.S. officials pressed export controls on firms such as Megaspeed suspected of diverting Nvidia chips to China; Huang resigned in mid‑November.

**「impact」** The reporting has prompted increased Congressional and interagency scrutiny of Commerce Department export‑control decisions on AI chips, which could affect companies that sell or rely on Nvidia hardware and the financing deals that support them.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/15/bessent-nvidia-ceo-lutnick-megaspeed.html">Bessent calls for ‘dramatic shakeup’ at Nvidia , urges outside CEO</a></li>
<li><a href="https://www.nytimes.com/2026/11/15/us/politics/trump-lutnick-ai-chips-nvidia-cantor-fitzgerald.html">Lutnick Pushed to Weaken Chip Rules That Overlap With His Family...</a></li>

</ul>
</details>

**Tags**: `#ethics`, `#Nvidia`, `#export-controls`, `#national-security`, `#conflict-of-interest`

---

<a id="item-finance-news-2"></a>
### [Report: Jensen Huang in talks to return as Nvidia CEO](https://www.ft.com/content/0f30a230-4d66-481b-a4fd-3a4ed0c45855) ⭐️ 8.0/10

The Financial Times reports Jensen Huang is discussing a return as Nvidia CEO after he resigned last Thursday following revelations of two extramarital affairs — one person is alleged to be a suspected Chinese spy — and allies have gathered a supporter petition of more than 156,000 signatures while the board has reportedly contacted Arm CEO Rene Haas as a possible successor. The FT says the resignation and the spy allegation have raised questions about U.S.-China AI chip export and corporate-governance risks at Nvidia.

telegram · zaihuapd · Nov 16, 01:06

**「background」** Jensen Huang resigned last week after reports of two extramarital affairs, including one partner alleged to be a Chinese spy, and the Financial Times says Nvidia&\#x27;s board has contacted Arm CEO Rene Haas as a potential successor.

**「Impact」** If true, the reported leadership uncertainty could prompt increased U.S. export scrutiny of Nvidia&\#x27;s China sales and unsettle customers, partners and investors that rely on its AI GPUs.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.yahoo.com/technology/live/nvidia-live-updates-following-jensen-huangs-resignation-as-ceo-allegations-of-a-third-affair-emerge-195535310.html">Nvidia live updates: Following Jensen Huang &#x27;s resignation as CEO ...</a></li>
<li><a href="https://www.ft.com/content/a93307a7-e2cd-4abd-bd89-c38832d8c40e?syn-25a6b1a6=1">Nvidia shares slide as Jensen Huang resigns as chief executive</a></li>

</ul>
</details>

**Tags**: `#company-leadership`, `#semiconductors`, `#geopolitics`, `#corporate-governance`

---

<a id="item-finance-news-3"></a>
### [US, China and Russia leaders to hold first trilateral meeting at APEC on Nov 19](https://apnews.com/article/trump-xi-putin-summit-china-5fe92253ef38100bae913834a9b74d72) ⭐️ 8.0/10

China&\#x27;s foreign ministry spokesman announced that the leaders of the United States, China and Russia plan to hold their first dedicated three‑way meeting on Nov. 19 on the sidelines of the APEC summit in Shenzhen; the meeting is not part of APEC&\#x27;s official agenda, and media reports call it the first such trilateral meeting.

telegram · zaihuapd · Nov 16, 01:38

**「background」** China’s Foreign Ministry announced the U.S., Chinese and Russian leaders will hold a trilateral meeting on Nov. 19 on the sidelines of the APEC summit in Shenzhen — an event Chinese media describe as the first dedicated three-way meeting and which is not part of APEC’s formal agenda.

<details><summary>References</summary>
<ul>
<li><a href="https://apnews.com/article/trump-xi-putin-summit-china-5fe92253ef38100bae913834a9b74d72">Trump, Xi and Putin plan an unprecedented meeting next week ...</a></li>

</ul>
</details>

**Tags**: `#geopolitics`, `#summit`, `#APEC`, `#US-China-Russia`

---