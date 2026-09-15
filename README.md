<div align="center">

# 🦈 SharkTool

**一站式币圈工具平台 —— 从分析到发币，一站全搞定**

[![Website](https://img.shields.io/badge/官网-sharktool.shop-1F6FEB?style=for-the-badge)](https://sharktool.shop)
[![Chains](https://img.shields.io/badge/多链-BSC%20%7C%20ETH%20%7C%20Polygon%20%7C%20Arbitrum%20%7C%20Base%20%7C%20Solana-8957E5?style=for-the-badge)](#-支持的区块链)
[![No Code](https://img.shields.io/badge/无需写代码-一键部署-2EA043?style=for-the-badge)](#-核心功能)

[🌐 官网](https://sharktool.shop) · [🔍 代币分析](https://sharktool.shop/analyze) · [🧬 代币克隆](https://sharktool.shop/launch) · [🧩 模块化发币](https://sharktool.shop/builder) · [◎ Solana 套件](https://sharktool.shop/solana) · [🛒 源码商城](https://sharktool.shop/shop)

</div>

---

![SharkTool 首页](docs/images/home.png)

## 📖 这是什么

SharkTool 是一个面向普通用户的**链上代币工具箱**：把「查一个币」和「发一个币」这两件事，从需要写代码、请人代做的门槛，压缩成网页上点几下就能完成。

无论是刚接触链上、想看懂一个代币里有没有坑，还是想自己发行代币、搭建流动性、管理已部署的合约，都可以在这一个站点里完成——不需要安装任何软件，也不需要编写或部署一行合约代码。所有涉及链上资产的操作都在你自己的钱包里签名，平台不托管私钥。

---

## ✨ 核心功能

### 🔍 代币分析 `/analyze`

输入合约地址即可得到一份链上体检报告，用于判断「这个币能不能碰」。

- **基本信息**：名称、符号、发行量、精度、销毁比例、合约 Owner、是否开源、编译器版本、开源协议、代理实现地址。
- **风险检测（14 项）**：买入/卖出税率、是否貔貅（蜜罐）、费率是否可改、是否限制大额交易、黑名单/白名单、是否可增发、是否代理合约、是否可暂停、是否有交易冷却、是否可源码审计等。
- 自动识别 `ERC20 / ERC721 / ERC1155` 代币标准与所有权放弃（renounce）状态。
- 多 RPC 自动故障转移，单条线路异常不影响查询。
- 分析完可一键跳转克隆流程，直接复刻该代币。

### 🧬 代币克隆 `/launch`

**源码级百分百克隆**——不是简单复制名称符号，而是让新合约的部署字节码与原合约完全一致。

1. 从区块浏览器拉取已验证的开源合约源码；
2. 在浏览器本地用编译器精确编译，解析出构造函数参数与**源码里硬编码的参数**；
3. 生成可编辑参数表单，税率、营销钱包、供应量上限等都能改；
4. 部署出一个与原合约 100% 一致的代币，并可一键在区块浏览器完成开源验证。

- **三种模式**：源码克隆（推荐）、简易模板、带税/限额/交易开关的完整模板。
- **AI 参数解读**：一键把每个参数翻译成人话，说明作用、怎么填、有没有风险，看不懂的英文变量名不再是障碍。
- 部署后给出新合约地址、部署交易，以及手动开源的完整信息（编译器版本、许可证、优化配置、源码、构造参数编码），可一键复制或下载。

### 🧩 模块化发币 `/builder`

像拼积木一样组装代币——左侧是功能模块库，拖到画布上连线组合，实时校验冲突，确认无误后一键部署。

内置 **23 个发币功能模块**，分为 5 大类：

| 类别 | 模块 |
|---|---|
| 基础 | 基础信息、地址前缀、地址后缀 |
| 交易税 | AMM 交易对、营销税、销毁税、回流税、分红税、外币税（集收转兑） |
| 钱包 | 推荐奖励（多级） |
| 供应量 | 增发代币、销毁代币、自动空投、黑洞分红、持币复利、底池燃烧、LP 挖矿、314 协议 |
| 开关与限制 | 交易开关、单笔交易上限、最大持仓量、黑名单、杀区块（KillBlock 反狙击） |

- **智能校验**：依赖关系检查、买卖总税率上限、机制冲突提醒（如双销毁、多重增发通胀）。
- **自定义合约地址（CREATE2）**：为代币合约指定地址前缀/后缀，支持 EIP-55 大小写校验。
- **一键开源**：部署后自动向区块浏览器提交源码并轮询验证结果。
- 含税模块会引导注册 AMM 交易对，确保税收到账。

### 🎛 代币控制台 `/console`

把在本平台部署过的代币集中管理（也可手动添加任意地址）。

- 实时读取链上状态：当前税费、上限、权限归属等。
- 自动筛选出可调用的管理函数（改费率、黑名单、暂停、增发、销毁、放弃/转移所有权、提取等），生成参数表单，钱包签名即可执行并查看回执。
- **AI 函数解释**：说明这个函数做什么、调用有什么风险、参数怎么填。

### ◎ Solana 套件 `/solana`

一套完整的 SPL 代币流水线，主网与 Devnet 可切换（Devnet 可免费领测试币练手）。

- **发币**：一笔交易完成创建 Mint、初始化、创建账户、铸造、写入链上元数据，可选撤销铸币权/冻结权；支持上传代币图标。元数据走 Metaplex 并做永久存储，成本明细清晰列出租金与网络费。
- **我的代币**：查看自己发行过的代币，实时查询供应量与权限状态（是否已放弃铸币权/冻结权）。
- **靓号地址**：本地生成前后缀匹配的钱包地址，难度预估、导出 Phantom / Solflare 可导入格式，**私钥全程不离开浏览器**。
- **流动性**：通过 Raydium 真实建池（代币 + SOL，无需 OpenBook），查看自己 LP 的数量与占比，一键撤回赎回。
- **工具**：批量转账（SPL / SOL 清单式群发，指令按体积自动打包）、空投（自有地址名单，每人固定数量）、归集（多个钱包一把扫回主钱包）、持币分析（前 20 大持仓与筹码集中度、池子与合约地址识别）、权限检查（铸币权/冻结权是否已撤销）。批量类工具支持**钱包逐笔签名**或**私钥本地签名**两种方式。

### 💼 定制开发 `/custom`

承接代币合约、交易机器人、钱包与工具、DEX 与流动性、前端与面板、安全与审计等定制需求，覆盖 BSC / Ethereum / Polygon / Arbitrum / Base / Solana / Tron，标准化四步交付流程。

---

## ⛓ 支持的区块链

| 网络 | 原生币 | 代币分析 | 发币 / 建池 |
|---|---|---|---|
| BNB Smart Chain | BNB | ✅ | ✅ |
| BNB Smart Chain 测试网 | tBNB | ✅ | ✅ |
| Ethereum | ETH | ✅ | ✅ |
| Polygon | POL | ✅ | ✅ |
| Arbitrum One | ETH | ✅ | ✅ |
| Base | ETH | ✅ | ✅ |
| Solana | SOL | — | ✅ |

波场（Tron）网络在源码商城支付与定制服务中支持。更多网络持续接入中。

---

## 👑 会员体系

开通会员后，**站内所有按次收费的发币 / 建池服务在有效期内免费**，商城源码商品同时享受等级折扣。

| 档位 | 时长 | 价格 | 商城折扣 |
|---|---|---|---|
| 🐟 体验会员（天卡） | 1 天 | 0.1 BNB | 9 折 |
| 🦈 标准会员（周卡） | 7 天 | 0.5 BNB | 8 折 |
| 👑 至尊会员（年卡） | 365 天 | 2 BNB | 半价 |

- 有效期内再次购买为**叠加时长**，而非覆盖。
- 会员覆盖的发币 / 建池动作**不限次数**。
- 支持 BSC 主网 BNB 支付。

---

## ⛽ 服务费说明

按次收费的服务费**随发币 / 建池的那笔交易一并完成**，不额外下单、不单独等待到账：

| 服务 | 费用 |
|---|---|
| EVM 代币克隆 | 0.1 BNB（BSC 主网） |
| EVM 模块化发币 | 0.1 BNB（BSC 主网） |
| Solana 发币 | 0.1 SOL |
| Solana 建池 | 0.1 SOL |

EVM 各链（Ethereum、Polygon、Arbitrum、Base、BSC 测试网）单独定价，币种与金额跟着当前所选网络走，以页面上显示的服务费为准。

靓号地址生成等**纯本地计算**的功能不收取任何链上费用。

---

## 🛒 源码商城 `/shop`

除在线工具外，SharkTool 还提供经过实战使用的工具源码，购买后即可获得完整源码包。

| 商品 | 说明 | 价格 |
|---|---|---|
| 批量钱包生成与归集工具 | 多链批量生成与归集：原生币 / 任意代币，三种归集模式，含测试网 | $90 |
| 多链批量转账工具源码 | 填私钥本地签名，合约批量一笔全发完，含测试网（BSC/ETH/Polygon/Arbitrum） | $199 |
| Solana 靓号钱包生成器 | 三档引擎自动切换：原生 GPU / WebGPU / CPU，前后缀靓号 | $129 |
| EVM 通用靓号地址生成器 | GPU 加速，ETH / BNB / MATIC 全 EVM 链通用，任意前后缀 | $229 |
| 波场 TRON 靓号地址生成器 | GPU 加速，TRX / TRC20 靓号（T 开头），前后缀组合匹配 | $199 |
| 波场转账监控机器人 | 批量地址 · 多代币 · 双向监控，Telegram 实时推送 | $299 |

- 价格以**美元标价**，下单时按**实时汇率**折算成所选支付币种，实际应付数量以付款页显示为准。

- 支持 BSC BNB、BSC USDT、Tron USDT、Solana SOL、Solana USDT 支付。
- 收款地址为平台固定地址（每条链一个），系统按金额与时间把到账对回订单，确认后自动解锁下载。
- 源码包通过**限时签名链接**下发，不暴露公开下载入口。

---

## 🔐 安全说明

- **私钥永不外传**：靓号、批量工具等均在本地运算，平台不索取、不存储任何私钥或助记词。
- **链上操作由你自己签名**：发币、建池、管理合约等每笔交易都在你的钱包中确认。
- **密钥留在服务端**：AI 解读、区块浏览器等第三方密钥由服务端代理，浏览器端不持有。
- **工具类页面只读**：代币分析、监控、靓号等功能仅做查询与本地计算，不触碰资产。

> ⚠️ 链上资产操作存在风险，请务必核对合约地址与交易内容后再签名。本平台提供的分析结论仅供参考，不构成投资建议。

---

## 📚 文档（GitBook）

- 中文正文：`docs/`（GitBook 站点根目录，见 `.gitbook.yaml`）
- 英文版：`docs/en/`（与中文同名文件一一对应，配图在 `docs/en/images/`）

**英文页要显示出来，需要在 GitBook 后台配置一次**（仓库侧改不了）：
Site structure → **Add variant**，把英文版指向 `docs/en` 目录并设置 language = English；
配置好后 GitBook 会自动出现语言切换器（`gitbook-docs.yaml` 由 GitBook 在保存映射时生成/更新，不要手写）。

> 以后改中文文档时，记得同步改 `docs/en/` 里对应的那页——英文是人工翻译、随仓库版本管理，不会自动跟着变。

---

## 🔗 相关链接

- 🌐 官网：<https://sharktool.shop>
- 🛒 源码商城：<https://sharktool.shop/shop>
- 👑 会员中心：<https://sharktool.shop/member>
- ✈️ 联系与合作：Telegram [@sharktool_admin](https://t.me/sharktool_admin)

---

<details>
<summary><b>English</b></summary>

### About SharkTool

SharkTool is an all-in-one on-chain toolkit for the crypto community. It turns "researching a token" and "launching a token" into a few clicks in the browser — no coding, no contract development required.

**Highlights**

- **Token Analyzer** — paste a contract address to get supply, ownership, open-source status and 14 risk checks (buy/sell tax, honeypot, mintable, blacklist, pausable, proxy, and more).
- **Token Cloner** — source-level 100% cloning: pulls verified source, recompiles it locally, lets you edit hardcoded parameters, then deploys a bytecode-identical token with one-click contract verification.
- **Modular Launchpad** — drag-and-drop 23 token modules (taxes, supply mechanics, trading limits, KillBlock anti-snipe, multi-level referrals, CREATE2 custom addresses) with real-time validation.
- **Token Console** — manage deployed tokens: read live state and call admin functions straight from the UI, with AI explanations.
- **Solana Suite** — SPL token launch with on-chain metadata, vanity addresses (keys never leave your browser), and Raydium CPMM liquidity pools.
- **Source-code Shop** — battle-tested tools (batch wallet, batch send, vanity generators, TRON transfer monitor) with multi-chain payment and instant delivery.

**Supported chains:** BSC, Ethereum, Polygon, Arbitrum, Base, Solana (plus Tron for shop payments and custom development).

**Membership:** day / weekly / annual passes waive all per-use service fees site-wide and unlock discounts in the shop.

🔗 Website: <https://sharktool.shop>

</details>

---

<div align="center">

**🦈 SharkTool — 从分析到发币，一站全搞定**

</div>
