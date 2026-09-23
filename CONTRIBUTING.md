# Contributing

Thanks for helping map the way out of AI slop.

## Adding an entry

1. Put it in the section that fits best. If it would fit two, pick the one that matches its primary job.
2. Add a row to that section's table in this format:

   ```html
   <tr>
   <td align="center" width="64"><img src="LOGO_URL" width="32" height="32" alt="Name logo"></td>
   <td><a href="URL"><b>Name</b></a><br><sub>What it does, and specifically how it prevents or fixes generic AI design.</sub></td>
   <td align="center" width="120"><img src="https://img.shields.io/github/stars/OWNER/REPO?style=flat-square&logo=github&label=&color=1B1A17" alt="GitHub stars"></td>
   </tr>
   ```

   - **Logo:** use the project's site favicon (`https://www.google.com/s2/favicons?domain=example.com&sz=64`). If it has no site, use the GitHub owner avatar (`https://github.com/OWNER.png?size=64`).
   - **Last column:** use a star badge for GitHub repos, or `<sub><b>Hosted</b></sub>` for hosted-only services.

3. Link to the source (repo, official docs), not to a blog post about it.
4. One entry per PR is preferred, and the PR title should be `Add <name>`.

## What gets accepted

- Skills, rule sets, MCP servers or references that measurably change what an agent designs, or that let it see and critique its own output.
- It works today. The repo is public, not archived, and has usable install instructions.
- It isn't a thin re-post of another entry.

## What doesn't

- General-purpose component libraries with no agent-facing piece.
- Paid-only products with no free tier or open component.
- Prompt dumps with no design point of view.
- Anything that clones paid templates or other people's sites pixel for pixel.
