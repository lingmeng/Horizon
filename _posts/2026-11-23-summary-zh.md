---
layout: default
title: "Horizon Summary: 2026-11-23 (ZH)"
date: 2026-11-23
lang: zh
---

> 从 28 条内容中筛选出 10 条重要资讯。

---

**科技新闻**
1. [困惑度与智能](#item-tech-news-1) ⭐️ 8.0/10
2. [英媒：柬埔寨太子集团涉疑英伟达芯片走私](#item-tech-news-2) ⭐️ 8.0/10
3. [中国要求美国撤销电话号段限制](#item-tech-news-3) ⭐️ 8.0/10
4. [Windows Server 2028 默认不含 WoW64](#item-tech-news-4) ⭐️ 8.0/10
5. [硅谷发生了什么？](#item-tech-news-5) ⭐️ 7.0/10
6. [谷歌用 Mirror Dimension 模拟互联网测试 Chrome AI 代理](#item-tech-news-6) ⭐️ 7.0/10

**科技博客**
1. [不确定时就四处试验](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [美股科技股暴跌，亚洲多地启动市场稳定措施](#item-finance-news-1) ⭐️ 9.0/10
2. [超级厄尔尼诺海温破纪录，粮食援助承压](#item-finance-news-2) ⭐️ 8.0/10
3. [蚂蚁领投 Simplexity Robotics 完成 1 亿美元融资、估值 16 亿美元](#item-finance-news-3) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [困惑度与智能](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 8.0/10

OpenAI 在其 Index 上发表了一篇题为“Perplexity and Intelligence”的文章，主张语言模型的困惑度（perplexity，基于交叉熵的下一个 token 预测误差度量）与模型“智能”或能力之间存在明确对应关系，并建议将困惑度作为一个简单、统一的基准来衡量模型进展。该主张在社区内引发强烈讨论：支持者认为困惑度直接反映了从原始数据中学习世界模型的能力，而反对者和评论者指出文章未给出形式化的定义或统一的评测细节，并且当前证据更多是趋势关联而非独立、严格验证的证明。文章因此更多表现为对评估重点的建议与论证，而非经同行严格复现的结论。 

hackernews · acossta · 11月22日 17:06 · [社区讨论](https://news.ycombinator.com/item?id=50601525)

**「困惑度（perplexity）与语言模型评价的基本概念」** 困惑度通常用来衡量语言模型在预测下一个标记时的不确定性，数学上等价于对验证集上平均负对数概率（交叉熵）取指数，数值越低表示模型对下一个标记的预测越有把握。作为语言模型训练和比较的标准化持出集指标，困惑度被用来评估模型对原始文本流的预测/压缩能力，因此任何关于“困惑度与智能相关性”的论断都是在把模型的下一个标记预测性能（即困惑度）与更高阶能力或表现进行关联和解释。

**「影响」** 如果业界采纳这篇文章的建议，模型发布方和研究团队可能会开始在共享的持出评测集上披露（对数）困惑度并以降低困惑度作为重要目标；因此，模型发布与论文应明确说明所报告的是对数困惑度还是困惑度、本次评测用的分词器与持出集，以及数值来自预训练还是微调后的模型。社区评论还报告有厂商开始把自家模型加入同一困惑度图表，表明评测可比性和评测集治理将成为需要解决的兼容性问题。

**「社区讨论要点」** 评论者指出文章没有对“perplexity”做出精确定义并提醒应说明计算细节（例如对数尺度、分词和持出集）；有人惊讶于在强化学习微调广泛使用后交叉熵相关指标仍然显著相关，而另有评论者从理论上支持困惑度等同于预测/压缩能力并认为这天然对应智能——这些都是意见性争论而非经验证的结论。

**标签**: `#evaluation-metrics`, `#language-models`, `#benchmarks`, `#AI-research`

---

<a id="item-tech-news-2"></a>
### [英媒：柬埔寨太子集团涉疑英伟达芯片走私](https://www.ft.com/content/f3ad8a81-3890-4a8a-8853-ff0a94b08ba9?syn-25a6b1a6=1) ⭐️ 8.0/10

英国《金融时报》援引知情人士报道，所谓被美国财政部认定为柬埔寨太子集团“二号人物”的胡小伟，涉嫌参与通过空壳公司和一家马来西亚子公司将英伟达芯片运往中国的走私网络；报道称 Megaspeed 马来西亚子公司在 2024 年 12 月至 2025 年 12 月申报进口货值约 46 亿美元，部分芯片据称流入中国黑市。报道还指该网络使用地下融资渠道和私人飞机运输，但太子集团否认胡小伟为其工作并反驳有关走私和私人飞机指控。该报道是基于匿名消息来源和贸易数据的指控，目前仍属未独立证实的指控与当事方否认并存。

telegram · zaihuapd · 11月22日 04:34

**「必要背景」** 近年来，针对部分高端 AI 与数据中心芯片的出口限制促生了“灰色市场”和走私链路，相关芯片常被经由第三国、子公司或空壳公司转运以规避管控。多家媒体和分析指出，这类网络通常同时依赖地下融资、代理公司和非公开运输方式，将受限芯片从制造国经中转地送往最终需求市场。

**「影响与建议」** 这一报道直接增加了对 AI 芯片供应链与出口管制执行的监管与合规风险：进口商、分销商与云服务商应审查与 Megaspeed 类似中间方的尽职调查记录、加强对下游流向的追踪，并准备应对可能的调查、执法行动或更严格的许可要求。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://asiatimes.com/2026/11/daigou-the-gray-market-that-moves-nvidias-chips-to-china/">Daigou: the gray market that moves Nvidia &#x27;s chips to... - Asia Times</a></li>

</ul>
</details>

**标签**: `#hardware`, `#supply-chain`, `#export-controls`, `#security`, `#investigation`

---

<a id="item-tech-news-3"></a>
### [中国要求美国撤销电话号段限制](https://www.bloomberg.com/news/articles/2026-11-22/china-objects-to-us-curbs-on-telecoms-access-to-phone-numbers) ⭐️ 8.0/10

中国商务部于 11 月 22 日敦促美国撤销一项措施，该措施禁止中国移动、中国电信和中国联通三家运营商直接获取美国电话号码。美国联邦通信委员会（FCC）在 11 月 19 日投票收紧对申请直接接入美国号码的互联网语音服务商的安全要求，新增“国家安全认证”并规定阻止列入 Covered List 的实体、设备和服务接入美国网络。商务部称该举措违反非歧视与公平竞争原则，并警告此举可能导致双方在电信、通信及检测认证领域的脱钩，中方表示将采取必要措施维护自身利益。

telegram · zaihuapd · 11月22日 06:44

**「背景说明」** 美国联邦通信委员会（FCC）在 11 月 19 日投票收紧了对“直接接入美国号码”的安全要求，新增了国家安全认证并授权阻止列入其 Covered List 的实体、设备和服务接入美国网络。所谓“直接接入”通常指为境外互联网语音服务商分配或连接美国号段、SIP 中继或其它号码资源的能力，因此这类监管变化会把号码分配与互联接入置于国家安全审查之下。

**「影响与行动建议」** 直接影响包括：中国三大运营商如果未能通过新的国家安全认证，可能失去直接申领美国号段的能力，从而需依赖第三方中介或调整号码分配与互联互通策略；同时，所有申请直接接入美国号码的互联网语音/VoIP 服务商将需要满足更严格的安全与合规要求。受影响的电信运营商和云通信平台应审查 FCC 最新要求并准备合规材料，以评估是否位于 Covered List 上或能通过新的认证流程，避免接入申请被拒绝。

**标签**: `#telecom`, `#policy`, `#China-US`, `#national-security`, `#regulatory`

---

<a id="item-tech-news-4"></a>
### [Windows Server 2028 默认不含 WoW64](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 8.0/10

微软在 Ignite 2026 上宣布，Windows Server 2028 的出厂默认配置将不再包含 WoW64（Windows-on-Windows 64）兼容子系统，因此开箱即不能运行 32 位用户模式应用。微软说明 WoW64 会作为“按需功能”（Feature on Demand）提供，管理员可在需要时通过 Server Core 上的 PowerShell 或 DISM 将其安装回去。微软将此改变的理由归于减少攻击面并阻止 32 位恶意软件；该版本计划与 Windows 11 27H2 一同在 2027 年秋季发布。

telegram · zaihuapd · 11月23日 03:03

**「背景」** WoW64 是 Windows 的兼容子系统，允许 32 位用户模式程序在 64 位 Windows 上运行，长期用于保持遗留软件在 64 位平台上的兼容性。此前大多数 Windows Server 发行版默认包含 WoW64，因而许多遗留服务器应用在无额外操作下可继续运行。

**「影响与行动建议」** 对系统管理员和运维团队的具体后果是：仍依赖 32 位二进制的服务器映像、部署脚本或遗留业务软件需要显式在镜像或自动化中添加 WoW64（例如在 Server Core 上使用 DISM 或 PowerShell 安装 FoD），否则这些应用在默认安装下将无法运行；建议在测试环境中列出 32 位依赖、更新部署镜像并在发布前验证应用可用性。Windows 11 目前仍保留 WoW64，微软尚未公布对其移除的计划。

**标签**: `#windows-server`, `#compatibility`, `#security`, `#sysadmin`, `#wow64`

---

<a id="item-tech-news-5"></a>
### [硅谷发生了什么？](https://www.oreilly.com/radar/what-happened-to-silicon-valley/) ⭐️ 7.0/10

O’Reilly Radar 在 2026-11-22 发布了一篇作者署名为 greenyouse 的长篇分析，检视了当代硅谷的失调并呼吁从激励与机制设计角度重新思考产业目标。文章的核心主张是把“机制设计（逆向博弈论）”用于问“我们应当玩什么样的游戏？”，并建议将目标从公司利润或股东价值转向“人类福祉”的优化。该文是价值判断与政策与设计建议的论述，而非新的实证数据或测量结果，因此结论更多属于分析性主张而非可独立验证的性能声明。

hackernews · greenyouse · 11月22日 19:20 · [社区讨论](https://news.ycombinator.com/item?id=50602947)

**「背景：机制设计与价值取向」** 机制设计可以被视为逆向博弈论——通过设定规则和激励来引导个体与组织产生期望的社会或经济结果。O’Reilly Radar 的这篇长文把理解硅谷现状的讨论放在“从价值创造到价值提取”这一框架下，因而需要读者先理解机制设计如何塑造公司和市场的行为。

**「影响」** 对工程师、产品经理与公司治理者的直接后果是需要把产品指标、商业化路径与薪酬／激励体系纳入机制设计审查；文章建议组织审查并调整 KPI 与货币化激励，以避免系统性地优化出对用户或社会有害的结果。

**「社区讨论要点」** 评论中最有用的讨论聚焦在“问题的根源是什么”这一分歧：一部分评论（如 zhivota）援引 Hal Varian 的例子说明早期产品能创造大量超额价值而非直接变现，另一些评论（如 CoolestBeans）把责任指向长期低利率（ZIRP）及随之而来的扩张性融资；多位评论者（如 Animats、michalsustr）则支持文章的核心建议——用机制设计重新对齐系统目标以优先人类福祉，并把这作为可操作的治理方向而非单纯的价值评判。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.oreilly.com/radar/">Radar – O’Reilly</a></li>

</ul>
</details>

**标签**: `#tech-industry`, `#mechanism-design`, `#governance`, `#AI-ethics`

---

<a id="item-tech-news-6"></a>
### [谷歌用 Mirror Dimension 模拟互联网测试 Chrome AI 代理](https://www.landian.news/archives/128701.html) ⭐️ 7.0/10

据蓝点网报道，谷歌为 Chrome 的 AI 代理搭建了一个名为 Mirror Dimension 的模拟互联网，用于在隔离环境中大规模测试代理打开网站、搜索浏览、登录、加入购物车和完成任务等交互行为。报道称该环境包含数千个模拟网站，每名工程师在单独隔离的测试环境中工作，团队每天运行超过 1000 个测试用例，测试重点包括对抗恶意网页的提示词注入等攻击。该报导提供了操作范围的数字细节，但没有给出深入的技术实现细节或独立验证，目前应将这些内容视为媒体报道而非谷歌的官方完整公开说明。

telegram · zaihuapd · 11月23日 01:30

**「背景说明」** 提示词注入是指网页通过特意构造的内容改变或覆盖对话代理的指令，从而诱导代理执行非预期操作；当浏览器内置代理能够自动执行登录与购物等动作时，这类攻击面会扩大。使用一个可控的模拟互联网可以在不影响真实用户和真实站点的情况下，批量运行对抗性测试并评估针对恶意页面和注入攻击的防御措施。

**「影响与建议」** 对浏览器厂商、网站开发者和安全团队来说，这一做法表明需把浏览能力的代理视作新的攻击面，并把提示词注入纳入威胁模型与测试清单；证据支持的直接措施包括在隔离环境中进行自动化、对抗性测试以及在设计上限制代理对敏感操作（如凭证使用或自动提交）的权限。鉴于报道缺乏技术细节，安全团队在评估风险或调整防护策略时应等待更多公开细节或官方说明。

**标签**: `#Chrome`, `#AI agent`, `#sandboxing`, `#security`, `#prompt-injection`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [不确定时就四处试验](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** 作者认为在面对模糊问题或没有明确指引时，等待或谨慎观望通常不是最佳策略：缺乏信息的情境需要尽快与现实接触以获得可用反馈。

**「方案」** 作者的核心建议是有目的地“乱试”：同时开展许多小实验、对来自他人和系统的反馈保持高度敏感、并且果断放弃没有正向反馈的想法。这样做的理由包括三个：一是通过多次试错与现实直接接触，快速暴露哪些假设成立；二是多数方案会失败，只有数量化的尝试才能把赌注分散；三是多方案并行减少对单一计划的过度投入，从而更容易放弃失败路径。作者还把这种方法分成产品、工程与组织三类应用场景：在产品开发里多做边缘实验寻找可粘性功能（作者提到在 GitHub Models 的尝试中发现了“持续 AI”的种子）；在工程问题上建议做若干投机性改动并观察指标，必要时用 AI 生成多种重构方案以快速筛选；在组织问题上可以通过自动化、承担任务或提出长期方案来试探改进方向，但要尤为留意人际反馈以免损害信任。作者警告这做法有名誉风险、容易让人感觉像在“乱搞”，并且文章以经验性、轶事性为主，缺乏严格量化证据，因此需要小心权衡和场景判断。

**「启示」** 作者的结论是：在不确定时，与其等答案不如同时启动多条小路径、密切观测反馈并迅速放弃失败者——短期的尴尬和试错换来的是更快的事实性学习与方向发现。

**标签**: `#experimentation`, `#engineering-culture`, `#product-management`, `#organizational-change`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美股科技股暴跌，亚洲多地启动市场稳定措施](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

美国 AI 科技股周五遭大规模抛售，纳斯达克单日下跌 5.28%（实际结果）。新华社报道，中国内地将融资保证金最低比例下调至 80%作为市场稳定措施。

telegram · zaihuapd · 11月22日 13:24

**「背景」** 美国股市于 11 月 20 日发生大规模科技股抛售，纳斯达克综合指数单日下跌 5.28%、波动率指标 VIX 显著上升，随后中国内地、韩国与台湾地区宣布或启动调整融资保证金、回购和卖空等市场稳定措施以应对突发波动。

**「影响」** 这将直接影响依赖融资（杠杆）和借券做空的个人与机构投资者，因为内地、韩国与台湾当局通过调整保证金、回购与卖空规则改变融资成本与交易可得性（新华社/韩联社/中央社报道）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.gate.com/zh/news/detail/us-stocks-crash-nasdaq-turns-negative-for-2026-vix-surges-past-40-25797766">美股暴跌：纳斯达克指数2026年迄今转为负收益，VIX飙升至40以上 | Gat...</a></li>
<li><a href="https://news.qq.com/rain/a/20261121A0A4S500">美股遭遇6年来罕见暴跌！纳指单日暴跌5.28%，英伟达一周重挫23%，华尔...</a></li>

</ul>
</details>

**标签**: `#market turmoil`, `#regulatory response`, `#US tech sell-off`, `#Asia markets`

---

<a id="item-finance-news-2"></a>
### [超级厄尔尼诺海温破纪录，粮食援助承压](https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/) ⭐️ 8.0/10

伯克利气候学家 Zeke Hausfather 报告称，截至 10 月，用于衡量厄尔尼诺强度的中热带太平洋升温已达 3.5°C，超过此前约 2.75°C 的纪录，并预计在初冬升至约 4°C 峰值（估计）。世界粮食计划署（WFP）在 8 月警告，本轮厄尔尼诺可能到 2027 年底将额外约 4,900 万人推入急性粮食不安全，使受影响总数达约 2.74 亿；WFP 还指出全球援助资金在 2025 年较 2022 年峰值已下降约 30%（报告/警告）。

telegram · zaihuapd · 11月22日 14:09

**「背景」** 伯克利地球气候学家 Zeke Hausfather 的分析显示，截至 10 月，中热带太平洋相对于长期基线的海表温度异常已约为 3.5°C（高于 2015–16 年约 2.75°C 的纪录），多模式气候预测显示该异常可能在初冬升至约 4°C，表明本次“超级厄尔尼诺”强度异常。 

**「影响」** 受影响主体为依赖援助的脆弱家庭与小农户：厄尔尼诺通过极端天气导致产量下降和价格上升，而 WFP 指出因援助资金在 2025 年较 2022 年下降约 30%，应急覆盖和救助能力可能受限。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.wired.com/story/2026-el-nino-the-strongest-in-150-years/">The 2026 El Niño Is on Track to Be the Strongest on Record</a></li>
<li><a href="https://www.carbonbrief.org/simply-staggering-rapidly-developing-super-el-nino-on-track-to-peak-in-december">‘Simply staggering’: Rapidly developing ‘super El Niño’ on ...</a></li>

</ul>
</details>

**标签**: `#El Niño`, `#Food security`, `#Humanitarian aid`, `#Climate`, `#Agriculture`

---

<a id="item-finance-news-3"></a>
### [蚂蚁领投 Simplexity Robotics 完成 1 亿美元融资、估值 16 亿美元](https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race) ⭐️ 8.0/10

彭博报道，蚂蚁集团领投中国具身智能公司 Simplexity Robotics 完成 1 亿美元 pre‑A 轮融资，投后估值为 16 亿美元（彭博报道）。

telegram · zaihuapd · 11月23日 02:02

**「背景」** Simplexity Robotics 于 2025 年 7 月在杭州成立，核心团队来自理想汽车，并曾披露在成立半年内完成五轮、累计融资约 20 亿元人民币、投后估值已超过 10 亿美元。

**「影响」** 彭博称资金将用于与宇树、优必选等更成熟厂商争夺中国人形机器人市场，这将直接影响同业竞争格局和寻求部署人形机器人的企业客户。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://ifr.org/">International Federation of Robotics</a></li>

</ul>
</details>

**标签**: `#private financing`, `#robotics`, `#China tech`, `#valuation`, `#corporate investors`

---