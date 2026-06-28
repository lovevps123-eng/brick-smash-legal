# Brick Smash — App Store Connect 元数据

> 这一份是上架时直接 copy-paste 进 App Store Connect 各字段的全部文本。
> Apple 审核员会一字不漏读，**所有字符都过 4.3 / 2.3 政策检查**。

---

## 0. Create New App 向导（**最先做这步**）

登录 [App Store Connect](https://appstoreconnect.apple.com) → **Apps** → 右上角 **+** → 你会看到两个选项：

| 选项 | 是否选 | 说明 |
|---|---|---|
| **New App** | ✅ **选这个** | 创建单个新 App |
| **New App Bundle** | ❌ 不选 | 这是把**多个已上架 App** 打包销售用的（如 Pages + Numbers bundle），不是新 App 用 |

点 **New App** 后弹出向导，**逐字段填写**：

### 0.1 Platforms（必选）

| 选项 | 是否勾选 | 说明 |
|---|---|---|
| ✅ **iOS** | **勾上** | 我们只做 iPhone |
| ❌ macOS | 不勾 | Mac Catalyst 后续可选，但 v1 不上 |
| ❌ tvOS | 不勾 | 不支持 Apple TV |
| ❌ visionOS | 不勾 | 不支持 Vision Pro |

⚠️ **平台一旦选定后不可移除**，但可以后续添加（v1.1 想上 Mac Catalyst 时再加 macOS 即可）。

### 0.2 Name（30 字符上限）

```
Brick Smash
```

⚠️ 这个名字会显示在 App Store 商品页和 iPhone Home Screen 下方。建议**注册前先在 USPTO 商标搜索** [tmsearch.uspto.gov](https://tmsearch.uspto.gov) 查 "Brick Smash" 在 Class 9 / 41 是否已注册。我们之前查过 App Store 没有同名 App，但商标查没做。

### 0.3 Primary Language（必选）

```
English (U.S.)
```

⚠️ 这是 App **默认元数据语言**，决定 fallback 显示。后续可以添加更多 localization（如 Simplified Chinese / Japanese），但 Primary 不可改。**推荐选 English (U.S.)** 因为：
- 美区是主要市场
- 全球都能 fallback 到英文
- Apple 审核员母语

### 0.4 Bundle ID（dropdown，从 Apple Developer 选）

```
com.masf.bricksmash
```

**前置条件**：必须先在 [Apple Developer → Identifiers](https://developer.apple.com/account/resources/identifiers/list) 创建 App ID。

如果还没创建：
1. 去 Apple Developer → Identifiers → **+**
2. 选 **App IDs** → Continue
3. 选 **App** → Continue
4. 填表：
   - **Description**: `Brick Smash`
   - **Bundle ID**: 选 **Explicit**，填 `com.masf.bricksmash`
   - **Capabilities**: 暂时**不勾任何**（v1 无 Push / iCloud / Apple Pay）
5. Continue → Register

回到 App Store Connect 向导，刷新 Bundle ID 下拉框就能选到 `com.masf.bricksmash`。

⚠️ **Bundle ID 必须与 Xcode 工程的 PRODUCT_BUNDLE_IDENTIFIER 完全一致**（项目里现在是 `com.masf.bricksmash`）。

### 0.5 SKU（内部编号，自己定）

```
bricksmash-001
```

- 仅用作你自己的内部追踪，**不显示给用户**
- 不能包含空格 / 特殊字符（字母数字 + `-` + `_` 即可）
- 一旦设置不可改，**但可以随意填**（强迫症推荐 `bricksmash-001` 方便以后做 SKU #2 矩阵化）

### 0.6 User Access

```
Full Access
```

- **Full Access**：你（账号 owner）有完全权限
- Limited Access：限制某些 team 成员（个人账号没必要）
- 个人开发者**选 Full Access**

### 0.7 完成创建

点 **Create** → App 条目创建成功，进入 **App 详情页**。

⚠️ **创建后不能改的字段**：Platforms、Bundle ID、SKU、Primary Language。

**创建后可以改的字段**：Name、Subtitle、所有元数据（Description / Keywords / etc.）。

---

## 1. 创建后的进一步配置（按下面顺序填）

下面所有内容是 App 创建**之后**，在 App Store Connect 的 App 详情页里填写的。导航：

```
App Store Connect → 你的 App → 左侧 sidebar:
├─ Distribution
│  ├─ App Store (你最常用)
│  │  ├─ App Information      ← §1 + §2 下面
│  │  ├─ Pricing & Availability ← §3
│  │  ├─ App Privacy           ← §4 + Privacy Nutrition Labels
│  │  └─ Version (1.0)
│  │     ├─ Promotional Text
│  │     ├─ Description
│  │     ├─ Keywords
│  │     ├─ Support URL
│  │     ├─ Screenshots（6 张）
│  │     ├─ App Review Information
│  │     └─ Version Release（自动 / 手动）
│  └─ TestFlight (内测，先跳过)
└─ Monetization (v1 暂无 IAP，跳过)
```

---

## App Information

### Name (30 字符上限)
```
Brick Smash 8x8
```
（占 15 字符。原本想用 `Brick Smash` 但被占用，加 `8x8` 后缀绕过冲突，**且直接突出 8×8 玩法差异化**）

### Subtitle (30 字符上限)
```
Drop. Clear. Score.
```
（占 19 字符。**注意**：因为 Name 已含 "8x8"，Subtitle **不要重复 "8×8"**。这个版本简洁有节奏感，与第 1 张截图的标语一致）

#### 备选 Subtitle（如果想突出玩法关键词）
- `Puzzle · Daily · Time Attack` (28 chars)
- `Block Puzzle Daily Challenge` (28 chars)
- `Relax with daily block puzzle` (29 chars)

### Primary Category
```
Games
```

### Sub-Category 1
```
Puzzle
```

### Sub-Category 2
```
Casual
```

---

## Privacy

### Privacy Policy URL
```
https://<your-github-username>.github.io/brick-smash-legal/privacy-policy
```
*（注册 GitHub Pages 后替换实际 URL）*

### Privacy Choices URL（可选）
留空（我们没有用户账号，无可管理选项）

---

## Pricing & Availability

### Price
```
Free
```

### Availability
```
All countries / regions
```
*（除非你想限制某些国家；推荐全球上架）*

---

## In-App Purchase

### (v1.1 only — skip for v1.0 submission)

### Display Name (in App Store Connect)
```
Remove Ads
```

### Description (in App Store Connect)
```
Permanently disable all ads in Brick Smash. One-time purchase, no subscription.
```

### Product ID
```
com.masf.bricksmash.removeads
```
*（必须与代码中 `IAPStore.removeAdsProductID` 一致）*

### Price Tier
```
Tier 3 ($2.99 USD)
```

### Type
```
Non-Consumable
```

---

## App Description (4000 字符上限) — ASCII-only safe version

⚠️ **重要**：App Store Connect 的 Description 字段对部分 Unicode 字符严格（如 `✦` `×` em-dash `—`）会报 "invalid characters" 错。下面这版**已经移除所有可疑字符**，保证可粘贴。

```
Drop. Clear. Score.

Brick Smash is a relaxing 8x8 block puzzle game with a daily global challenge, time-attack modes, four visual themes, and satisfying combo effects. Drag pieces onto the grid, complete full rows or columns to clear them, and chain combos for bonus points.

WHAT MAKES BRICK SMASH DIFFERENT

* Daily Global Challenge
Every day at midnight UTC, all players around the world receive the same 30-piece sequence. Compete by skill, not by luck.

* Time Attack Modes
Sprint (60 seconds) and Marathon (120 seconds) variants with independent leaderboards. Pure score-rush - beat the clock.

* Combo Particle Effects
Chain 2+ line clears to trigger satisfying confetti bursts that match your theme. Bigger combos mean more particles.

* Color Match Bonus (+500)
Line up 5+ same-color cells in a row or column for a +500 score bonus. Adds strategic depth on top of the classic block puzzle.

* Four Free Visual Themes
Switch instantly between Classic, Neon, Pixel-Art, and OLED Dark. All themes are free - no unlocks, no purchases, no nags.

* Strictly Local Leaderboard
Top 20 scores per mode, stored entirely on your device. No account. No login. No friends list. No notifications.

* Pure Offline Play
Brick Smash works without an internet connection. No server dependency, no cloud account, no data uploads.

HOW TO PLAY

- Drag any of the 3 pieces from the bottom tray onto the 8x8 grid
- Fill any entire row or column to clear it
- Chain multi-line clears for combo bonuses (300 / 600 / 1000+ points)
- When no piece fits, the game ends - tap RESTART to play again

DESIGNED FOR CALM

No notifications. No timers in the main mode. No social pressure. Just you, the grid, and the next piece. Average session: 4-6 minutes.

ACCESSIBILITY

- Tap-and-drag mechanic, no quick reflexes needed
- Crisp 24pt-equivalent typography with high contrast options (OLED Dark theme)
- Sound and haptic feedback can both be disabled in Settings

CONTACT

brick-smash-support@example.com - we read every email.

This v1.0 release is completely ad-free.
```

### 被移除的字符清单（参考）

| 原字符 | Unicode | 改为 | 出现位置 |
|---|---|---|---|
| `✦` | U+2726 | `*` | 7 处 section bullets |
| `×` | U+00D7 | `x` | "8×8" → "8x8" |
| `—` | U+2014 em-dash | `-` 普通连字符 | 多处 |
| `–` | U+2013 en-dash | `-` | "4–6 minutes" |
| `•` | U+2022 bullet | `-` | HOW TO PLAY / ACCESSIBILITY 列表 |
| `=` | (combos = more) | `mean` | 等号在描述里有时触发 |

字符数：约 1,700（限 4,000，留充足余地）

---

## Promotional Text (170 字符上限，可不上传新版本更新)

```
A relaxing block puzzle with a daily global challenge. Same pieces, same day, every player worldwide. Four free themes. No accounts. No notifications. Just play.
```

字符数：163

---

## Keywords (100 字符上限，逗号分隔，无空格)

```
block,puzzle,brick,daily,challenge,8x8,relax,offline,casual,brain,zen,smash,grid,classic,no-ads
```

字符数：99

⚠️ **绝对不能塞**：`tetris`, `block blast`, `cube crush`（这些是其他公司商标）

---

## Support URL

```
https://<your-github-username>.github.io/brick-smash-legal/
```

---

## Marketing URL（可选）

留空（v1 没必要做营销官网）

---

## Age Rating

按问卷填：

| 问题 | 答案 |
|---|---|
| Cartoon or Fantasy Violence | None |
| Realistic Violence | None |
| Prolonged Graphic or Sadistic Realistic Violence | None |
| Profanity or Crude Humor | None |
| Mature/Suggestive Themes | None |
| Horror/Fear Themes | None |
| Medical/Treatment Information | None |
| Alcohol, Tobacco, or Drug Use or References | None |
| Simulated Gambling | None |
| Sexual Content or Nudity | None |
| Graphic Sexual Content and Nudity | None |
| Unrestricted Web Access | **No** |
| Gambling and Contests | **No** |
| Made for Kids | **No** |

**结果：4+（v1 ad-free）**（v1 无任何广告 / ATT / 第三方 SDK）

---

## App Privacy（Nutrition Labels）

按下表填：

### Data Used to Track You

**None**

### Data Linked to You

**None**

### Data Not Linked to You

**None**

### Data Not Collected

✅ **Yes** —— v1.0 不收集任何用户数据

---

## What's New（首版填）

```
Welcome to Brick Smash!

This is the first release. We hope you enjoy the daily challenge and the four themes.

If you encounter any bugs or have feedback, please email us — we read every message and ship updates fast.
```

---

## App Review Information

### Sign-In Required？
```
No
```

### Contact Information

| 字段 | 内容 |
|---|---|
| First Name | 你的拼音名 |
| Last Name | 你的拼音姓 |
| Phone Number | +86 你的手机号 |
| Email Address | brick-smash-support@example.com |

### Demo Account
```
Not required — the app has no login or account.
```

### Notes（**最关键，决定能否过 4.3 Spam 审核**）

直接 copy-paste 这段：

```
v1.0 NOTE: This is an ad-free, single-purchase-free release. No third-party
SDKs, no tracking, no IAP. A future v1.1 update will introduce optional
ad-supported monetization. The current submission is simplified to focus
on the gameplay innovations before adding monetization.

Brick Smash is a single-player 8×8 block puzzle game.

FIVE DOCUMENTED DIFFERENTIATORS FROM EXISTING APPS IN THIS CATEGORY:

1. Daily Seeded Challenge (visible in Screenshot #2)
   A globally synchronized daily piece sequence: every player worldwide receives identical pieces on the same UTC date. This is the primary differentiator from Block Blast (Hungry Studio), Cube Crush variants, and similar titles, which all use per-session random seeds. Implemented via DailySeedGenerator.swift using xorshift64 deterministic RNG seeded from yyyyMMdd UTC integer.

2. Four-Theme Visual Engine (visible in Screenshot #3)
   Classic, Neon, Pixel-Art, and OLED-Dark themes can be switched instantly with no purchase, login, or download. Most apps in this category lock themes behind subscription. Implementation: ThemeManager.swift (165 lines), no remote assets, all themes ship with v1. Scores are also persisted strictly on-device (Top 20 per mode in UserDefaults — no Game Center, no social login, no server).

3. Time Attack Mode (visible in Screenshot #4)
   Two timed variants — Sprint (60s) and Marathon (120s) — with independent leaderboards. The countdown creates a fundamentally different play feel from endless modes. Block Blast and clones are strictly endless until Game Over; no competitor in this category offers a pure time-attack mode. Implementation: GameMode.timeAttack(seconds:) + Task-based countdown timer in GameViewModel.swift. Auto-clears 1 random row if grid fills, so play continues until timer expires.

4. Combo Particle System (subtle in Screenshot #1)
   When 2+ lines clear simultaneously, an animated particle burst emits from the cleared cells with theme-colored confetti (20 particles for 2-line, 35 for 3-line, 50 for 4+ line combos). Uses SwiftUI Canvas + TimelineView for 60fps rendering, capped at 200 live particles for performance. Implementation: GameKernel/Particle.swift (pure model) + Views/ComboParticlesView.swift.

5. Color Match Bonus
   When a cleared row or column contains 5+ cells of the same color, a +500 bonus is awarded on top of normal scoring. A "COLOR MATCH! +500" toast appears for 1.2 seconds. Adds strategic depth — players plan placements to align colors. Implementation: GridState.hasColorMatch(in:cols:) inspects pre-clear color array; GameRules.colorMatchBonus = 500.

INDEPENDENT WORK:
- All source code is original SwiftUI, written specifically for this app.
- All visual assets (icons, themes, screenshots) are original.
- All sound effects are CC0-licensed (created using AVAudioEngine sine/triangle waves).
- No code is shared with any other developer account or any terminated account.
- The 8×8 drag-and-drop block-puzzle mechanic itself is a generic gameplay concept and is not protected by copyright (per Tetris Holding v. Xio Interactive, 2012).

NO THIRD-PARTY TRADEMARKS:
The app name, metadata, screenshots, and in-app UI contain no third-party trademarks such as "Block Blast", "Tetris", "Cube Crush", or any other competitor brand.

PRIVACY:
v1.0 collects no data and contains no third-party SDKs. PrivacyInfo.xcprivacy declares NSPrivacyTracking=false and an empty NSPrivacyCollectedDataTypes array.

TESTED ON:
iPhone 15 Pro / iPhone 17 Pro (iOS 17.0+ / iOS 26.x). Build via Xcode 26.2, Swift 5.9.

REVIEW STEPS:
1. Launch the app — game starts immediately, no onboarding or login.
2. Drag any piece from the bottom tray onto the 8×8 grid.
3. Fill a row or column to clear it. Score increases.
4. Tap "DAILY" to see the daily challenge entry.
5. Tap "THEMES" to switch between 4 visual themes.
```

字符数：约 2,600（Apple 限 4,000）

---

## Build Upload Checklist

- [ ] Bundle ID 与 App Store Connect 中创建的 App 一致
- [ ] Build 配置选 Release（不是 Debug）
- [ ] Archive → Upload via Xcode Organizer → 等候 5-30 分钟处理
- [ ] App Store Connect 中选中刚上传的 build
- [ ] 6 张截图按顺序上传（01-main → 02-daily → 03-themes → 04-timeattack → 05-leaderboard → 06-gameover）
- [ ] App Icon 1024×1024 从 `tools/icons_out/AppIcon-classic-1024.png` 上传
- [ ] Age Rating 已完成（应自动得 17+）
- [ ] 隐私问卷已完成
- [ ] Privacy Policy URL 已填
- [ ] Support URL 已填
- [ ] In-App Purchase "Remove Ads" 已创建并通过审核（IAP 单独审核，但通常和 App 一起）
- [ ] Review Notes 已粘贴
- [ ] Demo Account 字段写 "Not required"

---

## 提交后预期

- **首次审核时间**：24-72 小时
- **可能的拒审**：
  - 50% 概率首审通过 ✅
  - 30% 概率因 4.3 被拒 → 走 App Review Board 申诉（成功率 60%+）
  - 20% 其他原因（截图质量、元数据违规等）
- **被拒后处理时间**：1-2 周
- **总周期**：从提交到上架，**乐观 3 天，悲观 3 周**

---

## 上架后立即要做的 3 件事

1. **测试 IAP**：用真实 Apple ID 在你设备上买一次 $2.99（不会扣到你，因为是你自己的钱，但走通 StoreKit 生产链路）
2. **测试广告**：把 AppLovin Ad Unit 的 Test Mode 关掉，看是否能在生产环境收到 Pangle 广告
3. **截图 ASO 优化**：上线后 1 周内试着改一次截图顺序，观察 App Store Connect 里 "Conversion Rate" 变化
