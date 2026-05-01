---
name: habit-casino
description: "RPG gamification engine for your actual life. Your agent IS the game master — dynamic quests, XP, achievements, rivalries, and narrative flavour text."
version: 1.0.0
author: Hermes Agent
license: MIT
metadata:
  commands:
    - name: casino:status
      description: "Show current level, XP, active quests, streak info, and RPG title"
      usage: casino:status
      examples:
        - "casino:status"
    - name: casino:quest
      description: "Generate or show today's quests based on goals and recent performance"
      usage: casino:quest [--difficulty easy|medium|hard|epic]
      examples:
        - "casino:quest"
        - "casino:quest --difficulty hard"
    - name: casino:log
      description: "Log a real-life action and earn XP"
      usage: casino:log [action description]
      examples:
        - "casino:log went to the gym"
        - "casino:log 8k steps"
        - "casino:log under budget today"
        - "casino:log read for 30 minutes"
    - name: casino:achieve
      description: "Check for newly unlocked achievements and badges"
      usage: casino:achieve
      examples:
        - "casino:achieve"
    - name: casino:rivalry
      description: "Compare today's stats against past versions of yourself"
      usage: casino:rivalry [--vs yesterday|last-week|best-streak]
      examples:
        - "casino:rivalry"
        - "casino:rivalry --vs best-streak"
    - name: casino:leaderboard
      description: "Weekly/monthly performance summary with RPG narrative"
      usage: casino:leaderboard [--period week|month]
      examples:
        - "casino:leaderboard"
        - "casino:leaderboard --period month"
---

# 🎰 Habit Casino

**Your life is the game. Your agent is the dungeon master.**

Habit Casino turns your actual daily activities into an RPG — but not a shallow gamification skin. The agent IS the game master. It designs quests around YOUR specific goals, adjusts difficulty dynamically based on YOUR recent performance, creates rivalries with past versions of yourself, and generates narrative flavour text that makes the mundane feel epic.

Every real-life action earns XP. Steps, gym visits, staying under budget, reading, sleep quality — everything counts. But the magic is the agent: it watches how you're doing, generates quests that push you just enough, and writes flavour text that makes "I went to the gym" feel like "You descended into the Iron Sanctuary and emerged stronger."

## XP System

### Earning XP

| Action | Base XP | Notes |
|--------|---------|-------|
| Gym/workout | 50 | +25 if before 7am, +15 if consecutive day |
| Steps (per 1k over 5k) | 10 | Bonus XP for hitting step milestones |
| Under daily calorie target | 30 | +20 if under by 200+ |
| Protein target met | 25 | 162g+ for user's profile |
| Reading (per 15 min) | 15 | +10 if non-fiction |
| Under budget (daily) | 40 | +20 if £10+ under |
| Good sleep (7+ hours) | 20 | +10 if 8+ hours |
| Hydration (2L+) | 15 | Tracked manually |
| Journaling/gratitude | 20 | Written in Obsidian |
| No alcohol | 30 | +15 if on a weekend |
| Meditation | 25 | 10+ minutes |
| Cooking at home | 20 | +10 if meal-prep for week |

### Level Progression

| Level | XP Required | Title | Unlock |
|-------|-------------|-------|--------|
| 1 | 0 | Wandering Novice | Basic quest access |
| 2 | 500 | Apprentice Wanderer | Daily quests |
| 3 | 1,200 | Steady Strider | Rivalry mode unlocked |
| 4 | 2,000 | Resolute Trekker | Hard difficulty quests |
| 5 | 3,500 | Iron Path Runner | Achievement badges |
| 6 | 5,500 | Discipline Adept | Custom quest design |
| 7 | 8,000 | Endurance Sage | Weekly tournaments |
| 8 | 11,000 | Virtue Champion | Epic difficulty quests |
| 9 | 15,000 | Stalwart Paragon | Title customisation |
| 10 | 20,000 | Sovereign of Self | Define your own real-world reward |

### Real Rewards

At each level, you can define a real-world reward:
- Level 5: "Buy that book I've been eyeing"
- Level 8: "New gym shorts"
- Level 10: "Those trainers"

These are stored in your Obsidian vault and claimed on level-up.

## Quests

### How Quests Work

The agent generates quests based on:
1. **Your goals** — pulled from your Obsidian vault and fitness profile
2. **Recent performance** — if you've been slacking on steps, you get a step quest
3. **Difficulty calibration** — quests are achievable but push you
4. **Variety** — it won't assign the same quest type 3 days running

### Quest Types

**Daily Quests** (refresh every morning at 6am)
- 2-3 quests assigned per day
- Each has XP value and difficulty rating
- Bonus XP for completing all daily quests

**Weekly Challenges** (refresh Monday)
- 1 major challenge spanning the whole week
- Higher XP reward, usually multi-day commitment
- Example: "Walk 100k steps this week" or "Cook dinner every night"

**Epic Quests** (monthly)
- One major life goal challenge per month
- Massive XP reward
- Example: "Lose 1kg this month" or "Read 2 books"

### Difficulty Scaling

The agent adjusts quest difficulty based on your recent 7-day performance:
- **On a hot streak** (7+ days consistent) → quests get harder
- **Just getting back** (missed 3+ days) → quests get easier, more encouraging
- **Middle ground** → moderate difficulty, slight stretch

### Quest Generation Process

1. Check the last 7 days of logged actions via Obsidian + session history
2. Identify areas of strength (keep these as bonus quests) and weakness (these become focus quests)
3. Generate 2-3 quests that:
   - Are achievable today (not "run a marathon")
   - Push slightly beyond comfort zone
   - Vary across categories (physical, financial, mental, social)
   - Have flavour-appropriate names and descriptions

**Example quest generation:**
```
⚔️ Daily Quests — Wednesday, Day 14 of Your Journey

1. 🏋️ The Iron Covenant (Medium — 75 XP)
   "The weights call. Answer them."
   → Hit the gym today. +25 bonus XP if you go before 8am.

2. 🚶 The Pedestrian's Path (Easy — 40 XP)
   "Your feet know the way to 10,000 steps."
   → Reach 10k steps today. You're at 8.2k average this week — close.

3. 💰 The Frugal Feast (Medium — 60 XP)
   "A sovereign saved is a sovereign earned."
   → Cook dinner at home tonight. Your meal-prep skill has recipes ready.

🎯 Complete all 3 for a 100 XP bonus!
```

## Achievements

### Achievement Categories

**Streak Achievements** (consistency)
- 🔥 Kindling — 3-day gym streak
- 🔥 Blaze — 7-day gym streak
- 🔥 Inferno — 14-day gym streak
- 🔥 Eternal Flame — 30-day gym streak ("Dragon Slayer")
- 🚶 Pathfinder — 7 consecutive 10k step days
- 🚶 Wayfinder — 14 consecutive 10k step days
- 💰 Copper Saver — 7 days under budget
- 💰 Gold Hoarder — 30 days under budget

**Milestone Achievements** (cumulative)
- ⚔️ Centurion — 100 gym visits
- 🚶 Million Step March — 1,000,000 total steps
- 📚 Scholar — Read 10 books
- 🍗 Protein Monarch — Hit protein target 30 times
- 💤 Dream Weaver — 30 nights of 7+ hours sleep

**Special Achievements** (one-time)
- 🌅 Dawn Warrior — Gym before 6am
- 🥶 Ice Bath Spartan — Gym on a day below 0°C
- 🎄 No Holiday — Gym on Christmas Day
- 🏔️ Mountain climber — 20k steps in a single day
- 💪 Iron Discipline — 0 alcohol for 30 consecutive days

**Meta Achievements** (meta-game)
- 🎰 First Roll — Log your first action
- 📊 Statistician — Check status 7 days in a row
- ⚖️ Balanced — Complete a quest in every category in one week
- 🔄 Comeback Kid — Resume after 7+ day break

### Achievement Format

Each achievement has:
- **Icon** — RPG-style emoji
- **Name** — Thematic title
- **Flavour text** — Narrative description
- **XP bonus** — One-time XP reward for unlocking
- **Unlock condition** — What triggers it

**Example:**
```
🏆 Achievement Unlocked: Dragon Slayer

"You faced the dragon of inertia for 30 consecutive days.
Its flames grew weaker with each visit. On the 30th dawn,
you emerged from the Iron Sanctuary, scales glinting,
knowing the beast would never threaten you again."

+500 XP | +Title: "Dragon Slayer"
```

## Rivalry System

### How It Works

You compete against past versions of yourself — not other people. The agent tracks your stats and creates NPC-like rivals from your history.

### Rival Types

- **Yesterday-You** — Can you beat what you did yesterday?
- **Last-Week-You** — Can you outperform the last 7 days?
- **Best-Streak-You** — Your peak performance. The ultimate rival.
- **Level-N-You** — What were you like at Level 3? Can Level-8-You beat it?

### Rivalry Display

```
⚔️ rivalry Report — vs Best-Streak-You (March 10-23)

         You (This Week)    Best-Streak-You
Steps    72,400              81,200          ⚠️ -8,800
Gym      4 visits            6 visits         ⚠️ -2
Budget   £12 under           £45 under        ⚠️ -£33
Sleep    7.2h avg            7.8h avg         ⚠️ -0.6h

🛡️ Best-Streak-You is winning.
But you're gaining on steps (up 15% vs last week).
Keep pushing — legends aren't made in comfort.
```

## Obsidian Integration

### Vault Structure

All Habit Casino data is stored in your Obsidian vault:

```
~/obsidian-vault/
  Areas/
    Habit Casino/
      Dashboard.md          — Current status, level, active quests
      Achievement Log.md     — Unlocked achievements with dates
      Rivalry History.md     — Past rivalry results
      Stats/
        Daily Log.md         — Logged actions with XP earned
        Weekly Summary.md    — Auto-generated weekly narratives
        Level History.md     — XP progression over time
      Config/
        Rewards.md           — Real-world rewards per level
        Custom Actions.md    — User-defined actions and XP values
```

### Dashboard Template

```markdown
# 🎰 Habit Casino — Dashboard

**Level:** [N] — [Title]
**XP:** [current] / [next level]
**Streak:** [N] days
**Active Quests:** [list]

## Today
- [ ] Quest 1: [name] ([difficulty], [XP] XP)
- [ ] Quest 2: [name] ([difficulty], [XP] XP)
- [ ] Quest 3: [name] ([difficulty], [XP] XP)

## Recent Achievements
🏆 [achievement] — [date]

## Rivalry Status
⚔️ vs Best-Streak-You: [winning/losing/tied]
```

## Integration with Other Skills

Habit Casino works best when connected to other skills:

- **fitness-nutrition** — Auto-logs gym visits, step counts, calorie targets
- **apple-health-sync** — Pulls real step/sleep/workout data from Apple Health
- **budget-tracker** — Tracks daily spending against budget for XP
- **habits** — Uses habit tracking data for streak calculations
- **weather-alerts** — Modifies quest difficulty based on weather (harder gym quest if it's pouring)

## Commands (Detailed)

### `casino:log`

Log a real-life action and earn XP. The agent interprets natural language:

```
casino:log went to the gym
→ ⚔️ +50 XP — Iron Sanctuary visited!
   +25 bonus (before 8am!)
   Total: 75 XP

casino:log had 8k steps today
→ 🚶 +30 XP — 8,000 steps logged
   (Need 10k for full Pathfinder bonus — keep walking!)
   Total: 30 XP

casino:log stayed under budget
→ 💰 +40 XP — Fiscal discipline!
   +20 bonus (saved £15!)
   Total: 60 XP

casino:log read for 30 minutes
→ 📚 +30 XP — Knowledge consumed!
   Total: 30 XP
```

The agent also logs the entry to the Obsidian Daily Log with timestamp, action, XP earned, and running total.

### `casino:leaderboard`

Weekly or monthly summary with RPG narrative:

```
📊 Monthly Leaderboard — May 2026

🏆 Level Progress: 6 → 7 (Discipline Adept)
⚡ XP Earned: 3,200 / 8,000 for Level 8
🔥 Best Streak: 12 days (gym)
📚 Top Activity: Gym (18 visits, 1,350 XP)
🪖 Biggest Day: May 14 — 280 XP (gym + steps + budget + reading)

📜 The Chronicler Writes:
"Month of May saw the Wanderer push beyond the familiar.
The Iron Sanctuary doors opened 18 times — more than any
previous month. Steps accumulated like cobblestones on
a long road, and the treasury grew. The next challenge
beckons: Endurance Sage awaits at Level 8, and the
path requires 4,800 more XP of dedication."
```

## Pitfalls

1. **Don't make it a chore** — If logging feels tedious, the system is broken. Keep logging natural with brief natural language.

2. **Balance XP values carefully** — Gym (50 XP) should feel rewarding but not dwarf reading (15 XP). Every action should matter.

3. **Dynamic difficulty is critical** — Never assign "run 10 miles" to someone who doesn't run. Quests must be calibrated to the individual's current level.

4. **The rivalry system should motivate, not demoralise** — Always include a positive angle. "You're gaining on your best streak" not "you're losing."

5. **Keep flavour text fun, not cringe** — Avoid forced medieval language. Write like a good RPG narrator, not a LARPer at Ren Faire.

6. **Real rewards must be user-defined** — Never auto-purchase or promise anything financial. Rewards are self-declared goals, not agent actions.

7. **Don't gamify everything** — Some things shouldn't be gamified (mental health crises, grief, serious illness). The agent should recognise and disable casino mode during difficult periods.

8. **Obsidian is the source of truth** — All state is stored in the vault, not in memory. If the vault is missing, reconstruct from session history.

9. **Integration with Apple Health requires the apple-health-sync skill** — Don't attempt to parse Health data directly.

10. **Alcohol-free streak tracking** — Only count "no alcohol" days that are explicitly logged or verified. Don't assume silence = sobriety.

## Verification

- [ ] Run `casino:status` and see your current level, XP, and streak
- [ ] Run `casino:quest` and get 2-3 personalised daily quests
- [ ] Run `casino:log went to the gym` and see XP earned with flavour text
- [ ] Run `casino:achieve` and see any newly unlocked achievements
- [ ] Run `casino:rivalry` and compare stats against past-you
- [ ] Run `casino:leaderboard --period week` and see a narrative weekly summary
- [ ] Check `~/obsidian-vault/Areas/Habit Casino/Dashboard.md` exists and is updated
- [ ] Verify XP calculations are correct and level thresholds match the table above

## The Philosophy

Most habit trackers punish you for missing days. Habit Casino rewards you for showing up. It doesn't shame you for breaking a streak — it creates a new rival called "Comeback Quest" that gives you bonus XP for resuming after a break.

The real innovation isn't the gamification. It's the **agent as game master**. A static app gives you the same quests every day. An agent watches your patterns, adjusts difficulty, writes narrative that matches your actual journey, and creates rivalries that are deeply personal because they're literally against your past self.

**Your life is the game. Play it well.**