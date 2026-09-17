# Exercise: same plot, twice

You will ask Copilot for the same plot two times: once with a lazy prompt and no
context, once with an AGENTS.md file and plan mode. Then compare the two results.

The data: 240 participants did a Stroop task in a *control* or *stress* condition.
Columns include `condition`, `rt_mean_ms` (mean reaction time), `accuracy`, and `stress_score`.

## 1. Get set up  (2 min)

```
mkdir stroop
cd stroop
curl -O https://raw.githubusercontent.com/pzirlis/AI_Agents_Workshop/main/stroop_clean.csv
copilot
```
When asked, trust the folder.

## 2. Round one: lazy prompt  (3 min)

Type exactly this and let it run:

> plot reaction time by condition

Approve what it asks. When it finishes, note:
- Which language and plotting package did it pick?
- Where did it save the figure — or did it only print it?
- Did it ask you anything?

## 3. Write AGENTS.md  (3 min)

Create a file called `AGENTS.md` in the `stroop` folder (any text editor, or ask Copilot to
create it with this content). Four rules:

```
# AGENTS.md
- This is an R project. Use ggplot2 with theme_minimal() and a colourblind-safe palette.
- Save every figure to figures/ as PNG, 300 dpi, with a descriptive filename.
- Always propose a plan and wait for my approval before writing any code.
- Label axes with units (reaction time is in milliseconds).
```

## 4. Round two: plan mode + focused prompt  (5 min)

Restart Copilot so it reads the new file (`/exit`, then `copilot` again).
Press **Shift + Tab** to switch to plan mode. Then:

> Using @stroop_clean.csv, make one figure comparing mean reaction time between the
> control and stress conditions, showing the distribution and not just the means.
> Propose the plan first: plot type, what goes on each axis, filename. Wait for my approval.

Read the plan. Change one thing if you like (a different plot type, a title). Approve.

## 5. Compare  (2 min)

Open both figures side by side. Everything different between them came from AGENTS.md
and the prompt — not from a smarter model.

---
### If you finish early
Ask in plan mode: "Add a second panel showing accuracy by condition, same style."
See whether it follows AGENTS.md without you repeating the rules.
