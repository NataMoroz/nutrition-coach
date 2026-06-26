# nutrition-coach

> A nutrition coach that actually understands training, breastfeeding, and real life.
> Built as a Claude skill — works out of the box, learns your patterns, tracks your food.

---

## The story behind this

I've been athletic most of my life. Before getting pregnant I completed an Olympic-distance triathlon, ate clean, trained consistently. No meat for years. Never counted calories — just ate intuitively and it worked.

During pregnancy I kept moving. After giving birth I was back training by month two or three — swimming, running, cycling, gym, yoga. About five sessions a week.

Everyone told me breastfeeding would melt the weight off. It didn't. I was constantly hungry, the scale barely moved, and at some point I was actually gaining. Sleep got better. Body composition didn't.

A friend suggested something I'd never done before: count calories and create a small deficit. So I did what I always do — I went deep. I read through the research, looked at what actually applies to postpartum women (not just the generic fitness advice extrapolated from male studies), factored in breastfeeding, training load, and hormonal context. Then I built a set of instructions for Claude that reflected my specific situation.

It worked. Slowly, sustainably, without starving or sacrificing milk supply.

Friends started noticing. They asked what I was doing. I shared the Claude project, then decided to clean it up and make it available to anyone who needs it.

---

## What this is

A Claude skill for personalized nutrition coaching. It:

- Runs onboarding to build your profile (goals, training, health context, macro targets)
- Logs every meal to `meals.md` — a running food diary with daily totals
- Remembers your patterns and preferences across conversations via `user-data.md`
- Flags safety issues: protein gaps, too-aggressive deficits, calorie floor
- Understands female physiology — cycle phases, postpartum, breastfeeding
- Works in any language

It's not a generic macro calculator. It's a coach that learns you.

---

## Install

### Option A — Project skill (one project only)

```bash
mkdir -p .claude/skills/nutrition-coach
curl -o .claude/skills/nutrition-coach/SKILL.md \
  https://raw.githubusercontent.com/NataMoroz/nutrition-coach-skill/main/skills/nutrition-coach/SKILL.md
curl -o .claude/skills/nutrition-coach/onboarding.md \
  https://raw.githubusercontent.com/NataMoroz/nutrition-coach-skill/main/skills/nutrition-coach/onboarding.md
```

### Option B — User skill (available in all your projects)

```bash
mkdir -p ~/.claude/skills/nutrition-coach
curl -o ~/.claude/skills/nutrition-coach/SKILL.md \
  https://raw.githubusercontent.com/NataMoroz/nutrition-coach-skill/main/skills/nutrition-coach/SKILL.md
curl -o ~/.claude/skills/nutrition-coach/onboarding.md \
  https://raw.githubusercontent.com/NataMoroz/nutrition-coach-skill/main/skills/nutrition-coach/onboarding.md
```

### Option C — Clone manually

```bash
git clone https://github.com/NataMoroz/nutrition-coach-skill.git
cp -r nutrition-coach-skill/skills/nutrition-coach ~/.claude/skills/
```

> **Verify it loaded:** run `/skills` inside Claude Code — `nutrition-coach` should appear.

---

## First run

Open Claude Code and say anything food-related — or just say hi. The skill will detect it's your first time, run onboarding (~2 min), and create your personal `user-data.md` locally. After that, just log what you eat.

---

## Files

```
skills/nutrition-coach/
├── SKILL.md        — the coach: routing logic, coaching instructions, memory rules
└── onboarding.md   — first-run flow: collects your profile and creates user-data.md

Created on your machine (not in this repo):
├── user-data.md    — your profile, targets, and learnings
└── meals.md        — your food diary
```

---

## License

MIT
