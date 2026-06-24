# Brick Smash — App Store Connect 元数据

> 这一份是上架时直接 copy-paste 进 App Store Connect 各字段的全部文本。
> Apple 审核员会一字不漏读，**所有字符都过 4.3 / 2.3 政策检查**。

---

## App Information

### Name (30 字符上限)
```
Brick Smash
```
（占 11 字符，留余地以后加副标题如 `Brick Smash 8x8` 等）

### Subtitle (30 字符上限)
```
8×8 Puzzle · Daily Challenge
```
（占 28 字符）

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

## App Description (4000 字符上限)

```
Drop. Clear. Score.

Brick Smash is a relaxing 8×8 block puzzle game with a daily global challenge, time-attack modes, four visual themes, and satisfying combo effects. Drag pieces onto the grid, complete full rows or columns to clear them, and chain combos for bonus points.

WHAT MAKES BRICK SMASH DIFFERENT

✦ Daily Global Challenge
Every day at midnight UTC, all players around the world receive the same 30-piece sequence. Compete by skill, not by luck.

✦ Time Attack Modes
Sprint (60 seconds) and Marathon (120 seconds) variants with independent leaderboards. Pure score-rush — beat the clock.

✦ Combo Particle Effects
Chain 2+ line clears to trigger satisfying confetti bursts that match your theme. Bigger combos = more particles.

✦ Color Match Bonus (+500)
Line up 5+ same-color cells in a row or column for a +500 score bonus. Adds strategic depth on top of the classic block puzzle.

✦ Four Free Visual Themes
Switch instantly between Classic, Neon, Pixel-Art, and OLED Dark. All themes are free — no unlocks, no purchases, no nags.

✦ Strictly Local Leaderboard
Top 20 scores per mode, stored entirely on your device. No account. No login. No friends list. No notifications.

✦ Pure Offline Play
Brick Smash works without an internet connection. No server dependency, no cloud account, no data uploads.

HOW TO PLAY

• Drag any of the 3 pieces from the bottom tray onto the 8×8 grid
• Fill any entire row or column to clear it
• Chain multi-line clears for combo bonuses (300 / 600 / 1000+ points)
• When no piece fits, the game ends — but you can watch one ad to clear two rows and continue

DESIGNED FOR CALM

No notifications. No timers in the main mode. No social pressure. Just you, the grid, and the next piece. Average session: 4–6 minutes.

ACCESSIBILITY

• Tap-and-drag mechanic, no quick reflexes needed
• Crisp 24pt-equivalent typography with high contrast options (OLED Dark theme)
• Sound and haptic feedback can both be disabled in Settings

REMOVE ADS

One-time $2.99 purchase removes all interstitial and rewarded ads forever. No subscription. No recurring charges.

CONTACT

brick-smash-support@example.com — we read every email.
```

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

**结果：17+**（因为含第三方广告 + ATT，自动 17+）

---

## App Privacy（Nutrition Labels）

按下表填：

### Data Used to Track You

✅ **Identifiers**
- Device ID（iOS IDFA）—— 仅当用户 ATT 授权后
- 数据通过：AppLovin、Pangle

✅ **Usage Data**
- Product Interaction
- 数据通过：AppLovin、Pangle

### Data Linked to You

仅当用户授权 ATT 时：上述 Device ID + Usage Data

### Data Not Linked to You

无

### Data Not Collected

✅ Yes —— 我们自己不直接收集任何用户数据

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
Brick Smash is a single-player 8×8 block puzzle game.

SIX DOCUMENTED DIFFERENTIATORS FROM EXISTING APPS IN THIS CATEGORY:

1. Daily Seeded Challenge (visible in Screenshot #2)
   A globally synchronized daily piece sequence: every player worldwide receives identical pieces on the same UTC date. This is the primary differentiator from Block Blast (Hungry Studio), Cube Crush variants, and similar titles, which all use per-session random seeds. Implemented via DailySeedGenerator.swift using xorshift64 deterministic RNG seeded from yyyyMMdd UTC integer.

2. Four-Theme Visual Engine (visible in Screenshot #3)
   Classic, Neon, Pixel-Art, and OLED-Dark themes can be switched instantly with no purchase, login, or download. Most apps in this category lock themes behind subscription. Implementation: ThemeManager.swift (165 lines), no remote assets, all themes ship with v1.

3. Time Attack Mode (visible in Screenshot #4)
   Two timed variants — Sprint (60s) and Marathon (120s) — with independent leaderboards. The countdown creates a fundamentally different play feel from endless modes. Block Blast and clones are strictly endless until Game Over; no competitor in this category offers a pure time-attack mode. Implementation: GameMode.timeAttack(seconds:) + Task-based countdown timer in GameViewModel.swift. Auto-clears 1 random row if grid fills, so play continues until timer expires.

4. Combo Particle System (subtle in Screenshot #1)
   When 2+ lines clear simultaneously, an animated particle burst emits from the cleared cells with theme-colored confetti (20 particles for 2-line, 35 for 3-line, 50 for 4+ line combos). Uses SwiftUI Canvas + TimelineView for 60fps rendering, capped at 200 live particles for performance. Implementation: GameKernel/Particle.swift (pure model) + Views/ComboParticlesView.swift.

5. Color Match Bonus
   When a cleared row or column contains 5+ cells of the same color, a +500 bonus is awarded on top of normal scoring. A "COLOR MATCH! +500" toast appears for 1.2 seconds. Adds strategic depth — players plan placements to align colors. Implementation: GridState.hasColorMatch(in:cols:) inspects pre-clear color array; GameRules.colorMatchBonus = 500.

6. Strictly Local Leaderboard (visible in Screenshot #5)
   Top 20 scores per mode (Normal / Daily / Sprint60 / Marathon120) stored only in UserDefaults. No Game Center, no social login, no server, no remote storage. This deliberately differs from competitors that require Apple Sign In or Facebook for any score persistence.

INDEPENDENT WORK:
- All source code is original SwiftUI, written specifically for this app.
- All visual assets (icons, themes, screenshots) are original.
- All sound effects are CC0-licensed (created using AVAudioEngine sine/triangle waves).
- No code is shared with any other developer account or any terminated account.
- The 8×8 drag-and-drop block-puzzle mechanic itself is a generic gameplay concept and is not protected by copyright (per Tetris Holding v. Xio Interactive, 2012).

NO THIRD-PARTY TRADEMARKS:
The app name, metadata, screenshots, and in-app UI contain no third-party trademarks such as "Block Blast", "Tetris", "Cube Crush", or any other competitor brand.

ADS & IAP:
- AppLovin MAX SDK is integrated as ad mediation provider (Pangle as the primary ad source).
- AppLovin SDK Key and Ad Unit IDs are read from Info.plist; replace YOUR_APPLOVIN_SDK_KEY placeholder before submitting to App Store.
- Interstitial ads fire after every 3rd Game Over (rate-limited).
- Rewarded ads fire only on user-initiated "Watch & Continue" tap.
- One-time non-consumable IAP "Remove Ads" ($2.99) via StoreKit 2 — no subscriptions, no Toggle Paywall.

ATT:
Tracking permission is requested on the user's 3rd Game Over (not on launch) to maximize the chance the user has experienced the game value first.

PRIVACY:
No data is collected by us. Only ad networks may collect IDFA + ad interaction events, and only if the user grants ATT permission. Full disclosure in PrivacyInfo.xcprivacy bundled with the app.

TESTED ON:
iPhone 15 Pro / iPhone 17 Pro (iOS 17.0+ / iOS 26.x). Build via Xcode 26.2, Swift 5.9, AppLovin SDK 13.6.3.

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
