---
layout: default
title: "Horizon Summary: 2026-11-24 (ZH)"
date: 2026-11-24
lang: zh
---

> 从 39 条内容中筛选出 20 条重要资讯。

---

**科技新闻**
1. [黄仁勋获董事会全票恢复 CEO 并重返董事会](#item-tech-news-1) ⭐️ 9.0/10
2. [GLM-5.4：首个循环 Transformer 与编码优化](#item-tech-news-2) ⭐️ 8.0/10
3. [NariQ: BF16-level Qwen3.8-27B in a 10 GB file](#item-tech-news-3) ⭐️ 8.0/10
4. [Codex2api 疑似供应链投毒](#item-tech-news-4) ⭐️ 8.0/10
5. [AI 辅助 Lean 证明黎曼猜想被指空转](#item-tech-news-5) ⭐️ 8.0/10
6. [4.5 万组织联名要求欧盟调查 iPhone 浏览器限制](#item-tech-news-6) ⭐️ 8.0/10
7. [新加坡不会成规避美芯片管制的通道](#item-tech-news-7) ⭐️ 8.0/10
8. [Anthropic 称 Claude 生成 VP≠VNP Lean4 证明](#item-tech-news-8) ⭐️ 8.0/10
9. [Arm 要求社区文档镜像在 2026-12-04 下线](#item-tech-news-9) ⭐️ 7.0/10
10. [Stalwart 宣称可替代 Microsoft Exchange](#item-tech-news-10) ⭐️ 7.0/10
11. [Ladybird 浏览器进入 Alpha](#item-tech-news-11) ⭐️ 7.0/10
12. [Meta AI 负责人：超级智能即将来临](#item-tech-news-12) ⭐️ 7.0/10
13. [鸿蒙终端设备突破 1 亿台](#item-tech-news-13) ⭐️ 7.0/10
14. [神舟二十四号将于 11 月 25 日发射 首次含巴基斯坦航天员](#item-tech-news-14) ⭐️ 7.0/10

**科技博客**
1. [vLLM 对 ERNIE 5.5 Flash 的 Day‑0 支持](#item-tech-blog-1) ⭐️ 8.0/10

**财经新闻**
1. [威廉姆斯：需“逐步”进一步行动以将通胀降至 2%](#item-finance-news-1) ⭐️ 8.0/10
2. [英伟达恢复黄仁勋为 CEO 引发美股反弹](#item-finance-news-2) ⭐️ 8.0/10
3. [Anthropic IPO 引发抛售，冲击中国 AI 上市计划](#item-finance-news-3) ⭐️ 8.0/10
4. [上海地铁票价时隔 21 年首次调整](#item-finance-news-4) ⭐️ 8.0/10
5. [SpaceX 向 Anthropic、Google 出租算力，报道称月入数十亿美元](#item-finance-news-5) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [黄仁勋获董事会全票恢复 CEO 并重返董事会](https://nvidianews.nvidia.com/news/nvidia-board-reinstates-jensen-huang-as-president-ceo-and-board-director) ⭐️ 9.0/10

英伟达董事会全票决定即刻恢复黄仁勋为总裁兼首席执行官，并重新任命其为董事会成员；此前由科莱特·克雷斯担任临时 CEO，现将继续担任首席财务官。董事会称在听取美国政府高层意见后认为黄仁勋复任不构成国家安全风险，同时已成立由独立董事组成的调查委员会、设立国家安全与出口管制委员会，并启动首席合规官职位的招聘，黄仁勋表示将全力配合调查。

telegram · zaihuapd · 11月23日 14:02

**「背景」** 此前有报道指出黄仁勋曾成为外国情报活动的潜在目标，公司在报道期间由科莱特·克雷斯出任临时 CEO。此次董事会复位决定明确提到已听取美国政府高层的意见，这是董事会作出结论的一个直接前提。

**「影响与行动建议」** 董事会成立国家安全与出口管制委员会并招聘首席合规官，表明英伟达将强化合规与出口管制治理；与英伟达有业务往来的供应商、客户和合作伙伴应审查与出口管制相关的合同与合规流程，并监控公司后续政策与披露以便及时调整合规做法。独立调查委员会的调查结果也可能带来后续治理或合规披露变动，相关方应关注未来公告。

**「社区讨论要点」** 评论里最常被引用的论点是董事会提到已听取美国政府高层意见，这被许多人视为决定性说明但并不等同于对事实的司法认定；同时有评论对董事会在短期内从替换到全票恢复这一完全转变感到惊讶，并有人援引德拉瓦州 Caremark 判例讨论董事责任与法律风险，这些都是舆论关注的主要分歧点。

**标签**: `#nvidia`, `#leadership`, `#national-security`, `#ai`, `#corporate-governance`

---

<a id="item-tech-news-2"></a>
### [GLM-5.4：首个循环 Transformer 与编码优化](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai 发布了 GLM‑5.4，这是该团队首个采用“循环（loop）Transformer”架构的模型。博文说明，在这种架构中一组权重共享的层会在一次前向传播中迭代运行多次，从而在不增加参数量的前提下获得更深的网络表征。GLM‑5.4 的权重尚未开源，当前只能通过 Z.ai 的 Coding Plan 订阅并使用其与 OpenAI 兼容的 Responses API（https://api.z.ai/api/v1）访问；博文作者的简单视觉测试（pelican 测试）显示 5.4 与 5.3 在质量上相近。 

hackernews · foohis · 11月23日 10:06 · [社区讨论](https://news.ycombinator.com/item?id=50609685)

**「背景」** 传统 Transformer 在一次推理过程中每一层仅运行一次；循环 Transformer 则重复运行一组权重共享的层以逐步细化隐藏状态。该方法被提出部分是为了解决推理时把整层权重在内存与芯片之间移动所带来的带宽瓶颈问题，从而以较少参数实现更深的计算。 

**「影响与行动建议」** 想要试用 GLM‑5.4 的开发者需要订阅 Z.ai 的 Coding Plan，因为该模型目前不通过常规 API 公开访问；好消息是它使用与常规 Z.ai 服务相同的 OpenAI 兼容 Responses API，因此现有兼容客户端在获得合适的 API key 后应能调用该模型。由于权重未开源，研究人员不能本地重现或离线评估模型，插件和第三方集成（例如博文中提到的 llm-zai）可能需要更新以支持新模型，开发者应关注相关插件的兼容性更新或临时使用作者自建适配器。 

**「社区讨论要点」** 评论中有人称赞 Zhipu（Z.ai）在技术细节上的透明度，并认为循环 Transformer 是明显的发展方向但仍有问题需解决；另有评论指出部分中文模型在生成时表现出“马拉松式思考”（即过度反复确认导致响应慢且耗时），这是社区对可用性和时延的一个主观担忧。也有用户在评论中解释称循环 Transformer 可帮助缓解内存带宽瓶颈，这是社区对该架构的常见技术性解释。 

**标签**: `#loop-transformer`, `#LLM-release`, `#model-architecture`, `#API-access`

---

<a id="item-tech-news-3"></a>
### [NariQ: BF16-level Qwen3.8-27B in a 10 GB file](https://huggingface.co/nari-labs/Qwen3.8-27B-NariQ-GGUF) ⭐️ 8.0/10

NariQ presents 3-bit-and-lower quantizations of Qwen3.8-27B claiming near-BF16 quality on multiple benchmarks and context lengths, with provided numeric comparisons and a required llama.cpp fork.

hackernews · toebee · 11月23日 13:42 · [社区讨论](https://news.ycombinator.com/item?id=50611402)

**标签**: `#quantization`, `#model-compression`, `#inference-performance`, `#benchmarks`, `#Qwen3.8`

---

<a id="item-tech-news-4"></a>
### [Codex2api 疑似供应链投毒](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 8.0/10

社区报告称开源项目 Codex2api 的作者账号疑似被入侵，攻击者绕过 main 分支推送 tag，导致发布的二进制/Release 构建出带后门的版本。报告具体称 v3.1.11 去掉了鉴权，等同于无密码的远程命令执行（RCE）；同时还包含一个 workflow，将仓库中 16 个 GitHub Actions secrets 外传，波及同一账号下至少 21 个仓库。受影响者被建议：已安装或更新到 3.1.10–3.1.12 的立即停用并回退到 3.1.9，同时轮换 GitHub token、SSH key、数据库凭证及报告中提到的 DeepSeek 等所有相关密钥。该内容来自社区/Telegram 报告，本文未对指控做独立验证。

telegram · zaihuapd · 11月23日 11:21

**「背景」** Codex2API 是一个把多路上游 Codex 账号聚合并对外提供 OpenAI 兼容接口的反向代理与管理系统（以 Go + 前端技术实现），常被用来部署自建网关并路由 API 请求。因为用户通常从项目的 Release 或仓库工作流构建并运行该软件，任何被植入后门的发布包或恶意 GitHub Actions workflow 都可能在运行时执行任意命令并访问或外传仓库的 secrets。

**「对用户和维护者的直接后果」** 如果报告属实，受影响的发布包含可被远程滥用的无鉴权 RCE，并且攻击者已经外传了至少 16 个 Actions secrets，意味着使用这些凭证的系统（CI、部署主机、数据库和第三方服务）可能已被泄露或入侵；受影响仓库的维护者应当立即停用受影响版本、回退到 3.1.9、撤销并重新生成所有 GitHub token、SSH key、数据库密码与第三方服务密钥，审查并删除恶意 workflow、检查运行器和访问日志以识别可疑活动，并按已被入侵的假设处置任何使用过这些凭证的环境。该建议基于社区报告的具体指控，尚未有独立公开的技术验证报告。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepwiki.com/james-6-23/codex2api">james-6-23/ codex2api | DeepWiki</a></li>

</ul>
</details>

**标签**: `#supply-chain`, `#security`, `#RCE`, `#GitHub Actions`, `#open-source`

---

<a id="item-tech-news-5"></a>
### [AI 辅助 Lean 证明黎曼猜想被指空转](https://x.com/i/web/status/2124987173439209561) ⭐️ 8.0/10

社交媒体报道称，数学家 Alpöge 与名为 Claude 的模型宣称已用 Lean 形式化系统证明黎曼猜想及其广义版本，但只公开了一个庞大的代码库——约 1,700 万行 Lean 代码、约 17.5 万个文件，而没有提供人类可读的证明说明。报道进一步称，Lean 与 mathlib 社区翌日表示对代码“有充分信心”，但随后有研究者指出关键定义被写成恒真或使几何条件形同虚设，质疑证明是否为实质性论证；Alpöge 据称已承认“25 万页是玩笑”，并称代码“满是垃圾但能编译”，同时认为对其的批评是合理的。该信息来自社交媒体报告，未见独立第三方的全面验证。

telegram · zaihuapd · 11月24日 01:29

**「背景说明」** Lean 是一种交互式定理证明助手，用来把数学证明形式化为可由计算机检查的代码；对此类代码的“证明成立”通常指形式化库能在证明检查器中无误地通过而不是传统的人类可读的证明。近期报道说，Levent Alpöge 发布了一个宣称证明黎曼猜想及其广义版本的 Lean 归档，包含约 175,187 个文件、约 1,740 万行代码，并有报告称可以本地编译该代码，还有组织表示已独立核查该形式化证明的通过情况。

**「影响与须要采取的动作」** 此事对形式化证明和依赖自动化工具的研究社区提出了具体的可重复性与信任挑战：大型、自动生成且缺乏可读性证明库不能替代经过人工审查的、带有证明思路和最小可复现示例的发表材料。受影响的研究者和评审机构应要求对声称的重要定理提供（1）简明的人类可读证明草案或思路、（2）可独立检查的最小 Lean 示例与单元测试、以及（3）对关键定义的审计记录，以便区分“仅能编译”的代码与数学上有内容的形式证明。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=aDl7-MWFLVc">17 Million Lines Claim to Prove Riemann . We Ran Them. - YouTube</a></li>
<li><a href="https://www.theguardian.com/technology/2026/nov/21/anthropic-riemann-hypothesis-solved-claude-ai">Two groups verify mathematician’s claim that Claude ... | The Guardian</a></li>
<li><a href="https://math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/">Alpöge / Claude proof of the Generalized Riemann Hypothesis</a></li>

</ul>
</details>

**标签**: `#formal-verification`, `#AI-assisted-proof`, `#reproducibility`, `#open-source`, `#math-foundations`

---

<a id="item-tech-news-6"></a>
### [4.5 万组织联名要求欧盟调查 iPhone 浏览器限制](https://appleinsider.com/articles/26/11/23/eu-urges-to-challenge-apples-grip-on-iphone-browsers?utm_source=rss) ⭐️ 8.0/10

包括 Mozilla 和 Shopify 在内的约 4.5 万至 5.5 万家欧盟企业与组织向欧盟委员会联名致信，要求对苹果在 iPhone 上的浏览器引擎与 App Store 相关限制立案调查。信中指出，尽管《数字市场法》在欧盟要求允许第三方浏览器使用非 WebKit 引擎，但现有的技术与法律要求仍令厂商难以将现有 iOS 用户从 WebKit 迁出，且企业仍严重依赖 App Store 触达用户；联署征集截至 2026 年 12 月 3 日。联名方估算，若一半原生 iOS 应用转为网页应用，欧盟企业每年可节省约 110 亿欧元开发成本和约 13 亿欧元 App Store 费用，但这些数字来自联名方的测算而非独立核验。

telegram · zaihuapd · 11月24日 03:02

**「背景说明」** 欧盟的《数字市场法》（DMA）要求对平台型“守门人”放宽限制，从而在法律层面允许在 iPhone 上提供使用非苹果引擎的竞品浏览器；但在技术和合规实现层面，厂商报告称现有规则和技术细节仍导致 WebKit 在 iOS 生态中保持事实上的主导地位。正因为这种技术与分发（App Store）上的依赖关系，受到影响的企业将关心是否能实际将原生 iOS 应用迁移到基于网页的替代方案。 

**「影响」** 这份大规模请愿会增加欧盟对苹果 iOS 浏览器与分发规则的监管压力，并可能促使委员会考虑对苹果是否违反《数字市场法》或竞争法立案调查。若欧盟立案或采取强制性措施，浏览器厂商与 iOS 应用/网页开发者应准备记录并保存与 WebKit 兼容性、引擎替换难点及分发限制相关的技术证据，并评估为支持非 WebKit 引擎或更多分发渠道所需的兼容性与测试工作。

**标签**: `#regulation`, `#Apple`, `#iOS`, `#web browsers`, `#EU DMA`

---

<a id="item-tech-news-7"></a>
### [新加坡不会成规避美芯片管制的通道](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 8.0/10

新加坡总理黄循财表示，新加坡不会被允许成为企业规避美国芯片出口管制的通道，并称当局正在调查 Megaspeed 采购英伟达芯片的交易。此声明发生在美国商务部将 Megaspeed 及另外六家东南亚企业列入贸易黑名单之后，《联邦公报》称这些公司存在向未获授权用户转移先进计算产品的“重大风险”。据报道，名单还涉及马来西亚和泰国的关联实体，阿里巴巴的新加坡子公司 Apex Enterprise Solutions 也在名单中，但阿里巴巴否认转移受管制的先进计算芯片。该表态是政府对正在进行调查与美国制裁措施的官方回应，而非对具体违法结论的宣判。

telegram · zaihuapd · 11月24日 05:03

**「相关背景」** 美国商务部会对被认定有将受管制的“先进计算产品”转移给未获授权方的企业，采取将其列入贸易黑名单等措施以限制这些企业与美国公司和技术的交易。近期公布的黑名单包含新加坡的 Megaspeed 及其在马来西亚、泰国的关联实体，这一行动与对用于 AI/机器学习的高性能芯片（例如英伟达产品）的出口审查直接相关。

**「影响与建议」** 受影响的半导体供应链参与者与云/AI 硬件买家应预期对与新加坡及东南亚相关交易的更严格审查与合规要求，可能导致采购和交付延迟。相关企业应立即审查其供应链和合规流程，保存交易链条证明，并在涉及美国原产或受控技术的转移时评估是否需要申请美国出口许可或采取其他合规措施。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.indiatoday.in/world/story/megaspeed-us-blacklist-nvidia-export-control-espionage-probe-3045532-2026-11-24">Megaspeed US blacklist : Nvidia customer faces export control and...</a></li>

</ul>
</details>

**标签**: `#export-controls`, `#semiconductors`, `#supply-chain`, `#AI-hardware`, `#geopolitics`

---

<a id="item-tech-news-8"></a>
### [Anthropic 称 Claude 生成 VP≠VNP Lean4 证明](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 8.0/10

Anthropic 于 11 月 24 日在其仓库（Anthropics/formal-math）公开论文《VP ≠ VNP over every field》及对应的 Lean 4 形式化证明，声明该结果由内部研究用的 Claude 模型发现并且论文与代码均由 AI 撰写。论文给出哈密顿圈多项式在算术电路下的超多项式下界，从而得出 VP 是 VNP 的真子类——若成立，则解决 Valiant 1979 年的代数复杂度猜想，但该结论仅针对算术电路，不涉及经典的 P 与 NP 问题。仓库说明形式化通过“三条标准公理审计”并由独立内核 nanoda 复核，仓内除预留文件外无 sorry；同时也声明尚无人类数学家通读，Lean 无法确认形式化陈述与所声称命题完全一致，并在附录 Q 中列出若干出入，等待独立人类审阅。

telegram · zaihuapd · 11月24日 06:02

**「相关背景」** Anthropic 是 Claude 系列大型语言模型的开发者，Claude 是一类由 Anthropic 使用 Constitutional AI 训练的通用大语言模型，这解释了报告中所称的“内部 Claude 模型”。 在代数复杂度理论里，VP 与 VNP（由 Valiant 在 1979 年提出）是关于算术电路能否高效表示特定多项式的核心判定问题，研究者常把重要证明以定理证明器（此处为 Lean 4）形式化，以便机器验证并供独立数学家复核。

**「对研究者和审验流程的直接影响」** 在没有独立人类专家通读并确认形式化陈述与论文主张完全一致之前，代数复杂度与形式化验证社区不应将该结果视为已定论；有必要由领域内数学家和形式化证明专家对公开的 Lean 4 仓库与附录 Q 进行逐条审查与复核。该工作若被证明正确，将只解决算术电路情形的 VP vs VNP，而不会改变 P vs NP 的状态；同时，这一事件促进了对由大型语言模型生成数学证明时应施行的审验与可证化流程的关注与改进。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Anthropic">Anthropic - Wikipedia</a></li>
<li><a href="https://claude.com/">Claude by Anthropic | The AI for problem solvers</a></li>

</ul>
</details>

**标签**: `#algebraic-complexity`, `#formal-verification`, `#AI-generated-research`, `#VP-vs-VNP`

---

<a id="item-tech-news-9"></a>
### [Arm 要求社区文档镜像在 2026-12-04 下线](https://arm.jonpalmisc.com/) ⭐️ 7.0/10

Hacker News 帖子报道称，Arm 已要求社区维护的文档镜像站 arm.jonpalmisc.com 在 2026 年 12 月 4 日下线。站点维护者 jonpalmisc 在评论中确认了这一要求，并表示 Arm 指控其在站点上使用了 Arm 的商标和知识产权；维护者正在评估镜像迁移、法律咨询或在剔除 Arm IP 后发布生成站点源码等备选方案。该报导基于社区贴文和维护者的说明，而不是 Arm 的官方公告。

hackernews · tech234a · 11月23日 19:17 · [社区讨论](https://news.ycombinator.com/item?id=50617499)

**「相关背景：ARM 文档与社区镜像的角色」** ARM 将其 CPU 架构的规范以多种手册形式发布（如 ISA 参考与机器可读规范 MRAS），这些文档是芯片实现者和低级软件开发者确认指令行为与兼容性的权威资料。社区常用镜像、聚合与可搜索化的方式来简化对分散或难以检索的官方手册的访问；在该 Hacker News 帖子中，评论者还就 Arm 的下线请求、商标/版权问题以及部分人声称的 MRAS 许可（有人称某些 MRAS 版本采用 BSD 样式许可）展开了讨论。

**「对开发者的直接影响」** 依赖该集中镜像查阅 ARM 架构文档的工程师、CI 和工具将在 12 月 4 日后失去该便捷入口，任何以该站点固定 URL 为依赖的脚本或工具可能会中断；受影响方应在下线前备份或镜像必要文档、切换到官方文档来源，或与站点维护者/Arm 联络以寻求可持续访问方式。

**「社区讨论要点」** 维护者说明 Arm 的要求基于商标与知识产权使用；社区评论对是否构成合理使用和可执行性提出质疑，并有用户提到 ARM 的机器可读规范（MRAS）及其许可证问题。评论中有人建议镜像迁移或寻求法律援助，但这些都是社区意见而非法律结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.autozone.com/">AutoZone - Official Site</a></li>

</ul>
</details>

**标签**: `#arm`, `#documentation`, `#legal`, `#developer-tools`, `#open-source`

---

<a id="item-tech-news-10"></a>
### [Stalwart 宣称可替代 Microsoft Exchange](https://stalw.art/blog/microsoft-exchange-replacement/) ⭐️ 7.0/10

Stalwart 被宣传为可以作为 Microsoft Exchange 的“开箱即用”替代方案，用于替换本地 Exchange 部署。该说法来自项目/报道的宣称，但公开证据和独立验证尚不足以确认其在企业环境中的无缝兼容性；关键不确定点包括与 Outlook 的原生集成（例如 MAPI/Exchange 协议）是否完全兼容、对监管性长期不可更改归档（例如德国 GoBD 类要求）的支持情况，以及与 Office 365 客户端/服务绑定功能的兼容性。社区讨论表明这些兼容性和合规性问题会显著影响是否可把 Stalwart 作为直接、无额外改动的企业替代品使用。

hackernews · shaunpud · 11月23日 22:32 · [社区讨论](https://news.ycombinator.com/item?id=50620349)

**「背景说明」** 在许多企业环境中，长期以来“邮件服务器”通常指 Microsoft Exchange，“邮件客户端”通常指 Outlook；Stalwart 在其博客中宣布发布 1.2.0，并称该版本可作为 Microsoft Exchange 的“drop-in”替代品。所谓“drop-in 替代”通常意味着声称可以在不更改现有客户端、配置或管理流程的前提下直接互换部署，是否能做到完全兼容则取决于对 Exchange 专有协议、客户端互操作性以及企业级归档与合规集成等细节的支持与现实测试结果。

**「对运维、客户端兼容性与合规性的直接后果」** 社区评论指出，不能假定 Stalwart 能无缝替代 Exchange 并保留所有 Outlook/Exchange 专有功能；在迁移前，系统管理员需要对 Outlook 与 MAPI/Exchange 特性、搜索与日历互操作性以及新版 Outlook 对 IMAP 的处理进行全面测试，以避免用户工作流中断。评论还强调合规风险：例如德国的税务归档要求（评论中提及）需要不可更改的长期邮件归档，而据称 Stalwart 的常规或开源版本并不包含此类功能；有合规义务的组织必须在迁移前验证或部署符合要求的归档/保留方案。最后，评论指出即便能节省许可费，协议与客户端生态的“锁定效应”仍可能存在；因此实际行动应包括兼容性测试、法律合规评估和针对客户端或归档功能的替代计划或补充部署。

**「社区讨论」** 评论集中在三点：Outlook 与 Exchange 的原生集成及新版 Outlook 对 IMAP 的限制（用户 hobo123、traceroute66）；合规归档需求（如德国 GoBD）在常规或开源版本中可能缺失（rmoriz）；以及继续支持 Microsoft 协议栈可能带来的锁定问题（andreashaerter）；还有用户提到 Stalwart 被用于 Mozilla 的 Thunderbird（markstos）。这些意见表明社区对其能否作为企业级“无缝”替代存在实务性怀疑，而非一致接受的结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://stalw.art/blog/microsoft-exchange-replacement/">Stalwart is now a drop - in replacement for Microsoft Exchange</a></li>
<li><a href="https://en.wikipedia.org/wiki/Microsoft">Microsoft - Wikipedia</a></li>
<li><a href="https://www.microsoft.com/">Microsoft – AI, Cloud, Productivity, Computing, Gaming &amp; Apps</a></li>

</ul>
</details>

**标签**: `#email`, `#open-source`, `#sysadmin`, `#interoperability`, `#compliance`

---

<a id="item-tech-news-11"></a>
### [Ladybird 浏览器进入 Alpha](https://ladybird.org/posts/alpha/) ⭐️ 7.0/10

Ladybird 项目发布了首个 alpha 版本，用户现在可以在 macOS 和 Linux 上下载并安装浏览器，而无需自行编译。该浏览器从头实现了 HTML 解析、CSS 引擎、布局、JavaScript 和 WebAssembly 引擎，但仍依赖 HarfBuzz、Skia、ffmpeg 和 SQLite 等第三方库。多位试用者报告大多数网站能正常加载，并能运行基于 WebAssembly 的 ffmpeg 和 Pyodide，但对复杂的 service worker/worker 使用场景存在兼容性缺失（例如缺少 navigator.serviceWorker.startMessages 导致 Datasette Lite 无法启动）。项目明确标注这是 alpha，会偶发崩溃，用户可以在崩溃后查看并选择提交崩溃报告，项目也在十月通过一轮大量改进显著提升了 Web 平台测试通过数和部分 WASM/JS 性能。 

hackernews · janvdberg · 11月23日 16:13 · [社区讨论](https://news.ycombinator.com/item?id=50614249)

**「背景」** 现代网页浏览器由多个复杂子系统组成——包括 HTML 解析、CSS 样式与布局引擎、JavaScript 与 WebAssembly 引擎、进程隔离、以及图形/文本渲染等——这些子系统既可从头实现也可复用现成库。Ladybird 起源于 SerenityOS 的相关工作，虽在若干环节采用了 HarfBuzz、Skia、ffmpeg 与 SQLite 等现成组件，但项目团队近期通过大量提交和以 AI 辅助的移植工作（例如将部分 LibJS 从 C++ 移植到 Rust）快速推进兼容性和功能，因而发布了首个 alpha 版本以供 macOS 与 Linux 安装测试。

**「影响」** 前端开发者和兼容性测试人员现在可以在 macOS/Linux 环境上下载 Ladybird 进行实机测试，尤其应该重点验证 Service Worker、WebAssembly 与多线程 worker 的行为，因为已有具体站点复现了相关缺陷；安全研究者和漏洞分析人员也被项目鼓励审计并提交崩溃与安全报告。由于项目仍为 alpha，不建议将其作为每日主浏览器使用，用户在意隐私或稳定性的场景应谨慎采用并保持备份浏览器。 

**「社区讨论要点」** 社区评论普遍对 Ladybird 的页面兼容性和轻量界面表示惊喜并给予赞誉，同时有人报告页面滚动有轻微卡顿并提出对浏览器指纹识别与更严格权限控制的担忧；也有声音称采用成熟组件（如 SQLite、Skia）帮助提升了可用性，同时对项目保持怀旧与支持的情绪并存。 

**标签**: `#browser`, `#open-source`, `#web-compatibility`, `#systems`, `#privacy`

---

<a id="item-tech-news-12"></a>
### [Meta AI 负责人：超级智能即将来临](https://thenextweb.com/news/metas-ai-chief-says-superintelligence-is-arriving-and-control-is-at-risk) ⭐️ 7.0/10

Meta 首席 AI 官、超级智能实验室负责人 Alexandr Wang 在 X 发文称，超级智能已不再是“未来某天”的议题，并以一项据称由 Anthropic 的 Claude 协助、并由 Lean 与 Mathlib 社区机器校验的黎曼猜想证明作为能力证据。Wang 表示，目前 AI 与顶尖人类之间的差距只剩具体知识、工程整合与实验三块，并警告人类很难继续掌控可无限自我改进或比人类聪明约 1000 倍的系统。Wang 呼吁紧急增加对安全、对齐与防护研究的投入，但该所谓证明目前尚无可供人类阅读的版本，因此其可复现性和作为能力量尺的有效性仍不明确。

telegram · zaihuapd · 11月23日 12:49

**「背景」** 黎曼猜想是一个已有约 167 年历史的著名未解数学问题；数学家 Levent Alpöge 宣称在与 Anthropic 的 AI 模型 Claude 合作后得出了解法，并以可由证明助手检查的 Lean 表述提交。随后，Lean FRO 与 Mathlib Initiative 等组织对该 Lean 形式化陈述进行了机器可检验的认证——也就是说，独立检查者复核了用于表述证明的 Lean 程序或形式化声明，而不是仅基于传统的人类可读论文来判定正确性。

**「影响」** 对研究机构、企业与资助方的直接后果是，会带来对安全与对齐研究短期内增加资金、审查和红队测试的压力；开发团队应优先强化可解释性、可验证性与外部审计流程。鉴于该证明目前没有人类可读的版本，监管机构与学术同行在将这类机器验证结果作为能力或政策依据前，应要求公开、可复查的证明或可重复的验证流程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theguardian.com/technology/2026/nov/21/anthropic-riemann-hypothesis-solved-claude-ai">Two groups verify mathematician’s claim that Claude ... | The Guardian</a></li>
<li><a href="https://riemannhypothesissolved.com/">Lean proof of the Riemann hypothesis: an interactive map</a></li>

</ul>
</details>

**标签**: `#AI safety`, `#superintelligence`, `#AI capabilities`, `#formal verification`, `#industry news`

---

<a id="item-tech-news-13"></a>
### [鸿蒙终端设备突破 1 亿台](https://www.xinhuanet.com/20261124/68842538167d4e59a875056d5eb885ad/c.html) ⭐️ 7.0/10

华为终端有限公司 24 日宣布，搭载鸿蒙操作系统（HarmonyOS）5、6、7 的手机、平板和电脑终端累计已突破 1 亿台。公司同时称可获取的应用和服务超过 46 万项，注册开发者超过 1200 万人；开源鸿蒙已有 1.4 万余名贡献者并形成 120 余个行业发行版，合作伙伴贡献的创新能力超过 160 项并被 1600 余款应用集成调用。上述数据来自华为对外公布，为厂商自报告的里程碑，报道未提供第三方独立验证或更详细的地域/机型分布信息。

telegram · zaihuapd · 11月24日 01:46

**「背景」** 鸿蒙操作系统（HarmonyOS）是华为面向手机、平板和电脑的多端操作系统，最早于 2019 年首次发布。华为在 2024 年 10 月发布了“原生鸿蒙”版本，这一早期演进是理解其随后设备装机量和生态（应用与开发者）扩展的关键背景。

**「对开发者与合作方的直接影响」** 华为所报的超过 1 亿台终端为希望覆盖华为生态的开发者或厂商提供了一个可量化的潜在用户规模，应在上架或适配时覆盖 HarmonyOS 5、6、7 并做相应的兼容性测试；同时可评估是否采用已被合作伙伴集成的那些创新能力（报道提到被 1600 余款应用调用）。由于这些数字为公司自报，开发者和合作方在投入大量工程资源或商业化前，应优先核实目标用户活跃度与具体机型分布以评估回报。

**标签**: `#operating-systems`, `#mobile`, `#open-source`, `#ecosystem`, `#developer-community`

---

<a id="item-tech-news-14"></a>
### [神舟二十四号将于 11 月 25 日发射 首次含巴基斯坦航天员](https://www.news.cn/20261124/3b116eb35c404cd7b897b23a50099b5b/c.html) ⭐️ 7.0/10

中国载人航天工程在酒泉宣布，神舟二十四号瞄准 11 月 25 日 8 时 18 分发射，乘组由汤洪波、武毅和巴基斯坦航天员穆罕默德·齐尚·阿里组成，汤洪波任指令长。飞船将采用 3.5 小时自主快速交会对接，目标为天和核心舱前向端口；这是中国载人航天工程首次含外籍航天员，阿里将成为首位到访“天宫”的外籍航天员。阿里计划在完成访问后与张志远、黎家盈一同乘神舟二十三号返回。

telegram · zaihuapd · 11月24日 04:08

**「背景与技术概念」** 报道中的“天宫”指的是中国在轨空间站，神舟二十四号将与天和核心舱的前向端口实施对接。文中提到的“3.5 小时自主快速交会对接”是指航天器在发射后利用自身导航和推进系统，在数小时内完成接近并与目标对接的程序，与需要数日逐步调整的传统交会方案不同。

**「直接影响」** 这一安排使巴基斯坦成为首个向中国空间站派出访客航天员的国家，且阿里的飞行被安排为短期访问——他将在神舟二十三号上返回，这对双方在训练、任务对接和后勤支持方面提出了具体协调要求。对于空间站运行方而言，本次任务将按 3.5 小时自主快速交会对接的时间表执行，相关地面跟踪、交会对接监控和资源分配需配合该快速交会弧线。

**标签**: `#spaceflight`, `#aerospace`, `#China`, `#international-cooperation`, `#launch`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [vLLM 对 ERNIE 5.5 Flash 的 Day‑0 支持](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 8.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** 作者指出 ERNIE 5.5 Flash 是一个面向推理成本优化、支持 1M 上下文的稀疏 MoE 模型（280B 参数、每 token 激活 14B），传统逐算子实现会因大量中间张量和内存往返而成为长上下文推理的瓶颈。

**「方案」** 为了解决这些瓶颈，vLLM 与 ERNIE 团队通过一组工程措施实现了 Day‑0 支持：针对新结构（VHA、Multi‑Router Latent MoE、MultiMax 等）设计了多种融合内核，作者称这些内核比逐算子实现快约 1.55×–6.53×；FlashIndexer 用基于 token 的动态头路由加阈值预筛减小索引开销，在 1M 上下文下文档称可达约 1.4×（40%）加速；量化方面将路由后的专家权重做成 MXFP4（W4A8，使用量化感知训练以保持无损），其他权重与 KV 缓存采用 FP8，DSpark 草案模型做多阶段投机解码（最多草拟 7 token，作者报告平均接受长度&gt;4.0），并配合张量并行、预填/解码拆分与 KV 下溢到 CPU 的工程手段提升端到端吞吐。最后，部署路径是一个独立的 vLLM‑ERNIE 插件（兼容 vllm==0.32.0，通过 vllm.general\_plugins 自动注册、按需导入），无需维护 fork 或专用镜像，模型特定修复和特性可随插件下发。

**「启示」** 作者的结论是：通过针对性核融合、轻量路由器索引器、量化感知训练与投机解码的组合工程，vLLM 能在发布日以插件方式高效支持 ERNIE 5.5 Flash，从而把模型架构创新快速转化为可部署的推理加速。

**标签**: `#inference-acceleration`, `#kernel-fusion`, `#quantization`, `#sparse-attention`, `#vLLM-plugin`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [威廉姆斯：需“逐步”进一步行动以将通胀降至 2%](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 8.0/10

纽约联储行长约翰·威廉姆斯表示，需要在一段时间内继续采取行动以将通胀降回 2%，并预测通胀在 2027 年接近 2%、2028 年达到 2%（威廉姆斯的预测）。市场已完全计入 12 月 8–9 日联邦公开市场委员会可能把当前 3.75%–4.00%的联邦基金目标区间上调 0.25 个百分点（市场预期）。

rss · CNBC Finance · 11月23日 21:02

**「背景」** 在美联储将于 12 月 8–9 日召开 FOMC 会议、市场普遍定价可能在 12 月加息 25 个基点的背景下，纽约联储行长约翰·威廉姆斯在纽约表示，通胀“将在 2027 年更接近”美联储的 2%目标，并称需要“随时间”采取行动以确保最终回到该目标。

**「影响」** 投资者和债券市场会根据威廉姆斯的“渐进式”措辞与市场对 12 月加息的定价调整利率预期，进而影响债券收益率和短期借贷成本。

<details><summary>参考链接</summary>
<ul>
<li>Fed&#x27;s John Williams indicates higher interest rates likely &#x27;over ... - CNBC</li>
<li>New York Fed&#x27;s Williams says the Fed must act &#x27;over time&#x27; to bring inflation ...</li>
<li>Williams keeps December Fed hike in play as inflation seen above 2 ...</li>

</ul>
</details>

**标签**: `#monetary policy`, `#Federal Reserve`, `#interest rates`, `#inflation`, `#US economy`

---

<a id="item-finance-news-2"></a>
### [英伟达恢复黄仁勋为 CEO 引发美股反弹](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo-market-rally.html) ⭐️ 8.0/10

英伟达宣布恢复黄仁勋为首席执行官后，CNBC 报道美股周一出现大幅反弹。此前自 2026 年 11 月 12 日初次公布该消息至上周五，标普 500 累计下跌逾 9%（实际结果）。

rss · CNBC Finance · 11月23日 18:00

**「背景」** 英伟达在 11 月 12 日宣布免去首席执行官黄仁勋后，到上周五标普 500 已累计下跌逾 9%；黄仁勋被报道复职后周一触发了救援性反弹。

**「影响」** 专家表示此事短期内可能止住近期的普遍抛售并重振以英伟达为核心的 AI 相关股票，但数据中心审批、超大云服务商资本支出是否见顶以及国会可能的审查等风险仍未消除，可能继续影响相关公司和投资者情绪。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.m.wikipedia.org/wiki/Nvidia">Nvidia - Wikipedia</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#Market rally`, `#AI trade`, `#Equities correction`, `#CEO reinstatement`

---

<a id="item-finance-news-3"></a>
### [Anthropic IPO 引发抛售，冲击中国 AI 上市计划](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 8.0/10

Anthropic 的创纪录 IPO 引发全球科技股抛售，报道称中国科技股自 2026 年 6 月底以来累计蒸发 1.7 万亿美元（报道的累计市值损失）。

telegram · zaihuapd · 11月23日 09:31

**「背景」** 据 Bloomberg 报道，Anthropic 此前完成规模为 1195 亿美元的创纪录 IPO，该发行被指触发了全球科技股抛售，使中国科技股自 6 月底以来累计蒸发约 1.7 万亿美元市值。

**「影响」** 报道称，这波抛售已使 DeepSeek、月之暗面和阶跃星辰等在筹备或考虑上市的中国 AI 公司面临估值承压与 IPO 窗口收窄的风险，可能影响这些公司的发行条件和潜在投资者。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bloomberg.com/">Bloomberg - Business News, Stock Markets, Finance, Breaking &amp;...</a></li>

</ul>
</details>

**标签**: `#AI IPO`, `#market selloff`, `#China tech IPOs`, `#investor sentiment`

---

<a id="item-finance-news-4"></a>
### [上海地铁票价时隔 21 年首次调整](https://weibo.com/1699432410/5368461393397183) ⭐️ 8.0/10

上海地铁时隔 21 年首次调整票价，新华社报道新起步价为 3 元（起步里程 0–4 公里）。新票价及配套优惠自 12 月 1 日起实施，计次票将于 11 月 26 日开售。

telegram · zaihuapd · 11月23日 10:45

**「背景」** 上海地铁自 1993 年开始运营，是中国大陆重要的城市轨道交通系统；据报道，本次是时隔 21 年的首次票价调整。

**「影响」** 高频出行者可通过推出的计次票（35/45/60/90 次，定价 190/210/270/390 元）和同一支付渠道当月累计满 90 元后 9 折的优惠，部分抵消涨价影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://zh.wikipedia.org/wiki/%E4%B8%8A%E6%B5%B7%E5%9C%B0%E9%93%81%E8%BD%A6%E7%AB%99%E5%88%97%E8%A1%A8">上海地铁 车站列表 - 维基百科，自由的百科全书</a></li>

</ul>
</details>

**标签**: `#public-transport`, `#fare-change`, `#Shanghai`, `#consumer-impact`, `#policy-change`

---

<a id="item-finance-news-5"></a>
### [SpaceX 向 Anthropic、Google 出租算力，报道称月入数十亿美元](https://www.nytimes.com/2026/11/23/business/elon-musk-ai-anthropic-google.html) ⭐️ 8.0/10

据《纽约时报》报道，自今年 5 月起，SpaceX 开始每月向 Anthropic、Google 等公司出租大规模数据中心算力。报道称 SpaceX 因此“月入数十亿美元”（美元、报道基于三名匿名知情人士），并称马斯克在 8 月将部门群聊改名为“Sell compute because we can&\#x27;t compete”。

telegram · zaihuapd · 11月24日 02:06

**「背景」** 据报道，自今年 5 月起 SpaceX 开始向 Anthropic 和 Google 出租其数据中心算力；8 月，马斯克 reportedly 将工程师群聊改名为“Sell compute because we can&\#x27;t compete”，并警告浪费 GPU 的员工将被要求离开，相关细节来自匿名消息和社交媒体转述，仍有不确定性。

**「影响」** 如果报道属实，这可能把 SpaceX 从内部 AI 研发转向为大型 AI 训练算力的外部供应商，从而改变云基础设施的供需并直接影响 AI 公司和云服务市场（依据同一报道）。

<details><summary>参考链接</summary>
<ul>
<li>Grace Kay (@graceihle) / X</li>
<li>Mark Hogan (@MB_Hogan) / X</li>

</ul>
</details>

**标签**: `#SpaceX`, `#AI infrastructure`, `#Cloud compute`, `#Elon Musk`, `#Anthropic/Google`

---