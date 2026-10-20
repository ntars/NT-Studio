# 星玖工作室 Ntarstudio 官网主页

基于原始仓库部分内容，原作者仓库：https://github.com/asorn/asorn-open

许可证：本项目自研代码采用 MIT 协议（见 `LICENSE`）；派生自 asorn/asorn-open 的部分仍为 Apache License 2.0（见 `LICENSE-Apache-2.0.txt` 与 `NOTICE`）。

---

## 项目概览

星玖工作室（Ntarstudio）个人/团队品牌主页，支持暗色/亮色双主题，包含品牌展示、社交媒体入口与多个子项目导航。

## 站点链接

| 平台 | 地址 | 说明 |
|------|------|------|
| 官网主页 | [https://ntars.github.io/Home-Page/](https://ntars.github.io/Home-Page/) | 本项目部署地址 |
| 玄玖灵犀 NT-Xhex | [https://yi.ntars.cn/](https://yi.ntars.cn/) | 传统文化与现代科技的智慧连接（卡片之首） |
| 玄玖知识库 NT-Know | [https://k.ntars.cn/](https://k.ntars.cn/) | 知识沉淀与资料检索中心 |
| 玄玖测试库 NT-List | [https://q.ntars.cn/](https://q.ntars.cn/) | 性格与心理测试题的趣味集合 |

> 主列表卡片顺序：玄玖灵犀 NT-Xhex → 玄玖知识库 NT-Know → 玄玖测试库 NT-List（共 3 张）。
> 「联系我们」为页面**右上角固定文字入口**（非卡片），点击后弹窗展示社交/联系方式。

---

## 联系我们

「联系我们」为页面**右上角固定文字入口**（`#contact-card`，`position: fixed`），点击后弹出模态框，遮罩点击 / 关闭按钮 / `Esc` 均可关闭；打开时入口淡出、背景滚动锁定，关闭后自动还原。

| 分类 | 名称 | 内容 | 行为 |
|------|------|------|------|
| 社交平台 | GitHub 主页 | github.com/ntars | 新窗口跳转 |
| 社交平台 | 爱发电 | ifdian.net/a/ntars | 新窗口跳转 |
| 社交平台 | 哔哩哔哩 Bilibili | space.bilibili.com/499925438 | 新窗口跳转 |
| 联系方式 | 邮箱 | ntarsx@163.com | 点击复制 |
| 联系方式 | QQ | 3933361415 | 点击复制 |
| 联系方式 | 微信 | Ntarsv | 点击复制 |

> 说明：社交平台为网页跳转；邮箱 / QQ / 微信为纯文本，点击复制到剪贴板（不跳转）。抖音联系方式已删除。

## 技术架构

```
Home-Page/
├── index.html              # 主页面（主题初始化 + 设备检测 + 彩蛋 + 联系我们弹窗 + PWA + Typed.js）
├── manifest.json           # PWA Web App Manifest
├── sw.js                   # Service Worker（离线缓存加速）
├── README.md               # 项目文档
├── LICENSE                 # MIT 协议（自研代码）
├── LICENSE-Apache-2.0.txt  # Apache-2.0 协议（派生自 asorn/asorn-open 的部分）
├── NOTICE                  # 版权声明与上游致谢
├── baidu_verify_codeva-C4tp7NQbk5.html  # 百度站长验证
├── tencent-cloud-config.yml              # 腾讯云部署配置
└── assets/
    ├── css/
    │   └── base.css        # 全局样式（暗/亮双主题 / 过渡动画 / 响应式 / PWA适配 / 联系我们弹窗）
    ├── js/
    │   ├── security.js     # 安全防护模块（禁止选中/复制/右键/快捷键/链接触摸/篡改监测）
    │   ├── app.min.js      # 卡片光晕悬停交互（鼠标位置跟随 radial-gradient）
    │   ├── anime.js        # 动画引擎库（anime.js v2.0.2）
    │   ├── firework.js     # 烟花粒子效果（点击/触摸触发，主题颜色适配）
    │   ├── trail.js        # 鼠标拖尾效果（主题适配 / 触摸支持）
    │   └── bg.js           # 背景交互粒子（鼠标排斥 / 触摸支持 / 连线效果）
    └── img/
        ├── favicon-color.svg       # SVG 网站图标
        ├── apple-touch-icon.png    # Apple Touch Icon (180x180)
        ├── icon-192.png            # PWA 图标 192x192
        └── icon-512.png            # PWA 图标 512x512
```

---

## 核心特性

### 1. 双主题支持
- 默认主题根据用户系统偏好（`prefers-color-scheme`）自动切换
- 无系统偏好时根据时间（6:00-18:00 亮色，其余暗色）
- 双击 "星玖工作室出品" 标题可手动切换主题
- 主题切换带 0.5s CSS 过渡动画
- 所有视觉元素（背景、卡片、光晕、拖尾、烟花、星星）均适配双主题

### 2. 安全防护 (`assets/js/security.js`)
- 禁止文本选中、复制、剪切
- 禁止右键菜单、拖拽操作
- 禁止键盘快捷键（F12 / Ctrl+Shift+I/C / Ctrl+U/S/P/C / Ctrl+A）
- 鼠标悬停链接时隐藏 URL 显示
- DOM 篡改监测（body 被清空时自动刷新）
- 控制台保护（DevTools 检测 + 警告提示）

### 3. 视觉特效
- **烟花粒子** (`firework.js`)：点击/触摸触发烟花绽放动画，颜色随主题切换
- **鼠标拖尾** (`trail.js`)：鼠标/触摸移动产生渐变拖尾，自动适配主题颜色
- **背景交互粒子** (`bg.js`)：浮动粒子连线网络，鼠标靠近时排斥
- **卡片光晕** (`app.min.js`)：悬停时 radial-gradient 光晕跟随鼠标
- **底部装饰**：紫色光晕 + 三层上升星星动画 + 地球圆
- **背景点阵**：问候语区域虚线点阵装饰

### 4. PWA 支持
- **Web App Manifest**：`display: standalone` 独立窗口模式
- **Apple Web App 适配**：`apple-mobile-web-app-capable` + safe-area-inset
- **Service Worker**：缓存优先策略，离线可用
- **安装事件**：`beforeinstallprompt` 浏览器原生安装横幅

### 5. SEO 与搜索引擎优化
- **meta description / keywords**：多关键词覆盖（品牌、技术栈、内容平台等）
- **Open Graph 标签**：社交媒体分享预览优化
- **JSON-LD 结构化数据**：Schema.org Organization 标记，含 sameAs 社交媒体关联
- **canonical 链接**：规范 URL 声明，避免重复收录
- **百度站长验证**：`baidu_verify_codeva-C4tp7NQbk5.html`
- **robots 策略**：`index, follow` 允许收录，`noarchive` 防止缓存快照

### 6. 设备适配与彩蛋
- **手机端**：显示 "Hi, I'm Ntars"（个人模式）
- **桌面端**：显示 "Hi, We're Ntarstudio"（工作室模式）
- **平板端**：横屏显示工作室模式，竖屏显示个人模式，自动切换
- **触发方式**：点击名字区域可手动切换（平板端除外）
- **平滑过渡**：淡入淡出动画
- **打字效果**：Typed.js 自动打字动画

### 7. 联系我们弹窗
- **触发**：点击页面右上角「联系我们」固定文字入口（`#contact-card`，`position: fixed`；带 `tabindex`/`role=button`，支持键盘 `Enter`/`空格`）
- **关闭**：点击遮罩、右上角关闭按钮（`#contact-modal-close`）或按 `Esc`
- **状态联动**：打开时入口淡出（`.is-hidden`）、锁背景滚动；关闭后入口还原、解锁滚动
- **防跳动**：锁/解锁滚动条采用 `body` + `paddingRight` 滚动条宽度补偿，且滚动恢复**延迟到面板动画结束后**，避免内容横向位移（视觉跳动）
- **内容分两组**：
  - 社交平台：GitHub 主页、爱发电、哔哩哔哩 Bilibili（均新窗口跳转）
  - 联系方式：邮箱、QQ、微信（均为点击复制到剪贴板，不跳转）
- **动画**：入场——面板滑入淡显 + 遮罩渐显 + 条目错峰上浮；退出——纯淡出（transform 不参与过渡，避免关闭时朝角落位移）；遵循 `prefers-reduced-motion`
- **无障碍**：`role=dialog`、`aria-modal`、`aria-labelledby`，标题居中，关闭按钮位于面板右上角，打开时聚焦关闭按钮、关闭时归还焦点
- **复制兼容**：纯文本项（邮箱/QQ/微信）用 `data-contact-copy` 借 `Clipboard API` 手动写剪贴板，成功显示"已复制"、失败显示"复制失败"；支持鼠标点击与键盘 `Enter`/`空格`——因 `security.js` 全局拦截了选中/复制，且纯文本无法靠 `<a>` 跳转

---

## 本地开发

```bash
python3 -m http.server 8000
# 浏览器打开 http://localhost:8000
```

> Service Worker 仅在 `localhost` 下生效，`file://` 协议不支持。

## 部署

- **GitHub Pages**：推送至 `main` 分支自动部署
- **腾讯云 COS**：通过 GitHub Actions 部署，需配置 `TENCENT_CLOUD_*` 密钥
