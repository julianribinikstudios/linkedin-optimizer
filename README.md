# LinkedIn Optimizer

A [Cowork](https://claude.com) skill that rewrites your LinkedIn profile end-to-end and updates it directly on the site for you. Walks you through your headline, About section, experience descriptions, and skills, with you approving every change before it goes live.

Works for any industry or career goal — clients, jobs, partnerships, speaking gigs, visibility.

## What it does

The skill runs a complete LinkedIn overhaul in seven phases:

1. **Reads your current profile** — navigates to your LinkedIn in Chrome and extracts what's there
2. **Asks discovery questions** — industry, role, goal, credentials, markets, differentiator
3. **Rewrites your headline** — generates 3-5 keyword-rich options under LinkedIn's 220 char limit
4. **Rewrites your About** — a ~250-word section that opens with search terms, weaves in proof, and ends with a CTA
5. **Rewrites experience entries** — frames descriptions for your actual goal (clients vs. jobs vs. partnerships)
6. **Keyword injection pass** — identifies high-value search terms missing from your profile
7. **Adds skills** — suggests 5-10 relevant skills and associates them with experience entries

You approve everything before it touches your live profile.

## Install

1. Download `releases/linkedin-optimizer.skill` from this repo (or [click here](releases/linkedin-optimizer.skill)).
2. Double-click the file — Cowork will open with an install prompt.
3. Click **Save skill**.

Done. Start a Cowork chat and type "optimize my LinkedIn" to trigger it.

## Requirements

- [Cowork](https://claude.com) (Anthropic's desktop app)
- [Claude in Chrome](https://chromewebstore.google.com/) extension, signed in
- A Chrome window with LinkedIn loaded and logged in
- About 30-60 minutes for the full optimization

## Full user guide

For step-by-step usage instructions, see [docs/HOW-TO-USE.md](docs/HOW-TO-USE.md).

## How it works under the hood

The skill is a single `SKILL.md` file that tells Claude how to run the workflow. When you trigger it, Claude:

- Uses the Claude in Chrome MCP to navigate and read your LinkedIn page
- Runs a discovery interview using Cowork's question tool
- Drafts copy and shows it to you for approval in chat
- Uses the Chrome MCP again to make the edits on LinkedIn after you approve

No data leaves your Cowork session. The skill operates inside your own browser on your own account.

## Customizing

The skill is just markdown — open `linkedin-optimizer/SKILL.md` and edit it. A few things you might want to tweak:

- **Default character targets** (headline 220, About ~250 words) — change these if you have different preferences
- **Word avoidance rules** — the skill avoids "luxury" by default; add your own no-go words
- **Section order** — the skill goes headline → About → experience → skills, but you can reorder
- **Discovery questions** — add or remove questions in Phase 2 based on what you care about

After editing, repackage with:

```bash
cd linkedin-optimizer
zip ../releases/linkedin-optimizer.skill SKILL.md
```

## License

MIT — see [LICENSE](LICENSE). Use it, fork it, modify it, share it.

## Credits

Built with [Anthropic's skill-creator](https://docs.claude.com) for Cowork. Inspired by a real LinkedIn optimization session.

## Contributing

PRs welcome. If you find a phase that doesn't work well for your industry, open an issue with details and the actual copy that came out — that's the most useful feedback.
