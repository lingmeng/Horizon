---
layout: default
title: "Horizon Summary: 2026-11-22 (EN)"
date: 2026-11-22
lang: en
---

> From 23 items, 13 important content pieces were selected

---

**Technology News**
1. [Lean formalization of the Riemann Hypothesis verified](#item-tech-news-1) ⭐️ 9.0/10
2. [GPGME memory bug, potential RCE](#item-tech-news-2) ⭐️ 8.0/10
3. [Muru: AI-assisted Rust server for ASGI/WSGI](#item-tech-news-3) ⭐️ 8.0/10
4. [OpenRouter: MiniMax prompts may have been exposed](#item-tech-news-4) ⭐️ 8.0/10
5. [Zhejiang University demos QRAM on superconducting chip](#item-tech-news-5) ⭐️ 8.0/10
6. [Tesla starts FSD v15 rollout](#item-tech-news-6) ⭐️ 8.0/10
7. [特朗普：美企在别国建 AI 数据中心将面临巨额税款](#item-tech-news-7) ⭐️ 7.0/10
8. [Windows adds RDMA over USB4 for multi‑PC local AI](#item-tech-news-8) ⭐️ 7.0/10
9. [Debian Game Hardware Team formed to explore gaming edition](#item-tech-news-9) ⭐️ 7.0/10
10. [China&\#x27;s National Data Administration to standardize token metering and quality](#item-tech-news-10) ⭐️ 7.0/10
11. [Google Gemini: separate controls for history and training data](#item-tech-news-11) ⭐️ 7.0/10

**Technology Blog**
1. [To code well, avoid blunders](#item-tech-blog-1) ⭐️ 4.0/10

**Financial News**
1. [China leverages APEC summit to convene major leaders and pledge $20 million](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Lean formalization of the Riemann Hypothesis verified](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/) ⭐️ 9.0/10

Levent Alpöge posted a Lean formalization he presents as a proof of the Riemann Hypothesis on 2026-11-20; the release is reported to be about 17 million lines of code. On 2026-11-21 the Lean FRO and the Mathlib Initiative jointly stated that the formal statement matches Mathlib&\#x27;s RiemannHypothesis entry, the repository compiles without errors, and multiple independent proof checkers validated the proof. These claims come from the Lean community report and related community channels and should be treated as provisional pending conventional mathematical scrutiny and archival of the verification artifacts.

telegram · zaihuapd · Nov 21, 16:48

**「Background on Lean and formal verification」** Lean is an interactive theorem prover whose community-maintained library, Mathlib, encodes definitions and proofs as machine-checkable code; formal verification in Lean means the system mechanically checks every inference in a development. The Lean community blog post and joint statement from the Lean FRO and the Mathlib Initiative describe the recent release and the communities&\#x27; independent checks of the repository and its compatibility with Mathlib \(see source\).

**「Impact」** If the joint verification claim holds, the Riemann Hypothesis would be established inside the checked Lean ecosystems cited, allowing other Mathlib developments to import and build on a machine-checked RH assumption; maintainers and downstream users should plan to update imports and continuous-integration configurations once the repository and its verification logs are archived. Because the verification depends on multiple checkers rather than a single implementation, the formal-verification community will need to perform independent audits of the codebase and checker outputs to reduce the remaining risk of correlated or systemic implementation errors.

**「Community discussion」** Commenters note two central points: that multiple independent implementations and consistency proofs make a common-kernel bug less likely, but that prior incidents where incorrect proofs passed checkers mean human expert review and archival evidence remain essential. Several contributors credited Levent for orchestrating the work and observed that a very large body of modern mathematics appears to have been formalized to support the claim.

<details><summary>References</summary>
<ul>
<li>Lean verification of the Riemann Hypothesis | Lean community blog</li>

</ul>
</details>

**Tags**: `#formal-verification`, `#theorem-proving`, `#Lean`, `#Riemann-hypothesis`, `#mathlib`

---

<a id="item-tech-news-2"></a>
### [GPGME memory bug, potential RCE](https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html) ⭐️ 8.0/10

A memory-corruption bug in libgpgme affecting versions prior to 2.3.0 was disclosed under coordinated disclosure, and downstream vendors \(including a GitLab Omnibus patch\) have issued fixes. The bug was reported to GitLab by the researcher named Johan Carlsson and disclosure was moved earlier than planned, with public disclosure occurring on 2026-11-20. Public discussion describes the issue as a potential remote-code-execution \(RCE\) vector, but some security researchers characterize it as a double-free that may not by itself produce a working RCE chain, leaving exploitability uncertain.

hackernews · gdgghhhhh · Nov 21, 08:32 · [Discussion](https://news.ycombinator.com/item?id=50587208)

**「Why GPGME matters」** GPGME \(GnuPG Made Easy\) is the C library many applications use to perform OpenPGP operations—signing, verification, encryption, and key management—and is commonly linked into mail clients, desktop GUIs, and server software. GnuPG&\#x27;s advisory for CVE-2026-129975 states the bug was discovered by Johan Carlsson and was managed as a coordinated disclosure that was moved earlier than planned, with the project publishing the advisory on 2026-11-20.

**「Impact」** Any software that links or bundles GPGME versions older than 2.3.0—whether as a shared library, DLL, or statically linked—should be treated as potentially vulnerable; example consumers named in discussion include Gpg4win, GnuPG Desktop, many mail and XMPP clients, Samba, and Flatpak-packaged software. Operators should apply vendor patches or upgrade to GPGME 2.3.0 or later where available, and specifically check packaged distributions and statically linked binaries \(for example GitLab Omnibus\) for provided fixes.

**「Community discussion」** Comments show a clear disagreement about exploitability: some participants \(for example, &\#x27;mik1998&\#x27;\) say the flaw is a double-free rather than a direct RCE, while others emphasize the seriousness because of GPGME&\#x27;s role in signing and infrastructure. Discussion also summarized the disclosure timeline \(discovered by Johan Carlsson, reported to GitLab on 2026-11-12, and disclosed on 2026-11-20\) and included a user report that Red Hat had an earlier fix in their packaging that upstream missed.

<details><summary>References</summary>
<ul>
<li><a href="https://lists.gnu.org/archive/html/info-gnu/2026-11/msg00006.html">GnuPG Security Advisory for GPGME (T8557,CVE-2026-129975)</a></li>

</ul>
</details>

**Tags**: `#gpgme`, `#vulnerability`, `#security`, `#gitlab`, `#code-signing`

---

<a id="item-tech-news-3"></a>
### [Muru: AI-assisted Rust server for ASGI/WSGI](https://simonwillison.net/2026/Nov/21/muru/) ⭐️ 8.0/10

Graham Dumpleton \(author of mod\_wsgi\) is developing Muru, an AI-assisted server written in Rust that aims to run both ASGI and WSGI Python applications; the project is public on GitHub and Dumpleton has published a rapid, detailed series of development posts between Nov 4 and Nov 21, 2026. The posts cover design and operational topics — worker internals, import-once/fork-many, HTTPS in development, Kubernetes integration, canaries, scaling to zero, tracing, and a developer toolbar — but Muru is early-stage and not yet presented as proven production software.

rss · Simon Willison · Nov 21, 23:56

**「Background」** Dumpleton is best known for creating mod\_wsgi, a long-standing WSGI deployment option for Python web apps, and Muru is his attempt to apply modern tooling \(Rust\) and AI-assisted development to the problem of reliably serving both synchronous WSGI and asynchronous ASGI workloads. The project&\#x27;s public documentation and blog posts show it is being designed with contemporary deployment concerns \(containers, Kubernetes, canaries, scaling\) in mind.

**「Impact」** For Python deployers and platform engineers, Muru is a candidate to watch as a single-server option for mixed WSGI/ASGI fleets; you can start following the GitHub repo and evaluating it in staging to test compatibility and operational behavior, but you should avoid assuming production readiness until the project matures and provides stable releases and real-world operational reports.

**Tags**: `#web-servers`, `#Python`, `#Rust`, `#ASGI/WSGI`, `#AI-assisted-development`

---

<a id="item-tech-news-4"></a>
### [OpenRouter: MiniMax prompts may have been exposed](https://news.ycombinator.com/item?id=50585962) ⭐️ 8.0/10

OpenRouter emailed users saying prompts sent to the MiniMax model may have been read by third parties. Security researchers who sent prompts containing test URLs to MiniMax between July and October 2026 observed those URLs being accessed by third parties 40–130 hours after the prompts were sent. OpenRouter identified the issue as affecting MiniMax and its forwarding/hosting partners AtlasCloud, Novita, and StreamLake, removed the &quot;zero data retention&quot; label from the affected endpoints, and advised users with sensitive credentials to rotate API keys and passwords; OpenRouter&\#x27;s public website had not published details at the time of the report. The account of the incident comes from community-sourced reports \(Telegram / Hacker News\) and has not been independently confirmed by an official public post from OpenRouter in the supplied material.

telegram · zaihuapd · Nov 21, 06:53

**「Background」** OpenRouter is an API routing service that forwards developers&\#x27; requests to models hosted by multiple providers, and some endpoints carry a &quot;zero data retention&quot; label to indicate the vendor&\#x27;s claim not to retain prompt content. Security researchers commonly embed unique canary or test URLs in prompts to detect exfiltration; in this case a researcher sent such URLs to MiniMax between July and October 2026 and later observed third parties fetching those links, which is how the possible exposure was discovered.

**「Immediate consequence」** Users and developers who sent secrets, credentials, or other sensitive data to MiniMax or integrations that route through AtlasCloud, Novita, or StreamLake should rotate affected API keys and passwords and treat those prompts as potentially exposed; teams should also stop relying on the removed &quot;zero data retention&quot; claim for those endpoints and audit any production use of MiniMax until OpenRouter publishes a full investigation.

<details><summary>References</summary>
<ul>
<li><a href="https://www.hallattorneys.com/investigations/openrouter-minimax">OpenRouter MiniMax Prompt Exposure Investigation - Hall Attorneys</a></li>
<li><a href="https://www.privacyaffairs.com/openrouter-minimax-prompts/">OpenRouter: MiniMax Prompts May Have Been Read by Others</a></li>

</ul>
</details>

**Tags**: `#security`, `#data-leak`, `#LLM-privacy`, `#AI-infrastructure`

---

<a id="item-tech-news-5"></a>
### [Zhejiang University demos QRAM on superconducting chip](https://finance.sina.com.cn/stock/2026-11-21/doc-iniznhsk3530826.shtml) ⭐️ 8.0/10

A Zhejiang University team reports the first claimed on-hardware implementation of a quantum random-access memory \(QRAM\) on its in-house superconducting chip “Tianmu‑2,” published in Nature Physics. The group demonstrated prototype retrieval of 4‑bit and 8‑bit data with reported accuracies of 80.9% and 60.4%, respectively, reduced circuit depth by more than 30% compared with an unoptimized design, and presented initial evidence that the architecture has local noise resilience. These results are reported by the research team and describe a small-scale, early-stage hardware milestone rather than a turnkey, large-scale QRAM product.

telegram · zaihuapd · Nov 21, 08:31

**「What QRAM is and why hardware matters」** Quantum random-access memory \(QRAM\) is a proposed hardware layer that lets a quantum processor query memory addresses in superposition and return the corresponding data as quantum states, a capability often cited as an ingredient for quantum machine learning and some quantum algorithms. Building QRAM on real devices is challenging because those queries must be implemented with low circuit depth and high coherence amid device noise, so small-scale, real-hardware demonstrations are used to test feasible architectures and noise-resilience approaches before any large-scale memory can be realized.

**「Immediate consequence」** For quantum-hardware researchers and teams exploring quantum memory, the report supplies an experimental blueprint and empirical numbers \(accuracy and depth reduction\) that can guide follow-on designs and benchmarking; however, because the prototypes are limited to 4‑ and 8‑bit retrieval with modest accuracies, developers should treat this as an early validation and explicitly test scalability, error rates, and whether the reported local noise resilience holds at larger sizes before assuming production viability.

<details><summary>References</summary>
<ul>
<li><a href="https://unsloth.ai/blog/dynamic-4bit">Unsloth - Dynamic 4 - bit Quantization</a></li>

</ul>
</details>

**Tags**: `#quantum-computing`, `#hardware`, `#QRAM`, `#superconducting-qubits`

---

<a id="item-tech-news-6"></a>
### [Tesla starts FSD v15 rollout](https://x.com/Tesla/status/2124222447855743019) ⭐️ 8.0/10

Tesla has begun rolling out FSD v15 overseas to vehicles running its Full Self-Driving software. The update introduces a new &quot;Tesla Reality View&quot; visualization that overlays camera feed and FSD driving plans on the vehicle screen with full-screen, map, split-screen and a &quot;quiet&quot; mode; navigation can now overlay turn information and the turn-signal chime is softened and fades. Tesla also says FSD v15 improves handling of safety-critical scenarios by 25× \(a vendor claim not independently verified\) and makes targeted driving-behavior changes for potholes, debris, school zones and adverse-weather speed control.

telegram · zaihuapd · Nov 22, 00:03

**「Background」** Tesla&\#x27;s FSD \(Full Self-Driving\) is the company&\#x27;s driver-assist/autonomy software bundle that runs on the vehicle&\#x27;s onboard compute and uses camera perception plus planning to steer and control speed. A visualization overlay like the announced “Tesla Reality View” layers camera imagery with the vehicle&\#x27;s planned path and UI elements on the central display to make the system&\#x27;s perception and intended maneuvers visible to the driver.

**「Impact」** Drivers with FSD-equipped cars should expect an over-the-air update that changes the in-car UI, visual overlays, and turn-signal audio, and may want to review the new interface and settings after installation; fleet operators, testers, and regulators should treat the &quot;25×&quot; safety improvement as a vendor assertion and verify real-world behavior in controlled testing before relying on it for operational decisions.

**Tags**: `#ai`, `#autonomous-driving`, `#tesla`, `#software-update`, `#safety`

---

<a id="item-tech-news-7"></a>
### [特朗普：美企在别国建 AI 数据中心将面临巨额税款](https://apnews.com/article/trump-artificial-intelligence-data-centers-f1ac03b73d13445400eeed8631d9d879) ⭐️ 7.0/10

Trump said he plans to impose large taxes on US companies that build AI data centers abroad to keep them in the United States and preserve an AI edge over China, and urged communities to accept data centers despite local concerns.

telegram · zaihuapd · Nov 21, 03:26

**Tags**: `#policy`, `#ai-infrastructure`, `#data-centers`, `#regulation`, `#geopolitics`

---

<a id="item-tech-news-8"></a>
### [Windows adds RDMA over USB4 for multi‑PC local AI](https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model) ⭐️ 7.0/10

Microsoft published a developer preview of RDMA over USB4 for Windows that lets multiple PCs share memory and GPU compute over ordinary USB4 links so they can run a single local AI model without specialized RDMA NICs or switches. Microsoft demonstrated three AMD Ryzen AI Max+ 395 systems running a 4-bit quantized Qwen3-235B-A22B variant at about 18.5 tokens/second, and said the preview will be delivered via Windows Insider. The announcement is a developer preview with limited public performance data and unspecified hardware/driver requirements.

telegram · zaihuapd · Nov 21, 06:13

**「Why this matters」** RDMA \(remote direct memory access\) lets one host access another host&\#x27;s memory with low latency and CPU overhead, which is useful for distributed inference. USB4 supports high-bandwidth tunneling of PCIe and can carry RDMA traffic over a simple cable, so enabling RDMA-over-USB4 in Windows allows commodity PCs to be pooled for model inference without installing specialized network cards or switches.

**「Immediate consequence and recommended action」** For developers and hobbyists wanting to run large local models across several ordinary PCs, this provides a lower-cost path to pooled memory/GPU inference but requires USB4-capable hardware, matching drivers, and Windows Insider access; performance and robustness are currently demonstrated only in a limited lab scenario. If you plan to evaluate it, test on non-critical workloads, verify your systems have USB4 host controllers and appropriate cables, and expect to wait for broader testing and a stable release before deploying it in production.

**Tags**: `#RDMA`, `#USB4`, `#distributed-inference`, `#windows`, `#local-ai`

---

<a id="item-tech-news-9"></a>
### [Debian Game Hardware Team formed to explore gaming edition](https://www.ithome.com/1/030/390.htm) ⭐️ 7.0/10

Debian maintainer Karamtoth has announced the formation of the &quot;Debian Game Hardware Team&quot; to test gaming hardware and emulators and to explore running Debian on game handhelds and consoles. The group also plans to produce a dedicated Debian-based edition aimed at integrators and hardware enthusiasts that would ship preconfigured and boot directly into a game mode. This is an announced plan rather than a released product: the report gives no timelines, release artifacts, or technical specifications. The write-up also notes Debian&\#x27;s roughly two-year major-release cadence and the associated risk of lagging support for the newest hardware.

telegram · zaihuapd · Nov 21, 09:10

**「Why a Debian gaming edition would matter」** Debian&\#x27;s conservative packaging and roughly biennial major-release cadence mean new hardware and drivers often arrive later in Debian than in faster-update distributions. Because gamers and hardware integrators commonly turn to more up-to-date or specialized distributions \(for example, Arch- or Fedora-based gaming spins\) to get newer drivers, a preconfigured Debian gaming edition aimed at consoles, handhelds and integrators would seek to close that compatibility and convenience gap.

**「Immediate consequence for users and integrators」** If the plan is implemented, integrators and hobbyist hardware vendors could gain a ready-made Debian image for gaming devices and preconfigured systems, reducing setup work; however, because Debian&\#x27;s major-release cycle can delay upstream driver and kernel availability, interested parties should expect to track the team&\#x27;s test results and be prepared to use newer kernels or vendor-supplied drivers or backports to ensure support for very recent hardware.

**Tags**: `#debian`, `#linux-gaming`, `#distro`, `#hardware`, `#emulation`

---

<a id="item-tech-news-10"></a>
### [China&\#x27;s National Data Administration to standardize token metering and quality](https://www.cls.cn/detail/2540805) ⭐️ 7.0/10

China&\#x27;s National Data Administration announced at the 2026 World Computing Conference in Changsha that it will expand token \(词元\) service applications and establish standards for token metering, billing, and quality assessment. Director Liu Liehong said &quot;token factories&quot; are rapidly emerging to turn compute rental, model supply, and data capabilities into token production services. The agency stated these standards aim to avoid low-quality repeated construction; this is a stated regulatory plan rather than published or enacted technical standards.

telegram · zaihuapd · Nov 21, 10:19

**「What &\#x27;tokens&\#x27; and &\#x27;token factories&\#x27; mean here」** The announcement describes 词元 \(tokens\) as the value‑transmission link between compute, models, and data, and says “token factories” are rapidly emerging services that turn compute rental, model supply, and data capabilities into token production services. Metering, billing and quality‑assessment standards would establish how those token services are measured and paid for and are intended to prevent low‑quality, duplicative construction of such services.

**「Impact」** Organizations that provide or consume tokenized compute, model, or data services should expect forthcoming requirements for per-token metering, billing transparency, and measurable quality metrics, and should prepare to add or expose token-level metering and quality reporting. Infrastructure, billing, and procurement teams should track the National Data Administration&\#x27;s follow-up documents and plan to update billing, logging, SLAs, and dataset quality-assessment processes once the standards are released.

**Tags**: `#China`, `#AI policy`, `#tokens`, `#standards`, `#infrastructure`

---

<a id="item-tech-news-11"></a>
### [Google Gemini: separate controls for history and training data](https://blog.google/innovation-and-ai/products/gemini-app/updated-controls/) ⭐️ 7.0/10

Google says Gemini will replace its single “keep activity” control with two separate settings within weeks: one that sets how long chat history is retained, and another that independently opts conversation content \(text and attachments\) out of use for training generative AI models. Users will be able to keep their chat history while disabling model‑training use of that content; audio and Gemini Live recordings remain excluded from model improvement by default. When the change goes live, the two new settings will be initialized to the current state of the original switch, and Gemini notes that when history is turned off new conversations are stored for about two months and may be accessed with human reviewers to reply, process feedback, and protect Google, its users, and the public.

telegram · zaihuapd · Nov 22, 01:24

**「Why this matters」** Previously a single “keep activity” option governed both whether conversations were kept and whether their content could be used to improve models; separating the controls lets users choose retention length and a distinct training opt‑out independently.

**「Practical effect for users」** The concrete consequence is that users who want Gemini to retain searchable chat history can now also prevent their conversation text and attachments from being used to train models; because the new controls inherit the old switch state at rollout, users who want to change that behavior should review the settings after the update. If a user’s goal is to avoid any retention, they still need to disable the history retention setting entirely — turning off the training opt‑out alone does not delete or shorten stored history.

**Tags**: `#privacy`, `#model-training`, `#product-update`, `#Google Gemini`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [To code well, avoid blunders](https://seangoedecke.com/to-code-well-avoid-blunders/) ⭐️ 4.0/10

rss · Sean Goedecke · Nov 22, 00:00

**「Background」** Sean Goedecke argues that in large, team-owned codebases — what he calls “impure engineering” — the biggest win comes from avoiding catastrophic mistakes rather than inventing clever abstractions. He frames the problem as one of fragility: a single blunder can turn an otherwise elegant codebase into a janky, hard-to-maintain system.

**「Solution」** The author identifies two cardinal sins to avoid: inconsistency \(introducing parallel systems, a second source of truth, new failure modes, or complicated interfaces\) and unnecessary requirements. Goedecke explains why unnecessary requirements are especially dangerous: they tend to stick because future engineers will assume they’re needed, and they multiply complexity by forcing every new feature to consider interactions with the extra requirement. His practical prescription is minimalist and conservative: when changing code, find the place that fits most naturally into the existing design and reduce your task to the smallest set of real requirements; resist “clever” patterns or extra-credit features that increase surprise. He also notes this mindset applies whether you’re writing code yourself or orchestrating AI agents.

**「Takeaway」** Goedecke’s core claim is simple: in large team codebases, attention to detail and an obsessive focus on avoiding inconsistency and needless requirements matter far more than cleverness.

**Tags**: `#software engineering`, `#code quality`, `#consistency`, `#practical advice`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China leverages APEC summit to convene major leaders and pledge $20 million](https://www.cnbc.com/2026/11/21/china-xi-trump-putin-global-diplomacy-shenzhen.html) ⭐️ 7.0/10

China convened a trilateral meeting in Shenzhen that brought President Xi Jinping together in person with Vladimir Putin and U.S. President Donald Trump, and at the APEC Economic Leaders&\#x27; Meeting announced a pledge of $20 million in support for the Asia‑Pacific region.

rss · CNBC Finance · Nov 21, 06:00

**「background」** Beijing has increasingly used summit diplomacy—hosting more than 40 foreign leaders this year and previously brokering talks such as the 2023 Saudi‑Iran diplomatic restoration—to expand its global influence through multilateral forums.

**「impact」** The summit strategy strengthens China’s diplomatic leverage with Asia‑Pacific governments by pairing high‑profile in‑person leader meetings with targeted economic support, exemplified by the $20 million pledge.

**Tags**: `#China`, `#summit diplomacy`, `#APEC`, `#geopolitics`, `#foreign policy`

---