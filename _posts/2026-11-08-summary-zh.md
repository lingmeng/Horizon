---
layout: default
title: "Horizon Summary: 2026-11-08 (ZH)"
date: 2026-11-08
lang: zh
---

> 从 39 条内容中筛选出 18 条重要资讯。

---

**科技新闻**
1. [Claude Code 本地设置被指致 1,122 文件泄密](#item-tech-news-1) ⭐️ 8.0/10
2. [Coldframe：超市冷柜控制器诱饵](#item-tech-news-2) ⭐️ 8.0/10
3. [Asahi Linux 进展报告 7.3](#item-tech-news-3) ⭐️ 8.0/10
4. [内蒙古 Galaxy AI 机房实地报道](#item-tech-news-4) ⭐️ 8.0/10
5. [Claude Code 泄露登录邮箱问题](#item-tech-news-5) ⭐️ 8.0/10
6. [苹果披露人形机器人系统 HALO](#item-tech-news-6) ⭐️ 8.0/10
7. [GitHub Rubicon：支持每秒 7200 次推送](#item-tech-news-7) ⭐️ 8.0/10
8. [微软研究院“AI Frontiers”小组疑似结束](#item-tech-news-8) ⭐️ 7.0/10
9. [MaxxBench 质疑 DeepSWE 得分的稳健性](#item-tech-news-9) ⭐️ 7.0/10
10. [Mac 上疑含未记录的家庭成员分类守护进程的报告](#item-tech-news-10) ⭐️ 7.0/10
11. [Discord 的 Windows 11 客户端内存大幅下降](#item-tech-news-11) ⭐️ 7.0/10
12. [Need for Speed Underground 2 浏览器多人移植](#item-tech-news-12) ⭐️ 7.0/10
13. [土耳其用 TraceART 与法医技术追回文物](#item-tech-news-13) ⭐️ 7.0/10
14. [法院裁定 Anthropic 须就 Claude Max 用量宣传应诉](#item-tech-news-14) ⭐️ 7.0/10
15. [美议员呼吁立法禁止 AI 递归自我改进](#item-tech-news-15) ⭐️ 7.0/10

**财经新闻**
1. [软银与 ABB 拟分拆中国业务以挽救被叫停的机器人收购](#item-finance-news-1) ⭐️ 8.0/10
2. [全国启动覆盖 3.35 万座寺院的财务大检查](#item-finance-news-2) ⭐️ 8.0/10
3. [伯克希尔第三季度回购加速至$9.6 billion](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Claude Code 本地设置被指致 1,122 文件泄密](https://apiiro.com/blog/coding-agents-leaking-secrets-github-dont-ask-again) ⭐️ 8.0/10

报道称，在公共 GitHub 仓库中有 1,122 个文件包含了由 Claude Code 本地设置和“Don&\#x27;t Ask Again”批准记录暴露的秘密（例如密码或密钥）。报告指出，问题出现在开发者把本应保留为本地的 .claude/settings.local.json 或整个 .claude 文件夹手动创建并提交到版本库后，其中包含的经批准的命令里有秘密值被公开。Claude 团队的评论称历史上 Claude Code 并未进行秘密清理（secret scrubbing），团队正在调查可能的防护措施；同时有人指出仅按下“Don&\#x27;t Ask Again”并不会自动把秘密公开，关键在于这些本地文件被提交到代码仓库。 

hackernews · shmulc · 11月7日 20:45 · [社区讨论](https://news.ycombinator.com/item?id=50407882)

**「背景说明」** AI 编码代理能在开发者环境中自动执行任务并在本地保存权限批准与运行命令的设置；这类代理（例如为编码场景设计的模型和工具）常在开发机上保有本地配置以减少交互。Claude Code 的本地设置文件（例如 .claude/settings.local.json）被设计为应当留在本地并被自动加入 .gitignore，只有当用户手动将这些设置文件提交到代码仓库，并且这些设置里包含已批准的命令文本中直接写入了密钥或密码时，才会把秘密暴露到公共仓库；单纯点击“不要再次询问（Don&\#x27;t Ask Again）”本身并不会自动把密码写入仓库。

**「对开发者的具体影响」** 受影响的开发者和组织应将仓库中是否包含 .claude 或 settings.local.json 等本地设置作为审计目标，并在发现已泄露凭据时立即撤销/轮换这些凭据；同时应从版本库中移除此类文件并将 .claude 加入 .gitignore。鉴于 Claude Code 历来未进行自动秘密清理，用户不能仅依赖代理工具来防止凭据泄露，应改为使用密码管理器、按需提取凭据或将敏感操作限制在隔离环境中以降低风险。 

**「社区讨论要点」** 部分评论认为标题易导致误解——真正的问题是开发者把本应本地的 .claude 文件提交到仓库并在这些提交中包含了秘密，而不是单纯按下“Don&\#x27;t Ask Again”键；Claude 团队确认没有自动清理秘密并表示会着手改进。社区提出的缓解办法包括不要将本地设置提交、使用密码管理器并通过 CLI 动态提取凭据、在隔离的临时 VM 中运行代理，以及对已泄露密钥进行轮换。 

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.jetbrains.com/ai/2026/10/mellum2-1-gets-to-work-a-fast-open-model-for-coding-agents/">Mellum2.1 Gets to Work: A Fast Open Model for Coding Agents - The...</a></li>

</ul>
</details>

**标签**: `#secrets`, `#security`, `#AI-agents`, `#github`, `#developer-tools`

---

<a id="item-tech-news-2"></a>
### [Coldframe：超市冷柜控制器诱饵](https://github.com/hedgerow-dev/coldframe) ⭐️ 8.0/10

Coldframe 是作者发布的开源 Python 单文件 honeypot，模拟超市制冷控制器的 Web 界面，分别扮演 Danfoss AK‑SM 800A 与 Dixell XWEB。作者声称通过比对 Shodan 上的真实设备记录来复刻指纹（包括 TLS/证书字段、响应头顺序——Danfoss 人设发送与真实设备相同的 nginx 头顺序；Dixell 人设不返回 Server 头并将页面填充到 8,202 字节）、并可识别若干已知漏洞的利用尝试（包括 CVE‑2025‑41450 及其他 Danfoss/XWEB 漏洞），还能记录提交的“当日代码”是否正确。默认登录会打开一个假的店铺仪表盘（例如除霜按钮），以便观察攻击者的第二步行为；作者已上线两个实例运行约一天，迄今仅记录到通用扫描器和 Shodan 的爬虫。

hackernews · hedgerow-dev · 11月7日 17:27 · [社区讨论](https://news.ycombinator.com/item?id=50406292)

**「蜜罐与制冷控制器被指纹化的背景」** 蜜罐是故意伪装成易受攻击设备以吸引、观察并记录入侵者行为的系统，常被用于工业控制系统（ICS/OT）的安全研究。作者在原帖中说明，许多超市制冷控制器已被互联网上的扫描器（例如 Shodan）指纹化，因此仿真这些设备可以让研究者看到攻击者在面对看起来真实的界面时会如何行动。

**「影响与建议」** 因为 Coldframe 能记录漏洞利用尝试并展示登录后的后续操作，它为工业控制系统/OT 安全研究人员和防御者提供了观察攻击者行为（包括是否尝试 CVE‑2025‑41450 的利用链及“当日代码”校验）的手段；但作者依赖 Shodan 记录来构建指纹，说明在部署或用其作结论前应与实物设备指纹比对验证，且不应单靠此类诱饵替代补丁、网络分段或正式入侵检测。

**「社区讨论要点」** 有人对依赖 Shodan 数据构建指纹表示怀疑，建议用真实或已知未被篡改的设备做对照；作者与评论者也提到相关目标（例如血液库或缺乏安全团队的超市）可能更具影响力，但这些为观点而非已证实的事件。

**标签**: `#honeypot`, `#industrial-control-systems`, `#security-research`, `#open-source`

---

<a id="item-tech-news-3"></a>
### [Asahi Linux 进展报告 7.3](https://asahilinux.org/2026/11/progress-report-7-3/) ⭐️ 8.0/10

Asahi Linux 发布了 7.3 进展报告，概述了针对 Apple Silicon 的持续开发工作与已知缺口。报告强调项目在发行节奏上有进展——团队能够在上游 Fedora 发布当天推出 Fedora Asahi Remix——同时仍有关键硬件支持问题未解决（例如 USB‑C 外接显示器支持）。报告还指出存在针对项目采用的宽松许可进行利用、意图接管并商业化的尝试，以及驱动和图形子系统的持续工程工作。

hackernews · ackyshake · 11月7日 05:20 · [社区讨论](https://news.ycombinator.com/item?id=50401867)

**「背景与先前进展」** Asahi Linux 是将主流 Linux 移植到 Apple Silicon（Apple 的 M 系列 SoC）上的社区项目，靠一系列进度报告和上游补丁跟进内核与驱动的兼容性与合并状况。此前项目已将对 M3 系列机器的支持合并进安装器，使 Asahi 官方支持搭载 M3 SoC 的 Mac，这为在接下来的 Linux 7.3 开发周期中继续进行上游提交和驱动工作提供了直接的前置条件。

**「影响与建议」** 对终端用户而言，外接显示器（USB‑C 显示）尚未可靠支持，这意味着需要外接显示功能的用户在安装之前应先核实其具体机型和接口的兼容性。对贡献者和发行方而言，报告中关于被滥用许可进行商业化尝试的陈述提示项目应审查许可、分发和治理策略以防止被替代或滥用。

**「社区反馈要点」** 评论者 alsetmusic 对能在 Fedora 上游发布当日推出 Fedora Asahi Remix 表示欢迎并称其为里程碑式的操作；alentred 表示 USB‑C 外接显示支持是其决定是否使用 Asahi 的阻塞点。另有评论者（aroman）对报告中提到的“利用宽松许可接管项目并商业化”的说法表示关切并质疑许可选择，开发者（ADevWithAnIdea）则提到其他相关努力（例如声称已在另一个项目上实现 Vulkan 1.4、M4/M5 支持并推进休眠恢复）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://asahilinux.org/2026/11/progress-report-7-3/">Progress Report: Linux 7.3 - Asahi Linux</a></li>
<li><a href="https://asahilinux.org/2026/09/m2-episode-1/">M2: Episode 1 (or, Asahi Linux on M3)</a></li>

</ul>
</details>

**标签**: `#asahi-linux`, `#apple-silicon`, `#linux`, `#device-drivers`, `#open-source`

---

<a id="item-tech-news-4"></a>
### [内蒙古 Galaxy AI 机房实地报道](https://newsletter.semianalysis.com/p/we-visited-chinas-stargate-in-inner) ⭐️ 8.0/10

SemiAnalysis 记者在内蒙古乌兰察布的 Galaxy 机房实地报道了一个大规模中国 AI 数据中心园区：该园区规划最高可达 800MW IT 容量（为规划规模），其首个 120MW 阶段在不到一年的时间内交付完毕，报道称建造成本约为美国同类项目的五分之一。该园区为两家互联网巨头定制建造，位于查哈尔高新区周边，据当地报道该区约有 3 万名施工人员参与 22 个数据中心项目。机房由能源企业 Envision 控股和建设，现场展示了深度纵向一体化：厂方建设风力发电场并架设专用输电线、在园区附近有叶片工厂，并在园区内部设计集成了低压模块与 800V 供电体系、制造并部署了电池储能以平滑负载，并参与预制变电所的共同设计。

rss · Semianalysis · 11月7日 19:01

**「背景」** 大型生成式 AI 的训练与推理对电力和机架容量要求极高，因此出现了所谓的“千兆瓦级”（gigawatt-scale）AI 数据中心园区，Stargate Abilene（为 OpenAI 建设）常被用作美国同类建设的代表。SemiAnalysis 的现场报道把这一尺度放到中国内蒙古，介绍了规划至多 800MW 的 Galaxy 园区，并提到其首期 120MW 在一年内交付且据报道建造成本约为美国的五分之一，以及园区在能源与设备上的深度垂直整合，这些要点有助理解新闻中强调的规模、成本和能源一体化问题。

**「对扩容决策和技术对接的直接影响」** 这类以本地劳动力和能源一体化为核心的模式在成本和交付速度上产生明显优势，意味着在对比全球 AI 容量成本与交付节奏时，外部组织应把地区劳动力可得性、定制化电力供应与储能、一体化制造能力纳入基准和风险评估；在进行设备采购或跨境合作时，应核实类似 800V 供电架构、电池储能与预制变电所的兼容性与接入要求以避免后续集成问题。

**标签**: `#datacenter`, `#AI infrastructure`, `#China`, `#cloud`, `#industry-trends`

---

<a id="item-tech-news-5"></a>
### [Claude Code 泄露登录邮箱问题](https://github.com/anthropics/claude-code/issues/107757) ⭐️ 8.0/10

多名开发者投诉，Anthropic 的开发者工具 Claude Code 在执行联网网页搜索或发起外部请求时，可能把用户的登录邮箱嵌入请求并发送到第三方网站，从而暴露给外部接收方。Anthropic 工程师称，曾为解决模型“乱填作者名”的问题把登录邮箱放入模型上下文；据报告今年 7 月已有实例显示邮箱被发往 Wikipedia、美国证券交易委员会等站点。公司在 2.1.317 版本加入了拦截措施，但据称该拦截可被 Python 脚本绕过；Anthropic 表示计划在下一版本彻底从模型上下文移除登录邮箱。

telegram · zaihuapd · 11月7日 08:09

**「背景」** Claude Code 是 Anthropic 的编程代理，会代表用户进行网页搜索并生成像 curl 这样的 HTTP 请求。多份报告和问题追踪显示，Anthropic 曾把已登录账户的邮箱放入模型上下文以解决“乱填作者名”的问题，导致代理在构造请求时有时会把该邮箱写入 User-Agent 等请求头并发送给第三方；Anthropic 已在 2.1.317 中加入拦截且表示计划从上下文移除邮箱，但有分析称现有拦截能被绕过。

**「影响与建议」** 受影响的开发者的登录邮箱可能会被第三方网站接收并用于垃圾邮件或钓鱼活动——已有用户报告因此收到大量诈骗邮件；在厂商完全移除上下文字段并发布不可绕过的修复之前，受影响用户应避免在敏感场景使用 Claude Code、检查是否有同一邮箱被其他服务共享并考虑更换或使用专用登录邮箱，并审查或暂停会发起外部请求的自动化脚本以防止绕过当前拦截措施。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/anthropics/claude-code/issues/107757">Bug Report: Privacy violation in User-Agent header · Issue ...</a></li>
<li><a href="https://dev.to/frankchu/8-leaks-pass-anthropics-23-test-email-fix-2e66">8 leaks pass Anthropic&#x27;s 23-test email fix - DEV Community</a></li>
<li><a href="https://dev.to/axrisi/claude-code-email-in-user-agent-headers-how-it-happened-and-what-the-fix-covers-4i0p">Claude Code email in User-Agent headers: how it happened and ...</a></li>

</ul>
</details>

**标签**: `#privacy`, `#security`, `#AI-models`, `#Anthropic`, `#bug`

---

<a id="item-tech-news-6"></a>
### [苹果披露人形机器人系统 HALO](https://weibo.com/1642634100/RqjjGllvw) ⭐️ 8.0/10

苹果研究团队据称于 11 月 4 日在预印本平台 arXiv 提交论文，披露名为 HALO 的三层人形机器人自主控制系统，并在宇树 G1（Yushi G1）机器人上将仿真学到的动作迁移到陌生真实房间中验证。HALO 的三层架构为：上层使用千问 Qwen3.6-35B-A3B 进行任务编排，中层使用千问 Qwen3.5-2B 生成动作指令，底层为经过强化学习训练的动作跟踪器。作者还报告已公开用于数据生成、模型训练与部署的代码与数据，但这些发布和性能细节以论文与仓库为准，本文未进行独立验证。

telegram · zaihuapd · 11月7日 13:35

**「必要背景」** 千问（Qwen）是阿里巴巴的一系列大语言模型；Qwen 3.6-35B-A3B 是基于 3.6 系列的 35B 参数、Mixture‑of‑Experts 变体并继承更大上下文能力，而 Qwen 3.5-2B 则是规格更小的版本，经常用于对延迟或计算预算更敏感的任务。理解 HALO 的三层设计需要把这类“高层用大模型编排任务、中层用较小模型生成动作、底层用强化学习训练的跟踪器执行低级控制”的分层思路当作先验概念来阅读论文中的实验与部署细节。

**「影响与后续注意事项」** 如果论文中关于代码、数据与模型公开的声明属实，研究者和工程团队将能够复现并在物理人形平台上评估该 LLM+RL 的 sim-to-real 管线；复现工作将取决于能否获取所需的 Qwen 模型权重和具体训练/部署脚本。建议感兴趣的读者查验 arXiv 论文与公开仓库中的许可证、依赖项与访问要求，因为第三方模型许可或权重访问限制会直接影响可复现性和部署路线。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://pikabu.ru/story/kak_polzovatsya_qwen_v_2026_godu_neyroset_qwen_36_code_i_api_dlya_rabotyi_i_biznesa_13917165">Как пользоваться Qwen в 2026 году: нейросеть Qwen 3 . 6 , Code...</a></li>
<li><a href="https://huggingface.co/empero-ai/Qwen3.8-35B-A3B-Distill">empero-ai/ Qwen 3 .8- 35 B - A 3 B -Distill · Hugging Face</a></li>

</ul>
</details>

**标签**: `#robotics`, `#sim-to-real`, `#LLM-for-robotics`, `#reinforcement-learning`, `#Apple`

---

<a id="item-tech-news-7"></a>
### [GitHub Rubicon：支持每秒 7200 次推送](https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/) ⭐️ 8.0/10

GitHub 推出代号 Rubicon 的新 Git 存储架构，面向大量 AI 智能体并发操作单个仓库的场景。Rubicon 将 Git 对象存入 Azure Blob Storage，引用状态由 Ref‑CAS 管理，并以“虚拟副本”处理读写、由后台节点压缩数据包；GitHub 在内部测试中报告支持 5,000 个并发智能体并在峰值达到每秒 7,200 次推送。该架构目前处于有限私有预览，以上性能为 GitHub 报告的内部测试结果，而非第三方验证或广泛可用的生产 SLA。

telegram · zaihuapd · 11月7日 14:12

**「背景说明」** Git 仓库由对象（如 commits、blobs、trees）和引用（refs）构成，服务器端通常将对象打包为 pack 文件以减少存储与传输开销；理解这些分离的存储与索引方式有助于评估架构改动的意义。Rubicon 的关键实现把 pack 数据存放在 Azure Blob Storage、用 Ref‑CAS 管理 refs 与 pack 清单，并通过仅缓存状态的虚拟副本来处理读写与并发，这些技术细节是理解其并发和扩展性主张的前提。 

**「影响与建议」** 对大型组织、需要高并发推送的 CI/CI/CD 流程以及以大量 AI 智能体并行写入为特征的工作负载，Rubicon 的设计表明可能显著提高推送吞吐量和并发能力；但因为其依赖 Azure Blob Storage 并仍在私有预览阶段，相关团队应在生产迁移前跟踪可用性公告、在预览环境中进行兼容性和延迟测试，并评估与自托管或其他云存储策略的数据驻留与集成影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/">Inside GitHub &#x27;s new Git storage architecture - The GitHub Blog</a></li>

</ul>
</details>

**标签**: `#git`, `#scalability`, `#distributed-storage`, `#ai-agents`, `#infrastructure`

---

<a id="item-tech-news-8"></a>
### [微软研究院“AI Frontiers”小组疑似结束](https://hunch.net/?p=13764006) ⭐️ 7.0/10

社区帖子报告称，微软研究院（Microsoft Research，MSR）负责基础 AI 研究的“AI Frontiers”小组已结束运作。该信息来自社区来源（Hacker News 帖子），目前没有微软方面的官方确认或独立核实。若属实，这表明 MSR 在支持探索性、基础 AI 方法上的内部组织安排发生了变化，但现有公开证据未列明受影响的项目、人员或具体时间线。

hackernews · srean · 11月7日 18:02 · [社区讨论](https://news.ycombinator.com/item?id=50406563)

**「背景说明」** Microsoft Research 的 AI Frontiers 曾是 MSR 下的一个研究小组，官方页面说明该小组长期专注于高效语言模型与“agentic”系统等前沿基础研究。近期一位在该小组工作的研究者在其博客上宣布“AI Frontiers 已结束”，这篇博文成为有关该组织变动的直接来源。

**「可能的直接影响与建议动作」** 如果该小组确实解散，受影响的后果可能包括相关基础研究项目的缩减或重组、职位变动以及对非 transformer 探索性方法的内部资助减少；因此受影响的研究人员、合作者和招聘候选人应直接向微软或其在研联系人求证当前团队状态、保存并备份工作记录，并在必要时准备寻找替代资助或合作者。鉴于信息来源为社区报道，外部合作方在调整长期计划前应等待微软的正式声明或通过官方渠道确认细节。

**「社区讨论要点」** 评论主要表达两类观点：一是担忧大型科技公司当前更加优先推进以规模化 transformer 为主的路线，从而压缩对探索性基础研究的支持；二是对 MSR 过去“做出好研究就会得到支持”的文化及其可能被侵蚀表示失望。以上为评论者的意见与观察，并非独立证实的事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.microsoft.com/en-us/research/lab/ai-frontiers/">Microsoft Research AI Frontiers - Microsoft Research</a></li>
<li><a href="https://hunch.net/?p=13764006">The End of AI Frontiers – Machine Learning (Theory)</a></li>

</ul>
</details>

**标签**: `#microsoft-research`, `#ai-research`, `#industry-news`, `#organizational-change`

---

<a id="item-tech-news-9"></a>
### [MaxxBench 质疑 DeepSWE 得分的稳健性](https://maxxbench.unlap.ai/research/why-maxxbench/) ⭐️ 7.0/10

MaxxBench 的一篇分析（并在 Hacker News 上引发讨论）质疑了 DeepSWE 基准给出的高得分的稳健性，作者通过改变任务说明（task spec）来测试分数的泛化性，发现分数在微小变动下显著波动。讨论中还指出不同模型族表现差异明显（较小的模型在若干变体上“塌缩”更严重），并且报告了 DeepSWE 可能存在的基准或 API 行为问题（包括对“max 模式”行为的疑问）。这些结论来自独立分析和社区评价，而非 DeepSWE 官方的修正或厂商声明，所以目前应被视为可疑点与方法论建议而非已修复的缺陷。 

hackernews · antiuniverse · 11月7日 17:19 · [社区讨论](https://news.ycombinator.com/item?id=50406222)

**「背景」** DeepSWE 是用于评估大模型代码生成能力的一套基准测试；MaxxBench 则基于 DeepSWE，针对其中 89 个任务在指令或起始代码上做小幅变异来检验模型对任务规范变化的泛化能力。MaxxBench 在保持中位补丁增长很小（约 17 行、约 3.5%）的前提下，观察到原本在 DeepSWE 上得分接近的模型在这些变体上出现显著分歧（例如一组模型在变体上分别为 76.4% 和 53.4%，GPT‑6 Astra 与 Opus 5 在变体上分别为 71.9% 与 63.5%），因此被用来探测 DeepSWE 分数是否反映对真实变化的鲁棒性或仅是对固定规范的拟合。

**「对实践者的具体影响」** 对依赖 DeepSWE 或单一分数做模型选择的团队而言，直接后果是应避免把单次基准得分当作确定性证据：需要在不同任务说明、评分模式（例如非“max 模式”）和输入变体上做敏感性测试，以检验模型是否真正泛化；此外，应警惕小体量模型可能被当前基准设置系统性低估，并把基准实现和 API 行为纳入 QA 范围以寻找潜在错误。

**「社区讨论要点」** 评论者认为最有用的方法是简单地按参数变动来检验基准泛化性（这是多位评论者共同建议的第一阶检验）；有人报告观察到较小模型在多种变体上“塌缩”更严重，也有人指出 DeepSWE 存在若干可疑行为并建议不要盲用“max 模式”，同时有观点把问题归因于训练时环境多样性不足而非直接针对基准作弊。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://daily.dev/posts/maxxbench-nice-deepswe-score-but-is-it-true--ue9ulip60">MaxxBench – &quot;Nice DeepSWE score. But is it true?&quot;</a></li>
<li><a href="https://maxxbench.unlap.ai/research/why-maxxbench/">Introducing MaxxBench: Benchmarking Task Adaptation and ...</a></li>
<li><a href="https://kongchang.com/en/articles/maxxbench-questions-deepswe-leaderboard-is-the-impressive-score-genuine">MaxxBench Questions DeepSWE Leaderboard: Is the Impressive ...</a></li>

</ul>
</details>

**标签**: `#benchmarks`, `#LLM-evaluation`, `#robustness`, `#model-comparison`, `#AI-systems`

---

<a id="item-tech-news-10"></a>
### [Mac 上疑含未记录的家庭成员分类守护进程的报告](https://8rank.ai/game/apple-intelligence-personal-knowledge-graph) ⭐️ 7.0/10

一篇由 Hacker News 社区讨论并由 8rank.ai 的作者宣称的研究指出，自 2022 年以来的 Mac 设备上可能存在未在文档中披露的后台守护进程（作者称为“一对守护进程”），其目的是在本地构建个人知识图谱并进行家庭成员/关系分类。该说法来自社区汇报和研究作者的陈述，涉及对联系人、通信、位置和活动等信号的聚合与建模，但这一行为和守护进程的具体实现、名称或数据流向尚未被独立验证或由 Apple 官方确认。

hackernews · infwhispers · 11月7日 09:46 · [社区讨论](https://news.ycombinator.com/item?id=50403097)

**「背景与相关概念」** “个人知识图谱”在设备端指将关于用户及其联系人、人物关系、通信频率、位置和活动等信息结构化为可查询的模型，帮助消歧、完成自然语言指令（例如“给 James 发短信”时识别具体对象）和生成个性化建议。现代移动与桌面平台通常在本地运行机器学习模型，并在照片的人脸识别、联系人聚合以及日历/提醒等上下文中使用类似的本地数据表示来支持离线助理功能与隐私保护设计。

**「直接影响与建议动作」** 如果属实，受影响的是运行 macOS 的个人用户与受管理的企业/教育设备，因为未经记录的后台模型可能在用户不明确同意的情况下处理敏感关系与行为数据。建议的可行动作包括：审计设备以查找异常或未知守护进程（例如用活动监视器和系统日志）、检查并收紧与 Siri、照片、联系人、日历和系统分析相关的隐私设置、对受管设备制定临时策略以限制或监控可疑服务，并向 Apple 询问官方说明或补丁。鉴于当前证据有限，组织应先将其视为潜在隐私风险并采取保守的运维与合规措施，直至有进一步验证或官方澄清。

**「社区观点摘录」** 评论中有人指出若该功能为显式的、可选择的本地功能则具有实用价值，但也有人表达了对长期被记忆与社会影响的疲惫与担忧；另有评论者以 Photos、Calendar 等已有本地识别功能为背景，认为此类关系建模并不令人惊讶；研究作者在讨论中回应并提供了后续研究以供询问与澄清。以上均为社区意见而非经证实的事实。

**标签**: `#privacy`, `#apple`, `#macos`, `#on-device-ml`, `#personal-data`

---

<a id="item-tech-news-11"></a>
### [Discord 的 Windows 11 客户端内存大幅下降](https://www.windowslatest.com/2026/11/06/every-windows-11-app-should-kill-electron-and-discord-just-showed-why-no-starting-screen-and-70-less-ram-even-with-two-accounts-signed-in/) ⭐️ 7.0/10

据报道，Discord 的新版 Windows 11 客户端去掉了启动画面并在运行时显著减少内存占用——文章声称在双账号同时登录的情况下内存使用约降低 70%。该报导来自第三方新闻汇总与社区讨论（Hacker News），但原文未提供详细的测量方法、版本号或独立验证数据。虽然这是一个对桌面应用框架选择有直接参考价值的性能改进案例，但现有证据不足以证明这是对 Electron 通用问题的彻底解决或可被普遍复刻的最佳实践。

hackernews · thunderbong · 11月7日 11:11 · [社区讨论](https://news.ycombinator.com/item?id=50403507)

**「背景」** Electron 是一种用网页技术（HTML/CSS/JavaScript）打包成跨平台桌面应用的常见选择，其价值在于用一套代码支持多个操作系统，但也长期被诟病为内存占用和启动开销较高。Discord 近年来已着手将桌面客户端从 Electron 迁移到基于 Rust 的原生实现，已有报道称其 Windows 11 早期构建内存使用降至约 290 MB，这一先前开发能解释为什么人们会注意到本次有关更快启动和大幅降低内存占用的对比。

**「影响与建议」** 对工程师和产品团队而言，这一报告表明如果内存占用和启动延迟是首要约束，值得对现有 Electron 应用做基准测试并评估针对 Windows 11 的本地实现或轻量框架替代方案；团队应在决策前测试相同使用场景（例如多账号、语音/视频模块）以确认真实收益。兼容性与可达性风险也应一并评估，因为迁移可能影响输入法、无障碍支持以及多平台代码复用的开发效率。

**「社区讨论要点」** 讨论中有人指出 Electron 的核心价值是用一套 web 技术快速支持多平台，资源占用是早有的抱怨；另有意见提醒 Discord 在移动端的框架选择历来多变，不能简单当作模型。有评论提到 Electron 在无障碍和非英语输入法方面表现良好，而替代的原生或 Rust 工具链在这些领域可能还需时间成熟。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wccftech.com/discord-is-ditching-electron-for-rust-with-early-windows-build-using-just-290mb-of-ram/">Discord Is Ditching Electron For Rust, With Early Windows Build...</a></li>

</ul>
</details>

**标签**: `#electron`, `#desktop`, `#performance`, `#discord`, `#windows-11`

---

<a id="item-tech-news-12"></a>
### [Need for Speed Underground 2 浏览器多人移植](https://nfsu2.xyz/) ⭐️ 7.0/10

一位非官方团队将《Need for Speed: Underground 2》移植到浏览器并加入多人在线功能，当前可在 nfsu2.xyz 体验。该项目通过网页仿真与现代 Web API（报道中提到 WebGPU）在浏览器内运行，展示了用 WebGPU 和逆向/仿真技术恢复中期 2000 年代 PC 游戏的可行性，但实现细节、授权状态与长期可用性未经官方许可或独立验证。社区报告在某些平台（例如 Linux 上的 Chromium）需要启用不安全的 WebGPU 标志才能运行，并指出项目可能属于未授权/弃置软件，存在被下架的风险。

hackernews · fluxusars · 11月7日 09:36 · [社区讨论](https://news.ycombinator.com/item?id=50403052)

**「背景说明」** 该项目将 Need for Speed: Underground 2 的 PC 版本重新编译为 WebAssembly，并使用 WebGPU 在浏览器中渲染，从而能在现代浏览器运行原始的游戏逻辑与图形。项目通过自建服务器实现在线多人功能（在自由漫游中可见其他玩家、可加入房间或组队），并有报道指出在某些 Linux/Chromium 环境下需启用不安全的 WebGPU 选项以获得兼容性。

**「影响」** 玩家现在可以无需原始零售环境，通过浏览器跨平台与朋友联机重玩这款老游戏，但因为项目未经版权方授权，社区普遍预期可能会面临版权投诉和下架；使用者应准备应对临时不可用，并注意部分平台需要启用实验性或“不安全”的 WebGPU 功能才能运行。评论中也有人提醒，不应向未获授权的项目捐款，保存与复刻者应考虑授权与长期归档策略。

**「社区讨论要点」** 评论者普遍表现出怀旧与惊讶，报告包括在手机上运行顺畅、多人模式带来“混乱且有趣”的体验，同时也有人警告法律风险并反对为未授权内容募捐；另有用户分享了在 Linux/Chromium 上启用 --enable-unsafe-webgpu 的实用提示以使其可用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50403052">Need for Speed Underground 2 online in the browser | Hacker News</a></li>
<li><a href="https://www.inxanitylabs.com/games/need-for-speed-underground-2-online">NFS Underground 2 Online: Browser Multiplayer , Free</a></li>
<li><a href="https://portedgames.com/need-for-speed-underground-2-browser/">NFS Underground 2 Browser Game: Play NFSU 2 Online at nfsu 2 . xyz</a></li>

</ul>
</details>

**标签**: `#browser`, `#emulation`, `#webgpu`, `#game-preservation`, `#multiplayer`

---

<a id="item-tech-news-13"></a>
### [土耳其用 TraceART 与法医技术追回文物](https://www.artnews.com/art-news/news/turkey-uses-ai-tech-100-looted-antiquities-us-1234804634/) ⭐️ 7.0/10

土耳其文化部借助名为 TraceART 的 AI 平台，结合铅同位素分析和模具形状比对，从美国追回并在伊斯坦布尔考古博物馆展出约 200 件流失文物。展品重点包括 1960 年代遭盗掘的布尔本古城青铜雕像，以及 44 件公元前 700 至 480 年的陶制建筑板。报道指出 TraceART 自 2025 年启用，扫描全球拍卖站与社交媒体以辅助识别可疑文物，但公开资料未披露该 AI 的具体匹配方法、性能指标或规模细节。土耳其当局称自 1980 年以来已追回逾 26,700 件文物。

telegram · zaihuapd · 11月7日 03:43

**「方法与工具简述」** TraceART 是一款自 2025 年起投入使用的 AI 平台，按来源报道通过扫描全球拍卖站与社交媒体上的图片来识别疑似走失文物；报道同时指出，调查通常还会辅以铅同位素分析和模具形状比对等物理取证手段以确认出土地与来源。将数字图像比对与化学或形态学鉴定结合，是近年来文物追索工作中越来越常见的做法，有助于从线上线索过渡到可用于司法或外交交涉的证据链。

**「直接影响」** 对于博物馆、拍卖行和私人藏家来说，此案例表明将机器学习驱动的图像/数据比对与铅同位素等物理法医手段结合，能提高识别与追索流失文物的成功率；持有来源不明藏品的机构应主动审查来源证据并考虑与原产国和执法机构共享高分辨率影像与元数据，以降低被追索并需遣返的风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.artnews.com/art-news/news/turkey-uses-ai-tech-100-looted-antiquities-us-1234804634/">Turkey Uses AI to Claw Back 100 Looted Antiquities from the US</a></li>
<li><a href="https://www.techtimes.com/articles/329955/20261102/turkey-deploys-ai-isotope-science-reclaim-100-looted-antiquities-us.htm">Turkey Deploys AI and Isotope Science to Reclaim 100 Looted ...</a></li>

</ul>
</details>

**标签**: `#AI for cultural heritage`, `#computer vision / image matching`, `#digital forensics`, `#artifact repatriation`

---

<a id="item-tech-news-14"></a>
### [法院裁定 Anthropic 须就 Claude Max 用量宣传应诉](https://thenextweb.com/news/anthropic-claude-max-lawsuit-ruling-usage-claims) ⭐️ 7.0/10

美国加州北区联邦法院一名法官裁定，Anthropic 须就其 Claude Max 套餐用量宣传的误导指控应诉。原告称公司在销售页宣称 100 美元和 200 美元档分别比 Pro 多用 5 倍和 20 倍，但若按周计算实际约为 3.5 倍和 6 倍；法官指出“按会话计算”的说明仅藏在销售页的两个超链接之外，而用户按月付费可合理理解为按月计算。法院允许过失虚假陈述和违约指控继续审理，但驳回了加州不正当竞争和虚假广告两项指控。

telegram · zaihuapd · 11月7日 12:44

**「前情提要」** 今年 6 月在美国加州北区曾有人对 Anthropic 提出集体诉讼，指控其 Claude Max 的 $100（标称 5×）和 $200（标称 20×）方案的用量倍数低于宣传的数值。诉状称 Max 5× 实际约相当于 Pro 的 3.5 倍、Max 20× 约为 6–8 倍，并质疑 $200 方案是否如宣传所说能比 $100 方案节省约 50%。

**「影响」** 该裁定意味着 Anthropic 必须参与后续诉讼程序并就过失虚假陈述和违约指控进行答辩，这可能引发证据交换并促使公司在销售页上更明确地标注用量计算单位（例如按月或按会话）以降低未来因计量或披露方式引发的法律风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/anthropic-faces-class-action-over-claude-max-usage-limits">Anthropic faces class action over Claude Max usage limits | AI Weekly</a></li>
<li><a href="https://runtimewire.com/article/anthropic-faces-class-action-claim-over-claude-max-20x-limits">Anthropic faces class-action claim over Claude Max 20 x limits</a></li>

</ul>
</details>

**标签**: `#legal`, `#AI companies`, `#pricing transparency`, `#product claims`

---

<a id="item-tech-news-15"></a>
### [美议员呼吁立法禁止 AI 递归自我改进](https://x.com/AlexBores/status/2118494668769878037) ⭐️ 7.0/10

美国民主党议员 Alex Bores 在一条转发的推文/电报帖中呼吁国会在今年通过法律，禁止所谓的 AI 递归自我改进（RSI），即允许 AI 自动构建下一代 AI 的能力。Bores 在帖文中援引了 OpenAI 表示计划在 2028 年 3 月实现“自动化 AI 研究员”目标、Anthropic 员工对到 2027 年底 AI 可承担约 80% 前沿模型开发工作的内部预测，以及 METR 报告中关于 AI 研发加速的证据，作为他主张立刻禁令的理由。该项表态是单方面的立法呼吁，并非已通过的法律或独立验证的结论；原帖为社交媒体/电报转发，未在来源中提供完整的底层证据或法律草案细节。

telegram · zaihuapd · 11月8日 01:30

**「何谓递归自我改进及其近期讨论」** 递归自我改进（RSI）是指 AI 系统自动设计、训练或生成下一代更强大的 AI，这一能力被认为会改变 AI 研发的瓶颈和风险格局。多家厂商与媒体已公开讨论将部分 AI 研发流程自动化的进展与时间表，Anthropic 的说明和相关报道把到 2027 年左右能由 AI 承担更复杂研发任务的可能性列为重要背景事实，因此助于理解议员为何在近期呼吁立法。 

**「影响」** 这一公开呼吁将把“禁止 RSI”提到国会议程之上，可能在短期内增加立法和监管关注度；受影响的 AI 实验室与研发团队应评估其研发流程是否会被归入“递归自我改进”范畴，并准备与立法者或监管机构沟通与合规方案以降低法律不确定性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/institute/recursive-self-improvement">Our progress toward recursive self - improvement , and its implications.</a></li>
<li><a href="https://time.com/article/2026/08/07/ai-recursive-self-improvement-anthropic-openai/">time.com/article/2026/08/07/ ai - recursive - self - improvement ...</a></li>

</ul>
</details>

**标签**: `#ai-policy`, `#ai-safety`, `#governance`, `#recursive-self-improvement`, `#legislation`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [软银与 ABB 拟分拆中国业务以挽救被叫停的机器人收购](https://www.bloomberg.com/news/articles/2026-11-07/softbank-abb-weigh-china-carve-out-to-salvage-robotics-deal) ⭐️ 8.0/10

软银与 ABB 正考虑把 ABB 机器人业务的中国部分分拆为独立实体，以挽救被中国外商投资安全审查工作机制办公室叫停的 54 亿美元收购。

telegram · zaihuapd · 11月7日 11:24

**「背景」** 中国外商投资安全审查工作机制办公室本周四叫停了该 54 亿美元交易；知情人士称 ABB 正评估包括另寻买家在内的其他选项，并估计该中国业务价值约 20 亿至 30 亿美元（估算）。

**「影响」** 若分拆并重组交易结构以满足审查要求，该方案将直接影响交易双方（软银与 ABB）及中国机器人行业的跨境并购可行性，因其改变了对中国业务的控制权和交易架构。

**标签**: `#M&amp;A`, `#China investment review`, `#Robotics industry`, `#SoftBank`, `#ABB`

---

<a id="item-finance-news-2"></a>
### [全国启动覆盖 3.35 万座寺院的财务大检查](https://www.163.com/dy/article/LB2VSRQD0556HNS1.html) ⭐️ 8.0/10

据网易新闻报道，覆盖全国 3.35 万座寺院和 9000 余座道观的财务大检查已铺开，要求已承包的必须清退并切断寺院的上市与融资通道。

telegram · zaihuapd · 11月7日 15:02

**「背景」** 媒体在 11 月上旬报道，这是一轮全国性集中整治行动，针对寺院道观的商业化问题，报道列举了清退承包、切断上市融资通道、对高收入场所引入第三方审计以及统一捐款和收支公示等措施。

**「影响」** 该措施将直接影响宗教场所及与之有商业或融资关系的企业和投资者，实施手段包括引入第三方审计、统一功德箱与电子收款管理、限制住持亲属参与经营并核查教职人员对外投资与持股。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/1992513/djy/blob/master/gb/26/11/5/n14883359.md">djy/gb/26/11/5/n14883359.md at master · 1992513/djy · GitHub</a></li>

</ul>
</details>

**标签**: `#regulatory action`, `#religious sector`, `#compliance`, `#audit`, `#China`

---

<a id="item-finance-news-3"></a>
### [伯克希尔第三季度回购加速至$9.6 billion](https://www.cnbc.com/2026/11/07/berkshire-hathaway-q3-2026-earnings-buybacks.html) ⭐️ 7.0/10

伯克希尔·哈撒韦在 2026 年第三季度将股票回购加速至$9.6 billion，较第二季度的$4.5 billion 翻倍（公司公布的实际回购额）。

rss · CNBC Finance · 11月7日 15:23

**「背景」** 公司同时报告 2026 年第三季度营业利润（来自全资业务）为$12.705 billion，同比下降 5.8%；包括投资组合在内的总体收益为$22.112 billion，同比下降 28%，其中保险承保利润下滑 43%至$1.352 billion；公司报告季末现金为$377.435 billion，剔除铁路和公用事业现金与国库券应付项后为$352.3 billion。

**「影响」** 对投资者的直接影响：此次回购将使用$9.6 billion 现金，反映公司在现金储备（公司报告季末现金为$377.435 billion、剔除部分项后为$352.3 billion）与资本分配之间的取舍。

**标签**: `#Berkshire Hathaway`, `#share buybacks`, `#earnings`, `#insurance`, `#cash holdings`

---