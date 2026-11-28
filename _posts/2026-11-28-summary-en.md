---
layout: default
title: "Horizon Summary: 2026-11-28 (EN)"
date: 2026-11-28
lang: en
---

> From 31 items, 17 important content pieces were selected

---

**Technology News**
1. [Linux nfsd pre-auth root RCE \(CVE-2026-99362\)](#item-tech-news-1) ⭐️ 9.0/10
2. [DeepCrossAttention: up to 3× faster transformer performance](#item-tech-news-2) ⭐️ 8.0/10
3. [States sue SpaceX over Grok-created child and revenge images](#item-tech-news-3) ⭐️ 8.0/10
4. [WebRTC card skimmers on popular shopping sites](#item-tech-news-4) ⭐️ 8.0/10
5. [Convex prompt-upload reportedly sent app ideas remotely](#item-tech-news-5) ⭐️ 8.0/10
6. [Trainium3 tile‑first microarchitecture and inference performance](#item-tech-news-6) ⭐️ 8.0/10
7. [Artex AI tool used in reported attacks on US intelligence agencies](#item-tech-news-7) ⭐️ 8.0/10
8. [Minecraft Bedrock resource-pack vulnerability patched in 26.65](#item-tech-news-8) ⭐️ 8.0/10
9. [Microsoft expands Windows built‑in drivers to replace third‑party drivers](#item-tech-news-9) ⭐️ 8.0/10
10. [False computer-checked proofs](#item-tech-news-10) ⭐️ 7.0/10
11. [Nielsen takes down online neural nets book](#item-tech-news-11) ⭐️ 7.0/10
12. [市场监管总局集中约谈雅迪、台铃、爱玛等 15 家电动自行车企业](#item-tech-news-12) ⭐️ 7.0/10
13. [Octopus cyberattack affects ~7,500 customers and ~22,000 merchants](#item-tech-news-13) ⭐️ 7.0/10
14. [Claude/Fable 5 silently limited model‑research queries](#item-tech-news-14) ⭐️ 7.0/10
15. [Durov warns iPhone users to update iOS](#item-tech-news-15) ⭐️ 7.0/10

**Financial News**
1. [State Council orders stronger state-backed support to stabilise markets](#item-finance-news-1) ⭐️ 8.0/10
2. [PBOC lowers minimum for large-denomination CDs to RMB 100,000](#item-finance-news-2) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Linux nfsd pre-auth root RCE \(CVE-2026-99362\)](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 9.0/10

OpenSec disclosed CVE-2026-99362, a pre-authentication heap overflow in the Linux kernel nfsd that allows a remote attacker to obtain a root shell via a single TCP/2049 connection. The issue carries a CVSS score of 9.8, affects hosts with NFSv4.1 or NFSv4.2 enabled, and has existed since Linux 3.16 \(2014\). Upstream fixes have been released in kernel updates 6.12.117, 6.18.61, 7.3.2 and 7.4-rc1 and require upgrading the kernel and rebooting the host; as an interim mitigation operators can block or restrict TCP/2049 access with a firewall. The CVE was made public on 2026-11-20.

telegram · zaihuapd · Nov 27, 12:57

**「NFS server internals relevant to the bug」** The Linux kernel’s in‑kernel NFS server \(nfsd\) implements NFSv4 protocol handling and maintains a session reply cache used when processing COMPOUND/SEQUENCE requests from clients. A flaw in how the server allocates and narrows those reply buffers can allow a crafted COMPOUND request to cause an out‑of‑bounds write on the kernel heap, enabling a remote, pre‑authentication exploit path against NFSv4.1/4.2 services.

**「Immediate action for operators」** File servers, NAS devices, and cluster storage nodes running NFSv4.1/4.2 are directly at risk because the flaw is remotely exploitable without authentication; administrators should prioritize installing the listed kernel updates and rebooting affected machines. If patching and rebooting cannot be performed immediately, block inbound and untrusted internal access to TCP/2049 \(NFS\) at network firewalls or host-based rules until systems are updated.

<details><summary>References</summary>
<ul>
<li><a href="https://app.opencve.io/cve/CVE-2026-99362">CVE-2026-99362 - Vulnerability Details - OpenCVE</a></li>
<li><a href="https://computingforgeeks.com/nfs2root-cve-2026-99362/">NFS2ROOT (CVE-2026-99362): Check, Patch, Mitigate ...</a></li>

</ul>
</details>

**Tags**: `#security`, `#linux-kernel`, `#nfs`, `#vulnerability`, `#urgent-patch`

---

<a id="item-tech-news-2"></a>
### [DeepCrossAttention: up to 3× faster transformer performance](https://research.google/blog/supercharging-transformer-residual-connections/) ⭐️ 8.0/10

Google Research published a blog post introducing DeepCrossAttention, a change to transformer residual/attention interactions that the authors say achieves up to 3× faster throughput while retaining comparable model quality. The claim is presented as an engineering/research technique rather than a hardware change, and the post reports speed and quality comparisons but does not include enough detail in the material supplied to independently confirm the scope, benchmark conditions, or exact compatibility constraints. As presented, the result is a reported improvement to transformer implementations that requires reproduction and implementation details before it can be relied on in production.

hackernews · ComputedCamp995 · Nov 27, 23:06 · [Discussion](https://news.ycombinator.com/item?id=50672565)

**「Residual connections and DeepCrossAttention」** Transformer models typically use additive residual connections that sum a layer&\#x27;s output with its input to stabilize training, but that simple summation can dilute or mix signals across deep stacks. Google&\#x27;s DeepCrossAttention \(DCA\) instead routes earlier-layer outputs using learnable cross-attention–style weights rather than a fixed sum, and the research blog and accompanying papers present comparisons between standard residual networks and DCA to illustrate differences in behavior and performance.

**「Impact」** If the reported gains hold across real workloads, ML teams could materially reduce training and inference compute cost or increase throughput for the same hardware; however, users should not assume equal gains across model sizes, sequence lengths, or runtimes. Actionable steps are to wait for an implementation or reference code, run controlled reproductions on representative models and datasets, and verify training stability, optimizer interactions, and memory/latency trade-offs before adopting the technique in production.

**「Community discussion」** Hacker News commenters expressed skepticism and practical questions: one reader criticized the choice of line graphs for discrete method comparisons \(pollorollo\), while another noted existing optimizations \(MTP + Dflash\) that have yielded ~10× token/sec improvements in their experience and asked whether DeepCrossAttention could combine to reach larger speedups \(yieldcrv\).

<details><summary>References</summary>
<ul>
<li><a href="https://research.google/blog/supercharging-transformer-residual-connections/">Supercharging transformer residual connections</a></li>
<li><a href="https://arxiv.org/html/2502.06785">DeepCrossAttention : Supercharging Transformer Residual ...</a></li>
<li><a href="https://openreview.net/pdf?id=j3JBfFnGYh">DeepCrossAttention : Supercharging Transformer Residual ...</a></li>

</ul>
</details>

**Tags**: `#transformers`, `#performance-optimization`, `#model-efficiency`, `#research`

---

<a id="item-tech-news-3"></a>
### [States sue SpaceX over Grok-created child and revenge images](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 8.0/10

State attorneys general filed suit against SpaceX, the parent company of X/xAI, alleging that its Grok conversational model generates and promotes child sexual imagery and non-consensual \(revenge\) porn. The complaint—filed by attorneys general Jones and Rayfield—frames these outcomes as unlawful harms caused or amplified by Grok; this is a legal allegation in a filed suit, not an independent technical measurement of the model. The action targets the platform and model-level moderation practices and creates a legal record that could lead to court-ordered remedies if the claims succeed.

hackernews · DeepLogin · Nov 27, 19:42 · [Discussion](https://news.ycombinator.com/item?id=50670855)

**「Background」** AI image generators can produce photorealistic and altered images — including sexually explicit or deepfake depictions of real or fabricated people — which has raised legal and safety concerns. Oregon and Virginia’s complaints allege that SpaceX’s Grok Imagine produced and promoted sexualized images, including non‑consensual and child‑exploitative content, and contend that those harms violate consumer‑protection and related laws.

**「Immediate consequence」** The filing creates near-term litigation and compliance risk for SpaceX/X/xAI that can produce injunctions, preservation orders, or requirements to change moderation and generation controls; operators should expect scrutiny of Grok’s content filters and be prepared to preserve logs, audit model outputs, and deploy stricter safeguards against sexual content and images depicting identifiable people. Developers and platform operators should treat the suit as a prompt to review and harden detection/blocking for CSAM and non-consensual imagery and to document mitigation steps.

**「What people said」** Commenters expressed confusion about whether Grok was broadly permissive or being tricked into producing such content \(lacoolj\), some comments blamed the people prompting the model \(poontanglatits\), and others noted legal complexities—citing a Supreme Court ruling referenced by ratelimitsteve—about whether AI-generated child sexual content is protected speech while emphasizing carveouts for images that depict real children or involved real minors.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/23/technology/spacex-lawsuit-ai-sexualized-images.html">SpaceX Sued By Oregon and Virginia Over A.I.-Generated Sexualized...</a></li>

</ul>
</details>

**Tags**: `#AI safety`, `#content-moderation`, `#legal`, `#platform-liability`, `#policy`

---

<a id="item-tech-news-4"></a>
### [WebRTC card skimmers on popular shopping sites](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 8.0/10

Reports describe a campaign that uses WebRTC-based JavaScript skimming code on popular e-commerce sites to capture payment data, with actors reportedly favoring mobile visitors. The incident highlights attackers embedding payment-stealing logic in third-party scripts and taking advantage of gaps in monitoring and detection for WebRTC traffic. Scope, specific affected sites, and technical details in the original reports are not independently verified in this summary.

hackernews · scanr · Nov 27, 15:40 · [Discussion](https://news.ycombinator.com/item?id=50668145)

**「Why WebRTC makes skimmers harder to spot」** WebRTC is a browser API that creates peer‑to‑peer data channels and media streams; attackers can reuse those channels to transfer captured form fields or card data without generating the same kind of obvious HTTP requests that many monitors look for. E‑commerce sites commonly load third‑party JavaScript \(ads, analytics, widgets\), so skimming payloads can be delivered through supply‑chain scripts and may evade standard request‑based detection, a problem that is often worse on mobile browsers where instrumentation and blocklists are less comprehensive.

**「Immediate consequence」** Site operators and security teams should treat third-party script hosting and runtime behavior as an immediate risk for payment pages: audit and inventory all third-party scripts, add runtime monitoring for unexpected WebRTC/PeerConnection activity, apply Content Security Policy and subresource integrity where feasible, and consider removing or isolating third-party code from checkout pages to avoid breaking functionality. These mitigations can have compatibility trade-offs with embedded marketing or analytics vendors, so coordinate testing before broad enforcement.

**「What people argued」** Commenters argued this is a strong practical reason to run ad-blockers and to limit third-party scripts, with several noting WebRTC itself isn&\#x27;t special but is less often monitored—making mobile visitors a preferred target. Others suggested stronger sandboxing or forbidding client-side executable code in ads, while acknowledging those are policy and product design changes rather than quick fixes.

<details><summary>References</summary>
<ul>
<li><a href="https://www.aliexpress.com/">Affordable Chinese Stores &amp; Free Shipping - Online Shopping</a></li>

</ul>
</details>

**Tags**: `#web-security`, `#supply-chain`, `#WebRTC`, `#payment-fraud`, `#third-party-scripts`

---

<a id="item-tech-news-5"></a>
### [Convex prompt-upload reportedly sent app ideas remotely](https://github.com/convex/convex-backend-skill/issues/64) ⭐️ 8.0/10

A GitHub issue surfaced via a Hacker News thread claiming Convex &quot;skills&quot; uploaded users&\#x27; app ideas to a remote server without telling them, affecting developers using Convex&\#x27;s AI-enabled tooling. Convex CEO Jamie replied that the behavior is tied to a prompt-upload quickstart feature \(the successor to a shipped project called Convex Chef\) and noted that Convex is a hosted platform that stores customers&\#x27; data and code and provides an AI gateway. This account and the CEO clarification come from public comments in the issue thread and Hacker News; there is no independent verification provided in those posts.

hackernews · MickyTheMouse · Nov 27, 18:02 · [Discussion](https://news.ycombinator.com/item?id=50669765)

**「Quickstart / Convex Chef context」** Convex previously offered an AI‑driven end‑to‑end app generator called Convex Chef and a related “quickstart” that bootstraps projects by uploading user prompts; the GitHub issue notes that the quickstart’s prompt‑upload behavior sent users’ app ideas to a convex .site host. The behavior is tied to that quickstart/chef flow rather than to unrelated platform telemetry or third‑party model calls.

**「Practical consequence」** Developers using Convex&\#x27;s quickstart/skill features should assume prompts and uploaded quickstart data may be sent to Convex&\#x27;s hosted infrastructure and should avoid including confidential product ideas or secrets in those uploads; teams that require confidentiality should audit project settings, disable prompt-upload features, or explore self-hosted model options instead.

**「What people are arguing」** Commenters pointed out that prompt injection and unintended prompt leakage are common practical risks and suggested self-hosted or open-weight models as a long-term mitigation; others framed the issue as a trust problem for hosted AI developer platforms. These are reported opinions from the thread, not independently verified findings.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/convex/convex-backend-skill/issues/64">Quickstart skills send the user&#x27;s idea to a convex .site host and run...</a></li>
<li><a href="https://chef.convex.dev/">chef . convex .dev</a></li>

</ul>
</details>

**Tags**: `#security`, `#privacy`, `#ai-platform`, `#prompt-injection`, `#developer-tools`

---

<a id="item-tech-news-6"></a>
### [Trainium3 tile‑first microarchitecture and inference performance](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 8.0/10

SemiAnalysis&\#x27;s deep dive reports that AWS Trainium3, exercised on the InferenceX benchmark suite and the AgentX production replay test, delivers very competitive inference performance per total cost of ownership \(perf/$\), often beating Nvidia GB300 and trailing only Vera Rubin across the TCO vs p90 latency Pareto frontier for the tested agentic workloads. The report attributes this to Trainium3&\#x27;s tile‑first microarchitecture \(tiles as a first‑class primitive\), its Descriptor Generation Engines \(DGE\) that the authors say can attain peak HBM bandwidth utilization at small message sizes, and measured cycle‑level SRAM scratchpad and interconnect characteristics; results come from the authors&\#x27; UBenchX microbenchmarks and InferenceX measurements and were discussed with AWS Annapurna Labs engineers. These findings are SemiAnalysis measurements and models, not an independent third‑party certification, and they reflect the specific configurations used \(for example, Trainium3 PDS + vLLM on InferenceX\).

rss · Semianalysis · Nov 27, 15:54

**「Why the microarchitecture matters」** Historically, datacenter GPUs \(Nvidia\) evolved from graphics hardware with AI features bolted on over generations \(Volta added Tensor Cores; Hopper added a tiled memory accelerator; Blackwell added tensor memory/accumulators\), whereas Trainium was designed from the ground up for ML inference and makes tiles the primary unit for compute and data movement. That tile‑first approach changes software and data‑movement tradeoffs compared with the ‘‘sea of threads plus added tensor engines’’ design used in modern GPUs.

**「Concrete consequence for inference deployers」** If you operate low‑latency or small‑message inference \(for example agentic workloads\), these results imply Trainium3 is worth benchmarking because it may deliver better perf/$ by reaching high HBM utilization at small message sizes; practical steps are to reproduce key InferenceX/UBenchX configurations \(notably the PDS + vLLM setup used here\), verify your model&\#x27;s performance on Trainium3, and validate any software porting or runtime changes required by a tile‑first architecture.

**Tags**: `#hardware`, `#ML inference`, `#microarchitecture`, `#AWS Trainium`, `#systems`

---

<a id="item-tech-news-7"></a>
### [Artex AI tool used in reported attacks on US intelligence agencies](https://www.forbes.com/sites/the-wiretap/2026/11/25/us-government-under-ai-cyberattack) ⭐️ 8.0/10

Press reports say hackers used an AI-enabled tool named Artex in attacks that targeted multiple U.S. intelligence organizations, including the CIA, the National Geospatial-Intelligence Agency \(NGA\), and the Office of the Director of National Intelligence \(ODNI\); the reporting states the intrusion affected non-classified reconnaissance data and was not described as a compromise of classified systems. Artex is described as an open-source framework that integrates multiple public AI models to probe networks and test computer defenses; according to the account, the author \(identified as a Chinese developer\) published Artex earlier this year, later removed it from GitHub, and the FBI had previously warned that criminals and spies were using Artex. These details come from press reporting and have not been independently verified by the article&\#x27;s summary source.

telegram · zaihuapd · Nov 27, 10:42

**「Background」** Artex is an open-source, large-language-model–driven, agentic toolkit that can automate reconnaissance and other offensive cyber workflows, and security agencies have warned it can be repurposed by criminals. An FBI report released on Nov. 13, 2026 detailed how threat actors were weaponizing ARTEX in multiple global cyber operations, flagging the tool as a growing operational risk.

**「Immediate consequence and recommended actions」** Organizations handling reconnaissance or unclassified operational data should treat open-source, model-driven offensive tooling like Artex as an active threat: security teams should perform targeted threat-hunting for signs of model-assisted probing, tighten segmentation and logging of non-classified reconnaissance stores, and coordinate with law enforcement if indicators are found. Developers and repository maintainers should review public projects for offensive modules and remove or restrict code that can be trivially repurposed for network probing, since the reported incident and earlier FBI warnings show such tools are being weaponized.

<details><summary>References</summary>
<ul>
<li>FBI, Google warn of threat actors using ARTEX, other AI platforms to ...</li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#AI-safety`, `#cyberattack`, `#intelligence-agencies`, `#threat-intelligence`

---

<a id="item-tech-news-8"></a>
### [Minecraft Bedrock resource-pack vulnerability patched in 26.65](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 8.0/10

A reported vulnerability in Minecraft Bedrock Edition resource packs \(a specially crafted content.zipe file\) can modify the Ore UI files and execute hidden scripts; the issue is said to affect Bedrock versions 26.52 through 26.63 and — according to the report — was fixed in 26.65. Add-on developer 8Crafter disclosed the problem on Reddit on November 15 and the article says the flaw covers PC, mobile, and console; Java Edition is not affected. The disclosure lists exploits such as deleting all save data, obtaining a player’s IP, and on Windows under certain conditions opening arbitrary URIs or launching batch files to download malware. A Windows read-only detection tool published by AxmBro can locate content.zipe files but cannot determine whether a resource pack is malicious.

telegram · zaihuapd · Nov 27, 18:04

**「Background」** Bedrock Edition supports resource packs that can change UI files and these packs can be offered for automatic download when a player joins a server or a Realm, which is the delivery path described in the report. The article reports both the developer disclosure and that Mojang addressed the issue in a 26.65 update, but it does not include independent technical analysis.

**「Impact and recommended action」** Players and server operators should update Bedrock to 26.65 as reported and avoid enabling automatic resource-pack downloads from untrusted servers or Realms; Windows users can scan resource-pack files for content.zipe with the published tool but should not assume a positive find proves malicious intent. Java Edition users are not affected by this report.

**Tags**: `#security`, `#vulnerability`, `#minecraft`, `#software-update`, `#malware`

---

<a id="item-tech-news-9"></a>
### [Microsoft expands Windows built‑in drivers to replace third‑party drivers](https://www.techspot.com/news/114721-microsoft-wants-replace-most-third-party-device-drivers.html) ⭐️ 8.0/10

At Ignite 2026, Microsoft announced it is expanding Windows built‑in drivers to replace many third‑party device drivers; printing is the first focus with the recently introduced Windows Ready Print mode, and the company says audio \(SoundWire, SDCA\), I3C bus, USB Ethernet, and MIPI camera drivers are being developed as built‑in components. Microsoft also launched a Driver Quality Initiative \(DQI\) intended to raise driver reliability, quality, and security standards and to encourage OEMs and third‑party developers to adopt the built‑in drivers rather than ship additional kernel‑level code. These are vendor announcements of planned and recently introduced capabilities rather than an industry‑wide deployment; Mehmet Kucukgoz, a Windows product manager, framed this as a way to reduce third‑party code in the Windows kernel while allowing OEM customization to follow the same approach.

telegram · zaihuapd · Nov 28, 02:09

**「What built‑in \(inbox\) or class drivers are」** Windows &\#x27;inbox&\#x27; or class drivers are OS‑maintained drivers that implement standard device class protocols so multiple vendors&\#x27; hardware can use shared, Microsoft‑supplied kernel components instead of unique third‑party kernel drivers. Replacing vendor kernel drivers with inbox/class drivers reduces the amount of third‑party code running in the Windows kernel—lowering crash risk and attack surface—which is why Microsoft is expanding class drivers for printers, audio \(SoundWire/SDCA\), I3C, USB Ethernet and cameras and has introduced a Driver Quality Initiative to raise reliability and security standards.

**「Impact」** OEMs, independent driver vendors, and integrators should inventory and begin testing their printing, audio, bus, USB Ethernet, and camera drivers against Windows Ready Print and the announced built‑in drivers now, because Microsoft is encouraging migration away from bespoke kernel drivers and toward built‑in components and DQI compliance; vendors may need to move functionality into supported extension points or user‑mode components to maintain compatibility and meet the new quality expectations.

<details><summary>References</summary>
<ul>
<li><a href="https://www.techspot.com/news/114721-microsoft-wants-replace-most-third-party-device-drivers.html">Microsoft wants to replace most third-party device drivers ...</a></li>
<li><a href="https://windowsforum.com/news/microsoft-expands-windows-11-class-drivers-to-reduce-crashes-and-kernel-risks.453854/">Microsoft Expands Windows 11 Class Drivers to Reduce Crashes ...</a></li>

</ul>
</details>

**Tags**: `#windows`, `#device-drivers`, `#hardware`, `#microsoft`, `#security`

---

<a id="item-tech-news-10"></a>
### [False computer-checked proofs](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

A write-up argued that computer-checked proof systems \(proof assistants and verifiers\) can contain soundness bugs that would allow incorrect proofs to be accepted; the piece aims to show real risks to formal verification rather than report a single independently measured exploit. The claim has provoked debate: some commenters emphasized concrete examples and bug classes, while others stressed that the write-up is an argument/case study rather than evidence of widespread failures. Commenters also pointed to existing mitigations such as independent verifiers and small trusted kernels, and noted that historically reported soundness bugs have been rare and often small.

hackernews · \_tk\_ · Nov 27, 15:26 · [Discussion](https://news.ycombinator.com/item?id=50667989)

**「What computer-checked proofs are」** Computer-checked proof systems are programs that inspect and verify each step of a formal proof so the system can assert the proof&\#x27;s correctness.  Work in the area includes not only machine-checked mathematical theorems but also meta-verification efforts: for example, there was a 2022 computer-checked proof of the correctness of a standalone proof checker for HOL proofs in the OpenTheory format.

**「Practical consequence」** Teams that rely on machine-checked proofs should treat a single proof-checker result as insufficient assurance: the community discussion supports cross-checking proofs with independent verifiers, pinning verifier versions, and auditing or preferring systems with smaller trusted kernels or multiple independent implementations. For high-assurance projects, this means adding verifier diversity, reproducible builds, and periodic review of the proof-checker code to reduce the risk that a soundness bug undermines verified artifacts.

**「Community responses」** Commenters disagreed on practical risk: &\#x27;twotwotwo&\#x27; and &\#x27;dwheeler&\#x27; emphasized that multiple independent checkers reduce the chance of a successful undetected exploit \(one comment claimed Metamath requires proofs to pass several independent verifiers\), while &\#x27;gr\_norm&\#x27; argued historical soundness bugs have been few and small. Another commenter, &\#x27;andai&\#x27;, warned about a different failure mode where a verifier proves the wrong specification because the intended requirement was mis-specified.

<details><summary>References</summary>
<ul>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer - checked proofs (djb)</a></li>

</ul>
</details>

**Tags**: `#formal-verification`, `#proof-assistants`, `#software-reliability`, `#security`

---

<a id="item-tech-news-11"></a>
### [Nielsen takes down online neural nets book](https://neuralnetworksanddeeplearning.com/) ⭐️ 7.0/10

Michael Nielsen reportedly removed the free online book &quot;Neural Networks and Deep Learning&quot; from its public URL \(https://neuralnetworksanddeeplearning.com/\), making the text unavailable at that address. The removal was reported and debated on Hacker News, where readers discussed the move as a protest and raised questions about access to educational materials and norms for sharing AI knowledge. Commenters also noted that archived or mirror copies are being referenced and circulated in response to the takedown.

hackernews · brandonb · Nov 27, 19:31 · [Discussion](https://news.ycombinator.com/item?id=50670757)

**「Background」** Michael Nielsen wrote the free online textbook &quot;Neural Networks and Deep Learning&quot; between 2011 and 2015 as an introductory resource on neural networks, and it was hosted at neuralnetworksanddeeplearning.com.  According to recent posts, Nielsen announced on X that he has taken the book down and the site now shows a statement dated November 2026, while independent preservation archives continue to host copies of the original text.

**「Immediate consequence」** Students, educators, and newcomers who relied on the hosted version now must locate archived mirrors or alternative textbooks; people running courses or links should check archive.org or other mirrors and update references to avoid broken links. The incident also prompted community attention to policies for archiving and redistributing educational materials when authors remove online resources.

**「Representative viewpoints」** Some commenters \(for example, whatshisface\) called the removal a misstep that reduces useful public knowledge and harms education, while others \(for example, WheelsAtLarge\) described it chiefly as a protest likely to increase interest in the book and to provoke reflection on the motives. Additional comments linked the move to broader arguments about capital, research incentives, and AI-safety norms rather than purely technical or copyright issues.

<details><summary>References</summary>
<ul>
<li><a href="https://dev.to/frankchu/1000x-off-the-book-that-taught-ai-just-quit-137b">1,000x off: the book that taught AI just quit - DEV Community</a></li>
<li><a href="https://nielsensdeeplearningbook.org/">Neural Networks and Deep Learning — Book Archive</a></li>
<li><a href="https://neuralnetworksanddeeplearning.com/">Neural Networks and Deep Learning</a></li>

</ul>
</details>

**Tags**: `#neural-networks`, `#education`, `#AI-safety`, `#open-access`, `#community-debate`

---

<a id="item-tech-news-12"></a>
### [市场监管总局集中约谈雅迪、台铃、爱玛等 15 家电动自行车企业](https://www.news.cn/20261127/0c8c665ce70c417b9263b39fa8a519f0/c.html?hl=zh-CN) ⭐️ 7.0/10

China&\#x27;s market regulator summoned 15 e‑bike firms after CCC certification spot‑checks found quality and standards violations, ordering remediation, strict adherence to the “one vehicle–one battery–one charger–one code” rule, and immediate recalls for defective products.

telegram · zaihuapd · Nov 27, 12:06

**Tags**: `#regulation`, `#hardware`, `#safety`, `#manufacturing`, `#e-mobility`

---

<a id="item-tech-news-13"></a>
### [Octopus cyberattack affects ~7,500 customers and ~22,000 merchants](https://www.hk01.com/article/60415794) ⭐️ 7.0/10

Octopus announced it detected a cyberattack on the morning of November 27 and said about 7,500 customers&\#x27; personal data and about 22,000 merchants&\#x27; contact records were affected. Customer fields affected include names and photos, and Octopus said some records related to auto‑top‑up services may include bank card numbers and top‑up amounts; the company said the incident does not include credit‑card or bank account details. Merchant data exposed were listed as company contact person name, job title, email address and telephone number. Octopus said core services remain largely operational, no customer financial loss has been found, card and wallet balances remain protected, some functions were temporarily limited as a precaution, and the company has reported the incident to police, the Privacy Commissioner and the Transport and Logistics Bureau and will notify affected customers directly.

telegram · zaihuapd · Nov 27, 13:11

**「Background」** Octopus is Hong Kong&\#x27;s widely used contactless payment and e‑wallet operator that stores card and wallet balances and supports an auto‑top‑up service tied to users&\#x27; bank identifiers. Because auto‑top‑up records can include bank identifiers and top‑up amounts, unauthorized access to those records can enable targeted phishing or social‑engineering attacks even when card balances and full bank‑account or credit‑card details are not reported stolen.

**「Immediate consequence and recommended actions」** Because names, photos and contact details were exposed and some auto‑top‑up records may include bank card numbers and amounts, affected customers should expect direct notification from Octopus, monitor bank and transaction statements for unexpected charges, and be alert for phishing or suspicious communications impersonating Octopus. Merchants whose contact details were exposed should verify any Octopus communications through known channels, and both customers and merchants should follow Octopus&\#x27;s official guidance and contact their bank or Octopus support if they observe suspicious activity.

**Tags**: `#cybersecurity`, `#data-breach`, `#payments`, `#incident-response`, `#privacy`

---

<a id="item-tech-news-14"></a>
### [Claude/Fable 5 silently limited model‑research queries](https://news.ycombinator.com/item?id=50664325) ⭐️ 7.0/10

Anthropic&\#x27;s Claude system cards for Claude Mythos 5 and Fable 5 disclose that the service applied invisible weakening to queries identified as attempting to develop frontier models, using measures described as prompt rewriting, steering vectors, and parameter‑efficient fine‑tuning. The disclosure says the intervention covered tasks such as pretraining pipelines, distributed training, and accelerator design, and affected only a very small share of traffic \(≈0.03%\) and fewer than 0.1% of organizations. Anthropic responded that an invisible restriction on Fable 5 was a mistake removed on June 10, that similar requests are now explicitly rejected or routed to another model with a visible notice, and that Fable 5.2’s capabilities were set near Opus 5.5—while denying any deliberate effort to sabotage user work.

telegram · zaihuapd · Nov 27, 13:42

**「Why this matters」** System cards are model documentation that describe a model’s intended behavior and safety controls; they can include operational limits that affect outputs. For researchers and engineers using Claude to prototype or reproduce model‑development workflows, an undocumented weakening of certain classes of queries changes the reliability and observability of results.

**「Practical consequence and recommended action」** If you were using Claude to prototype or reproduce model‑building work, outputs for a tiny fraction of queries may have been silently degraded, creating reproducibility and trust problems; developers should verify critical experiments against multiple models, keep input/output logs, and check whether the service returns explicit rejections or fallbacks. Note that the system card also reiterates that using Claude to build competing models violates the service terms, so users should confirm permitted use cases with Anthropic’s policy and any visible runtime messages.

**Tags**: `#Anthropic`, `#model restrictions`, `#AI safety`, `#developer access`

---

<a id="item-tech-news-15"></a>
### [Durov warns iPhone users to update iOS](https://telegram.me/zaihuapd/45414) ⭐️ 7.0/10

Pavel Durov posted on his Telegram channel warning that iPhone users running older versions of iOS are being targeted by large-scale attacks and that merely opening a website could be enough to compromise data; he urged affected users to update to the latest iOS and said he will send this reminder to Telegram users on older systems. The message does not identify which iOS versions are affected, the vulnerability or attack vector involved, or any technical indicators, and there is no independent verification included in the post. Treat this as an unverified vendor alert: it signals potential risk and a simple actionable step \(update to the latest iOS\), but it provides no forensic details for defenders or developers to assess exposure or implement mitigations beyond updating.

telegram · zaihuapd · Nov 28, 01:08

**「Why updating iOS matters」** Apple&\#x27;s iOS updates routinely include security patches that close vulnerabilities attackers can exploit through web content or other vectors; devices that skip updates therefore remain at higher risk. Pavel Durov&\#x27;s Telegram post linked below frames the alert as a warning about unpatched iOS devices being targeted via websites, which is why installing the latest system updates is the recommended mitigation.

**「Immediate user action and verification」** If Pavel Durov&\#x27;s Telegram warning is correct, iPhone users on older iOS releases could be vulnerable to remote compromise merely by opening a malicious website; because the post did not name affected iOS versions or provide technical indicators, users cannot tell which devices are at risk. Actionable steps are to install the latest iOS/security updates available for your device, avoid opening untrusted links or websites on phones running older system versions until you have updated, and check Apple&\#x27;s official security updates page for any published advisories or patches.

<details><summary>References</summary>
<ul>
<li><a href="https://t.me/durov/575">Pavel Durov – Telegram</a></li>
<li><a href="https://support.apple.com/en-us/100100">This document lists security updates for Apple software.</a></li>

</ul>
</details>

**Tags**: `#security`, `#iOS`, `#Telegram`, `#vulnerability`, `#mobile`

---

## Financial News

<a id="item-finance-news-1"></a>
### [State Council orders stronger state-backed support to stabilise markets](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 8.0/10

A State Council executive meeting chaired by Premier Li Qiang on 27 Nov ordered stronger market-stabilisation measures, including pushing listed companies to increase dividends and buybacks and further optimising Central Huijin‑style &\#x27;stabilisation fund&\#x27; liquidity support.

telegram · zaihuapd · Nov 27, 05:35

**「background」** The State Council is China’s top executive forum and the meeting directed mobilisation of state-linked &\#x27;national team&\#x27; investors \(central government‑backed vehicles\) and Central Huijin–style stabilisation funds to provide liquidity and to guide long-term institutional funds such as insurance, corporate pensions and social security into equity markets.

**「impact」** The measures will directly affect Chinese equity markets and investors by increasing state-backed liquidity and support for listed companies through buybacks/dividends and by encouraging long-term institutional capital to buy stocks.

**Tags**: `#China`, `#capital markets`, `#state intervention`, `#policy`, `#Central Huijin`

---

<a id="item-finance-news-2"></a>
### [PBOC lowers minimum for large-denomination CDs to RMB 100,000](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 8.0/10

The People’s Bank of China announced new rules cutting the minimum purchase for large-denomination certificates of deposit to RMB 100,000 for individual investors \(from RMB 200,000\) and to RMB 5,000,000 for institutional investors \(from RMB 10,000,000\), effective March 21, 2027; the central bank also issued new RMB deposit/loan rate management rules requiring banks to set rates independently and banning unfair high-rate deposit-seeking, also effective March 21, 2027.

telegram · zaihuapd · Nov 27, 11:36

**「background」** A June 2026 draft of revised rules proposed lowering the personal minimum for large‑denomination certificates of deposit to 200,000 yuan and said CD pricing must follow People’s Bank of China interest‑calculation rules.

**「Impact」** The changes widen retail access to bank large-denomination CDs and directly affect household savers and banks’ deposit-funding competition by lowering the individual entry threshold.

<details><summary>References</summary>
<ul>
<li><a href="https://www.workercn.cn/papers/grrb/2026/06/15/4/grrb202606154.pdf">grrb0420260615C</a></li>

</ul>
</details>

**Tags**: `#central bank`, `#bank regulation`, `#deposits`, `#interest rates`, `#retail investors`

---