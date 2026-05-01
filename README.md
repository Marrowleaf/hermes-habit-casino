# Habit Casino

> RPG gamification engine for real life — earn XP, unlock achievements, complete dynamic quests, and battle past versions of yourself.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://github.com/Marrowleaf/hermes-habit-casino)

## Features

- **casino:status** — Show current level, XP, active quests, streak, and RPG title
- **casino:quest** — Generate personalized daily quests based on goals and recent performance
- **casino:log** — Log real-life actions (gym, steps, reading, budget) and earn XP
- **casino:achieve** — Check for newly unlocked achievements and badges
- **casino:rivalry** — Compare stats against past versions of yourself
- **casino:leaderboard** — Weekly/monthly performance summaries with narrative flair
- 10-level progression system with unique titles and unlocks
- Dynamic quest difficulty scaling based on recent 7-day performance
- Real-world rewards tied to level-ups
- Integration with fitness-nutrition, budget-tracker, and habits skills
- Obsidian vault dashboard for persistent state tracking

## Installation

```bash
hermes skills install health/habit-casino
```

Or manually clone into `~/.hermes/skills/health/habit-casino/`.

## Usage

```
casino:status                          # Check your level, XP, and active quests
casino:quest                           # Get today's personalized quests
casino:quest --difficulty hard          # Request harder quests
casino:log went to the gym             # Log action and earn XP
casino:log 8k steps today              # Log steps
casino:log under budget today          # Log financial win
casino:achieve                         # Check for new achievements
casino:rivalry                         # Compare vs yesterday-you
casino:rivalry --vs best-streak        # Compare vs your best streak
casino:leaderboard --period month      # Monthly narrative summary
```

## Configuration

- All state stored in Obsidian at `~/obsidian-vault/Areas/Habit Casino/`
- Dashboard: `Areas/Habit Casino/Dashboard.md`
- Custom actions: `Areas/Habit Casino/Config/Custom Actions.md`
- Real-world rewards: `Areas/Habit Casino/Config/Rewards.md`
- XP values and level thresholds are defined in SKILL.md

## Requirements

- Hermes Agent v0.12+
- Obsidian vault (for persistent state tracking)
- Recommended: fitness-nutrition, budget-tracker, and habits skills for auto-logging

## License

MIT