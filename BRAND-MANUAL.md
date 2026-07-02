# 莫干山 48H Break Point — 品牌手册

> 本手册基于 invitation.html（邀请函）和 poster.html（行程页）的实际代码提取整理。

---

## 1. 品牌定位

| 维度 | 定义 |
|------|------|
| 品牌名 | MOGANSHAN RUN CLUB × DEEPBEAT 记路家 |
| 活动名 | **48H Break Point**（邀请函）/ **48H Monster Speed**（行程） |
| 活动日期 | 2026年7月3日 14:00 — 7月5日 14:00 |
| 定位 | 运动 × 剧本杀 — 48小时山野任务，把奔跑、线索和路线设计剪成一支现场运动片 |
| 调性 | 电影感 / 户外探险 / 解谜悬疑 / 极限运动 |
| Tagline | THERE IS NO FINISH LINE · NO FINISH LINE · BUILT FOR THE OBSESSED |

---

## 2. 色彩系统

### 2.1 邀请函（Break Point）主色盘

| 变量名 | 色值 | 用途 |
|--------|------|------|
| `--track` | `#006D7D` | 主色调，标题文字、进度条、Marquee 背景 |
| `--track2` | `#0097A8` | 辅助蓝绿，Canvas 光线、装饰 |
| `--ink` | `#07100F` | 最深色，暗部文字 |
| `--white` | `#F7F4EA` | 主文字色，非纯白，偏暖米 |
| `--cream` | `#E8DEC9` | 辅助文字、次要信息 |
| `--lime` | `#C8DD4B` | 强调色，Canvas 光线、Kicker 标签 |
| `--orange` | `#E46C34` | 强调色，CTA、Kicker 标签、Canvas 光线 |
| `--pink` | `#A64B70` | 装饰色，Canvas 光线 |
| `--blue-dark` | `#053C4B` | 深底色 |
| `--line` | `rgba(247,244,234,0.22)` | 分隔线、边框 |
| `--muted` | `rgba(247,244,234,0.72)` | 次要文字 |

### 2.2 行程页（Monster Speed）主色盘

| 变量名 | 色值 | 用途 |
|--------|------|------|
| `--ink` | `#080907` | 最深色 |
| `--night` | `#11140E` | 暗底色 |
| `--pine` | `#1F2A1C` | 深绿底色 |
| `--moss` | `#7A8D4A` | 绿色强调，Day 3、Eyebrow、进度条 |
| `--paper` | `#EAE0C8` | 主文字色，偏暖纸色 |
| `--paper2` | `#CBBF9C` | 次要纸色，Day 1、Accent Bar |
| `--clay` | `#B86435` | 粘土橙，Day 2、CTA、倒计时紧急态 |
| `--rust` | `#7D3824` | 铁锈红，Accent Bar、紧急进度条 |
| `--fog` | `rgba(234,220,200,0.14)` | 雾气装饰 |
| `--muted` | `#928A75` | 次要文字 |
| `--dim` | `#575545` | 最弱文字 |

### 2.3 色彩使用原则

- **深色背景为基调**：两个页面均以 `#052A34`（邀请函）/ `linear-gradient(155deg, #006D7D, #052D38 54%, #061014)`（行程）为底，营造影院级暗调氛围
- **暖米色替代纯白**：主文字统一使用 `#F7F4EA` / `#EAE0C8`，避免刺眼，增加温暖质感
- **双色强调体系**：`lime/moss`（绿系）= 生机、山野；`orange/clay`（橙系）= 运动、紧迫
- **Accent Bar 四色条**：`#CBBF9F → #7A8D4A → #B86435 → #7D3824`，用于段落分隔装饰

---

## 3. 字体系统

### 3.1 字体族

```css
font-family: Inter, Helvetica, Arial, "PingFang SC", "Microsoft YaHei", sans-serif;
```

- **英文主字体**：Inter（几何无衬线，现代感）
- **中文回退**：PingFang SC（苹果）→ Microsoft YaHei（Windows）
- **辅助回退**：Helvetica → Arial → sans-serif

### 3.2 字号层级

| 层级 | 邀请函 | 行程页 | 用途 |
|------|--------|--------|------|
| Display | `clamp(54px, 15vw, 86px)` | `clamp(56px, 15vw, 96px)` | 主标题（Break Point / Monster Speed） |
| H2 | `36px` | `25px` | 章节标题（SEQUENCE / MISSION DECK） |
| Title | — | `20px` | 卡片标题（任务卡） |
| Event Name | — | `15px` | 行程事件名 |
| Body | `12px` | `14px` | 正文描述 |
| Subtitle | `12px` | `12px` | 副标题 |
| Stat Value | `14px` | `24px` | 数据展示 |
| Small/Label | `10px` | `10px` | 标签、元信息 |
| Micro | `10px` | `9px` | 最小标注 |

### 3.3 字重

| 值 | 用途 |
|----|------|
| `950` | Display 主标题、H2 |
| `900` | Stat Value、Event Name、卡片标题、倒计时数字 |
| `800` | Micro、CTA 按钮 |
| `700` | 正文强调、Subtitle |

### 3.4 字间距

| 值 | 用途 |
|----|------|
| `-4px` | Display 主标题（紧凑压迫感） |
| `-2px` | H2 |
| `-1px` | 倒计时数字 |
| `0px` | 正文 |
| `1px` | Label、Small、Stat Value |
| `1.5px` | Micro、元信息 |
| `2px` | 标签、Eyebrow |
| `3px` | Kicker、Eyebrow |

---

## 4. 布局系统

### 4.1 容器

```css
width: min(100%, 560px);
margin: 0 auto;
```

- **最大宽度 560px**，手机优先的居中卡片式布局
- 两端有大阴影 `box-shadow: 0 0 80px rgba(0,0,0,0.58)`
- 半透明背景 `rgba(0, 62, 75, 0.28)` 叠加在全屏渐变上

### 4.2 间距

| 场景 | 内边距 |
|------|--------|
| Hero 区 | `22px 24px 28px`（邀请函）/ `78px 24px 26px`（行程 Header） |
| 内容段落 | `32px 24px`（邀请函）/ `30px 24px`（行程） |
| 卡片内部 | `14px`（Seq Card）/ `16px`（Mission Card） |
| 移动端内边距 | `18px` |

### 4.3 网格

| 场景 | 布局 |
|------|------|
| Stat Row | `grid-template-columns: repeat(3, 1fr)` |
| Stat Grid（行程） | `grid-template-columns: repeat(3, 1fr); gap: 9px` |
| Credits Grid | `grid-template-columns: repeat(3, 1fr); gap: 14px` |
| Event Row | `grid-template-columns: 82px 1px 1fr 78px` |
| Mission Cards | `grid-template-columns: 1fr 1fr; gap: 12px` |
| Secret Countdown | `grid-template-columns: repeat(4, 1fr); gap: 8px` |

### 4.4 断点

```css
@media (max-width: 600px) {
  /* 移动端适配 */
  .page { width: 100%; }
  .stat-row, .credits-grid { grid-template-columns: 1fr; }
  .cards { grid-template-columns: 1fr; }
}
```

---

## 5. 视觉元素

### 5.1 圆角

| 值 | 用途 |
|----|------|
| `999px` | 按钮（`.pulse-control`、`.nav-link`）、状态点（`.film-dots i`）、圆形装饰 |
| `0px`（默认） | 卡片、统计框、事件行 — 全部直角，保持硬朗军事风 |

### 5.2 边框

| 样式 | 用途 |
|------|------|
| `1px solid rgba(247,244,234,0.5)` | 导航链接 |
| `1px solid rgba(234,224,200,0.14)` | 任务卡边框 |
| `1px solid rgba(234,224,200,0.12)` | 日程分隔线 |
| `2px solid var(--clay)` | 引用左边线 |
| `4px solid var(--paper2)` | 事件时间线左边线 |

### 5.3 背景效果

| 效果 | 实现 |
|------|------|
| **全屏径向渐变** | `radial-gradient(circle at 20% 15%, ...)` + `linear-gradient(135deg, ...)` |
| **扫描线纹理** | `repeating-linear-gradient(0deg, rgba(255,255,255,0.024) 0 1px, transparent 1px 7px)` |
| **网格叠加** | `linear-gradient` 48px/58px 间距，`mix-blend-mode: overlay` |
| **胶片颗粒** | `repeating-radial-gradient` 1px 点阵 |

### 5.4 毛玻璃

```css
backdrop-filter: blur(10px);  /* 导航、浮层 */
background: rgba(8,9,7,0.74); /* 半透明暗底 */
```

---

## 6. 动效系统

### 6.1 核心动画

| 名称 | 时长 | 缓动 | 用途 |
|------|------|------|------|
| `bodyBlur` | 5.2s | ease-in-out infinite | Hero 区光斑缓慢移动 |
| `limbSwing` | 4.8s | ease-in-out infinite | Ghost Limb 光影呼吸 |
| `titlePulse` / `titleKick` | 2.4s / 2.2s | ease-in-out infinite | 标题微缩放脉动 |
| `glitchA` / `glitchB` | 1.8s / 2.2s | steps(2,end) infinite | 标题故障抖动效果 |
| `marquee` | 14s | linear infinite | 底部文字滚动条 |
| `dotBeat` | 1.4s | ease-in-out infinite | 胶片点呼吸 |
| `knobRun` | 2.6s | ease-in-out infinite | CTA 按钮内圆点滑动 |
| `ripple` | 0.7s | ease-out forwards | 点击水波纹 |
| `fogSlide` | 10s | ease-in-out infinite | 行程 Header 雾气飘动 |
| `scan` | 5s | ease-in-out infinite | 面板扫描光线 |
| `beat` | 0.86s | ease-in-out infinite | 节拍条跳动 |

### 6.2 Canvas 动效

**邀请函 `motion-canvas`**：
- 58 条斜向光线（streaks），颜色在 `hsl(184)` (teal)、`hsl(25)` (orange)、`hsl(62)` (lime) 之间随机
- 响应鼠标位置偏移
- `globalCompositeOperation: 'lighter'` 叠加模式

**行程页 `case-canvas`**：
- 7 条等高线（contours）缓慢波动
- 透视追光线（trail）从地平线延伸
- 88 颗漂浮尘埃粒子（dust），缓慢上升

### 6.3 交互效果

| 效果 | 触发 | 说明 |
|------|------|------|
| 点击水波纹 | 全局 click | 圆形边框扩散后消失 |
| 卡片翻转 | Mission Card click | `rotateY(180deg)` 3D 翻转 |
| 行程行高亮 | Event Row click | 背景色变化 |
| 导航上浮 | hover | `translateY(-2px)` |
| 序列卡右移 | hover | `translateX(6px)` |

### 6.4 无障碍

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { animation: none !important; transition: none !important; }
}
```

---

## 7. 交互系统

### 7.1 三阶段状态机（行程页）

```
secret（倒计时锁定）→ ready（待启动）→ running（运行中）
```

| 阶段 | 触发条件 | 显示内容 |
|------|----------|----------|
| **Secret** | 当前时间 < 2026-07-03 14:00 CST | 全屏遮罩 + 倒计时 |
| **Ready** | 时间到 + 未点击启动 | 启动按钮遮罩 |
| **Running** | 点击 "START THE RUN" | 48小时倒计时 + 行程逐日解锁 |

### 7.2 逐日解锁

| 日期 | 解锁时间 (UTC) | 色彩标记 |
|------|----------------|----------|
| Day 01（7月3日） | 2026-07-03T06:00:00Z | `--paper2`（米色） |
| Day 02（7月4日） | 2026-07-03T16:00:00Z | `--clay`（粘土橙） |
| Day 03（7月5日） | 2026-07-04T16:00:00Z | `--moss`（苔绿） |

- 未解锁的日程 `opacity: 0.12; filter: blur(3px); pointer-events: none`
- 解锁时带 `unlocking` 闪光动画（1.2s）

### 7.3 紧急态

当倒计时 < 6 小时，计时器文字和进度条切换为 `--clay` / `--rust` 色系。

### 7.4 管理员模式

右下角隐藏 ADMIN 按钮，密码 `20260703`，可跳过时间限制直接解锁全部内容。

### 7.5 时间跳转（邀请函）

```js
// 2026-07-03 14:00 CST 后自动跳转到行程页
if (Date.now() >= new Date('2026-07-03T14:00:00+08:00').getTime()) {
  window.location.replace('poster.html');
}
```

---

## 8. 组件库

### 8.1 Eyebrow（眉标）

```html
<div class="eyebrow"><span class="seal-dot"></span>MOGANSHAN RUN CLUB / FIELD CASE</div>
```
- 颜色：`--moss`（行程）/ `--white`（邀请函）
- 字号：10px，字间距 3px，大写
- `seal-dot`：34×1px 横线 + `box-shadow` 发光

### 8.2 Kicker（小标题标签）

```html
<div class="kicker">SEQUENCE</div>
```
- 颜色：`--orange`（邀请函）/ `--moss`（行程）
- 字号：10px，字间距 1.5-3px，大写

### 8.3 Stat / Stat Item（数据卡片）

```html
<div class="stat-item" data-no="01">
  <div class="stat-label">DATE</div>
  <div class="stat-val">JUL 03-05</div>
  <div class="stat-sub">2026</div>
</div>
```
- 边框 + 半透明背景 + 径向渐变点缀
- 右下角 `data-no` 水印数字（40px，极低透明度）

### 8.4 Mission Card（任务卡）

```html
<article class="mission-card" data-code="01">
  <div class="card-meta"><span class="card-code">CARD 01</span><span class="card-status">ARRIVAL</span></div>
  <h3 class="card-title">抵达集结</h3>
  <p class="card-copy">...</p>
</article>
```
- 顶部 3px 渐变色条：`paper2 → moss → clay`
- 奇偶卡片背景色微调（绿/橙径向渐变）
- 点击翻转效果

### 8.5 Event Row（行程行）

```html
<div class="event-row" data-tminus="48" data-day="1">
  <div class="time-col"><div class="time-label">TIME</div><div class="time-value">14:00</div></div>
  <div class="event-divider"></div>
  <div class="event-col"><div class="event-phase">ARRIVAL / 抵达</div><div class="event-name">入住酒店</div></div>
  <div class="tminus-col"><div class="tminus-label">T-MINUS</div><div class="tminus-value">48:00</div></div>
</div>
```
- 四列布局：时间 | 分隔线 | 事件 | 倒计时
- 左侧 4px 彩色竖线标识日程

### 8.6 Pulse Control（CTA 按钮）

```html
<a class="pulse-control" href="poster.html"><span>OPEN FIELD CASE</span></a>
```
- 圆角胶囊形 `border-radius: 999px`
- 内部滑动圆点动画
- 毛玻璃背景

### 8.7 Marquee（滚动条）

```html
<div class="marquee"><div class="marquee-track"><span>FOG RUN</span>...</div></div>
```
- 白底深色字，倾斜 `-1.5deg`
- 14s 无限循环滚动

### 8.8 Overlay Panel（全屏遮罩面板）

```html
<div class="overlay-panel">
  <div class="overlay-content">...</div>
</div>
```
- `backdrop-filter: blur(18px)`
- 扫描光线动画
- 最大宽 560px

---

## 9. 品牌文案风格

### 9.1 语言策略

- **中英双语混排**：英文做标签/分类，中文做描述/叙事
- **电影术语**：SEQUENCE、CREDITS、FIELD SCRIPT、CASE FILE、DIRECTOR、GENRE、DROP
- **军事/任务术语**：MISSION、FIELD CASE、T-MINUS、ARRIVAL、CHASE、ROUTE、SEALED
- **极简短句**：NO FINISH LINE / BUILT FOR THE OBSESSED

### 9.2 文案层级

| 层级 | 示例 | 风格 |
|------|------|------|
| 品牌名 | MOGANSHAN RUN CLUB | 全大写，宽字距 |
| 活动名 | Break Point / Monster Speed | 超大号，紧凑字距 |
| Tagline | THERE IS NO FINISH LINE | 全大写，中等字距 |
| 描述 | 48小时山野任务… | 中文叙事，温暖 |
| 标签 | BREAK POINT / MISSION CARD | 全大写，小号宽字距 |

### 9.3 编号系统

- 步骤编号：`01` `02` `03`（两位数，900字重）
- 卡片编号：`CARD 01` — `CARD 06`
- 日程编号：`DAY 01` — `DAY 03`
- 水印编号：`data-no="01"`（40px，5% 透明度）

---

## 10. 技术规范

### 10.1 响应式

- 移动端优先，最大 560px
- 断点：600px（平板/桌面端不单独适配，保持卡片居中）
- 字号使用 `clamp()` 自适应

### 10.2 性能

- Canvas 动效使用 `devicePixelRatio` 限制最高 2x
- `prefers-reduced-motion` 全局关闭动画
- `pointer-events: none` 避免装饰层拦截交互
- `requestAnimationFrame` 驱动动画循环

### 10.3 文件结构

```
48H-交付-最终版/
├── invitation.html   # 邀请函（576行，纯 HTML/CSS/JS）
├── poster.html       # 行程页（1013行，纯 HTML/CSS/JS）
├── netlify.toml      # Netlify 部署配置
└── README.md         # 项目说明
```

### 10.4 部署

- 平台：Netlify
- 无构建依赖，纯静态文件
- 邀请函在 7月3日 14:00 CST 后自动跳转行程页

---

## 11. 设计语言速查

| 要素 | 规范 |
|------|------|
| 主色调 | Teal (#006D7D) + Warm White (#F7F4EA) |
| 强调色 | Lime (#C8DD4B) + Orange (#E46C34) |
| 行程页强调 | Moss (#7A8D4A) + Clay (#B86435) |
| 字体 | Inter + PingFang SC |
| 主标题 | 54-96px / weight 950 / letter-spacing -4px / skewX(-7deg) |
| 容器 | 560px max-width / 居中 / 半透明暗底 |
| 圆角 | 按钮 999px / 卡片 0px |
| 动效 | Canvas 粒子 + CSS glitch + 扫描光线 |
| 交互 | 点击水波纹 + 卡片翻转 + 逐日解锁 |
| 分隔线 | 1px 半透明暖白 |

---

*手册基于 v1.0 最终交付版提取，2026-07-01*
