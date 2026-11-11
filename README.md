# Jeison Figueroa's Skills

Personal reusable skills for Codex, maintained by Jeison Figueroa.

## Structure

Store each skill in its own folder:

```text
skills/
  skill-name/
    SKILL.md
    scripts/       # Optional executable helpers
    references/    # Optional supporting documentation
    assets/        # Optional templates and resources
```

Each `SKILL.md` starts with YAML frontmatter containing `name` and `description`, followed by focused instructions. Describe when the skill should be used, the expected inputs and outputs, and any non-obvious constraints.

## Create a skill

Open this repository in Codex and ask:

```text
Use $skill-creator to create a <skill-name> skill in this repository's
skills/ directory. It should <describe the workflow and when to use it>.
```

Start with instructions. Add scripts, references, or assets when they improve the workflow. Try each skill on realistic tasks and review the changes before committing.

## Use a skill locally

Keeping a skill in this repository's `skills/` folder does not automatically make it available in other projects. Codex supports local discovery through `~/.agents/skills/` and project discovery through `.agents/skills/`.

To make an individual skill available across your local projects, symlink its folder:

```sh
mkdir -p "$HOME/.agents/skills"
ln -s /absolute/path/to/jeisonfigueroa-skills/skills/skill-name "$HOME/.agents/skills/skill-name"
```

Replace the example path and skill name with your local checkout and actual skill. Avoid replacing an existing skill with the same name. If a newly installed skill does not appear, restart Codex.

For a project-specific skill, copy its complete folder into that project's `.agents/skills/` directory.

See the [official skill documentation](https://learn.chatgpt.com/docs/build-skills) for authoring, discovery, and plugin distribution.

## Repository hygiene

This repository is public. Keep credentials, private work data, and confidential references outside it. Commit only resources intended to be shared publicly.
