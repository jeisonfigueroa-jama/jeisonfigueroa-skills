# Jeison Figueroa's Skills

Personal reusable AI workflows for Codex, packaged as an installable plugin and maintained by Jeison Figueroa.

## Install

Requires Codex CLI with `codex plugin` support and Git.

```sh
codex plugin marketplace add jeisonfigueroa-jama/jeisonfigueroa-skills
codex plugin add jeisonfigueroa@jeisonfigueroa-skills
```

Start a new Codex chat after installation. If the desktop app does not show the plugin, restart it. Mention `$publish-personal-skill` to use the included workflow, or let Codex select it when your request matches its description.

Marketplace: `jeisonfigueroa-skills`. Plugin: `jeisonfigueroa`.

## Included skills

| Skill | Purpose |
| --- | --- |
| `publish-personal-skill` | Turn a prompt or repeated workflow into a focused skill in this repository. |

## Create or edit skills

Clone the source repository and open it as a Codex project:

```sh
git clone https://github.com/jeisonfigueroa-jama/jeisonfigueroa-skills.git
cd jeisonfigueroa-skills
```

Ask Codex:

```text
Use $publish-personal-skill to create a skill named <skill-name> that
<describe the workflow, when to use it, and the expected output>.
Validate it, then commit and push the changes.
```

You can also use the built-in `$skill-creator`, specifying `plugins/jeisonfigueroa/skills/` as the destination. If the plugin is not installed, use that built-in creator directly.

Edit the source checkout, not Codex's installed plugin cache. Give every skill its own folder and a `SKILL.md` with YAML `name` and `description`. Add `scripts/`, `references/`, or `assets/` only as needed. Update this skill list and bump the version in `plugins/jeisonfigueroa/.codex-plugin/plugin.json` for changed releases.

## Update an installation

After changes are committed and pushed, refresh the Git marketplace and install the current plugin package:

```sh
codex plugin marketplace upgrade jeisonfigueroa-skills
codex plugin add jeisonfigueroa@jeisonfigueroa-skills
```

Start a new Codex chat; restart the desktop app if needed. Marketplace refresh and plugin installation are separate steps. A `git pull` in your editable checkout alone does not refresh a Git-backed marketplace installation.

To update the editable checkout itself, run `git pull --ff-only` inside it when your working tree is clean.

## Structure

```text
.agents/plugins/marketplace.json
AGENTS.md
plugins/
  jeisonfigueroa/
    .codex-plugin/plugin.json
    skills/
      publish-personal-skill/
        SKILL.md
```

The marketplace catalog points to the plugin folder. The plugin manifest identifies the package and declares its skills directory. Each skill contains its own instructions and optional supporting resources.

## Public content

Only commit material intended for public sharing. Keep credentials, customer information, and private team workflows outside this repository.

## Documentation

- [Build skills](https://learn.chatgpt.com/docs/build-skills)
- [Package plugins](https://developers.openai.com/plugins/build/plugins)
- [Codex CLI reference](https://learn.chatgpt.com/docs/cli/reference)
