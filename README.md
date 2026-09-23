# Anti-Slop Atlas

> A curated map of skills, MCP servers, and design references that keep coding agents (Claude Code, Codex, Muse Code, Cursor, Copilot, Gemini CLI, and others) from shipping **AI slop frontends**.

You know the look: a purple-to-blue gradient hero, Inter everywhere, a centered headline over three identical feature cards, untouched shadcn defaults, glassmorphism on everything, emoji standing in for icons, and a dark mode that is really one big radial blob. Agents default to it because it is the statistical average of the web.

This list collects the tools that push agents away from that average and toward deliberate, reviewable design.

**Criteria for inclusion:** the resource has to change what an agent *produces* (a skill, rule set, or MCP server), or give it better *input* (design systems, tokens, guidelines), or let it *see and check* its own output (browser and audit tools). Plain component libraries and generic prompt collections don't count.

Star counts are a snapshot from September 2026. They show popularity, not quality.

## Contents

- [The slop tells](#the-slop-tells)
- [Anti-slop design skills](#anti-slop-design-skills)
- [Official skills from agent and platform vendors](#official-skills-from-agent-and-platform-vendors)
- [Specialized and stylistic skills](#specialized-and-stylistic-skills)
- [Design context: DESIGN.md, tokens and guidelines](#design-context-designmd-tokens-and-guidelines)
- [MCP servers: design sources](#mcp-servers-design-sources)
- [MCP servers: component registries](#mcp-servers-component-registries)
- [MCP servers: eyes on the output](#mcp-servers-eyes-on-the-output)
- [Per-agent install notes](#per-agent-install-notes)
- [Related lists](#related-lists)
- [Contributing](#contributing)

## The slop tells

A quick checklist you can paste into any agent's rules file (`CLAUDE.md`, `AGENTS.md`, `.cursor/rules`, and so on). If a design has three or more of these and nobody chose them on purpose, it's slop.

| Tell | Do this instead |
| --- | --- |
| Purple/indigo → blue gradient as the brand | Pick one dominant color that fits the product, plus one sharp accent |
| Inter / system sans for everything | Pair a display face that has character with a readable body face |
| Centered hero → 3 feature cards → testimonial → CTA | Build the layout around the content. Asymmetry is allowed |
| Untouched shadcn/ui defaults (radius, zinc, shadows) | Set your own tokens before you add any components |
| Glassmorphism, glow blobs, and radial "AI dark mode" | Flat surfaces with real contrast. Keep depth for things that need it |
| Emoji as icons | Use one consistent vector icon set, or no icons |
| Every card has the same padding, radius and shadow | Show hierarchy through spacing and weight, not decoration |
| Fade-up-on-scroll on every section, 400ms ease-in | Animate one or two meaningful moments and keep them short |
| Filler copy ("Unlock the power of…", "Seamless", "Revolutionize") | Say what the product does in plain words |
| Vanity visuals (3D globes, fake dashboards, abstract orbs) | Show the real product, or nothing |

## Anti-slop design skills

Skills whose whole purpose is to make agents design with taste, or to audit and rewrite output that doesn't.

- [Taste Skill](https://github.com/Leonxlnx/taste-skill) (~90k ★): a suite of taste variants (minimalist and others) plus image-generation skills. Three tunable parameters act like an equalizer on the output.
- [UI/UX Pro Max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) (~130k ★): a design-intelligence skill that generates a whole design system for your project, with dozens of named styles, color palettes by product category, and font pairings. Works across many agents.
- [Impeccable](https://github.com/pbakaus/impeccable) (~70k ★): gives you and the agent a shared design vocabulary. Commands like `polish`, `audit`, `critique`, `distill`, `animate`, `bolder` and `quieter` each load references on typography, color, motion, space, interaction, responsiveness and UX writing.
- [Hallmark](https://github.com/Nutlope/hallmark) (~29k ★): an anti-AI-slop design skill for Claude Code, Cursor and Codex. It refuses pixel-clones and paid templates.
- [anti-slop](https://github.com/miqdadbadjuber/anti-slop) (~3.6k ★): rules that filter generic AI output across UI, copy and code.
- [anti-ui-slop](https://github.com/github/awesome-copilot/tree/main/skills/anti-ui-slop) (in awesome-copilot): a community skill from GitHub's Copilot collection, with a reference folder and agent definitions. Also on the [awesome-copilot site](https://awesome-copilot.github.com/skill/anti-ui-slop/).
- [avoid-ai-design](https://github.com/funboy322/avoid-ai-design): audits frontend that's already been generated, scores it, and rewrites the slop patterns (purple gradients, Inter, default shadcn). The design counterpart to avoid-ai-writing.
- [claude-frontend-skills](https://github.com/Koomook/claude-frontend-skills): a Claude Code plugin that pushes toward bold, distinctive interfaces and away from generic fonts, gradients and minimal motion.
- [codex-skills](https://github.com/vipulgupta2048/codex-skills): a fix for the "purple slop" that Codex's frontend skill produces by default.
- [anti-slop-design](https://github.com/wwewtech/anti-slop-design): a strict rule set that enforces a 1-to-3 UX hierarchy, tactile micro-interactions, and a 7-axis quality check before any code is emitted.

## Official skills from agent and platform vendors

- [Anthropic: frontend-design skill](https://github.com/anthropics/skills/tree/main/skills/frontend-design): Anthropic's reference skill for distinctive, production-grade UI. It also ships as a [Claude Code plugin](https://github.com/anthropics/claude-code/tree/main/plugins/frontend-design).
- [Muse Code: `/taste`](https://dev.meta.ai/resources/blog/build-with-muse-code/): Meta's Muse Code bundles `/taste`, a flat checklist of visual defaults *not* to use, alongside `/grilling`, which questions you one decision at a time until the design holds up. Both run only when you invoke them explicitly.
- [Vercel: web-design-guidelines](https://github.com/vercel-labs/agent-skills/tree/main/skills/web-design-guidelines): reviews UI code against Vercel's [Web Interface Guidelines](https://github.com/vercel-labs/web-interface-guidelines) and reports findings as `file:line`.
- [OpenAI: curated Codex skills](https://github.com/openai/skills/tree/main/skills/.curated): includes `figma-implement-design`, `figma-create-design-system-rules`, `figma-generate-library`, `playwright` and `screenshot`. The catalog is deprecated in favor of [openai/plugins](https://github.com/openai/plugins).

## Specialized and stylistic skills

For a specific aesthetic or craft instead of a general anti-slop filter.

- [Emil Kowalski: skills](https://github.com/emilkowalski/skills) (~40k ★): skills for designers and engineers from the author of Sonner and Vaul, with a focus on animation and interaction craft.
- [make-interfaces-feel-better](https://github.com/jakubkrehel/make-interfaces-feel-better): the polish that makes an interface feel right, beyond just looking right.
- [UI Skills](https://github.com/ibelick/ui-skills): skills for design engineers, browsable at [ui-skills.com](https://www.ui-skills.com/).
- [Huashu Design](https://github.com/alchaincyf/huashu-design): an HTML-native design skill for high-fidelity prototypes, slides and animations. It includes 20 design philosophies and a 5-dimension review.
- [Nothing Design Skill](https://github.com/dominikmartn/nothing-design-skill): generates UI in the Nothing design language: monochrome, typographic, industrial.

## Design context: DESIGN.md, tokens and guidelines

Agents fall back to slop when nobody has told them what the brand looks like. These resources give them that information.

- [DESIGN.md spec](https://github.com/google-labs-code/design.md): a format for describing a visual identity to coding agents, so they keep a persistent, structured picture of your design system.
- [awesome-design-md](https://github.com/VoltAgent/awesome-design-md) (~117k ★): DESIGN.md files based on popular brands' design systems. Add one to your project to get a matching UI.
- [Dembrandt](https://github.com/dembrandt/dembrandt): pulls any website's design system (logo, colors, typography, borders) into tokens with one command.
- [Web Interface Guidelines](https://github.com/vercel-labs/web-interface-guidelines): Vercel's rules for building web interfaces. Short enough to paste into a rules file.
- [userinterface.wiki](https://github.com/raphaelsalaja/userinterface-wiki): a living manual for better interfaces.

## MCP servers: design sources

Let the agent build from a real design instead of guessing.

- [Figma MCP server](https://help.figma.com/hc/en-us/articles/32132100833559-Guide-to-the-Figma-MCP-server): Figma's official server, in remote and desktop versions. It exposes frames, variables and components to agents. [Usage guide](https://github.com/figma/mcp-server-guide).
- [Framelink Figma MCP](https://github.com/GLips/Figma-Context-MCP) (~16k ★): a community server that simplifies Figma layout data for agents like Cursor.
- [Penpot MCP](https://github.com/penpot/penpot-mcp): the official MCP server for Penpot, the open-source design tool.

## MCP servers: component registries

Give the agent tested components so it doesn't invent its own, and restyle them with your tokens.

- [shadcn/ui MCP](https://ui.shadcn.com/docs/mcp): the official server. It browses, searches and installs items from any shadcn-compatible registry.
- [shadcn-ui-mcp-server](https://github.com/Jpisnice/shadcn-ui-mcp-server): a community server that gives context on shadcn component structure and usage for React, Svelte 5, Vue and React Native.
- [21st.dev MCP (formerly Magic)](https://github.com/21st-dev/magic-mcp): search 10k+ React/Tailwind components or generate new ones from your editor.
- [Magic UI MCP](https://github.com/magicuidesign/mcp): Magic UI's animated components, searchable and installable.
- [Context7](https://github.com/upstash/context7): up-to-date library docs, so the agent uses current Tailwind and framework APIs.

> A warning: a component registry makes your UI *consistent*. It doesn't make it *distinctive*. Set your own tokens first, or you'll ship default shadcn slop.

## MCP servers: eyes on the output

An agent that can't see its render can't tell that the render is slop. Close the loop with screenshots, then critique, then revise.

- [Chrome DevTools MCP](https://github.com/ChromeDevTools/chrome-devtools-mcp) (~52k ★): controls and inspects a live Chrome, with screenshots, performance traces, Lighthouse and console access.
- [Playwright MCP](https://github.com/microsoft/playwright-mcp) (~37k ★): browser automation using accessibility snapshots. Good for checking responsive layouts and flows.

## Per-agent install notes

| Agent | Where skills live | Notes |
| --- | --- | --- |
| Claude Code | `~/.claude/skills/<name>/SKILL.md` or `.claude/skills/` | Plugins via `/plugin`. MCP via `claude mcp add` |
| Codex CLI | `~/.codex/skills/` or `.codex/skills/` | MCP servers in `~/.codex/config.toml` |
| Muse Code | Bundled `/taste` and `/grilling` | Explicit invocation only |
| Cursor / Copilot / Gemini CLI / others | Varies | [`npx skills`](https://github.com/vercel-labs/skills) installs SKILL.md packages across agents |

Most skills here follow the open `SKILL.md` format, so one skill usually works in several agents.

## Related lists

- [VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills): 1000+ agent skills across agents.
- [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills): Claude Skills, with a UI and frontend section.
- [travisvn/awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills): Claude Skills and resources.
- [github/awesome-copilot](https://github.com/github/awesome-copilot): Copilot instructions, agents and skills.
- [maxbogo/awesome-ai-tools-for-ui](https://github.com/maxbogo/awesome-ai-tools-for-ui): AI tools for UI/UX.

## Contributing

PRs are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md). One rule: every entry must say *how* it fights slop, not just that it's about design.

## License

[CC0 1.0](LICENSE). Public domain, use it however you like.
