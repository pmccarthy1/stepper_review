# Sequoia Stepper – Stakeholder Review Prototype

**Live demo:** https://pmccarthy1.github.io/stepper_review/

> A clickable HTML prototype of the Stepper component from the Sequoia Design System Library, built for stakeholder review. No frameworks or build step required — single self-contained `index.html`.

---

## What Was Built

### Source
Design system: Sequoia Library — Stepper component (Stepper Organism + Atoms/Molecules sections)

---

### Prototype Features

#### Tab 1 · Horizontal Stepper
| Feature | Detail |
|---|---|
| Interactive navigation | Next / Back buttons advance or retreat through steps |
| Click-to-jump | Clicking any step dot jumps directly to that step |
| Live step count control | +/− toggle switches between 2–8 step configurations |
| Progress chip | "Step X of N" label updates in real time |
| Static variant gallery | Side-by-side snapshots of 3-, 5-, and 8-step configs at mid-progress |
| Mobile breakpoint | 375px viewport frame with smaller (24px) dots |

#### Tab 2 · Vertical Stepper
| Feature | Detail |
|---|---|
| 5-step interactive demo | Steps expand on active with description text |
| Right-side content panel | Updates to show active step title + placeholder form area |
| Next / Back navigation | Advances through all 5 steps |
| Static 3-step variant | Non-interactive reference showing completed / current / incomplete |

#### Tab 3 · Anatomy & States
| Feature | Detail |
|---|---|
| Dot state reference | All three states rendered: Incomplete, Current, Complete — in both icon and numeral variants |
| Connector line states | Gray (incomplete) vs blue (complete) line examples |
| Anatomy labels | Numbered callouts for dot, connector, and label |
| Color token table | Maps each token name and hex value to its usage role |

---

## Design Rules Inferred from Figma

### Component Versions
The Figma file contains three named versions of the stepper:
- **Legacy** — older pattern, hidden in the organism frame
- **Rebrand** — current production version
- **Proposed** — next iteration under consideration

This prototype implements the **Rebrand** style with visual references to the **Proposed** variant where relevant.

---

### Step Dot

| State | Fill | Border | Icon |
|---|---|---|---|
| Incomplete | White (`#FFFFFF`) | 2px solid `#E0E0E0` | Step number (gray `#9E9E9E`) |
| Current | `#0057FF` | 3px solid white + 3px outer ring `#0057FF` | White center dot |
| Complete | `#0057FF` | 2px solid `#0057FF` | White checkmark (✓) |

**Sizes:**
- Desktop default: `32×32px`
- Mobile / small variant: `24×24px`

---

### Connector Line

| State | Color | Thickness |
|---|---|---|
| Incomplete (ahead) | `#E0E0E0` | 4px |
| Complete (behind current) | `#0057FF` | 4px |

Lines fill from left-to-right as steps are completed. The line directly before the current step is blue; all lines after are gray.

---

### Step Label

| State | Weight | Color |
|---|---|---|
| Incomplete | Regular (400) | `#9E9E9E` |
| Current | Bold (700) | `#212121` |
| Complete | Regular (400) | `#616161` |

Labels sit centered below their dot. Only the active step label is bold.

---

### Step Count Variants

The Figma organism frame includes explicit configurations for:
- **3 steps** (desktop + mobile)
- **5 steps** (desktop)
- **8 steps** (desktop)

The prototype supports 2–8 steps dynamically.

---

### Orientation Variants

| Variant | Breakpoints | Notes |
|---|---|---|
| Horizontal | Desktop, Mobile | Dots connected by horizontal lines; labels below dots |
| Vertical | Desktop | Dots stacked with vertical connector lines; labels / content to the right |

The vertical stepper supports a content expansion panel alongside — step body text and form content appear inline when a step is active.

---

### Interaction Behavior

- **Click completed step** → jump back to that step (all subsequent steps reset to incomplete)
- **Click incomplete step** → jump forward to that step
- **Hover on complete dot** → darkens to `#0041CC`
- **Hover on incomplete dot** → border and numeral shift to `#0057FF`

---

### Color Tokens

| Token | Hex | Role |
|---|---|---|
| `--blue-primary` | `#0057FF` | Current + complete dot fill; complete line |
| `--blue-hover` | `#0041CC` | Hover state for filled dots |
| `--blue-light` | `#E8F0FF` | Progress chip background |
| `--gray-200` | `#E0E0E0` | Incomplete dot border; incomplete connector line |
| `--gray-400` | `#9E9E9E` | Incomplete step label; incomplete numeral |
| `--gray-600` | `#616161` | Complete step label; secondary text |
| `--gray-900` | `#212121` | Current step label (bold) |

---

## File Structure

```
stepper-prototype/
├── index.html   # Self-contained prototype (HTML + CSS + JS, no dependencies)
└── README.md    # This file
```

---

## Updating the Live Demo

Edit `index.html`, then push the updated file to the `gh-pages` branch of the hosting repo.
