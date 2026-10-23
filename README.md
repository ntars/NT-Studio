# 星玖工作室 Ntarstudio 官网主页

基于原始仓库部分内容，原作者仓库：https://github.com/asorn/asorn-open

许可证：本项目自研代码采用 MIT 协议（见 `LICENSE`）；派生自 asorn/asorn-open 的部分仍为 Apache License 2.0（见 `LICENSE-Apache-2.0.txt` 与 `NOTICE`）。

---

## 项目概览

星玖工作室（Ntarstudio）的官方品牌主页，同时是三个自研项目的统一入口。

站点是**一个单页静态站点**：无框架、无构建、无后端、无运行时接口请求。克隆下来起一个静态服务器就能跑，推到任意静态托管即可上线。

页面承担的职责只有三件事：

1. **说清身份**——星玖工作室是谁、在做什么；
2. **指对入口**——把访客送到三个项目各自的正式地址；
3. **不制造误解**——每个项目的上线状态如实标注，未上线的项目不给死链。

### 三个项目

| 项目 | 一句话定位 | 当前状态 | 正式地址 |
|---|---|---|---|
| **玄玖灵犀 NT-Xhex** | 把千年术数文献搬进本地算法的传统术数数字化工具，纯离线、一套代码三端 | **已上线**（v3.4.0） | [yi.ntars.cn](https://yi.ntars.cn/) |
| **玄宠 NT-Dpet** | 把人格、记忆、情绪、声音、身体装配成一个装好就能用的 AI 拟人伴侣 | **官网已上线，软件研发中** | [pet.ntars.cn](https://pet.ntars.cn/) |
| **玄玖大模型 NT-Sine** | 只有中文、只有一个用途、只属于一个人的本地情感陪伴模型 | **网站筹备中**（域名 ai.ntars.cn 已规划，尚未解析） | 入口暂指向[源码仓库](https://github.com/ntars/NT-Sine) |

> **两处刻意为之的细节，避免产生歧义：**
>
> - **NT-Dpet 的卡片标「官网已上线」而不是「已上线」**。它的官网确实已经部署在 pet.ntars.cn，但**软件本体仍处于 S0 骨架阶段，仓库里没有任何可双击安装的产物**。把这两件事分开写，访客点进去看到「研发中」的路线图时不会觉得被骗。
> - **NT-Sine 的卡片不指向 ai.ntars.cn**。该域名当前**无 A 记录、无法解析**（实测返回空），若按格式直接挂上去就是一条死链。因此卡片保留同样的版式，入口暂时指向源码仓库，描述里写明「网站筹备中」。
>
> 这两条不是排版偏好，而是「不假报、不放死链」的具体做法。

---

## 站点链接

| 平台 | 地址 | 说明 |
|---|---|---|
| 官网主页（主域名） | [https://www.ntars.cn/](https://www.ntars.cn/) | 正式站点，EdgeOne Pages 托管 |
| 官网镜像（GitHub Pages） | [https://ntars.github.io/NT-Studio/](https://ntars.github.io/NT-Studio/) | 仓库直连的备用访问入口 |
| 玄玖灵犀 NT-Xhex | [https://yi.ntars.cn/](https://yi.ntars.cn/) | 已上线 |
| 玄宠 NT-Dpet | [https://pet.ntars.cn/](https://pet.ntars.cn/) | 官网已上线，软件研发中 |
| 玄玖大模型 NT-Sine | `https://ai.ntars.cn/` | **未上线**，域名尚未解析 |

> **主列表卡片顺序固定为三张**：玄玖灵犀 NT-Xhex → 玄宠 NT-Dpet → 玄玖大模型 NT-Sine。
> 「联系我们」不是卡片，而是页面**右上角固定文字入口**，点击后弹窗展示社交与联系方式。

### 已下线的两个旧项目

以下两个项目**已停止运营、域名已停止解析**，页面与元信息中不再出现，此处仅作历史说明，避免老访客找不到入口时产生困惑：

| 旧项目 | 原域名 | 当前状态 |
|---|---|---|
| 玄玖知识库 NT-Know | `k.ntars.cn` | 已下线（域名无 A 记录） |
| 玄玖测试库 NT-List | `q.ntars.cn` | 已下线（域名无 A 记录） |

若在别处看到这两个名字或旧版官网截图，均属过期信息，请以本页与三个正式项目地址为准。

---

## 联系我们

「联系我们」为页面**右上角固定文字入口**（`#contact-card`，`position: fixed`），点击后弹出模态框，遮罩点击 / 关闭按钮 / `Esc` 均可关闭；打开时入口淡出、背景滚动锁定，关闭后自动还原。

| 分类 | 名称 | 内容 | 行为 |
|------|------|------|------|
| 官方网站 | 星玖工作室官网 | www.ntars.cn | 新窗口跳转 |
| 社交平台 | GitHub 主页 | github.com/ntars | 新窗口跳转 |
| 社交平台 | 爱发电 | ifdian.net/a/ntars | 新窗口跳转 |
| 社交平台 | 哔哩哔哩 Bilibili | space.bilibili.com/499925438 | 新窗口跳转 |
| 联系方式 | 邮箱 | ntarsx@163.com | 点击复制 |
| 联系方式 | QQ | 3933361415 | 点击复制 |
| 联系方式 | 微信 | Ntarsv | 点击复制 |

> 说明：社交平台为网页跳转；邮箱 / QQ / 微信为纯文本，点击复制到剪贴板（不跳转）。抖音联系方式已删除。

---

## 技术架构

```
NT-Studio/
├── index.html              # 主页面（主题初始化 + 设备检测 + 彩蛋 + 联系我们弹窗 + 打字效果 + PWA 注册）
├── manifest.json           # PWA Web App Manifest
├── sw.js                   # Service Worker（缓存优先 + 后台更新）
├── README.md               # 项目文档（本文件）
├── LICENSE                 # MIT 协议（自研代码）
├── LICENSE-Apache-2.0.txt  # Apache-2.0 协议（派生自 asorn/asorn-open 的部分）
├── NOTICE                  # 版权声明、上游致谢与第三方组件清单
├── baidu_verify_codeva-C4tp7NQbk5.html  # 百度站长验证
├── tencent-cloud-config.yml              # 腾讯云部署配置
└── assets/
    ├── css/
    │   ├── base.css        # 全局样式（暗/亮双主题 / 过渡动画 / 响应式 / PWA 适配 / 联系我们弹窗）
    │   ├── base.scss       # asorn 底座时期的历史样式源（当前页面不引用，见下）
    │   └── base.min.css    # 历史压缩产物（当前页面不引用，见下）
    ├── js/
    │   ├── security.js     # 安全防护模块（禁止选中/复制/右键/快捷键/链接触摸/篡改监测）
    │   ├── app.min.js      # 卡片光晕悬停交互（鼠标位置跟随 radial-gradient）
    │   ├── anime.js        # 动画引擎库（anime.js v2.0.2，MIT）
    │   ├── firework.js     # 烟花粒子效果（点击/触摸触发，主题颜色适配）
    │   ├── trail.js        # 鼠标拖尾效果（主题适配 / 触摸支持）
    │   └── bg.js           # 背景交互粒子（鼠标排斥 / 触摸支持 / 连线效果）
    └── img/
        ├── favicon-color.svg       # SVG 网站图标（N+T 词标）
        ├── icon.svg                # 主图标（SVG，favicon 首选）
        ├── apple-touch-icon.png    # Apple Touch Icon (180x180)
        ├── icon-192.png            # PWA 图标 192x192
        └── icon-512.png            # PWA 图标 512x512
```

> **关于 `base.scss` 与 `base.min.css`**：页面实际只加载 `assets/css/base.css`。这两个文件是派生自 asorn/asorn-open 底座时期留下的历史文件，与当前样式已不同步（`base.scss` 仍含 about / blog 等本站未使用的模块）。
> 保留它们是为了不擅自删除带 Apache-2.0 来源痕迹的文件；它们**不参与构建、不被任何页面引用**。确认无需追溯后可在单独提交中一并清理。

---

## 核心特性

### 1. 双主题支持

- 默认主题根据用户系统偏好（`prefers-color-scheme`）自动切换；**系统偏好读不出来时**，按时间兜底（6:00–18:00 亮色，其余暗色）
- 首屏在 `<head>` 内联脚本里就把 `data-theme` 定下来，并用 `theme-lock` 类遮住首帧，避免「先亮后暗」的闪白
- 双击 "星玖工作室出品" 标题可手动切换主题，同步更新 `<meta name="theme-color">`
- 主题切换带 0.5s CSS 过渡动画；所有视觉元素（背景、卡片、光晕、拖尾、烟花、星星）均适配双主题

### 2. 安全防护（`assets/js/security.js`）

- 禁止文本选中、复制、剪切；禁止右键菜单与拖拽
- 禁止键盘快捷键（F12 / Ctrl+Shift+I/C / Ctrl+U/S/P / Ctrl+A）
- 鼠标悬停链接时隐藏 URL 显示
- DOM 篡改监测（body 被清空时自动刷新）
- 控制台保护（DevTools 检测 + 警告提示）

> 这是「提高随手复制的门槛」，不是加密。页面内容本身是公开的，任何安全模块都不应被当作保密手段——真正不能公开的东西不要放在前端。

### 3. 视觉特效

- **烟花粒子**（`firework.js`）：点击 / 触摸触发烟花绽放，颜色随主题切换
- **鼠标拖尾**（`trail.js`）：鼠标 / 触摸移动产生渐变拖尾，自动适配主题颜色
- **背景交互粒子**（`bg.js`）：浮动粒子连线网络，鼠标靠近时排斥
- **卡片光晕**（`app.min.js`）：悬停时 `radial-gradient` 光晕跟随鼠标位置
- **底部装饰**：紫色光晕 + 三层上升星星动画 + 地球圆
- **背景点阵**：问候语区域虚线点阵装饰

### 4. PWA 支持

- **Web App Manifest**：`display: standalone` 独立窗口模式
- **Apple Web App 适配**：`apple-mobile-web-app-capable` + `safe-area-inset`
- **Service Worker**：缓存优先 + 后台静默更新（Stale-While-Revalidate）；离线时 HTML 请求回退到首页
- **缓存版本纪律**：改动任何被预缓存的资源后，必须同步提升 `sw.js` 里的 `CACHE_NAME`（当前 `ntarstudio-v4`），否则回访用户会继续命中旧缓存
- **安装事件**：监听 `beforeinstallprompt`，依赖浏览器原生安装 UI

### 5. SEO 与搜索引擎优化

- **meta description / keywords**：覆盖品牌名与三个项目名
- **Open Graph 标签**：社交分享预览；`og:url` 与 `canonical` 统一指向主域名 `https://www.ntars.cn/`
- **JSON-LD 结构化数据**：Schema.org `Organization` 标记，含 `sameAs` 社交媒体关联
- **百度站长验证**：`baidu_verify_codeva-C4tp7NQbk5.html` + `<meta name="baidu-site-verification">`
- **robots 策略**：`index, follow` 允许收录，`noarchive` 防止缓存快照

### 6. 设备适配与彩蛋

- **手机端**：显示 "Hi, I'm Ntars"（个人模式）
- **桌面端**：显示 "Hi, We're Ntarstudio"（工作室模式）
- **平板端**：横屏显示工作室模式，竖屏显示个人模式，转屏时自动切换（平板端禁用点击切换，避免与转屏判定打架）
- **触发方式**：点击名字区域可手动切换（平板端除外）
- **平滑过渡**：淡入淡出 300ms；打字效果由 Typed.js 驱动，循环播放两句话

### 7. 联系我们弹窗

- **触发**：点击右上角「联系我们」固定文字入口（带 `tabindex` / `role=button`，支持键盘 `Enter` / `空格`）
- **关闭**：点击遮罩、右上角关闭按钮或按 `Esc`
- **状态联动**：打开时入口淡出（`.is-hidden`）、锁背景滚动；关闭后还原
- **防跳动**：锁滚动时给 `body` 补 `paddingRight`（等于滚动条宽度），且**滚动恢复延迟到面板动画结束后**，避免内容横向位移
- **动画**：入场——面板滑入淡显 + 遮罩渐显 + 条目错峰上浮；退场——纯淡出（`transform` 不参与过渡，避免关闭时朝角落位移）；遵循 `prefers-reduced-motion`
- **无障碍**：`role=dialog`、`aria-modal`、`aria-labelledby`；打开时聚焦关闭按钮，关闭时归还焦点
- **复制兼容**：纯文本项（邮箱 / QQ / 微信）用 `data-contact-copy` 走 `Clipboard API` 手动写剪贴板，成功显示「已复制」、失败显示「复制失败」，1.2s 后自动还原
  > 为什么要手动写剪贴板：`security.js` 全局拦截了选中与 `copy` 事件，纯文本项又没有 `<a>` 可跳转，只能绕过事件层直接调 API。

---

## 本地开发

```bash
python3 -m http.server 8000
# 浏览器打开 http://localhost:8000
```

> Service Worker 仅在 `localhost` 或 HTTPS 下生效，`file://` 协议不支持。
> 页面无构建步骤：改完 `index.html` / `base.css` / 脚本后刷新即可。

修改后的自查清单：

1. 三张卡片的标题、描述、链接与当前项目状态一致；
2. 改动任何预缓存资源后，`sw.js` 的 `CACHE_NAME` 已升版；
3. 浅色 / 深色两套主题下都看过一遍（双击标题切换）；
4. 手机宽度（<768px）与桌面宽度各看一遍，确认没有换行挤压。

## 部署

- **EdgeOne Pages**：主域名 `www.ntars.cn` 的托管方式，推仓库根即可（`tencent-cloud-config.yml` 保留为备用配置）
- **GitHub Pages**：推送至 `main` 分支自动部署，作为镜像入口
- **腾讯云 COS**：通过 GitHub Actions 部署，需配置 `TENCENT_CLOUD_*` 密钥

---

## 开源组件与许可

本站用到的第三方组件、版权归属与许可义务，**完整清单见 [`NOTICE`](NOTICE)**。此处只列结论：

| 组件 | 许可 | 用途 |
|---|---|---|
| asorn/asorn-open | Apache-2.0 | 页面结构底座（已大幅修改，属衍生作品） |
| anime.js v2.0.2 | MIT | 烟花粒子动画引擎 |
| Typed.js 2.0.16 | MIT | 问候语打字效果（经 unpkg CDN 引入） |

- 本站**不使用任何第三方字体**：字体栈为系统字体（Roboto / system-ui / -apple-system…），不加载网络字体，因此无字体许可义务；
- 本站**不使用任何第三方图标库**：favicon 与图标为自研，N+T 词标；
- 本站**不收集任何用户数据**：无统计脚本、无第三方埋点、无 Cookie。

## 许可

- 自研代码：**MIT**，全文见 [`LICENSE`](LICENSE)
- 派生自 asorn/asorn-open 的部分：**Apache-2.0**，全文见 [`LICENSE-Apache-2.0.txt`](LICENSE-Apache-2.0.txt)
- 再分发时请一并保留 `LICENSE`、`LICENSE-Apache-2.0.txt`、`NOTICE` 三份文件
