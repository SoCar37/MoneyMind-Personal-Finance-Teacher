# MoneyMind-Personal-Finance-Teacher
MoneyMind Personal Finance Teacher App
# MoneyMind v1.3 — Release Notes

## What's New in v1.3

### 🏷️ Layer + Module Labels on Every Card
Each module card now shows its position within its layer — e.g. **"Layer 1: Foundation · Module 2 of 4"**. This gives a clear sense of where you are and how much is left within each layer without overwhelming the user with a global count. Locked modules show the label at reduced opacity so the structure is visible but not distracting.

### 👋 Name Personalization
On first launch, MoneyMind asks "What should we call you?" before entering the app. The name is stored locally on the device and used to personalize the home screen greeting ("Hey, Marcus! 👋"). The greeting message also adapts based on progress — different text for just starting, in progress, and fully complete. A **✏️ Change Name** button in the progress screen lets users update it any time.

### 🔢 Dynamic Module Count
The "X total" count on the home screen progress bar is now pulled from the live modules array instead of being hardcoded. Stays accurate as content is added in future versions.

### ❌ Wrong Answer Explanations
When a quiz question is answered incorrectly, the app now:
- Highlights the selected wrong answer in red
- Highlights the correct answer in green
- Shows a question-specific explanation naming the correct answer and the reasoning behind it

Every one of the 12 quiz questions has its own tailored wrong-answer explanation — not a generic message. For example, getting Q1 wrong shows: *"❌ Not quite — the answer is $1,200. You're spending $200 more than you earn each month ($1,700 - $1,500). Over 6 months that adds up to $200 × 6 = $1,200 in debt. Small monthly gaps compound fast."*

---

## Bug Fixes

- **Unlock chain fixed** — completing a module now correctly marks it done and unlocks the next. Root cause: `nextStep()` never called `completeModule()` because the `'complete'` step was the last array entry, not a trigger for completion logic.
- **Continue button restored** — button is back inside the scrollable lesson content (reliable across all browsers). iOS bounce handled with `overscroll-behavior: none` on html/body.
- **Quiz answer corrected** — coffee spending question updated from "every weekday / $1,300" to "every day / $1,825" (more impactful number, unambiguous wording).
- **JavaScript syntax error fixed** — unescaped apostrophes in checkin response strings (c4–c6) were silently breaking the entire script, preventing the Let's Begin button from working.
- **Module count display** — was hardcoded to "13 total"; now dynamic.
- **Font contrast fixes** — name input on splash screen was white text on a near-white background (now white input with dark text and sage border). Module layer/position labels were too faint on white cards (bumped to readable contrast; locked cards remain dimmed).

---

## Content (unchanged from v1.2)

| Layer | Name | Modules | XP |
|-------|------|---------|-----|
| 1 | Foundation | 4 (required, sequential) | 230 |
| 2 | Applied Tools | 3 (interactive calculators) | 190 |
| 3 | Deep Concepts | 4 | 300 |
| 4 | Real Scenarios | 2 | 165 |
| 5 | Reflection | 1 | 60 |
| **Total** | | **14 modules** | **945 XP** |

---

## Version History

| Version | Highlights |
|---------|-----------|
| v1.0 | Initial release — 10 modules, 5 layers, badges, tips |
| v1.1 | localStorage persistence, streak tracking, reset button |
| v1.2 | 14 modules, expanded Layer 1 depth, new Layer 2/3/4/5 content, scenario doubling |
| **v1.3** | **Name personalization, layer+module labels, wrong-answer explanations, bug fixes** |

---

## Roadmap

### v1.4 — Content Expansion
- Show correct answer + explanation on wrong quiz selection *(completed in v1.3)*
- Layer 3: Understanding Taxes for Gig Workers
- Layer 3: Building Credit from Scratch
- Layer 4: Part 3 scenarios (longer-term decisions)
- Layer 5: Quarterly deep-dive reflection

### v2.0 — Polish & Platform
- Dark mode
- PWA manifest + offline support
- Animated badge unlock celebrations
- Native Android PWA wrapper
- Spanish (Latin American) localization

---

*© 2026 Burle Warren. All Rights Reserved.*
