# Legal Documents Hosting Guide

> 这里有两份你需要在 App Store Connect 提交时引用的法律文档：
> - [privacy-policy.md](privacy-policy.md) —— 隐私政策（**Apple 必填**）
> - [terms-of-use.md](terms-of-use.md) —— 服务条款（**StoreKit IAP 必填**）

App Store Connect 会要求你提供这两个文档的**公开可访问 URL**。最便宜（免费）的托管方式：**GitHub Pages**。

---

## 方案 A：GitHub Pages（推荐，免费，10 分钟搞定）

### Step 1 — 创建公开 repo

1. 登录你的 GitHub 账号（如果没有，去 github.com 注册）
2. 新建 public repo：`brick-smash-legal`
3. 把这两个 `.md` 文件提交进去

### Step 2 — 启用 Pages

1. Repo 页面 → Settings → Pages
2. **Source**：选 `Deploy from a branch`
3. **Branch**：选 `main` / `/(root)`
4. 保存

GitHub 1-3 分钟会生成你的页面 URL：

```
https://<your-github-username>.github.io/brick-smash-legal/privacy-policy
https://<your-github-username>.github.io/brick-smash-legal/terms-of-use
```

GitHub Pages 会自动把 `.md` 渲染成 HTML，URL **不需要** `.md` 后缀。

### Step 3 — 把这些 URL 填回

在以下三处替换占位 URL：

1. **App Store Connect**：你的 App → App Privacy → Privacy Policy URL
2. **App Store Connect**：你的 App → App Information → Privacy Policy URL
3. **应用内 SettingsView.swift**：搜索 `yourdomain.com/privacy` 替换为真实 URL
4. **应用内 PaywallView.swift**：同上

---

## 方案 B：Notion 公开页面（更快，2 分钟，但更不"专业"）

1. 在 Notion 里新建 page
2. 把 `.md` 内容粘贴进去
3. 右上 Share → Publish to web → Copy link
4. 你拿到一个 `notion.site/xxxxxx` 的 URL

✅ 优点：超快
⚠️ 缺点：URL 长且看起来不正式；Notion 网页含 watermark

---

## 方案 C：你自己的域名（专业，需购买域名）

如果你打算长期做 App 矩阵，建议买个域名（约 $10/年）：

- Namecheap / Porkbun / Cloudflare Registrar
- 注册后用 Cloudflare Pages / Netlify 免费托管

URL 形如 `https://brick-smash.com/privacy`，最专业。

---

## 你必须做的两件事

### 1. 替换占位邮箱

两份文档里都写了 `brick-smash-support@example.com`。在 markdown 文件里全局替换为你的真实邮箱（建议用 Gmail 别名：`yourgmail+bricksmash@gmail.com`，这样不暴露主邮箱）：

```bash
sed -i '' 's/brick-smash-support@example.com/<你的真实邮箱>/g' privacy-policy.md terms-of-use.md
```

### 2. 替换占位 URL

在所有 Swift 代码里搜索 `yourdomain.com` 占位，全部替换为你 GitHub Pages 的真实 URL。

```bash
cd /Users/masf/develop/cube-crush
grep -rl "yourdomain.com" BrickSmash/
# 然后手动或 sed 替换
```

---

## App Store Connect 隐私问卷快速对照

提交 App 时 Apple 会让你回答一份隐私问卷（Privacy Nutrition Labels）。基于我们的设计：

| 问题 | 答案 |
|---|---|
| Do you or your third-party partners collect data? | ✅ Yes |
| What data is linked to user's identity? | Device ID (IDFA, 仅广告网络) |
| What data is used to track? | Device ID, Product Interaction（仅广告网络） |
| Data used for advertising? | Yes（AppLovin + Pangle） |
| Data used for analytics? | No |
| Data used for product personalization? | No |
| Account creation required? | ❌ No |

详细每个 SDK 的数据收集列表见 `privacy-policy.md` 第 3 节。

---

## 检查清单（提交 App 前）

- [ ] privacy-policy.md 已修改占位邮箱
- [ ] terms-of-use.md 已修改占位邮箱
- [ ] 上传 GitHub Pages 或 Notion，拿到真实 URL
- [ ] URL 在浏览器能打开、能看到完整内容
- [ ] App Store Connect → App Privacy → Privacy Policy URL 已填
- [ ] SettingsView.swift / PaywallView.swift 里的 URL 已替换
- [ ] 隐私问卷答完（按上方对照表）
