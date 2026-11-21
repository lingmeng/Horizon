---
layout: default
title: "Horizon Summary: 2026-11-21 (EN)"
date: 2026-11-21
lang: en
---

> From 39 items, 24 important content pieces were selected

---

**Technology News**
1. [KVM CVE-2026-99312: AMD nested-VM can read host memory](#item-tech-news-1) ⭐️ 9.0/10
2. [Inkling 2 Mini](#item-tech-news-2) ⭐️ 8.0/10
3. [Tao: Navier–Stokes Singularity Linked to GRH](#item-tech-news-3) ⭐️ 8.0/10
4. [Claimed proof of Generalized Riemann Hypothesis by Alpöge](#item-tech-news-4) ⭐️ 8.0/10
5. [Claimed finite-time blow-up for Navier–Stokes](#item-tech-news-5) ⭐️ 8.0/10
6. [Yotta Plans 100k GPUs as US Curbs Shift Demand to India](#item-tech-news-6) ⭐️ 8.0/10
7. [Apple developing proactive AI agent, targeting late 2027](#item-tech-news-7) ⭐️ 8.0/10
8. [OpenAI background mode: async 2h/8h with up to 40% token discount](#item-tech-news-8) ⭐️ 8.0/10
9. [Anthropic claim: Claude produced Lean-encoded proof of the Riemann Hypothesis](#item-tech-news-9) ⭐️ 8.0/10
10. [Cursor weighs phasing out China‑developed model weights](#item-tech-news-10) ⭐️ 8.0/10
11. [TSMC pauses 16nm-and-below orders for Chinese firms](#item-tech-news-11) ⭐️ 8.0/10
12. [Masullo claims GRH proof \(hurried announcement\)](#item-tech-news-12) ⭐️ 7.0/10
13. [LLMs Rewriting Their Own Weights](#item-tech-news-13) ⭐️ 7.0/10
14. [Restricting AI agents from capturing Signal chats](#item-tech-news-14) ⭐️ 7.0/10
15. [SEC probe of NVIDIA&\#x27;s accounting reported — unconfirmed](#item-tech-news-15) ⭐️ 7.0/10
16. [TikTok launches global deepfake-detection and transparency tools](#item-tech-news-16) ⭐️ 7.0/10
17. [Tesla assisted driving approved in Italy](#item-tech-news-17) ⭐️ 7.0/10
18. [OpenAI: GPT‑6.2 Astra/Sol anti‑distillation cuts extraction to 0.2%](#item-tech-news-18) ⭐️ 7.0/10
19. [Trump proposes heavy tax on U.S. firms&\#x27; overseas AI data centers](#item-tech-news-19) ⭐️ 7.0/10

**Technology Blog**
1. [Why output caching doesn&\#x27;t work](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [Warsh avoids forward guidance as Fed officials speak up](#item-finance-news-1) ⭐️ 8.0/10
2. [Corporate shift from buybacks to net equity issuance](#item-finance-news-2) ⭐️ 8.0/10
3. [Alibaba sued over alleged concealment of business link to &\#x27;Alice Huang&\#x27;](#item-finance-news-3) ⭐️ 7.0/10
4. [Beijing draft bars deposit deductions for normal rental wear](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [KVM CVE-2026-99312: AMD nested-VM can read host memory](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 9.0/10

A Linux KVM vulnerability, tracked as CVE-2026-99312, lets a nested-virtualized guest on AMD hosts read host memory; researchers reportedly recovered about 127 GB of host RAM from a VM \(tested on DigitalOcean\). An upstream fix was released in the stable kernel series \(including 7.3.5\) on November 18, 2026, but many distribution kernels \(for example Debian and Ubuntu builds\) have not yet incorporated the patch. Until vendor kernels are updated, operators should disable nested virtualization on AMD hosts to mitigate risk.

telegram · zaihuapd · Nov 20, 14:23

**「Technical background」** Nested virtualization lets a guest run its own hypervisor, which requires special KVM handling of CPU/VM state; this bug arises only when nested virtualization is enabled on AMD-based hosts. The issue is specific to KVM on affected AMD platforms and does not apply to hosts where nested virtualization is disabled.

**「Immediate impact and recommended action」** System administrators and cloud operators running AMD hosts with nested virtualization enabled face concrete data-exposure risk: a guest could read substantial host memory \(the public test recovered ~127 GB\). Operators should either upgrade to a kernel that includes the upstream fix \(stable 7.3.5 or later\) once their distribution supplies it, or disable nested virtualization on vulnerable hosts right away; note that disabling nested virtualization will break workloads that depend on running hypervisors inside guests.

**Tags**: `#security`, `#virtualization`, `#linux-kernel`, `#KVM`, `#AMD`

---

<a id="item-tech-news-2"></a>
### [Inkling 2 Mini](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 8.0/10

Inkling 2 Mini is an open-weights, small looped-transformer model that community posts report can match much larger models on some benchmarks while running efficiently for local inference. Commenters say the project provides GGUF-compatible builds that run on Ollama/llama.cpp and that the authors trained end-to-end in nvfp4; community-measured decode rates include about 27 tokens/second on a Ryzen 395 \(Vulkan\) and about 10 tokens/second on an M1 Pro using q4\_xl. These performance and benchmark claims come from early community tests and project notes and have not been independently verified in published evaluations.

hackernews · jasondavies · Nov 20, 20:12 · [Discussion](https://news.ycombinator.com/item?id=50581260)

**「Looped-transformer and the Inkling 2 family」** Looped transformers reuse \(or &quot;loop&quot;\) internal layers multiple times during generation so a model can do more per-token computation; Thinking Machines says Inkling 2 Mini loops its middle layers to &quot;reason more per token&quot; and reach answers in fewer tokens.  The company frames Inkling 2 Mini as an open-weights, laptop-scale member of the Inkling 2 family, following their earlier Inkling 2 Small release and intended as a smaller, locally runnable complement.

**「Immediate consequence for users」** Developers and researchers wanting stronger local inference can try Inkling 2 Mini on consumer hardware with existing runtimes \(llama.cpp/Ollama\) and quantization \(q4\_xl\), but should run their own task-specific benchmarks and sanity checks because reported strengths vary by task and the community is still validating accuracy, speed, and safety/interpretability implications. If you rely on upstream runtimes, expect to track a few unmerged performance patches and tuning suggestions from the community to get the best speed.

**「Community takeaways」** Commenters are enthusiastic that a small looped-transformer with open weights could approach Qwen3.8-27B-level benchmarks and enable more local use, while others report mixed task results \(stronger on coding tests, weaker on some knowledge tasks\) and share microbenchmarks and small patches to improve llama.cpp performance. Several people urged more extensive, independent testing and raised questions about safety and interpretability as looped architectures become more common in open models.

<details><summary>References</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://thinkingmachines.ai/news/inkling-2-small/">Introducing Inkling 2 Small - Thinking Machines Lab</a></li>

</ul>
</details>

**Tags**: `#open-weights`, `#looped-transformer`, `#inference-performance`, `#benchmarks`, `#local-ml`

---

<a id="item-tech-news-3"></a>
### [Tao: Navier–Stokes Singularity Linked to GRH](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 8.0/10

Terence Tao published a blog post claiming a mathematical connection between an unforced Navier–Stokes singularity and the Generalized Riemann Hypothesis \(GRH\). The post presents a proposed argument tying these two longstanding open problems together; the claim is reported and discussed publicly but has not been independently verified or certified by peer review. The write-up has immediately provoked technical discussion on Hacker News about the role of AI in generating and checking proofs and about formal verification tools such as Lean.

hackernews · archon1410 · Nov 20, 17:21 · [Discussion](https://news.ycombinator.com/item?id=50578358)

**「Navier–Stokes existence and the unforced variant」** The Navier–Stokes existence and smoothness question asks whether the three‑dimensional Navier–Stokes equations always admit globally smooth solutions for given initial data \(with or without an external forcing term\), and it is a longstanding open problem in mathematics. The term “unforced” refers to the same equations with the external force set to zero, a natural variant of the general existence/smoothness question that underlies the blog post&\#x27;s focus.

**「Immediate consequence」** Researchers in analysis, number theory, and formal methods should treat the blog claim as provisional and expect detailed scrutiny, because if the asserted logical link is correct then progress \(or counterexamples\) on GRH would carry direct consequences for Navier–Stokes regularity; as a practical step, interested researchers will likely seek independent checking and mechanized formal verification of the argument before accepting its conclusions.

**「What people are saying」** Commenters on Hacker News raised two recurring points: one practical question about whether modern advances \(including AI assistance\) are producing new mathematical abstractions or mainly brute-force verifications, and a report that two independent proof kernels apparently accepted the result \(a user claim that has not been established here\). Several participants also expressed unease about AI&\#x27;s accelerating role in producing mathematical work and its implications for careers and trust in proofs.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_existence_and_smoothness">Navier – Stokes existence and smoothness - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#mathematics`, `#theorem-proving`, `#formal-verification`, `#AI-generated-proofs`

---

<a id="item-tech-news-4"></a>
### [Claimed proof of Generalized Riemann Hypothesis by Alpöge](https://alpo.ge/remark.pdf) ⭐️ 8.0/10

Levent Alpöge posted a PDF asserting he \(with the AI assistant Claude\) has proved the Generalized Riemann Hypothesis and has formalized the arguments in Lean; the claim is circulating on Hacker News. The paper and accompanying artifact are currently an unverified announcement, not a peer-reviewed or independently confirmed result, and Alpöge’s text credits substantial assistance from Claude. Community reports linked to the post say the provided Lean formalization is extremely large \(comments report roughly 1.3 GB and ~15 million lines\), which makes independent checking nontrivial.

hackernews · iamronaldo · Nov 20, 14:16 · [Discussion](https://news.ycombinator.com/item?id=50574968)

**「Why this matters」** The Generalized Riemann Hypothesis \(GRH\) is a long‑standing conjecture about zeros of L‑functions that underpins many results in analytic number theory and has implications for algorithmic complexity and some cryptographic bounds. A correct, verified proof would be a foundational mathematical result, but the current announcement is a claim that needs independent verification and peer review before it changes any mathematical or practical conclusions.

**「Immediate, practical consequence」** Researchers and formal‑methods engineers will prioritize downloading and checking the large Lean artifact and the PDF; reproducing and validating the claimed formal proof will require substantial storage, time, and the correct Lean/maths‑library environment, so verification will not be instantaneous. Until independent verification and acceptance by experts, practitioners should not alter cryptographic standards, security parameters, or mathematics that depend on GRH based on this claim alone.

**「What people are saying」** HN commenters report the artifact’s very large size and intense discussion about the role of Claude and LLMs in the result; some express excitement about the possibility while others urge caution and rapid independent checks. A few participants pointed to a separate blog post claiming a human proof, and some commenters framed the episode as raising questions about AI governance and coordination, which are opinions rather than established facts.

**Tags**: `#mathematics`, `#formal-verification`, `#proof-assistants`, `#cryptography`

---

<a id="item-tech-news-5"></a>
### [Claimed finite-time blow-up for Navier–Stokes](https://github.com/tristanbuckmaster/navier-stokes/) ⭐️ 8.0/10

A GitHub repository by user tristanbuckmaster posts a claimed proof of finite-time blow-up for the unforced Navier–Stokes equations, and the claim is the subject of active discussion on Hacker News \(item posted Nov 20, 2026\). The repository-hosted argument has not been peer-reviewed or independently verified, so the claim should be treated as provisional rather than established. If the posted proof indeed addresses the standard 3D incompressible unforced formulation, it would directly bear on the longstanding existence/regularity question for Navier–Stokes; however, no independent confirmation is yet available.

hackernews · trotro · Nov 20, 15:34 · [Discussion](https://news.ycombinator.com/item?id=50576232)

**「Prerequisite context」** The Navier–Stokes existence and smoothness question asks whether smooth initial velocity fields on R^3 or T^3 necessarily produce globally smooth solutions, and it is one of the Clay Millennium Prize problems; a claimed finite-time blow-up would settle that problem negatively.  The GitHub repository accompanies a paper by L. Alpöge and T. Buckmaster that claims an unforced finite-time blow-up and provides a Lean 4 formalization plus a computer-verified approximate self-similar profile checked by interval arithmetic; this follows an earlier, separate claim of a forced-counterexample that created a priority controversy. 

**「Impact」** If validated and shown to match the standard Clay Problem formulation for 3D incompressible unforced Navier–Stokes, the result would resolve that Millennium Problem; until independent verification and peer review occur, researchers should scrutinize the repository&\#x27;s arguments, attempt to reproduce any constructive steps, and journals and media should treat the claim as provisional.

**「Community discussion」** Commenters noted the distinction between this unforced claim and a recent forced-counterexample reported earlier \(tancop\), and several participants \(including ninkendo\) asked whether a numerical or physical demonstration of the alleged blow-up is possible; much of the thread mixes skepticism, humor, and calls for rapid expert verification.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_priority_controversy">Navier–Stokes priority controversy - Wikipedia</a></li>
<li><a href="https://hotrepo.ai/tristanbuckmaster/navier-stokes">tristanbuckmaster/navier-stokes: Lean 4 formalization of a ...</a></li>
<li><a href="https://aixiv.online/abs/2611.02204">[2611.02204] Finite-time blow-up for the Navier–Stokes ...</a></li>

</ul>
</details>

**Tags**: `#navier-stokes`, `#pde`, `#mathematics`, `#fluid-dynamics`, `#research-claim`

---

<a id="item-tech-news-6"></a>
### [Yotta Plans 100k GPUs as US Curbs Shift Demand to India](https://www.bloomberg.com/news/articles/2026-11-20/nvidia-scandal-fallout-india-ai-yotta-ambani-adani-am-intelligence-e2e-networks) ⭐️ 8.0/10

Bloomberg reports that new U.S. restrictions on advanced chip exports to Malaysia, Thailand and Singapore are redirecting demand for AI compute to India. Yotta says it plans to add about 100,000 GPUs over the next year, which it estimates would raise India’s existing compute capacity by roughly 10%. The report notes India currently has 153 data centers \(ranked 14th worldwide\) and cites reported investment pledges—up to $110 billion and $100 billion—from companies referred to in the source as 信实 and 阿达尼. The article also cautions that India’s expansion remains constrained by shortages in compute infrastructure and limits on available capital.

telegram · zaihuapd · Nov 20, 07:31

**「Why export curbs matter for AI compute」** High‑end GPUs and related advanced chips are the core hardware for large‑scale AI training, so export restrictions that limit shipments to Malaysia, Thailand and Singapore can redirect procurement and deployment to other countries. Absorbing that redirected demand requires available data‑center space, power and financing—factors tied to India&\#x27;s current footprint of 153 data centers and the large investment pledges and capacity plans reported by companies such as Yotta, Reliance and Adani.

**「Impact」** A concrete near-term consequence is increased demand pressure on Indian data‑center operators and suppliers: cloud customers seeking advanced GPUs should verify delivery timelines and contractual capacity commitments because orders that would have gone to Southeast Asian facilities appear likely to be redirected. Operators and developers should also plan for tighter competition for power, real estate and skilled staff as new GPU deployments scale.

**Tags**: `#export-controls`, `#ai-compute`, `#india`, `#data-centers`, `#cloud-infrastructure`

---

<a id="item-tech-news-7"></a>
### [Apple developing proactive AI agent, targeting late 2027](https://www.bloomberg.com/news/articles/2026-11-19/apple-is-working-on-ai-agent-for-device-control-apps-browsing-and-coding) ⭐️ 8.0/10

Bloomberg reports Apple is hiring engineering leaders to build a proactive, device-level AI agent that can write code, browse the web, and control apps, with an earliest possible release window reported as late 2027 and the project described as early-stage. The account is based on new Apple job listings rather than a shipped product or independent measurement. Separately, macOS 27.3 reportedly adds a warning page and increases the steps required for a third-party agent to obtain Mac control permissions from four steps to fourteen. The report also notes that competitors such as Meta \(Muse\) and OpenAI already offer similar agent products.

telegram · zaihuapd · Nov 20, 08:59

**「What a &\#x27;proactive AI agent&\#x27; means」** Proactive AI agents are systems that can perform multi-step tasks for users—such as browsing the web, editing or writing code, and controlling local apps—by taking actions on the device rather than only returning single-step answers. Bloomberg’s report frames Apple’s work against existing, shipped agent offerings from companies such as OpenAI and Meta and notes macOS 27.3 adds stricter permission and warning steps for third‑party agents, which explains why device-level controls and UI changes matter for any new Apple agent.

**「Immediate consequence」** Because macOS 27.3 raises the number of steps to grant control permissions, developers of third-party agents will need to adapt to a more involved consent flow and may face higher friction getting agents to access Mac app controls; users should expect stricter, more visible permission dialogs for agent features.

**Tags**: `#apple`, `#ai-agents`, `#macos-security`, `#platform`, `#industry`

---

<a id="item-tech-news-8"></a>
### [OpenAI background mode: async 2h/8h with up to 40% token discount](https://developers.openai.com/api/docs/guides/background) ⭐️ 8.0/10

OpenAI introduced a background \(asynchronous\) API mode for long-running requests that developers enable by setting background: true and selecting background\_options.completion\_window of 2h or 8h. The 2-hour and 8-hour windows are reported to offer token-rate discounts of about 30% and 40% versus standard pricing, while omitting the option uses the default soonest behavior with no discount. The capability is in beta on GPT-6.2 Astra, GPT-6.2 Sol, GPT-6.1 Terra, and GPT-6 Luna, and OpenAI notes responses may be temporarily stored even when store=false or zero data retention is enabled.

telegram · zaihuapd · Nov 20, 11:15

**「Why this matters」** Asynchronous/background request modes let clients submit jobs that take much longer than a normal synchronous API call and receive results later within a defined completion window. Before this, developers typically used their own job queues, polling, or kept long-lived connections open to handle multi-minute or multi-hour tasks.

**「Immediate impact and recommended actions」** Developers running long-running generation or analysis tasks can lower token costs and keep jobs open up to eight hours by switching to background:true and choosing an appropriate completion\_window, but they must update client logic to handle asynchronous completion and confirm model availability under the beta. Because OpenAI indicates responses may be temporarily stored even when store=false or zero data retention is enabled, teams with privacy or regulatory constraints should review the feature&\#x27;s data-handling behavior before using it in production.

**Tags**: `#OpenAI`, `#API`, `#asynchronous`, `#cost`, `#data-privacy`

---

<a id="item-tech-news-9"></a>
### [Anthropic claim: Claude produced Lean-encoded proof of the Riemann Hypothesis](https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/) ⭐️ 8.0/10

Levent Alpöge of Anthropic says he used the company’s Claude model to produce a Lean-encoded, machine-checkable proof of the Riemann Hypothesis and the broader Generalized Riemann Hypothesis, and that the formalized material runs to more than 250,000 pages. The claim was reported by Scientific American on November 20; the artifact is described as a Lean proof script rather than a conventional journal publication, and community verification of the correctness and completeness of the formalization has not been presented.

telegram · zaihuapd · Nov 20, 15:29

**「Technical background」** The Riemann hypothesis is a long-standing conjecture about the nontrivial zeros of the Riemann zeta function and their consequences for the distribution of prime numbers; it has been an open problem since the 19th century. Lean is a formal proof assistant that encodes definitions and proofs as machine-checkable code, so a “Lean-encoded” proof yields a large, verifiable artifact that still requires independent scrutiny of both the formalization and the underlying mathematics.

**「Immediate consequence for researchers」** Mathematicians and formal-methods researchers should treat this as an extraordinary but unverified claim and prioritize independent reproducibility: download and load the Lean files into a compatible Lean toolchain, run the proof checker, and audit key lemmas and reductions; acceptance by the broader community will depend on independent verification of the Lean artifact and its dependencies rather than the announcement alone.

<details><summary>References</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove Riemann hypothesis ...</a></li>
<li><a href="https://www.nytimes.com/2026/11/20/science/anthropic-ai-math-riemann-hypothesis.html">Anthropic Mathematician Claims to Solve Riemann Hypothesis ...</a></li>

</ul>
</details>

**Tags**: `#theorem-proving`, `#formal-verification`, `#AI-assisted-math`, `#Riemann-hypothesis`

---

<a id="item-tech-news-10"></a>
### [Cursor weighs phasing out China‑developed model weights](https://www.cnbc.com/2026/11/20/cursor-chinese-ai-models-geopolitical-risk.html) ⭐️ 8.0/10

SpaceX&\#x27;s developer-focused AI coding platform Cursor says it is considering phasing out open‑source model weights developed in China because of &quot;geopolitical risk.&quot; Cursor&\#x27;s Composer 2 programming model currently uses the Kimi K2.5 weights. The statement follows a report from the U.S. House Homeland Security Committee and the Select Committee on the Strategic Competition between the United States and the Chinese Communist Party that recommended creating a U.S. national open‑source weights program and restricting federal use of China‑developed AI models, building on an administrative order that barred DeepSeek from federal systems. Cursor described the plan as under consideration, not as a completed or enforced change.

telegram · zaihuapd · Nov 20, 16:13

**「Policy context」** In mid‑2026 U.S. agencies and congressional panels were reported to be considering restrictions on U.S. companies&\#x27; use of Chinese open‑source AI models, a response driven by concerns about cost, provenance, and national security. That debate—reported as proposals to limit federal use of certain China‑developed models—sets the policy backdrop for companies like Cursor weighing whether to phase out China‑origin model weights.

**「Immediate consequence for developers and procurement」** If Cursor moves ahead, developers and organizations using Composer 2 will need replacement model weights and compatibility testing because Kimi K2.5 is currently the model underpinning Composer 2. Actionable steps are to audit which model weights your projects depend on, track Cursor&\#x27;s policy decisions, and prepare a migration and testing plan for alternative weights to avoid disruption in development or production environments.

<details><summary>References</summary>
<ul>
<li>U.S. weighs curbs on Chinese open-source AI models after debut ...</li>
<li>CNBC: The US wants to restrict corporate use of Chinese AI</li>

</ul>
</details>

**Tags**: `#geopolitics`, `#open-source-models`, `#AI-policy`, `#supply-chain`

---

<a id="item-tech-news-11"></a>
### [TSMC pauses 16nm-and-below orders for Chinese firms](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 8.0/10

TSMC has told customers it will pause taking orders for chips produced at 16nm and smaller process nodes for Chinese companies, citing tightened U.S. semiconductor export controls. Under the revised rules, shipments to Chinese recipients require a prior U.S. export license or waiver, so affected firms are being steered toward older nodes \(for example, 28nm or 40nm\) and will lack access to high-bandwidth memory \(HBM\) used in AI data-center accelerators. TSMC previously evaluated customer designs for exemption eligibility itself but now requires customers to obtain U.S. approvals in advance; the report says Apple, AMD, and NVIDIA appear on U.S. approved lists while no Chinese company does, and TSMC stated it will comply with the new rules.

telegram · zaihuapd · Nov 21, 02:01

**「Background」** The U.S. recently tightened semiconductor export controls so that shipments of certain advanced-process chips and related technologies to Chinese firms now require U.S. government export licenses. Media reports say the new rules cover 16 nm and more advanced nodes, prompting foundries to pause or restrict orders for affected customers until a license is obtained.

**「Immediate consequences」** Chinese fabless firms and cloud/AI hardware buyers that relied on TSMC for 16nm-and-below parts will need to secure U.S. export licenses or redesign for older, less capable process nodes, a change that can degrade performance, increase power consumption, and prevent use of HBM-based accelerators; affected companies should urgently verify whether their products are covered by U.S. approvals and plan alternative sourcing or node migration.

<details><summary>References</summary>
<ul>
<li><a href="https://www.trendforce.com/news/2026/11/20/news-tsmc-samsung-reportedly-pause-china-consumer-chip-shipments-under-new-u-s-rules-16nm-orders-affected/">[News] TSMC , Samsung Reportedly Pause China Consumer Chip...</a></li>

</ul>
</details>

**Tags**: `#semiconductors`, `#supply-chain`, `#export-controls`, `#AI-hardware`, `#China`

---

<a id="item-tech-news-12"></a>
### [Masullo claims GRH proof \(hurried announcement\)](https://math216.wordpress.com/2026/11/20/hurried-announcement-alessandro-masullo-grh/) ⭐️ 7.0/10

Alessandro Masullo posted a hurried public announcement on Nov 20, 2026 claiming a proof of the Generalized Riemann Hypothesis; the manuscript and claim have not been independently verified. Hacker News discussion around the blog post highlights a long, hastily published draft and widespread skepticism about its completeness and correctness. Commenters also raised speculative concerns that parts of the work or related material could have been exposed to or discovered by AI labs \(notably Anthropic\), but no confirmed evidence of data leakage or independent AI validation has been presented.

hackernews · jasondavies · Nov 20, 18:33 · [Discussion](https://news.ycombinator.com/item?id=50579568)

**「What GRH is and recent AI‑assisted proof claims」** The Generalized Riemann Hypothesis \(GRH\) extends the Riemann Hypothesis to a family of L‑functions and is a longstanding unsolved conjecture about the locations of their nontrivial zeros. The drama around a hurried public draft is occurring alongside recent high‑profile claims of AI‑assisted proofs — notably a New York Times–reported claim that Levent Alpöge at Anthropic said he collaborated with the Claude system on a proof of the Riemann hypothesis — which helps explain community sensitivity to rapid announcements and to questions about whether AI systems or shared drafts played a role.

**「Immediate consequence」** Mathematicians and publishers should treat the claim as unverified pending standard peer review and independent checking, and researchers or institutions worried that private drafts may have been shared with AI services should promptly audit upload histories and service access logs.

**「Debate highlights」** Commenters such as Aurornis, prometheus1992, and Kotlopou argued the announcement appeared rushed \(to claim priority\), noted formatting and length problems in the draft, and speculated—without evidence—that portions might have been uploaded to or accessed by Anthropic; several participants emphasized the need for calm, methodical independent verification.

<details><summary>References</summary>
<ul>
<li><a href="https://math216.wordpress.com/2026/11/20/hurried-announcement-alessandro-masullo-grh/">Hurried Announcement : Alessandro Masullo GRH | Math 216 ...</a></li>
<li><a href="https://www.nytimes.com/2026/11/20/science/anthropic-ai-math-riemann-hypothesis.html">Anthropic Mathematician Claims to Solve Riemann Hypothesis With...</a></li>

</ul>
</details>

**Tags**: `#AI-assisted-theorem-proving`, `#data-leakage`, `#mathematics`, `#research-integrity`

---

<a id="item-tech-news-13"></a>
### [LLMs Rewriting Their Own Weights](https://arxiv.org/abs/2611.21885) ⭐️ 7.0/10

An arXiv preprint claims a language model can rewrite its own numerical weights using only its reasoning \(no gradients or conventional training\), by generating and testing weight-edit proposals on practice problems and applying only edits that improve performance; the authors report iterative gains across sessions. The paper is a preprint \(not peer-reviewed\) and the result as reported is a claim rather than an independently replicated measurement, with the demonstrated improvements described in discussion as modest and condition-dependent.

hackernews · lwhsiao · Nov 20, 16:29 · [Discussion](https://news.ycombinator.com/item?id=50577265)

**「Prerequisite concepts」** Most neural models are improved via gradient-based training, while the terms &quot;model editing&quot; and &quot;weight-space programming&quot; refer to techniques that change a model&\#x27;s stored parameters directly \(rather than only changing activations at inference time\). Prior work discussed in the community — including weight-space programming research and frameworks like Google’s &quot;sleep&quot; idea that use self-generated practice examples for offline weight updates — provides the immediate context for claims that a model can rewrite its own weights without gradients, and explains why questions about novelty, robustness, and safety arise.

**「Impact」** If the method is reproducible, developers and deployers should not enable autonomous in‑place weight editing in production systems without strict safeguards: the community discussion shows edits so far can be small or exploit prompt/token-limit artifacts, and safety researchers warn autonomous weight changes could be used to suppress safety‑related activations, so edits should be restricted to offline evaluation, versioned backups, and explicit approval workflows.

**「Community discussion」** Commenters note the reported gains appear limited \(one observed improvement came from shortening reasoning traces to avoid token limits\) and that similar ideas have precedents \(weight‑space programming and Google&\#x27;s &\#x27;sleep&\#x27; style work\); others flagged this as a high‑risk research direction because an autonomous model that changes weights could deliberately remove safety signals.

**Tags**: `#machine-learning`, `#language-models`, `#model-editing`, `#ai-safety`, `#research`

---

<a id="item-tech-news-14"></a>
### [Restricting AI agents from capturing Signal chats](https://signal.org/blog/protecting-your-privacy/) ⭐️ 7.0/10

Signal and community conversation have focused attention on the difficulty of preventing third‑party AI agents on mobile operating systems from capturing private chat data. The public material summarizes concerns and Signal’s ongoing efforts to limit such access, but it contains limited technical detail and does not publish forensic findings or a verified, platform‑level mitigation.

hackernews · dotcoma · Nov 20, 09:42 · [Discussion](https://news.ycombinator.com/item?id=50572348)

**「Why OS-level AI agents threaten private screen content」** Modern mobile and desktop operating systems are introducing agentic AI features that can ‘scan’ on-screen information to provide suggestions or context, which lets those agents access app content even when a user has not installed a third-party AI app. Signal has previously deployed per-app mitigations—such as its “Screen security” setting in Signal Desktop that tries to prevent screenshots on Windows—to limit ordinary screen capture, but those measures do not by themselves stop OS-level AI agents that inspect displayed content at the system level.

**「Impact for developers and platforms」** A concrete consequence is that app developers and platform vendors must treat platform access \(agents installed on contacts’ devices, background services, screenshot/notification capture capabilities\) as a realistic data‑exfiltration vector and coordinate on OS controls and transparency; Signal publishing its investigation details would materially help smaller developers replicate defenses or harden apps.

**「Community reactions」** Commenters urged greater transparency \(requesting Signal publish forensic findings\), recommended that users consider more locked‑down OSes like GrapheneOS, and pointed out related usability and privacy frustrations with Signal \(captcha/VPN friction and screenshot restrictions\) while noting the broader platform‑level challenge.

<details><summary>References</summary>
<ul>
<li><a href="https://signal.org/blog/protecting-your-privacy/">Signal &gt;&gt; Blog &gt;&gt; Signal is Serious About Protecting...</a></li>
<li><a href="https://signal.org/blog/signal-doesnt-recall/">Signal &gt;&gt; Blog &gt;&gt; By Default, Signal Doesn&#x27;t Recall</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#mobile-security`, `#ai-agents`, `#platforms`, `#signal`

---

<a id="item-tech-news-15"></a>
### [SEC probe of NVIDIA&\#x27;s accounting reported — unconfirmed](https://www.marketscreener.com/news/us-sec-s-nvidia-probe-is-examining-potential-accounting-issues-sources-say-ce785ed3dd8ff627) ⭐️ 7.0/10

Unconfirmed media reports say the U.S. Securities and Exchange Commission is examining potential accounting issues at NVIDIA, citing unnamed sources; neither the SEC nor NVIDIA has publicly confirmed the probe. The reporting provides few concrete details about the nature, scope, or timeframe of the alleged issues, so the development should be treated as unverified. Because NVIDIA is a central supplier of AI GPUs and related services, any confirmed SEC inquiry into its accounting could be material to investors and counterparties in the AI/hardware ecosystem. For now, the available accounts are preliminary and lack supporting evidence from filings or company statements.

hackernews · ftchd · Nov 20, 20:22 · [Discussion](https://news.ycombinator.com/item?id=50581438)

**「Why an SEC accounting probe matters」** An SEC probe of accounting practices examines whether a public company’s revenue recognition, disclosures, or internal controls comply with U.S. securities laws and accounting standards, and such probes can lead to restatements, enforcement actions, or civil penalties. The report says the inquiry comes on top of other regulatory scrutiny of Nvidia—Reuters has reported that the Justice Department is also reviewing Nvidia’s $12.9 billion acquisition of Hugging Face as part of broader antitrust and acquisition reviews.

**「Immediate consequence」** The most concrete near-term effect is likely market and governance scrutiny: investors and counterparties should expect potential share-price volatility and heightened demand for official disclosures. Stakeholders should avoid trading on the unverified reports and instead monitor SEC filings and formal statements from NVIDIA for confirmatory details before making decisions.

**「Notable reactions」** Commenters on the thread offered speculative and conflicting views, with some alleging long‑running &quot;circular financing&quot; and secret chip deals and others questioning why the CFO was named interim CEO if accounting problems existed. Those comments are opinions and conjecture rather than evidence of wrongdoing; they illustrate market anxiety but do not substitute for verified regulatory or corporate disclosures.

<details><summary>References</summary>
<ul>
<li><a href="https://www.investing.com/news/economy-news/exclusiveus-secs-nvidia-probe-is-examining-potential-accounting-issues-sources-say-5042460">Nvidia ’s accounting is a focus of US SEC investigation, sources say...</a></li>

</ul>
</details>

**Tags**: `#regulation`, `#nvidia`, `#semiconductors`, `#investigations`, `#corporate-governance`

---

<a id="item-tech-news-16"></a>
### [TikTok launches global deepfake-detection and transparency tools](https://www.straitstimes.com/world/tiktok-launches-tool-to-help-public-figures-detect-deepfakes-globally) ⭐️ 7.0/10

On Nov. 20, 2026, TikTok globally launched a Likeness Detection feature that notifies and lets third-party–verified public figures and top creators report unauthorized AI-generated uses of their image. TikTok also released a public transparency uploader that allows anyone to submit an image or video without an account to check whether it was produced by TikTok&\#x27;s own AI tools. TikTok framed the moves as helping protect upcoming 2027 European elections and noted EU rules from August requiring AI content labeling; the company did not publish technical details or independent accuracy measurements for the detection capability.

telegram · zaihuapd · Nov 20, 08:14

**「Context」** Platforms and researchers have already developed provenance and labeling measures—such as C2PA content credentials and platform-specific watermarks—to help identify AI-generated media; reporting indicates TikTok&\#x27;s public checker inspects C2PA credentials and its VeraDura watermark. Regulators including the EU began requiring AI content labels in August 2026, which has pushed major platforms to add detection and transparency tools.

**「Immediate consequence」** Verified public figures who complete TikTok&\#x27;s third-party identity verification can now receive automated alerts and a reporting channel for suspected AI misuse, so individuals and their teams should consider completing verification to use the feature; at the same time, journalists and researchers gain a no‑account way to check whether media originated from TikTok&\#x27;s AI, though the lack of published technical details limits independent validation of the tool&\#x27;s reliability.

<details><summary>References</summary>
<ul>
<li><a href="https://www.straitstimes.com/world/tiktok-launches-tool-to-help-public-figures-detect-deepfakes-globally">TikTok launches deepfake detection tool for public figures ...</a></li>
<li><a href="https://www.gate.com/news/detail/tiktok-launches-ai-content-detection-tool-rolls-out-global-likeness-25748695">TikTok Launches AI Content Detection Tool, Rolls Out Global ...</a></li>

</ul>
</details>

**Tags**: `#deepfake-detection`, `#content-moderation`, `#AI-transparency`, `#platform-security`, `#election-integrity`

---

<a id="item-tech-news-17"></a>
### [Tesla assisted driving approved in Italy](https://www.ilfattoquotidiano.it/2026/11/20/tesla-assisted-driving-arriva-in-italia-via-libera-alla-guida-assistita-avanzata/8578482/) ⭐️ 7.0/10

Italian authorities have approved Tesla&\#x27;s advanced driver‑assistance system and Tesla says it will be delivered to vehicles in Italy via an over‑the‑air \(OTA\) update, offered as a subscription for €99 per month. Tesla describes the feature as able to handle urban roads, intersections and lane changes while requiring continuous driver supervision and leaving legal responsibility with the driver. The company also reported cumulative European operation of more than 200 million kilometres and a claimed collision rate as low as one‑seventh of manual driving, but those safety figures are based on Tesla&\#x27;s own methods and have not been independently verified. Italy will be the twelfth European market for the feature; Tesla first launched it in the Netherlands in April 2026.

telegram · zaihuapd · Nov 20, 12:14

**「Why this matters」** Advanced driver‑assistance systems like Tesla&\#x27;s automate steering, speed and lane management in specific situations but do not remove the need for a human driver to monitor the system. The feature&\#x27;s prior public rollout began in the Netherlands in April 2026, and the Italy approval extends that regional deployment.

**「Immediate consequence」** Italian Tesla owners will be able to opt into the capability for €99/month once the OTA arrives, but they must continue to supervise the vehicle and remain legally responsible; because Tesla&\#x27;s safety claims come from its own data and methods, drivers, insurers and regulators should not treat the subscription as independently validated autonomous driving and may need independent verification or policy adjustments.

**Tags**: `#autonomous-driving`, `#regulation`, `#ADAS`, `#safety`, `#subscription-model`

---

<a id="item-tech-news-18"></a>
### [OpenAI: GPT‑6.2 Astra/Sol anti‑distillation cuts extraction to 0.2%](https://openai.com/index/combatting-adversarial-distillation/) ⭐️ 7.0/10

OpenAI says it strengthened defenses against adversarial distillation for GPT‑6.2 Astra and Sol, and that red‑team tests extracting historical chain‑of‑thought dropped from 54.0% success to 0.2% success. The company also reported weekly enforcement actions against “thousands to tens of thousands” of accounts it identifies as performing distillation, and said it notified Congress about suspected distillation by an entity named DeepSeek. These are OpenAI&\#x27;s reported test results and enforcement claims; the item does not include independent verification or technical details of the mitigations.

telegram · zaihuapd · Nov 21, 01:30

**「What adversarial distillation and chain-of-thought extraction are」** Adversarial distillation is an attack technique where an adversary issues many crafted queries to a model and uses the model&\#x27;s responses to train a surrogate or recover internal behavior; chain-of-thought extraction specifically tries to recover the model&\#x27;s step‑by‑step reasoning or other latent patterns from its outputs. Defenses against these attacks include detecting and blocking large-scale “distillation” accounts, altering or obfuscating outputs that reveal internal reasoning, and measuring attack success by attempting reconstruction on withheld prompts, so a drop in measured extraction rate indicates the defenses made reconstruction materially harder in that evaluation.

**「Immediate consequence」** If OpenAI&\#x27;s reported measurements are accurate, attackers and third parties will find adversarial distillation and chain‑of‑thought extraction on GPT‑6.2 Astra and Sol substantially less effective, so organizations that rely on external distilled copies should reassess threat and provenance assumptions and perform independent extraction tests. Security teams and researchers who run red‑team or distillation experiments should expect provider enforcement actions to affect account access and should monitor provider notices and policy changes accordingly.

**Tags**: `#model-extraction`, `#adversarial-ML`, `#security`, `#chain-of-thought`

---

<a id="item-tech-news-19"></a>
### [Trump proposes heavy tax on U.S. firms&\#x27; overseas AI data centers](https://apnews.com/article/trump-artificial-intelligence-data-centers-f1ac03b73d13445400eeed8631d9d879) ⭐️ 7.0/10

At a Nov. 20 White House press conference, Donald Trump said he plans to impose &quot;heavy taxes&quot; on U.S. technology companies that build AI data centers overseas, with the stated goal of keeping such infrastructure in the United States and maintaining a competitive advantage over China. He said he has not yet disclosed the plan to government officials and provided no implementation details or tax rates. Trump also urged U.S. communities to accept data-center projects and to negotiate payments from developers to localities concerned about power use and noise.

telegram · zaihuapd · Nov 21, 03:26

**「Why data-center location matters」** AI data centers are physical facilities that house the servers and networking used to train and serve large models, and they typically consume substantial electricity for compute and cooling. Because a data center’s physical location affects latency, regulatory jurisdiction, and national competitiveness, governments sometimes use taxes, subsidies, or other rules to influence where firms build that infrastructure.

**「Impact」** If the proposal is enacted, U.S. cloud and AI providers weighing foreign data-center builds could face higher costs that affect site selection, capital planning, and contractual commitments; until details are published, companies should monitor developments, review international deployment plans, and consider potential tax liabilities and community engagement strategies. Local governments and project developers may gain stronger leverage in negotiations over payments and community mitigation if federal policy explicitly favors domestic siting.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/20/trump-data-centers-ai-companies-tax.html">Trump vows to stop U.S. companies from building data centers ...</a></li>

</ul>
</details>

**Tags**: `#policy`, `#data-centers`, `#AI-infrastructure`, `#geopolitics`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Why output caching doesn&\#x27;t work](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 21, 00:00

**「Background」** The author frames a practical question for LLM-based agents: we already cache model inputs \(the KV cache\) to avoid re-computing conversation history, so should we likewise cache model outputs to avoid repeated visible text? This seems attractive because agents often reprint code, quotes, or earlier model outputs, and output tokens are more expensive and generated sequentially.

**「Solution」** Sean Goedecke argues that output caching delivers almost no return on effort because visible output is only a tiny slice of what actually consumes tokens. Based on his agent histories he estimates about 50% of output tokens are internal reasoning and 44% are tool calls, leaving roughly 6% as visible user-facing text; by Amdahl’s law, even an optimistic two‑thirds reduction in that visible portion would cut only about 4% of total output tokens. You could implement output caching by prompting or fine‑tuning models to emit references \(e.g., filenames or history spans\) that a harness expands, and mature inference providers may exploit speculative decoding to speed repeated outputs, but these optimizations only shave the small visible slice. Instead the author recommends reducing the invisible costs — smarter models or better harnesses that lower internal reasoning and tool-call tokens — because higher‑quality models can use far fewer tokens overall \(so a higher per‑token price can still be cheaper end‑to‑end\). He qualifies his claims as anecdotal and moderately confident, notes open questions about repetition inside tool calls, and invites practitioners with deeper data to contribute.

**「Takeaway」** Goedecke’s core point is that caching visible outputs is low-impact: most token cost is invisible internal work, so engineering effort is better spent on smarter models or harnesses that reduce reasoning and tool‑call tokens. Output‑caching is an easy optimization to imagine but usually not worth the ROI.

**Tags**: `#LLM inference`, `#caching`, `#performance`, `#engineering tradeoffs`, `#Amdahl&\#x27;s law`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Warsh avoids forward guidance as Fed officials speak up](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 8.0/10

Federal Reserve Chair Kevin Warsh has largely refused to give forward guidance while other Fed officials have increased public comments; traders now imply a 100% chance of at least a 0.25 percentage-point rate hike in December, according to CME Group&\#x27;s FedWatch.

rss · CNBC Finance · Nov 20, 21:10

**「background」** Since taking office, Fed Chair Kevin Warsh has rejected forward guidance — public signals about the likely path of interest rates — and that absence of a clear chair-led signal has coincided with a surge in other FOMC officials speaking publicly \(Bank of America counts more &\#x27;Fedspeak&\#x27; in the past two weeks than in any similar period since early 2025\), while October FOMC minutes show some participants would have preferred clearer signaling to justify a hold.

**「impact」** Investors and short-term borrowers face higher interest-rate risk because markets are pricing near-certain December tightening amid louder, sometimes conflicting Fed commentary.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html">Warsh wants Fed officials to talk less. Instead, they’re ...</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#FOMC communication`, `#inflation`

---

<a id="item-finance-news-2"></a>
### [Corporate shift from buybacks to net equity issuance](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 8.0/10

U.S. corporations have moved from net share repurchases to net equity issuance, with Acadian Asset Management reporting net new issuance equal to 3.1% of total market capitalization as of late last week \(Acadian investor letter\).

rss · CNBC Finance · Nov 20, 14:15

**「background」** Before 2026 U.S. corporations were net repurchasers of stock \(share buybacks, which shrink shares outstanding\), but Acadian Asset Management says that trend reversed: net new equity issuance equaled 3.1% of total market capitalization as of late last week, and large deals including Anthropic&\#x27;s roughly $81 billion IPO have added fresh supply.

**「Impact」** That rise in supply — illustrated by large raises and IPOs such as Anthropic&\#x27;s $81 billion offering — is a potential supply-side headwind for the four-year bull market because it reverses the scarcity and earnings-per-share boost that repurchases provided, affecting equity investors.

<details><summary>References</summary>
<ul>
<li><a href="https://www.acadian-asset.com/investment-insights/owenomics/the-smart-money-is-selling-equity">The smart money is selling equity | Acadian Asset Management</a></li>
<li><a href="https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html">equity issuance bull market problem - CNBC</a></li>
<li>Anthropic Prices IPO At $83 Per Share, Implying $1.5 Trillion Valuation</li>

</ul>
</details>

**Tags**: `#equity issuance`, `#share buybacks`, `#IPOs`, `#market structure`, `#corporate finance`

---

<a id="item-finance-news-3"></a>
### [Alibaba sued over alleged concealment of business link to &\#x27;Alice Huang&\#x27;](https://www.zaobao.com.sg/news/china/story20261120-10029652) ⭐️ 7.0/10

Shareholders filed a class-action suit against Alibaba in Manhattan federal court alleging the company understated export-control risks and hid a business relationship with &\#x27;Alice Huang&\#x27; and a Singapore firm; the complaint says Alibaba&\#x27;s shares fell 14% over four trading days \(alleged\) and names CEO 吴泳铭 \(Wu Yongming\) as a defendant, according to Lianhe Zaobao.

telegram · zaihuapd · Nov 20, 09:32

**「background」** Alice Huang—who, according to reporting, in 2023 and with her husband promoted a plan to build an artificial‑intelligence business in Southeast Asia—is named in the New York federal lawsuit that alleges Alibaba concealed a business tie and understated export‑control risks.

**「Impact」** If the allegations proceed, U.S.-listed Alibaba shareholders and investors in its American Depositary Shares could face direct financial and governance effects because the complaint links the alleged disclosure failures to a claimed 14% share-price decline over four trading days.

<details><summary>References</summary>
<ul>
<li><a href="https://cn.nytimes.com/technology/20261119/nvidia-alibaba-china-military/">cn.nytimes.com/technology/20261119/nvidia- alibaba -china-military</a></li>

</ul>
</details>

**Tags**: `#lawsuit`, `#Alibaba`, `#export controls`, `#corporate governance`, `#market impact`

---

<a id="item-finance-news-4"></a>
### [Beijing draft bars deposit deductions for normal rental wear](https://mp.weixin.qq.com/s/PmGxh5knIyxiBRhpRoJnoQ) ⭐️ 7.0/10

Beijing municipal authorities published a draft revision to the city&\#x27;s standard housing rental contract that would bar landlords from deducting security deposits for tenants&\#x27; normal wear and tear \(draft proposal; public consultation opened 20 Nov 2026\).

telegram · zaihuapd · Nov 20, 13:46

**「background」** Beijing’s housing authority and market regulator have released a draft revision to the city’s standard housing lease template — updating the model contract first issued in 2023 — and opened it for public comment starting 20 November 2026.

**「Impact」** If adopted, the change would directly protect renters from routine deposit deductions and require leasing firms to place deposits in supervised accounts, increasing compliance and cash‑management requirements for rental companies.

<details><summary>References</summary>
<ul>
<li>北京市住房租赁合同范本（2023） - 知乎专栏</li>
<li>北京住房租赁合同征求意见有哪些特点？ - 百度知道</li>

</ul>
</details>

**Tags**: `#Beijing`, `#rental regulation`, `#tenant protection`, `#deposit management`

---