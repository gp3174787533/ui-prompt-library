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

### 等宽数字：数字不跳动 (`detail-tabular-nums`)

```json
{
  "id": "detail-tabular-nums",
  "title": "等宽数字：数字不跳动",
  "category": "细节优化",
  "styles": [
    "数字",
    "字体",
    "细节"
  ],
  "scenario": "价格/计时器/数据表格等数字会变化的界面",
  "prompt": "Use tabular numbers everywhere numbers can change (prices, timers, counters, tables): font-variant-numeric: tabular-nums; so every digit has the same width and values never shift or jitter when they update. Apply it to KPI figures, prices, countdowns and any numeric column by default.",
  "prompt_zh": "会变的数字一律等宽：font-variant-numeric: tabular-nums，每个数字一样宽，更新时不左右跳。源自费纸张视频细节1。",
  "tools": [
    "v0",
    "Cursor",
    "Qoder"
  ]
}
```

### 错开入场：元素依次登场 (`detail-staggered-entrance`)

```json
{
  "id": "detail-staggered-entrance",
  "title": "错开入场：元素依次登场",
  "category": "细节优化",
  "styles": [
    "动效",
    "入场",
    "细节"
  ],
  "scenario": "页面/卡片首次出现的入场动画",
  "prompt": "Stagger the entrance animation: split the block into icon, title, body text and button, and let them fade/slide in one after another with about 100ms stagger between elements instead of everything appearing at once. Keep each animation short (200-300ms, ease-out) so it feels ordered and calm, never bouncy.",
  "prompt_zh": "入场要错开：图标、标题、正文、按钮拆开依次入场，间隔约 100ms，不要整块一起蹦出来。源自费纸张视频细节3（片尾汇总为100ms间隔）。",
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

#### 设置页主从布局 (`saas-settings-master-detail`)

```json
{
  "id": "saas-settings-master-detail",
  "title": "设置页主从布局",
  "category": "SaaS后台",
  "styles": [
    "主从布局",
    "表单",
    "设置"
  ],
  "scenario": "产品设置/账户/团队管理页",
  "prompt": "Design a settings page in a master-detail layout: left vertical nav (Profile, Account, Notifications, Billing, Security, Team) with the active item highlighted; right panel shows the active section as grouped cards, each setting as one row — title and helper text on the left, the control (toggle, select or button) on the right, comfortable 56px row height. Save per section and show a sticky 'Unsaved changes' bar at the bottom only when edits are pending. Put destructive actions in a separate red-bordered 'Danger zone' card at the very bottom. Calm neutral palette, one accent, no endless ungrouped scroll.",
  "prompt_zh": "设置页主从布局：左侧分组导航、右侧按卡分组的设置行（标题+说明+右侧控件）、有改动才吸底保存条、危险操作单独红框放最底。",
  "tools": [
    "v0",
    "Cursor",
    "Lovable"
  ]
}
```
