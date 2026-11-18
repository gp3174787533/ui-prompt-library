# 待整理收集区（inbox）

新收集的 UI 提示词先放这里，注明来源和日期；整理（去重、定分类、补中文说明）后移入 prompts.json，并从这里删掉。

<!-- 格式：
## YYYY-MM-DD · 来源（一句话）
- 原文/链接：
- 初步分类：
- 备注：
-->

## 2026-11-17 · 抖音 @费纸张《5个小细节让AI设计的界面看着更舒服》
- 原文/链接：https://v.douyin.com/rL3vWzup154/（短链实际作品 id 7699104647889423667（用户消息里的直链 7695264996816620863 是另一个作品：SpicyTater《用大白话向AI描述后台菜单交互Skill》，与本条无关））
- 状态：2026-11-17 已核对（未登录、关闭弹窗后观看）：费纸张《AI设计技巧分享》第3集，2026-10-21 发布，42 秒。5 个细节已核实：①等宽数字 tabular-nums ②同心圆角 外层=内层+内边距 ③错开入场（片尾汇总间隔100ms）④平衡标题换行 text-wrap: balance ⑤阴影代替边框（多层柔和 box-shadow）。完整旁白未转录成功，要点以画面文字/字幕片段/文案为准；第5条阴影完整代码值未在画面中完全显示。
- 已处理：先原创收集「细节优化」类 10 条；核对后已补入原作版 5 条（合集1 + 等宽数字/同心圆角/错开入场/平衡换行 4 条单项，阴影代替边框与已有 detail-shadow-border 同主题、合集条目内含原作版表述）。本条目留档，不再待办。

## 2026-11-17 · 公开渠道收集（Questera / Superdesign / TemplatesCenter）
- 原文/链接：https://www.questera.ai/blogs/ai-prompts-beautiful-ui-designs（Bento 网格、瑞士极简模板，已打开核对）；https://superdesign.dev/blog/ui-design-prompts（定价页、设置页主从布局模板，已打开核对）；https://www.templatescenter.com/blogs/liquid-glass-ui-prompts-20-templates-that-work（液态玻璃五要素配方，已打开核对）
- 状态：2026-11-17 已核对上述三页正文，按统一格式改写整理，非逐字摘录；与现有 33 条去重（避开已有粗野主义、杂志编辑风、Linear 后台等同场景同风格条目）。
- 已处理：新增 5 条 — landing-bento-grid、landing-swiss-minimal、landing-pricing-saas（落地页官网）、saas-settings-master-detail（SaaS后台）、detail-liquid-glass（细节优化），已移入 prompts.json 与对应分类 md。本条目留档，不再待办。

## 待验证区（2026-11-17 起执行新规：验证通过才进正式库）

以下条目已收集整理但尚未生成验证，暂存于此；逐条生成验证通过后才移入 prompts.json 并提交。

### 微交互：hover/点击反馈 (`detail-micro-interaction`)

```json
{
  "id": "detail-micro-interaction",
  "title": "微交互：hover/点击反馈",
  "category": "细节优化",
  "styles": [
    "动效",
    "反馈",
    "精致"
  ],
  "scenario": "界面死板/点了没反应感时的动效补充",
  "prompt": "Add tasteful micro-interactions to this UI: buttons darken 8% on hover and scale to 0.98 on press; cards lift 2px with a softer shadow on hover; page and modal transitions 200ms ease-out, nothing longer; toggles and checkboxes animate their state change; loading buttons show an inline spinner and disable repeat clicks. No bouncy, playful or attention-seeking animation — everything subtle and fast.",
  "prompt_zh": "克制的微交互：hover 变深、按下缩放 0.98、转场统一 200ms、开关/勾选有状态动画、加载按钮防重复点，不要弹跳卖萌动效。",
  "tools": [
    "v0",
    "Lovable"
  ]
}
```

### 图标一致性：一套线性图标 (`detail-icon-consistency`)

```json
{
  "id": "detail-icon-consistency",
  "title": "图标一致性：一套线性图标",
  "category": "细节优化",
  "styles": [
    "图标",
    "一致性",
    "线性"
  ],
  "scenario": "图标风格混杂像拼凑时的统一",
  "prompt": "Unify all icons in this UI: one single icon set (Lucide/Feather style), outline only, 1.5px stroke, rounded line caps, 20px default size, no filled/duotone/emoji icons mixed in; icons inherit the text color of their label; every icon must pair with a text label or tooltip — no naked mystery icons. Replace any inconsistent icon instead of styling around it.",
  "prompt_zh": "图标只用一套线性图标：描边 1.5px、圆头、20px、颜色跟文字走，禁止填充/双色/emoji 混用，每个图标配文字或提示。",
  "tools": [
    "v0",
    "Cursor"
  ]
}
```

### 对比度与可读性检查 (`detail-contrast-a11y`)

```json
{
  "id": "detail-contrast-a11y",
  "title": "对比度与可读性检查",
  "category": "细节优化",
  "styles": [
    "对比度",
    "无障碍",
    "可读性"
  ],
  "scenario": "字看不清/灰字太浅时的可读性修复",
  "prompt": "Fix readability in this UI to WCAG AA: body text contrast at least 4.5:1 against its background (no light-gray text on white for real content), large headings at least 3:1; minimum body size 14px on desktop and 16px on mobile inputs; placeholder text is not a label — keep visible labels; focus states get a clear 2px outline; tap targets at least 44px on mobile. Beauty must survive at arm's length and in sunlight.",
  "prompt_zh": "可读性到达标线：正文对比度 ≥4.5:1、真实内容不用浅灰字、移动端输入框 16px、保留可见标签、焦点 2px 描边、点击区 ≥44px。",
  "tools": [
    "v0",
    "Cursor",
    "Qoder"
  ]
}
```

### 视觉重量：一个页面一个主角 (`detail-visual-weight`)

```json
{
  "id": "detail-visual-weight",
  "title": "视觉重量：一个页面一个主角",
  "category": "细节优化",
  "styles": [
    "焦点",
    "层级",
    "留白"
  ],
  "scenario": "什么都想突出等于没重点时的焦点收敛",
  "prompt": "Rebalance the visual weight of this page so it has exactly one hero: the primary action is the only filled, colored button — all other actions become text or outline buttons; the key metric or headline is at least 2x larger than anything else; remove competing badges, banners and popups (keep at most one); dim secondary panels with a lighter background instead of borders and shadows. The eye should land in one second.",
  "prompt_zh": "一页一个主角：主按钮是唯一实心彩色按钮、核心数字/标题至少大 2 倍、横幅徽章最多留一个、次要面板用浅底弱化，一秒抓住眼球。",
  "tools": [
    "v0",
    "Lovable"
  ]
}
```

### 平衡标题换行：不留孤词 (`detail-balanced-headline`)

```json
{
  "id": "detail-balanced-headline",
  "title": "平衡标题换行：不留孤词",
  "category": "细节优化",
  "styles": [
    "排版",
    "标题",
    "细节"
  ],
  "scenario": "大标题/卡片标题的换行排版",
  "prompt": "Balance headline wrapping: apply text-wrap: balance to headings (h1/h2 and card titles) so multi-line titles break into lines of similar length and no single orphan word is left alone on the last line. Check every long title at mobile width as well.",
  "prompt_zh": "标题换行要平衡：h1 { text-wrap: balance; }，各行长度接近，最后一行不落单一个词。源自费纸张视频细节4。",
  "tools": [
    "v0",
    "Cursor"
  ]
}
```

- 验证记录（2026-11-17）：生成博客落地页目检不通过 — 主标题两行长度接近，但多张卡片标题末行只剩单个词（Environment / Standards / Processes），未做到无孤词，不进正式库，留待验证区改提示词后重验。

### 空间收集轮次新增（2026-11-17，同样待验证）

#### Bento 便当网格功能区 (`landing-bento-grid`)

```json
{
  "id": "landing-bento-grid",
  "title": "Bento 便当网格功能区",
  "category": "落地页官网",
  "styles": [
    "Bento网格",
    "卡片",
    "极简"
  ],
  "scenario": "SaaS/AI 产品功能展示区",
  "prompt": "Lay out the features section as a bento grid: 6 tiles of mixed sizes on a 12-column grid, one large 2x2 tile for the hero feature with a product visual, two medium tiles and three small tiles for supporting features, equal 16px gaps and unified 20px corner radius, each tile holds exactly one heading, one line of copy and one visual — no text walls. Light neutral background #F7F7F5, white tiles with 1px border #E7E5E4, one indigo accent only on the hero tile. Stack to a single column on mobile, keep tile order by importance.",
  "prompt_zh": "Bento 功能区：6 块大小不一的瓷砖、主功能占大格、统一 16px 间距和 20px 圆角、每格一标题一行文案一视觉，移动端单列堆叠。",
  "tools": [
    "v0",
    "Lovable",
    "Framer"
  ]
}
```

#### 瑞士极简网格官网 (`landing-swiss-minimal`)

```json
{
  "id": "landing-swiss-minimal",
  "title": "瑞士极简网格官网",
  "category": "落地页官网",
  "styles": [
    "瑞士极简",
    "网格",
    "黑白"
  ],
  "scenario": "设计工作室/建筑/文化机构官网",
  "prompt": "Restyle this website in a minimal Swiss International style: strict 12-column grid with visible alignment, one sans-serif typeface (Helvetica/Inter) in only two weights (regular and bold), near-black text #111111 on off-white #FAFAF8, one red accent #E30613 used only for primary actions and section numbers. No shadows, no gradients, no rounded corners, no decorative icons. Oversized left-aligned headlines, generous margins, hairline rules to separate sections, everything snaps to the grid.",
  "prompt_zh": "瑞士极简：严格 12 栏网格、一种无衬线字体只用两档字重、近黑配米白、红色只给主操作，无阴影无渐变无圆角。",
  "tools": [
    "v0",
    "Framer",
    "Cursor"
  ]
}
```

#### 液态玻璃：五要素材质配方 (`detail-liquid-glass`)

```json
{
  "id": "detail-liquid-glass",
  "title": "液态玻璃：五要素材质配方",
  "category": "细节优化",
  "styles": [
    "液态玻璃",
    "玻璃拟态",
    "iOS"
  ],
  "scenario": "卡片/导航/弹窗想要 Apple Liquid Glass 质感时",
  "prompt": "Apply a true Liquid Glass material, not plain blur: every glass panel needs all five properties together — (1) backdrop-blur-xl, (2) translucent fill bg-white/10 on dark or bg-black/5 on light, (3) 1px border border-white/20 to define the edge, (4) soft shadow-xl for depth, and (5) a specular highlight via ring-1 ring-inset ring-white/10 plus a bg-gradient-to-br from-white/20 to transparent overlay so light catches one edge. Keep text on a solid backing or dark enough area so contrast stays at least 4.5:1; without the highlight it is just frosted glass, not liquid glass.",
  "prompt_zh": "液态玻璃五要素缺一不可：强模糊+半透明填充+1px 亮边+柔和阴影+高光描边，文字区保 4.5:1 对比度，只有模糊不算液态玻璃。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ]
}
```

#### SaaS 定价页三档对比 (`landing-pricing-saas`)

```json
{
  "id": "landing-pricing-saas",
  "title": "SaaS 定价页三档对比",
  "category": "落地页官网",
  "styles": [
    "定价",
    "转化",
    "卡片"
  ],
  "scenario": "SaaS 订阅产品定价页",
  "prompt": "Design a SaaS pricing page with 3 tiers (Starter, Pro, Team): short headline plus a monthly/annual toggle at the top with annual showing a 'Save 20%' badge; three equal-width cards with 24px gaps, the middle Pro card highlighted as 'Most Popular' with a colored border, slightly larger scale and a badge; each card shows plan name, price with billing period, one-line who-it-is-for, a primary CTA, and a feature checklist with checkmarks (unavailable features grayed out, not hidden). Below add a full feature-comparison table and an FAQ accordion. Background #FAFAF9, cards white with 1px border #E7E5E4, text #1C1917, one accent color only. No dark patterns, no hidden pricing.",
  "prompt_zh": "SaaS 定价页：月/年切换带省 20% 徽章、三卡等宽中间档高亮为最受欢迎、每卡含人群说明+功能清单、下方对比表+FAQ，无暗黑套路。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ]
}
```

## 2026-11-17 晚 · 费纸张主页系统收集（用户登录抖音后逐条核对）

来源：费纸张抖音主页（抖音号 67394924732），作品 20 条，其中 17 条与 AI 设计/UI 相关，已逐条打开核对；3 条无关（Agent 省钱指南、实测 DeepSeek Flash 做视频、《看不见的城市》）只记标题跳过。用户已关注费纸张并授权持续收集其视频内容。

### 核心条目原文：第6集《四条规则去掉设计里的 AI 味儿》（2026-11-03，作品 7703624707744091446）

片尾提示词框（## 视觉规则）原文：配色：中性色为主，用明暗对比突出主要操作。强调色可选，最多一种。禁用渐变、发光和彩色阴影。／间距：仅用 4 8 12 16 24 32 px。组内间距小于组间间距。／圆角：仅用 6 10 16 px。嵌套圆角：外圆角 = 内圆角 + 内边距。／对齐：同一列元素共用左边缘。另第四条字幕：删掉表情符号、感叹号和装饰徽章。（评论区 WINDQIIIII 的「统一线性图标」是评论者补充，非视频原文，未计入。）

### 第3集《5个小细节》复核补充参数（作品 7699104647889423667）

等宽数字 font-variant-numeric: tabular-nums；同心圆角示例：外层 36 = 内层 20 + 内边距 16，border-radius: calc(20px + 16px)；错开入场时间轴 0 / 400ms / 800ms / 1.2s；平衡换行 h1 { text-wrap: balance; }；阴影代边框 box-shadow: 0 0 1px rgb(0 0 0 / .06), 0 1px 2px -1px rgb(0 0 0 / .06), 0 2px 4px rgb(0 0 0 / .04)。待验证区对应单条验证时按此参数核对。

### 只记录不立条目的两条

- 热成像文字特效（7694648035741044002）：44 行 SVG 滤镜代码画面字号过小未逐行抄录（节点含 feGaussianBlur/feColorMatrix/feBlend 等），无法忠实还原，不立条目。

- 一分钟入门字体设计（7694513054695869723）：字体分类知识（衬线/无衬线/几何/人文等），非生成提示词，只作知识记录，不立条目。

- 文字随音乐变色动效（7699531773557869865）：属产品发布视频文字动画，非 UI 提示词，不立条目。

### 本批新增待验证条目（13 条）

#### 费纸张：四条规则去掉 AI 味儿（原作版） (`detail-feizhang-deai-four`)

```json
{
  "id": "detail-feizhang-deai-four",
  "title": "费纸张：四条规则去掉 AI 味儿（原作版）",
  "category": "细节优化",
  "styles": [
    "去AI味",
    "原作摘录",
    "视觉规则"
  ],
  "scenario": "AI 生成的界面花哨、有廉价感时，一次性套用的视觉规则",
  "prompt": "Apply these visual rules to the UI: Colors — mostly neutral colors for surfaces and text, use light/dark contrast to highlight the primary action; at most one accent color; no gradients, no glow, no colored shadows. Spacing — only use 4, 8, 12, 16, 24, 32 px; spacing inside a group must be smaller than spacing between groups. Corner radius — only use 6, 10, 16 px; for nested corners, outer radius = inner radius + padding. Alignment — elements in the same column share one left edge. Remove decorative emojis, exclamation marks and ornamental badges.",
  "prompt_zh": "费纸张第6集原作视觉规则：中性色为主、明暗对比突出主操作、强调色最多一种、禁渐变/发光/彩色阴影；间距只用 4/8/12/16/24/32；圆角只用 6/10/16、嵌套圆角=内圆角+内边距；同列共用左边缘；删装饰表情/感叹号/徽章。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T22:15:10+08:00",
  "source": "费纸张抖音（已登录核对原文，2026-11-17）"
}
```

#### 费纸张：精致侧边栏优化（原作版） (`detail-sidebar-polish`)

```json
{
  "id": "detail-sidebar-polish",
  "title": "费纸张：精致侧边栏优化（原作版）",
  "category": "细节优化",
  "styles": [
    "侧边栏",
    "原作摘录",
    "间距圆角"
  ],
  "scenario": "已有侧边栏显粗糙时，不改内容配色只做精修",
  "prompt": "Refine this sidebar without changing its content, colors or interactions: keep the existing style; unify font sizes, corner radii and spacing; panels at the same level share the same radius, consistent with neighbouring panels; equal whitespace on both sides of the sidebar; icons slightly smaller than text with consistent icon-text gaps; every row fits its text with enough vertical padding and a generously sized click target; spacing between groups larger than spacing within groups, all following one spacing scale.",
  "prompt_zh": "费纸张第4集原作提示词：保留内容/配色/交互，统一字号圆角间距，同级面板圆角一致、两侧留白一致，图标小于文字、图文间距一致，每行留白与点击区域足够，组间比组内松。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T22:15:10+08:00",
  "source": "费纸张抖音（已登录核对原文，2026-11-17）"
}
```

#### 费纸张：玻璃界面五步配方（原作版） (`detail-glassmorphism-five`)

```json
{
  "id": "detail-glassmorphism-five",
  "title": "费纸张：玻璃界面五步配方（原作版）",
  "category": "细节优化",
  "styles": [
    "玻璃拟态",
    "原作摘录",
    "材质"
  ],
  "scenario": "想要有层次的玻璃拟态（glassmorphism）界面时",
  "prompt": "Create a layered glassmorphism surface in five steps: 1) blur — backdrop-filter blur(28px); 2) saturate — saturate(170%) to enrich the colors behind; 3) overlay white — background rgb(255 255 255 / 10%); 4) bright edge — inset box-shadow 1px 1px 0 rgba(255,255,255,0.4) for a lit rim; 5) refraction — an SVG displacement filter on the edge. Choose background shapes, colors and brightness deliberately so the glass stays translucent while text remains readable. Base CSS: .glass { backdrop-filter: blur(28px) saturate(170%); background: rgb(255 255 255 / 10%); box-shadow: inset 1px 1px 0 #fff6; }",
  "prompt_zh": "费纸张第1集原作五步：模糊→增色→叠白→亮边→折射，附最终 .glass 代码（blur 28px / saturate 170% / 白 10% / inset 亮边），并强调背景形状配色明暗与文字可读性。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T22:15:10+08:00",
  "source": "费纸张抖音（已登录核对原文，2026-11-17）"
}
```

#### 费纸张：卡片滚轮滚动五槽位（原作版） (`detail-card-scroll-slots`)

```json
{
  "id": "detail-card-scroll-slots",
  "title": "费纸张：卡片滚轮滚动五槽位（原作版）",
  "category": "细节优化",
  "styles": [
    "动效",
    "卡片滚动",
    "原作摘录"
  ],
  "scenario": "做卡片轮播/滚动切换、想要滚轮般流畅感时（动效类）",
  "prompt": "Build a fluid card-scrolling effect modelled as a wheel with five fixed slots that control each card's position, height, opacity and blur: hidden -2, capsule -1, expanded 0, capsule +1, hidden +2. The bottom card wraps back to the top when hidden. Handle the header bar, content fade in/out and motion blur during movement. Content can change freely; the slots never change.",
  "prompt_zh": "费纸张原作：把卡片滚动看成滚轮，五个固定槽位（隐藏-2/胶囊-1/展开0/胶囊+1/隐藏+2）控制位置/高度/透明度/模糊，最下卡片隐藏时绕回顶部，内容可换、槽位不变。动效类，验证需 GIF。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T22:15:10+08:00",
  "source": "费纸张抖音（已登录核对原文，2026-11-17）"
}
```

#### 费纸张：卡片三改（原作版） (`detail-card-three-fixes`)

```json
{
  "id": "detail-card-three-fixes",
  "title": "费纸张：卡片三改（原作版）",
  "category": "细节优化",
  "styles": [
    "卡片",
    "原作摘录",
    "对比改版"
  ],
  "scenario": "数据卡片（如步数/统计卡）显平庸时的小改版",
  "prompt": "Improve this data card with three small changes, keeping the data identical: 1) highlight only 'today' (the current item) and mute the rest; 2) replace the border with a soft tinted background fill; 3) add a smooth transition to the switch/toggle interaction.",
  "prompt_zh": "费纸张原作（步数卡片 8,214 步示例）：只突出「今天」、用柔和底色代替边框、给切换加平滑过渡；数据不变，观感更舒服。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T22:15:10+08:00",
  "source": "费纸张抖音（已登录核对原文，2026-11-17）"
}
```

#### 费纸张：侧边栏高亮动效规则（原作版） (`detail-sidebar-motion`)

```json
{
  "id": "detail-sidebar-motion",
  "title": "费纸张：侧边栏高亮动效规则（原作版）",
  "category": "细节优化",
  "styles": [
    "动效",
    "侧边栏",
    "原作摘录"
  ],
  "scenario": "侧边栏选中高亮动画跨组乱滑、扫过无关项时（动效类）",
  "prompt": "Sidebar selection motion rules: interaction feedback animations last 150-250ms; the selected highlight slides only within the same group; when selection crosses to another group it fades out and in instead of sliding; use distinct view-transition-name values per group so the browser never animates the highlight across groups or over unrelated items.",
  "prompt_zh": "费纸张第7集原作动效规则：反馈动效 150–250ms；高亮仅组内滑动，跨组淡入淡出；用不同的 view-transition-name 区分分组。动效类，验证需 GIF。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T22:15:10+08:00",
  "source": "费纸张抖音（已登录核对原文，2026-11-17）"
}
```

#### 费纸张：十种选择控件用法（原作版） (`detail-choice-controls`)

```json
{
  "id": "detail-choice-controls",
  "title": "费纸张：十种选择控件用法（原作版）",
  "category": "细节优化",
  "styles": [
    "控件选型",
    "原作摘录",
    "表单"
  ],
  "scenario": "表单/筛选界面不知道该用哪种选择控件时",
  "prompt": "Choose form selection controls by these rules: checkbox for multiple independent options, toggle switch for instant on/off, radio group for one of few visible options, segmented control for one of a few modes, dropdown select for picking from a short list by browsing, combobox for picking from a long list by typing/searching, toggle button for a single binary state, filter chips for multi-select filtering, slider for approximate numeric ranges, stepper for precise small numeric adjustments. Decide by: when the change takes effect, how many options there are, browse vs search, and the precision needed.",
  "prompt_zh": "费纸张原作：10 种选择控件（复选框/开关/单选组/分段控件/下拉框/组合框/切换按钮/筛选标签/滑块/步进器）按生效时机、选项数量、浏览或搜索、精度四维选型；长列表搜索用组合框，短列表浏览用下拉框。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T22:15:10+08:00",
  "source": "费纸张抖音（已登录核对原文，2026-11-17）"
}
```

#### 费纸张：视觉对齐四项检查（原作版） (`detail-visual-alignment`)

```json
{
  "id": "detail-visual-alignment",
  "title": "费纸张：视觉对齐四项检查（原作版）",
  "category": "细节优化",
  "styles": [
    "对齐",
    "视觉重心",
    "原作摘录"
  ],
  "scenario": "界面几何对齐了但眼睛看着别扭时，做视觉对齐检查",
  "prompt": "Alignment must obey the eye, not just geometry. Audit this UI's visual alignment while keeping the existing layout and interactions: check icon optical center (e.g. play triangles), whitespace balance inside icon+text buttons, the perceived size of circles versus squares, and hanging punctuation for quotes. Report the minimal fix and the reason for each; fix icon offsets inside the SVG itself rather than compensating with margins.",
  "prompt_zh": "费纸张原作提示词：对齐要听眼睛的；逐项检查图标重心、按钮留白、圆形视觉大小、引号悬挂；给最小修改和理由；图标偏移优先在 SVG 内修正，别靠外边距补救。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T22:15:10+08:00",
  "source": "费纸张抖音（已登录核对原文，2026-11-17）"
}
```

#### 费纸张：设置页三步排版（原作版） (`saas-settings-three-steps`)

```json
{
  "id": "saas-settings-three-steps",
  "title": "费纸张：设置页三步排版（原作版）",
  "category": "SaaS后台",
  "styles": [
    "设置页",
    "排版",
    "原作摘录"
  ],
  "scenario": "AI 做的设置页杂乱、框套框时",
  "prompt": "Lay out this settings page in three steps: 1) one setting per row — name on the left, control on the right; 2) remove the outermost frame — the page itself needs no extra card wrapper; 3) group settings under group titles with generous spacing between groups, tight spacing within groups and only hairline dividers between rows. Note: for registration/checkout forms instead put labels above full-width inputs, in fill order, leaving room for error messages and longer content.",
  "prompt_zh": "费纸张第5集原作三步：一项一行（左名右控件）、去掉最外层框、分组加标题（组间多留白、组内少留白、行间细线）；并对比表单场景：名称在上、全宽输入。与待验证区 saas-settings-master-detail 同场景，入库时归同一风格组。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T22:15:10+08:00",
  "source": "费纸张抖音（已登录核对原文，2026-11-17）"
}
```

#### 费纸张：苹果 HIG 落地清单（原作版） (`detail-apple-hig`)

```json
{
  "id": "detail-apple-hig",
  "title": "费纸张：苹果 HIG 落地清单（原作版）",
  "category": "细节优化",
  "styles": [
    "苹果规范",
    "HIG",
    "原作摘录"
  ],
  "scenario": "想让 AI 生成原生级 iOS/macOS 风格界面时",
  "prompt": "Design this interface following Apple Human Interface Guidelines: principles — hierarchy, harmony, consistency; use system components; tap targets at least 44pt; body text contrast at least 4.5:1; support Dynamic Type and Dark Mode. Write the rules into a DESIGN.md, generate with system components, then self-check the result against the checklist (foundations, interaction patterns, components, platform differences).",
  "prompt_zh": "费纸张原作：HIG 四大块（基础/交互模式/组件/平台差异）、三原则（层级/和谐/一致），落地标准 44pt 点击区、正文对比度 ≥4.5:1、动态字号与深色模式；规则写进 DESIGN.md 并按清单自查。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T22:15:10+08:00",
  "source": "费纸张抖音（已登录核对原文，2026-11-17）"
}
```

#### 费纸张：动效四技巧（原作版） (`detail-motion-four`)

```json
{
  "id": "detail-motion-four",
  "title": "费纸张：动效四技巧（原作版）",
  "category": "细节优化",
  "styles": [
    "动效",
    "原作摘录",
    "曲线"
  ],
  "scenario": "菜单/抽屉/图标动效显生硬时（动效类）",
  "prompt": "Make UI motion natural with four techniques: 1) interruptible — animations can be interrupted at any moment by new input; 2) gentle exit — elements leave softly, slightly faster and fading; 3) soft switch — crossfade state changes with opacity + scale + blur instead of hard cuts (especially icons); 4) ease-out entrance — entrances decelerate with an ease-out curve. Apply to menus, drawers and icons.",
  "prompt_zh": "费纸张原作四技巧：随时打断、轻轻退场、柔和切换（opacity·scale·blur）、入场缓出。动效类，验证需 GIF。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T22:15:10+08:00",
  "source": "费纸张抖音（已登录核对原文，2026-11-17）"
}
```

#### 费纸张：反光金属卡片五句（原作版） (`detail-metal-card-webgl`)

```json
{
  "id": "detail-metal-card-webgl",
  "title": "费纸张：反光金属卡片五句（原作版）",
  "category": "细节优化",
  "styles": [
    "金属质感",
    "WebGL",
    "原作摘录"
  ],
  "scenario": "想要可运行的反光金属质感卡片组件时",
  "prompt": "Build a runnable React + WebGL2 reflective metal card, 320x500px, radius 24px, card number 0001 2345 6789, in five parts: 1) Environment — canvas with a blue board, warm sphere and white light bars as the reflection scene, upload as texture per frame, blur in two passes, desaturate samples. 2) Reflection — beveled micro-noise normal map N; with I = camera-to-surface and R = reflect(I, N), q = R.xy / max(R.z, 0.2), UV = vUv + 0.12 * q; planar texture only, no panorama or gradient fills. 3) Interaction — spring 120/16, tilt target ±12 degrees, CSS and normals share the same angle, ease back on leave. 4) Layers — canvas + HTML title and number + highlight border; no people, cameras or external images. 5) Delivery — component with complete GLSL/CSS and run command; check DPR/size per frame, redraw only on change, WebGL fallback, cleanup on unmount.",
  "prompt_zh": "费纸张第2集原作五句：环境/反射/交互/图层/交付，React+WebGL2 金属卡片 320×500、圆角 24，含反射公式与弹簧参数 120/16、倾斜 ±12°。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T22:15:10+08:00",
  "source": "费纸张抖音（已登录核对原文，2026-11-17）"
}
```

#### 费纸张：跟手纹理三条规则（原作版） (`detail-texture-follow`)

```json
{
  "id": "detail-texture-follow",
  "title": "费纸张：跟手纹理三条规则（原作版）",
  "category": "细节优化",
  "styles": [
    "动效",
    "纹理",
    "原作摘录"
  ],
  "scenario": "想要指针跟随的纹理/十字高光特效时（动效类）",
  "prompt": "Create a pointer-following texture effect from 420 thin strips clipped into small cells, using three rules and CSS math only, no libraries: 1) clip — each strip is clipped inside its small cell; 2) turn — every strip rotates toward the finger/pointer; 3) widen — strips aligned horizontally/vertically with the pointer widen, forming a bright cross.",
  "prompt_zh": "费纸张原作三条规则：裁切、转向、变宽；420 根细条裁进小格、朝手指转向，横竖对齐的变宽形成亮十字，不用库。动效类，验证需 GIF。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T22:15:10+08:00",
  "source": "费纸张抖音（已登录核对原文，2026-11-17）"
}
```

## 2026-11-17 夜 · SpicyTater 主页系统收集（用户指示关注并收集）

作者：SpicyTater（抖音号 xinxinyaokuaileo，湖南，独立开发者），作品 62 条，设计相关 38 条；已关注（粉丝 6056→6057）。其第22集《后台菜单交互》即 2026-11-17 用户最早分享的那条链接（7695264996816620863）。

**重要局限**：本次浏览器里视频无法播放（播放器一直 00:00 加载），要点来自页面文案 + 抖音「章节要点」AI 摘要，**不是视频逐字原文**；条目已在 source 里如实标注「章节摘录」。8 条无章节要点且文案为模板/错贴，未能提取：Vibe 第33集（查数据）、第27集粒子交互、第23集高级布局、第19集编辑工具、第18集任务反馈、第17集标题动效、第8集图表动画、第4集展开面板——只在来源档案中记录，暂不立条目，待能播放时补。另有 12 条已摘录但本批未立条目（图片材质、电影感、触感、5种导航、命令面板、脱模板方法论、官网滚动、加载7种、弹窗7种、术语库、设置页以外的 Vibe 集数等），要点已在本节档案中保留，可后续提升为条目。作者称其 Skills 已开源在 GitHub 仓库 `spt-ui-interaction-skills`（文案说法，本次未核到确切网址），若后续取得仓库原文，可据原文升级这些条目。

### 本批新增待验证条目（20 条）

#### SpicyTater：后台菜单交互 8 类选型 (`spt-admin-menu`)

```json
{
  "id": "spt-admin-menu",
  "title": "SpicyTater：后台菜单交互 8 类选型",
  "category": "SaaS后台",
  "styles": [
    "后台菜单",
    "交互选型",
    "章节摘录"
  ],
  "scenario": "做后台/侧栏导航菜单，不知道用哪种展开方式时",
  "prompt": "Choose admin menu patterns by structure: sliding highlight block for sidebar nav and top tabs; expand-in-place submenus for hierarchical project/file trees; top drop-down panel when there are few sections but multiple entries (mouse and keyboard); floating bottom dock for frequent entries (magnify on hover, neighbours make room); command palette when entries are many (search + keyboard selection); status dots and count badges for new messages and pending items, animating the number when it changes. Pick the combination by section count, hierarchy depth and usage frequency; entries must stay obvious and reachable.",
  "prompt_zh": "SpicyTater 第22集（2062赞）：滑动高亮块/就地展开/顶部下落面板/底部悬浮停靠栏/命令面板/状态点徽标等 8 类后台菜单，按栏目数量、层级、频率选组合。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7695264996816620863"
}
```

#### SpicyTater：App 交互动画 10 种 (`spt-app-animation-10`)

```json
{
  "id": "spt-app-animation-10",
  "title": "SpicyTater：App 交互动画 10 种",
  "category": "细节优化",
  "styles": [
    "动效",
    "App交互",
    "章节摘录"
  ],
  "scenario": "给 App/小程序加有质感的交互动画时（动效类）",
  "prompt": "Implement these app interaction animations: theme switch expands in a circle from the tap point; drag-to-reorder where other rows yield space and the dragged row lifts out; batch check where checkmarks pop in sequence with a slight elastic scale; slider snap — after release the thumb glides with inertia then snaps to the nearest tick; text expand where container height animates with content and the arrow rotates 180°; stepper progress that overshoots slightly then settles with a soft rebound; linked switches giving visual feedback across the group without changing state; card delete where the card flies along a curve to the delete icon, shrinking, rotating and fading; card stacking where the top card pauses then is compressed by the next; tag selection where the chosen tag scales up and neighbours shift aside.",
  "prompt_zh": "SpicyTater 第9集（1926赞/2230收藏）：主题圆形扩散、拖拽排序、批量勾选弹性、滑杆吸附、文本展开、步骤条回弹、开关联动、卡片删除飞出、卡片堆叠、标签选择等 10 种交互动画。动效类，验证需 GIF。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7682010237578136858"
}
```

#### SpicyTater：下拉组件 8 种选型 (`spt-dropdown-8`)

```json
{
  "id": "spt-dropdown-8",
  "title": "SpicyTater：下拉组件 8 种选型",
  "category": "细节优化",
  "styles": [
    "下拉",
    "组件选型",
    "章节摘录"
  ],
  "scenario": "做下拉选择，不知道用哪种下拉形态时",
  "prompt": "Pick the dropdown form by the job: plain Dropdown for choosing one from a few fixed options; grouped dropdown (bus/group headers) when options are many; Typeahead searchable dropdown filtering as you type; Split action button — main area runs the primary action, the drop zone offers related actions; Date range picker via calendar for start/end; Cascade select for parent-child options, choosing a level expands the next; Tag Picker for multi-select, keeping chosen tags visible; Mega Menu for content-rich sites with many sections in multiple columns. State the option count, grouping, search and action model when asking an AI to build one.",
  "prompt_zh": "SpicyTater 第7集（1057赞/1239收藏）：Dropdown/分组下拉/Typeahead/拆分按钮/日期范围/级连/Tag Picker/Mega Menu 8 种下拉，按数量、分组、搜索、操作选型。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7680742171204439296"
}
```

#### SpicyTater：浮层 6 种选型与 3 个坑 (`spt-overlay-six`)

```json
{
  "id": "spt-overlay-six",
  "title": "SpicyTater：浮层 6 种选型与 3 个坑",
  "category": "细节优化",
  "styles": [
    "浮层",
    "弹窗选型",
    "章节摘录"
  ],
  "scenario": "纠结用弹窗、抽屉还是新页面时",
  "prompt": "Choose overlay components by weight: Tooltip — quietest, small text on hover, gone on leave; Toast — fleeting, for operation results; Alert — persistent, for important notices; Modal — for important decisions; plus Popconfirm for inline confirmation and Drawer for side content. Avoid three traps: don't close modals on backdrop click when there's unsaved input (add draft autosave instead); don't demand confirmation for deletable-and-undoable actions; write the action's result directly on the button. Long forms don't belong squeezed inside a small modal — use a drawer or a full page.",
  "prompt_zh": "SpicyTater 第28集（848赞/843收藏）：Tooltip/Toast/Alert/Modal/Popconfirm/Drawer 选型 + 三坑（蒙层误关配草稿保存、可撤销别弹窗确认、按钮直写结果）。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7699199951179418907"
}
```

#### SpicyTater：交互质感 8 指令 (`spt-app-texture-8`)

```json
{
  "id": "spt-app-texture-8",
  "title": "SpicyTater：交互质感 8 指令",
  "category": "细节优化",
  "styles": [
    "动效",
    "质感",
    "章节摘录"
  ],
  "scenario": "想要 App 交互有物理质感、遵循统一运动规则时（动效类）",
  "prompt": "Give interface motion one consistent physics: magnetic snap — resistance while approaching a target, acceleration inside the snap range, elastic settle at the end; liquid deformation — dragged cards stretch at edges and recover with a rebound on release; 3D parallax — foreground moves most, midground less, background slightly; center focus — items near screen center scale up, leaving items shrink or fade in weight; liquid tab — the selected background stretches horizontally, contracts past the midpoint, then a slight rebound; image expansion — from thumbnail to fullscreen with continuous direction and position; gesture-driven transitions whose progress follows the finger and completes past a threshold; collision push — elements have different motion weights, pushing and rebounding on contact.",
  "prompt_zh": "SpicyTater 第10集（511赞）：磁吸/液态形变/3D视差/中心聚焦/液态tab/图片展开/手势转场/碰撞推挤 8 种质感指令，核心是全场遵循同一套运动规则。动效类，验证需 GIF。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7682010730085862696"
}
```

#### SpicyTater：App 高级交互 7 指令 (`spt-app-gestures-7`)

```json
{
  "id": "spt-app-gestures-7",
  "title": "SpicyTater：App 高级交互 7 指令",
  "category": "细节优化",
  "styles": [
    "手势",
    "App交互",
    "章节摘录"
  ],
  "scenario": "做移动端手势交互、总觉得不跟手时",
  "prompt": "Implement these mobile gesture rules: edge-swipe back — drag from the screen edge pulls the previous page with the finger, release decides by distance, velocity and direction; press-and-slide-off cancel — pressing sinks the button, sliding out weakens the press state, releasing outside cancels the tap; partial text transition — when filters change, only the changed text transitions, unchanged text stays put; gesture direction lock — decide the direction at gesture start and never flip mid-gesture; interruptible animation takeover — a gesture can seize a running animation and continue from the element's current position; landing preview — while dragging a card horizontally, preview its predicted landing spot and land exactly there; boundary damping — pulling past the top keeps moving with increasing resistance, then springs back on release.",
  "prompt_zh": "SpicyTater 第11集（1225赞）：跟手返回/滑出取消/文字局部过渡/方向锁定/动画中途接管/落点预览/边界阻尼 7 条高级交互指令。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7682681851068026152"
}
```

#### SpicyTater：展开动画 6 种 (`spt-expand-animations`)

```json
{
  "id": "spt-expand-animations",
  "title": "SpicyTater：展开动画 6 种",
  "category": "细节优化",
  "styles": [
    "动效",
    "展开",
    "章节摘录"
  ],
  "scenario": "小组件需要展开成大内容时（动效类）",
  "prompt": "Use these expansion patterns: dot-to-capsule — a circle expands into a capsule carrying a status or short message; capsule-to-card — a compact capsule expands into a full info card with more content and actions; compact-to-panel — the same feature appears compact first and expands into a full control panel when needed; radius morph — changing corner radius morphs one form smoothly into another; size morph — animate width and height so a small widget becomes a larger module; content reflow — after expanding, inner content rearranges, and collapsing retraces the same path back to the small entry. Always specify start state, end state, which properties change, and how it collapses back.",
  "prompt_zh": "SpicyTater 第6集（308赞）：圆点变胶囊/胶囊变信息卡/紧凑态展开/圆角形态过渡/尺寸变形/内容重排，描述时讲清起止状态、变化属性、收回方式。动效类，验证需 GIF。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7680037853694381327"
}
```

#### SpicyTater：像产品不像作业的六步 (`spt-product-not-homework`)

```json
{
  "id": "spt-product-not-homework",
  "title": "SpicyTater：像产品不像作业的六步",
  "category": "细节优化",
  "styles": [
    "方法论",
    "产品级",
    "章节摘录"
  ],
  "scenario": "AI 做的页面总像模板作业、想做到产品级时",
  "prompt": "Take an AI-built page from homework to product in six steps: 1) design system first — unify fonts, colors, radii, spacing and component styles; 2) page structure — clarify navigation, content hierarchy and layouts across screen sizes; 3) interaction flows — define what happens on every click plus empty, loading, success and failure states; 4) concept image to confirm direction and visual focus; 5) real functionality — buttons, forms and data flows actually work; 6) detail pass — assets, responsive layout and interaction feedback.",
  "prompt_zh": "SpicyTater 第14集（271赞，12分钟）：先定规范→搭结构→补交互流程（含空/加载/成功/失败态）→概念图定方向→落地真实功能→打磨细节。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7687151464640220456"
}
```

#### SpicyTater：导航组件 7 种选型 (`spt-nav-7`)

```json
{
  "id": "spt-nav-7",
  "title": "SpicyTater：导航组件 7 种选型",
  "category": "细节优化",
  "styles": [
    "导航",
    "组件选型",
    "章节摘录"
  ],
  "scenario": "给页面选导航组件时",
  "prompt": "Choose navigation components precisely: Tabs for switching parallel content within one page; Segmented Control for fast switching between 2-3 views (fewer options, tighter layout); Breadcrumb for deep hierarchies, showing current position and quick return; Pagination for browsing large content by page; Stepper for process progress, showing done and remaining steps; Sidebar for feature-rich backends/desktops, fixed main entries with the current page highlighted; Bottom Navigation for mobile, 3-5 frequent entries fixed at the bottom. When asking an AI, name the component, its placement, what it switches and what gets highlighted.",
  "prompt_zh": "SpicyTater 第3集（227赞）：Tabs/Segment Control/Breadcrumb/Pagination/Stepper/Sidebar/Bottom Navigation 7 种导航的适用与描述要点。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7678886080376098086"
}
```

#### SpicyTater：拖拽动效 6 种 (`spt-drag-6`)

```json
{
  "id": "spt-drag-6",
  "title": "SpicyTater：拖拽动效 6 种",
  "category": "细节优化",
  "styles": [
    "拖拽",
    "动效",
    "章节摘录"
  ],
  "scenario": "界面需要拖拽类交互时",
  "prompt": "Implement the right drag pattern for the job: drag-and-drop — drag an object to a target zone, release to place or move; drag-to-sort — drag a list item while others auto-shift, save the new order on release; slider drag — drag a thumb to adjust a value, progress or option; drag-to-resize — drag an edge or corner to change width/height; drag-to-select — drag on empty space to draw a selection box over multiple objects; drag-to-upload — drag files into a marked zone with clear feedback. Each needs its drag direction, draggable area, target and release feedback spelled out.",
  "prompt_zh": "SpicyTater 第5集（192赞）：拖放/拖拽排序/滑块拖动/拖拽调整大小/拖拽框选/拖拽上传 6 种，描述须含方向、区域、目标与松手反馈。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7679648378807979305"
}
```

#### SpicyTater：空间卡片编排 6 种 (`spt-card-arrangements`)

```json
{
  "id": "spt-card-arrangements",
  "title": "SpicyTater：空间卡片编排 6 种",
  "category": "细节优化",
  "styles": [
    "卡片编排",
    "展示",
    "章节摘录"
  ],
  "scenario": "作品集/相册想要非常规的卡片展示方式时",
  "prompt": "Arrange showcase cards spatially: fan spread — cards fan around a pivot like playing cards, clicking one lifts it (covers, collections); depth stack — cards offset along depth for browsing one by one; cylinder ring — cards wrap a cylinder, drag to rotate (portfolios, albums, projects); sphere layout — cards distributed on a sphere for exploring photos/inspiration; spiral layout — cards along a spiral path (project stages, timelines); wave matrix — a tidy grid where neighbours offset in rhythm (photo walls, overviews). When asking an AI, specify the arrangement, the browsing method, how selection is shown and where cards return on close.",
  "prompt_zh": "SpicyTater 第15集（171赞）：扇形展开/纵深叠排/圆柱环绕/球面排布/螺旋排布/波浪矩阵 6 种空间卡片编排及适用场景。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7687510825015315712"
}
```

#### SpicyTater：点击区域与反馈五查 (`spt-tap-feedback`)

```json
{
  "id": "spt-tap-feedback",
  "title": "SpicyTater：点击区域与反馈五查",
  "category": "细节优化",
  "styles": [
    "点击热区",
    "反馈",
    "章节摘录"
  ],
  "scenario": "界面精致但点不动、点不准时",
  "prompt": "Audit tap usability: hit area — icons may be small but buttons must not shrink with them; size touch targets in CSS pixels adjusted per platform; hot-zone conflicts — fix overlaps by adjusting spacing and layout; distinguish tap from drag so gestures never misfire; feedback must be explicit — pressed state change, submitting state, and failure notice. When briefing an AI, always check: hit areas, hot-zone conflicts, links, tap-vs-drag distinction, and feedback states.",
  "prompt_zh": "SpicyTater 第32集：点击范围（图标小按钮不能小）/热区冲突/区分点击与拖动/点击反馈明确（按下变化、提交状态、失败提示）五查。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7705257186435403058"
}
```

#### SpicyTater：卡片/列表/表格按任务选型 (`spt-layout-by-task`)

```json
{
  "id": "spt-layout-by-task",
  "title": "SpicyTater：卡片/列表/表格按任务选型",
  "category": "细节优化",
  "styles": [
    "布局选型",
    "数据展示",
    "章节摘录"
  ],
  "scenario": "挑图片、找文件、比数据不知道用卡片还是列表时",
  "prompt": "Match data layout to the task: cards for browsing visual items (photos, furniture) — big image first, name in one line; lists for finding a known file — small thumbnail aside, full name expanded; tables for comparing data — show name, dimensions, format with the same data aligned in columns. When switching layouts, preserve the search conditions and selection state so the user never has to redo their work.",
  "prompt_zh": "SpicyTater 第29集：卡片适合展示、列表适合查找、表格适合比数据；切换布局保留搜索条件与勾选状态。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7699718828174937379"
}
```

#### SpicyTater：选择器与菜单别混用 (`spt-picker-menu`)

```json
{
  "id": "spt-picker-menu",
  "title": "SpicyTater：选择器与菜单别混用",
  "category": "细节优化",
  "styles": [
    "下拉",
    "选型",
    "章节摘录"
  ],
  "scenario": "跟 AI 说做个下拉框总不好用时",
  "prompt": "Distinguish pickers from menus: a picker selects a value, a menu issues an action. Few options can be shown directly; when they don't fit, use a picker; two options are not automatically a toggle switch. Many options need grouping and a scrollable list that never overflows the screen. Familiar values can be typed directly; when space is tight, flip the opening direction. When briefing an AI, state: what is being chosen, what happens after choosing, and where the result stays. A music app's 'pick a song and keep browsing' is not the same as 'choose an action and dismiss'.",
  "prompt_zh": "SpicyTater 第31集：选择器用于选择、菜单用于操作；选项少直展、多则分组滚动；明确选什么、选完做什么、结果留在哪。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7701961806482279715"
}
```

#### SpicyTater：底部浮层 5 种区分 (`spt-bottom-layers`)

```json
{
  "id": "spt-bottom-layers",
  "title": "SpicyTater：底部浮层 5 种区分",
  "category": "移动端App",
  "styles": [
    "底部浮层",
    "组件选型",
    "章节摘录"
  ],
  "scenario": "移动端底部弹出的东西分不清该用哪种时",
  "prompt": "Tell bottom layers apart: Action Sheet — bottom action panel, dismisses right after choosing; Bottom Sheet — expandable sheet that stays where released, its inner content can scroll (e.g. keep browsing songs); Snack Bar — bottom notice whose height follows content and screen, never full-screen by default; Tour — guided walkthrough that skips steps the user already knows; Lightbox — image viewer for detail, without leaving the page; plus inline validation — show the error where it happened.",
  "prompt_zh": "SpicyTater 第30集：Action Sheet/Bottom Sheet/Snack Bar/Tour/Lightbox 五种底部浮层的区别与行内验错。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7701274323436227880"
}
```

#### SpicyTater：多语言按钮防挤爆 (`spt-i18n-overflow`)

```json
{
  "id": "spt-i18n-overflow",
  "title": "SpicyTater：多语言按钮防挤爆",
  "category": "细节优化",
  "styles": [
    "国际化",
    "响应式",
    "文案摘录"
  ],
  "scenario": "界面切换语言后按钮被长译文挤爆时",
  "prompt": "Design buttons for long translations: never shrink the font to force-fit long text; let buttons grow with content, allow the action bar to wrap, or switch to full-width taller buttons; then verify with real translations, narrow windows and larger font sizes, checking for clipping, collisions and horizontal overflow.",
  "prompt_zh": "SpicyTater 第35集：长译文别缩字硬塞；让按钮增长、操作栏换行或全宽增高；用真实译文+窄窗口+大字号查裁切/碰撞/横向溢出。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7707974421738278187"
}
```

#### SpicyTater：圆角看整体轮廓 (`spt-radius-contour`)

```json
{
  "id": "spt-radius-contour",
  "title": "SpicyTater：圆角看整体轮廓",
  "category": "细节优化",
  "styles": [
    "圆角",
    "轮廓",
    "文案摘录"
  ],
  "scenario": "圆角越调越大还是不像设计稿时",
  "prompt": "Fix corner radius as a whole contour, not a number: stop only increasing the radius; lock the element's size and layout first, then compare the corner transition curve; make image clipping, strokes and shadows all follow the same contour; finally re-check at normal size and in narrow cards for show-through gaps and squeezed text.",
  "prompt_zh": "SpicyTater 第34集：别只改半径；锁尺寸布局、比转弯过渡、让裁切/描边/阴影沿用同一轮廓、回正常与窄卡片查露底挤字。与已验证的同心圆角互补。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7707970051038645546"
}
```

#### SpicyTater：聊天页滚动位置锚定 (`spt-chat-scroll-anchor`)

```json
{
  "id": "spt-chat-scroll-anchor",
  "title": "SpicyTater：聊天页滚动位置锚定",
  "category": "AI产品",
  "styles": [
    "聊天界面",
    "滚动",
    "文案摘录"
  ],
  "scenario": "聊天页新消息一来就把用户拽走时",
  "prompt": "Anchor chat scrolling to the reader: new messages may keep streaming in, but never decide for the user where they are reading; when the user scrolls up, pause auto-follow; resume following when they return to the bottom; when loading history above, keep the currently read message exactly in place.",
  "prompt_zh": "SpicyTater 第36集（2026-11-17 当天新作）：上翻暂停跟随、回到底部恢复、加载历史保住当前消息位置。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7707976118627798312"
}
```

#### SpicyTater：图片交互 7 种 (`spt-image-interactions-7`)

```json
{
  "id": "spt-image-interactions-7",
  "title": "SpicyTater：图片交互 7 种",
  "category": "细节优化",
  "styles": [
    "图片交互",
    "动效",
    "章节摘录"
  ],
  "scenario": "给图片展示加高级交互时（多为动效类）",
  "prompt": "Add advanced image interactions: before-after slider — drag a divider to change the revealed range; mask reveal — pointer or finger movement uncovers the image; pixel transition — pixel blocks cover the frame then dissolve to reveal the next image; ripple distortion — ripples follow the pointer and decay after it stops; sticker peel — the image peels from a corner like a sticker, revealing content beneath; image trail — images spawn along the pointer path and shrink/fade after a pause; glare hover — a highlight follows the pointer across the card.",
  "prompt_zh": "SpicyTater 图片交互篇：前后对比滑块/遮罩揭示/像素转场/水波扭曲/贴纸揭起/图片拖尾/悬停反光 7 种。动效类，验证需 GIF。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7682679805443149108"
}
```

#### SpicyTater：无限画布 5 指令 (`spt-infinite-canvas`)

```json
{
  "id": "spt-infinite-canvas",
  "title": "SpicyTater：无限画布 5 指令",
  "category": "细节优化",
  "styles": [
    "无限画布",
    "协作工具",
    "章节摘录"
  ],
  "scenario": "做白板/无限画布类产品时",
  "prompt": "Build infinite-canvas interactions: pan & zoom — zoom around the pointer position, drag empty space to pan, cards keep relative positions; multi-selection & grouping — rubber-band select and group, moving a group keeps internal distances; connector binding — connectors bind to cards and anchor points, paths update while dragging, support reconnect and delete; auto layout — arrange by content type while preserving connectors and groups, with undo; minimap navigation — minimap shows content distribution and the current viewport, click to jump, drag the viewport box.",
  "prompt_zh": "SpicyTater 第13集：缩放中心/框选成组/连线绑定/自动布局/小地图导航 5 条无限画布指令。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-17T23:11:51+08:00",
  "source": "SpicyTater 抖音（2026-11-17 收集；视频未能播放，要点据页面文案与抖音章节要点摘录，非逐字原文）",
  "source_video": "https://www.douyin.com/video/7684165291919543586"
}
```

## 2026-11-18 · 公开渠道收集（StyleKit / ByteMint / Superdesign / YouTube 车机教程）

来源核对：新拟态提示词见 Vibe Coder《Web Design Guide》1.2 节（搜索结果原文）；孟菲斯/包豪斯风格定义见 StyleKit 151 风格库与 ByteMint UI 提示词库（搜索结果原文），提示词按风格定义原创改写；交易邮件提示词见 Superdesign《UI Design Prompts》(2026) 第 8 节（已打开页面核对原文）；车机提示词据 YouTube《How to Vibe Code a Car Dashboard with Claude》简介中的计划提示词摘要改写。以上 5 条均为库里没有的风格/场景（新拟态、孟菲斯、包豪斯、车机 UI、邮件模板），只进待验证区。

#### 新拟态音乐播放器 (`style-neumorphism-player`)

```json
{
  "id": "style-neumorphism-player",
  "title": "新拟态音乐播放器",
  "category": "内容社交",
  "styles": [
    "新拟态",
    "柔和立体",
    "音乐播放器"
  ],
  "scenario": "音乐播放器/控制面板想要柔和立体触感时",
  "prompt": "Create a neumorphism music player dashboard on a #e0e5ec background. Build raised circular play/pause buttons using dual box-shadows: box-shadow: 6px 6px 12px #b8bec7, -6px -6px 12px #ffffff. Add pressed (active) state with inset shadows: inset 4px 4px 8px #b8bec7, inset -4px -4px 8px #ffffff. Include a volume slider and a track progress bar in the same neumorphic style; album art sits in a soft recessed well, track title and artist in dark gray. Keep every element the same #e0e5ec tone so depth comes only from shadows, and keep text contrast readable.",
  "prompt_zh": "新拟态音乐播放器：#e0e5ec 同色底、双向阴影做出凸起与按压、圆形播放键+音量滑杆+进度条，深度只靠阴影，文字对比度要可读。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-18T08:20:00+08:00",
  "source": "Vibe Coder《Web Design Guide》1.2 新拟态节（搜索结果原文核对，2026-11-18）"
}
```

#### 孟菲斯撞色落地页 (`landing-memphis`)

```json
{
  "id": "landing-memphis",
  "title": "孟菲斯撞色落地页",
  "category": "落地页官网",
  "styles": [
    "孟菲斯",
    "撞色",
    "几何"
  ],
  "scenario": "创意/潮流品牌落地页想要 80 年代孟菲斯活力时",
  "prompt": "Design a landing page in Memphis style, the 80s Italian design movement: bold geometric shapes (circles, triangles, squiggles, grids), vivid contrasting colors (hot pink, yellow, teal, black), irregular playful patterns that break the grid, thick black outlines, oversized geometric headline type. Hero with a big geometric composition, feature cards as tilted color blocks with hard shadows, playful scattered shapes across sections. Keep the copy short and the layout energetic but readable; one clear primary CTA.",
  "prompt_zh": "孟菲斯风落地页：大胆几何图形+高饱和撞色+不规则图案+粗黑描边，活力十足但文案要短、主按钮唯一。",
  "tools": [
    "v0",
    "Lovable",
    "Framer"
  ],
  "group": {
    "id": "landing-styles",
    "name": "落地页官网 · 风格组"
  },
  "variant_label": "孟菲斯撞色几何",
  "added_at": "2026-11-18T08:20:00+08:00",
  "source": "StyleKit 151 风格库 + ByteMint UI 提示词库孟菲斯条目（搜索结果原文核对；提示词按风格定义原创改写，同类收集，2026-11-18）"
}
```

#### 包豪斯几何官网 (`landing-bauhaus`)

```json
{
  "id": "landing-bauhaus",
  "title": "包豪斯几何官网",
  "category": "落地页官网",
  "styles": [
    "包豪斯",
    "几何",
    "现代主义"
  ],
  "scenario": "设计/建筑/文化机构官网想要包豪斯现代主义时",
  "prompt": "Design a website in Bauhaus style: functionalist modernism built only from circles, squares and triangles, thick black borders, hard offset shadows, and pure Bauhaus primaries (red, blue, yellow) plus black and off-white. Asymmetric architectural layout, oversized geometric headline, grid-based sections, no gradients, no rounded corners, no decoration beyond geometry. Form follows function — every shape earns its place.",
  "prompt_zh": "包豪斯风官网：只用圆/方/三角+粗黑边+硬偏移阴影+红蓝黄三原色，非对称建筑感布局，无渐变无圆角。",
  "tools": [
    "v0",
    "Framer",
    "Cursor"
  ],
  "group": {
    "id": "landing-styles",
    "name": "落地页官网 · 风格组"
  },
  "variant_label": "包豪斯几何原色",
  "added_at": "2026-11-18T08:20:00+08:00",
  "source": "StyleKit 151 风格库 + ByteMint UI 提示词库包豪斯条目（搜索结果原文核对；提示词按风格定义原创改写，同类收集，2026-11-18）"
}
```

#### 车机中控屏：特斯拉风 (`car-infotainment-tesla`)

```json
{
  "id": "car-infotainment-tesla",
  "title": "车机中控屏：特斯拉风",
  "category": "车机出行",
  "styles": [
    "车机",
    "深色",
    "信息娱乐"
  ],
  "scenario": "车机/中控大屏 UI 设计时",
  "prompt": "Design a Tesla-style car infotainment screen, 1280x720 landscape touchscreen, plain HTML/CSS/JS, no photos: left third shows a top-down car in inline SVG, gear selector P R N D, large speed readout, battery percentage and range; right panel shows a stylised city map with a blue route line, next-turn card and ETA; bottom dock holds driver temperature, music controls, fan speed and seat controls. Colors: base #0B0D10, glass panels #15181D, borders #262B33, accent cyan #2FD3FF, text #E8ECF1. Big touch targets, glanceable while driving, no small text.",
  "prompt_zh": "特斯拉风车机中控：1280×720 横屏、左车况+中地图+下快捷坞，深色玻璃面板+青色强调色，驾驶时一眼可读。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-18T08:20:00+08:00",
  "source": "YouTube《How to Vibe Code a Car Dashboard with Claude》（据视频简介的计划提示词摘要改写，同类收集，2026-11-18）"
}
```

#### 交易邮件模板：欢迎/验证 (`email-transactional`)

```json
{
  "id": "email-transactional",
  "title": "交易邮件模板：欢迎/验证",
  "category": "邮件模板",
  "styles": [
    "邮件",
    "交易邮件",
    "极简"
  ],
  "scenario": "欢迎/验证类交易邮件模板设计时",
  "prompt": "Design a welcome / email-verification transactional email. Single-column layout, max 600px wide, works in dark and light mail clients. Structure: small logo at top, a clear headline, one short paragraph of context, one prominent primary button (the single action), a plain-text fallback link under it, and a simple footer (company, address, unsubscribe). Visual system: minimal, high-contrast, one brand color on the button only, system fonts, generous padding. Tone: warm and human, one sentence of personality. Avoid image-only emails, multiple competing CTAs, and tiny tap targets.",
  "prompt_zh": "交易邮件（欢迎/验证）：单栏 600px、一个主按钮+纯文本备用链接、系统字体、品牌色只用在按钮上，深浅邮件客户端都可用。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ],
  "added_at": "2026-11-18T08:20:00+08:00",
  "source": "Superdesign《UI Design Prompts: A Copy-Paste Library for Real Interfaces (2026)》第 8 节（已打开页面核对原文，括号占位按通用版整理，2026-11-18）"
}
```
