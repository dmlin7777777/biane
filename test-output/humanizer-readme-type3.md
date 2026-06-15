# Humanizer: Remove AI Writing Patterns

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="License">
  <img src="https://img.shields.io/badge/type-Capability-purple" alt="Type: Capability">
  <img src="https://img.shields.io/badge/patterns-24-orange" alt="24 Patterns">
  <img src="https://img.shields.io/badge/source-Wikipedia%20AI%20Cleanup-forestgreen" alt="Source">
</p>

> **你的文字读起来像 AI 写的——你知道，读者也知道。手动改要一小时。**
>
> Humanizer 在 3 秒内识别 24 种 AI 写作模式，逐句重写。基于 Wikipedia 数千案例验证。

---

## 安装

```bash
npx skills add humanizer
```

装完直接说：

> "帮我把这段文字去 AI 味"

---

## 它能检测什么

24 种 AI 写作模式，分 5 大类。每种都有 Before → After 对比。

### 📝 Content Patterns（内容模式）

<details>
<summary><b>1. 夸大意义与遗产</b> — "marks a pivotal moment" "reflects broader" "indelible mark"</summary>

**Before:** The institute was officially established in 1989, marking a pivotal moment in the evolution of regional statistics. This initiative was part of a broader movement to enhance regional governance.

**After:** The institute was established in 1989 to collect and publish regional statistics independently from the national office.
</details>

<details>
<summary><b>2. 夸大知名度</b> — "independent coverage" "leading expert" "active social media presence"</summary>

**Before:** Her views have been cited in The New York Times, BBC, and Financial Times. She maintains an active social media presence with over 500,000 followers.

**After:** In a 2024 New York Times interview, she argued that AI regulation should focus on outcomes rather than methods.
</details>

<details>
<summary><b>3. -ing 假深度句</b> — "highlighting..." "symbolizing..." "reflecting..."</summary>

**Before:** The temple's color palette resonates with the region's natural beauty, symbolizing Texas bluebonnets and reflecting the community's deep connection to the land.

**After:** The temple uses blue, green, and gold colors. The architect said these were chosen to reference local bluebonnets and the Gulf coast.
</details>

<details>
<summary><b>4. 广告/促销语</b> — "boasts" "vibrant" "nestled in the heart of" "breathtaking"</summary>

**Before:** Nestled within the breathtaking region of Gonder, Alamata Raya Kobo stands as a vibrant town with a rich cultural heritage and stunning natural beauty.

**After:** Alamata Raya Kobo is a town in the Gonder region of Ethiopia, known for its weekly market and 18th-century church.
</details>

<details>
<summary><b>5. 模糊引用</b> — "Industry reports" "Experts argue" "Observers have cited"</summary>

**Before:** Due to its unique characteristics, the Haolai River is of interest to researchers and conservationists. Experts believe it plays a crucial role in the regional ecosystem.

**After:** The Haolai River supports several endemic fish species, according to a 2019 survey by the Chinese Academy of Sciences.
</details>

<details>
<summary><b>6. 模板化"挑战与展望"结语</b> — "Despite its... faces several challenges..."</summary>

**Before:** Despite its industrial prosperity, Korattur faces challenges typical of urban areas. With its strategic location, it continues to thrive as an integral part of Chennai's growth.

**After:** Traffic congestion increased after 2015 when three new IT parks opened. The municipal corporation began a stormwater drainage project in 2022.
</details>

---

### 🔤 Language & Grammar（语言模式）

<details>
<summary><b>7. AI 高频词汇</b> — "Additionally" "crucial" "delve" "pivotal" "showcase" "underscores" "vibrant"</summary>

**Before:** An enduring testament to Italian colonial influence is the widespread adoption of pasta in the local culinary landscape, showcasing how these dishes have integrated into the traditional diet.

**After:** Pasta dishes, introduced during Italian colonization, remain common, especially in the south.
</details>

<details>
<summary><b>8. 回避 is/are</b> — "serves as" "stands as" "represents" "boasts" "features"</summary>

**Before:** Gallery 825 serves as LAAA's exhibition space. The gallery features four separate spaces and boasts over 3,000 square feet.

**After:** Gallery 825 is LAAA's exhibition space. The gallery has four rooms totaling 3,000 square feet.
</details>

<details>
<summary><b>9. 否定排比</b> — "Not only...but..." "It's not just about..., it's..."</summary>

**Before:** It's not just about the beat riding under the vocals; it's part of the aggression and atmosphere. It's not merely a song, it's a statement.

**After:** The heavy beat adds to the aggressive tone.
</details>

<details>
<summary><b>10. 三件套强迫症</b> — 所有事物都要凑 3 个</summary>

**Before:** The event features keynote sessions, panel discussions, and networking opportunities. Attendees can expect innovation, inspiration, and industry insights.

**After:** The event includes talks and panels. There's also time for informal networking between sessions.
</details>

<details>
<summary><b>11. 优雅换词</b> — "protagonist" "main character" "central figure" "hero" 指同一个人</summary>

**Before:** The protagonist faces many challenges. The main character must overcome obstacles. The central figure eventually triumphs. The hero returns home.

**After:** The protagonist faces many challenges but eventually triumphs and returns home.
</details>

<details>
<summary><b>12. 伪区间</b> — "from X to Y" 但 X 和 Y 不在同一条轴上</summary>

**Before:** Our journey through the universe has taken us from the singularity of the Big Bang to the grand cosmic web, from the birth and death of stars to the enigmatic dance of dark matter.

**After:** The book covers the Big Bang, star formation, and current theories about dark matter.
</details>

---

### ✍️ Style Patterns（风格模式）

| # | 模式 | 信号词 | 改法 |
|---|------|--------|------|
| **13** | Em dash 滥用 | — 每段出现 2-3 次 | 换成逗号或句号 |
| **14** | 粗体滥用 | **每段都加粗关键词** | 去掉，正常文字 |
| **15** | 带冒号的项目符号 💀 | `- **关键词：** 解释` | 写成正常句子 |
| **16** | 标题每个词大写 | "Strategic Negotiations And Global Partnerships" | "Strategic negotiations and global partnerships" |
| **17** | Emoji 装饰 | 🚀💡✅ 装饰标题 | 去掉 emoji |
| **18** | 弯引号 | "..." 而非 "..." | 换成直引号 |

---

### 💬 Communication Patterns（对话残留）

| # | 模式 | 信号词 | 改法 |
|---|------|--------|------|
| **19** | 对话套话残留 | "I hope this helps!" "Of course!" "Certainly!" | 直接删掉 |
| **20** | 知识截止声明 | "as of [date]" "based on available information" | 找具体来源替代 |
| **21** | 谄媚语气 | "Great question!" "You're absolutely right!" | 正常表达 |

---

### 🧹 Filler & Hedging（废话）

| # | 模式 | Before | After |
|---|------|--------|-------|
| **22** | 填充短语 | "In order to achieve this goal" | "To achieve this" |
|  |  | "Due to the fact that" | "Because" |
|  |  | "At this point in time" | "Now" |
| **23** | 过度模糊 | "It could potentially possibly be argued that..." | "The policy may affect outcomes." |
| **24** | 空洞正能量结尾 | "The future looks bright!" "Exciting times lie ahead!" | 删掉，用具体信息收尾 |

---

## 全面对比

**Before（AI-sounding — 包含了 8 种模式）：**

> The new software update serves as a testament to the company's commitment to innovation. Moreover, it provides a seamless, intuitive, and powerful user experience—ensuring that users can accomplish their goals efficiently. It's not just an update, it's a revolution in how we think about productivity. Industry experts believe this will have a lasting impact on the entire sector, highlighting the company's pivotal role in the evolving technological landscape.

**After（Humanized — 8 种模式全部清除）：**

> The software update adds batch processing, keyboard shortcuts, and offline mode. Early feedback from beta testers has been positive, with most reporting faster task completion.

---

## 它不做什么

- **不改变你的内容** — 只改表达方式，不改核心信息
- **不统一风格** — 保留你的语气（正式 / 随意 / 技术向）
- **不保证完全隐蔽** — 这是基于已知模式的检测，不是万能隐身衣

---

## 方法论来源

全部 24 种模式来自 [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)，由 WikiProject AI Cleanup 维护。模式来自于数千个 Wikipedia 上 AI 生成文本的实例观察。

关键洞察："LLMs use statistical algorithms to guess what should come next. The result tends toward the most statistically likely result that applies to the widest variety of cases."

---

## License

MIT
