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

### 字体层级：三级标题拉开层次 (`detail-type-hierarchy`)

```json
{
  "id": "detail-type-hierarchy",
  "title": "字体层级：三级标题拉开层次",
  "category": "细节优化",
  "styles": [
    "字体",
    "层级",
    "可读性"
  ],
  "scenario": "界面看着平/没重点时的字体优化",
  "prompt": "Improve this UI's typography hierarchy: only three heading levels plus body and caption text; page title 28px semibold, section title 18px medium, body 14px regular with 1.6 line height, captions 12px in gray; use weight and size — not color — to create hierarchy; limit the design to one font family and at most 4 font sizes per screen; make numbers in data areas tabular and slightly larger.",
  "prompt_zh": "字体只留三级标题+正文+小字：靠字重和大小分层不用颜色，一屏最多 4 种字号，正文行高 1.6，数据数字放大用等宽数字。",
  "tools": [
    "v0",
    "Cursor",
    "Qoder"
  ]
}
```

### 阴影与边框：细边框代替重阴影 (`detail-shadow-border`)

```json
{
  "id": "detail-shadow-border",
  "title": "阴影与边框：细边框代替重阴影",
  "category": "细节优化",
  "styles": [
    "阴影",
    "边框",
    "轻量"
  ],
  "scenario": "卡片显脏/显廉价时的质感优化",
  "prompt": "Fix the cheap look of these cards: replace heavy drop shadows with a 1px border (#0000000F) plus one very soft shadow (0 1px 2px rgba(0,0,0,0.04)); unify corner radius to 12px everywhere; remove inner shadows and glow effects; interactive cards may lift slightly on hover with a deeper shadow, static cards stay flat. The result should feel like Linear/Notion — quiet and precise.",
  "prompt_zh": "卡片去廉价感：重阴影换成 1px 细边框+一层极淡阴影，圆角统一 12px，删内阴影和发光，Linear/Notion 式安静精准。",
  "tools": [
    "v0",
    "Cursor"
  ]
}
```

### 对齐强迫症：左边缘一条线 (`detail-alignment-grid`)

```json
{
  "id": "detail-alignment-grid",
  "title": "对齐强迫症：左边缘一条线",
  "category": "细节优化",
  "styles": [
    "对齐",
    "网格",
    "秩序感"
  ],
  "scenario": "元素参差不齐/看着歪时的对齐修正",
  "prompt": "Audit and fix alignment in this UI: every text block, icon and button in a column must share the same left edge; icon sizes unified to 20px inside 40px touch targets; list rows share identical height and padding; form labels and inputs align to one baseline grid; no element may sit at a unique random offset — if it cannot align, remove it. Pixel-perfect order is the goal.",
  "prompt_zh": "对齐修正：同列元素共用左边缘、图标统一 20px/点击区 40px、列表行高内边距一致、表单基线对齐，对不齐的元素宁可删掉。",
  "tools": [
    "v0",
    "Cursor",
    "Qoder"
  ]
}
```

### 状态补全：空/加载/错误态 (`detail-states-complete`)

```json
{
  "id": "detail-states-complete",
  "title": "状态补全：空/加载/错误态",
  "category": "细节优化",
  "styles": [
    "状态",
    "完整度",
    "产品感"
  ],
  "scenario": "界面像半成品时的状态补全设计",
  "prompt": "Design the missing states for this product UI so it feels finished: (1) empty state with a small illustration, one-line explanation and a primary action button; (2) skeleton loading screens matching the real layout, no spinners on white; (3) inline error states with what happened + how to retry, in plain language; (4) success confirmation that is quiet, not a confetti modal. Keep all states in the same visual language as the main UI.",
  "prompt_zh": "补齐四种状态：空状态（小插图+一句话+主按钮）、骨架屏加载、说人话的行内错误+重试、安静的成功反馈，风格与主界面一致。",
  "tools": [
    "v0",
    "Lovable",
    "Cursor"
  ]
}
```

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
