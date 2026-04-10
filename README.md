# caveman skill

Ultra-compressed communication mode for Claude. Cuts token usage ~75% by dropping linguistic fluff while preserving full technical accuracy.

---

## What It Does

Switches Claude's response style to terse, caveman-like communication. Articles gone. Filler gone. Hedging gone. Technical substance stays intact. Code blocks and error messages always quoted exactly.

---

## Trigger Phrases

- `caveman mode`
- `talk like caveman`
- `use caveman`
- `less tokens`
- `be brief`
- `/caveman`

---

## Intensity Levels

Switch anytime with `/caveman <level>`. Default is **full**.

| Level | Style |
|-------|-------|
| `lite` | No filler or hedging. Articles and full sentences kept. Professional but tight. |
| `full` | Drop articles. Fragments OK. Short synonyms. Classic caveman. |
| `ultra` | Abbreviate everything (DB/auth/fn/req/res). Arrows for causality. One word when one word enough. |
| `wenyan-lite` | Semi-classical Chinese. Drop filler, keep grammar structure. |
| `wenyan-full` | Full 文言文. ~80-90% character reduction. Classical particles and patterns. |
| `wenyan-ultra` | Maximum classical Chinese compression. Extreme terseness. |

---

## Quick Example

**Prompt:** "Why does my React component re-render?"

| Level | Response |
|-------|----------|
| lite | "Your component re-renders because you create a new object reference each render. Wrap it in `useMemo`." |
| full | "New object ref each render. Inline object prop = new ref = re-render. Wrap in `useMemo`." |
| ultra | "Inline obj prop → new ref → re-render. `useMemo`." |
| wenyan-full | "物出新參照，致重繪。`useMemo`包之。" |

---

## Auto-Clarity Exceptions

Caveman mode pauses automatically for:

- Security warnings
- Irreversible or destructive action confirmations
- Multi-step sequences where fragment order risks misread
- Situations where the user is confused

Normal caveman resumes immediately after the critical part.

---

## Boundaries

- Code, commits, and PRs: always written normally regardless of level.
- Level persists across the session until changed.
- `stop caveman` or `normal mode` exits caveman entirely.

---

## File

`SKILL.md` — loaded by Claude at runtime to apply caveman rules.
