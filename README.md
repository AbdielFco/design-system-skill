# Design System Skill

> Turn a web page into a design system, then build new UI in that style.

Give Cursor a page or a component. The skills answer with custom CSS: tokens, component styles, and HTML.

## What it offers

| Mode | What you ask for | What you get |
|---|---|---|
| Analyze | A URL, a screenshot, or an HTML snippet | Tokens, component CSS, and a prompt you can reuse on the next screen |
| Dark SaaS | A component in the dark system | Raw HTML and CSS on a near-black UI |

## What it uses

- HTML and custom CSS
- Colors, type, spacing, radii, and borders as `:root` variables
- Inter
- Flexbox or grid, with gaps on an 8px scale (`0.5rem`, `1rem`, `1.5rem`)
- 1px borders for depth

## How it works

1. Cursor loads the skills in `.cursor/skills/` when this folder is the open workspace.
2. **Analyze** reads the page and returns three sections: tokens, component styles, and a reusable prompt.
3. **Dark SaaS** builds the component you named and returns only HTML and CSS.
4. Save an analysis as `guides/<page-slug>.md` so a later component can follow that page.

## Use

Open this folder as the Cursor workspace.

To use the skills in another project, copy these folders into that project's `.cursor/skills/`:

- `design-system-analyze`
- `design-system-reusable` (dark SaaS)

To use them in every project on this machine:

```bash
mkdir -p ~/.cursor/skills
cp -R .cursor/skills/design-system-analyze ~/.cursor/skills/
cp -R .cursor/skills/design-system-reusable ~/.cursor/skills/
```

Run that from this folder.

## Quick start

Analyze a page:

```text
Analyze this page and write the design system:
https://example.com
```

Build with a built-in system:

```text
Build a pricing card with three tiers in the dark SaaS style.
```

```text
Build the same pricing card with the prompt in examples/light-saas.md.
```

## Examples

Both files are a reusable prompt you can copy. Dark is also the skill Cursor loads. Light is the example only.

### Dark SaaS

[examples/dark-saas.md](examples/dark-saas.md) · skill [`.cursor/skills/design-system-reusable/SKILL.md`](.cursor/skills/design-system-reusable/SKILL.md)

| Token | Value |
|---|---|
| Page | `#0A0A0A` |
| Card | `#111111`, 1px `#27272A`, 24px padding, 8px radius |
| Text | `#EDEDED` / `#A1A1AA` |
| Button | `#EDEDED` background, `#0A0A0A` text, 6px radius |
| Accent | `#3B82F6` |

### Light SaaS

[examples/light-saas.md](examples/light-saas.md)

| Token | Value |
|---|---|
| Page | `#FFFFFF` |
| Card | `#F4F4F5`, 1px `#E4E4E7`, 24px padding, 8px radius |
| Text | `#0A0A0A` / `#71717A` |
| Button | `#0A0A0A` background, `#EDEDED` text, 6px radius |
| Accent | `#3B82F6` |

## Analysis output

An analysis is these three sections, in this order. Save the file under `guides/`.

1. Design System Tokens, as `:root` variables
2. UI Patterns and Component Styles, as CSS classes
3. Reusable Developer Prompt, in a code block

Skill: [`.cursor/skills/design-system-analyze/SKILL.md`](.cursor/skills/design-system-analyze/SKILL.md)
