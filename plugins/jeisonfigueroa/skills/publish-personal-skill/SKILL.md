---
name: publish-personal-skill
description: Turn a supplied prompt or repeatable workflow into a reusable skill in Jeison Figueroa's skills repository. Use when asked to add, standardize, or improve a personal skill in that collection.
---

# Publish Personal Skill

Create or improve a focused skill from the user's prompt or workflow.

1. Identify the intended outcome, inputs, outputs, and requests that should trigger the skill. Ask only for missing details that materially affect the result.
2. Locate the editable checkout of `jeisonfigueroa-jama/jeisonfigueroa-skills`. Write under `plugins/jeisonfigueroa/skills/`. An installed plugin cache is not the source repository; if the checkout is unavailable, ask for its location.
3. Inspect any existing relevant skill before creating another. Use a short lowercase hyphenated folder name matching the skill's `name`.
4. Write `SKILL.md` with YAML `name` and a concise `description` explaining when it applies. Preserve domain rules and authorization boundaries, remove chat-specific context, and keep instructions focused on decisions that matter. Use the built-in skill creator if available.
5. Add scripts, references, or assets only when they improve reliability or keep conditional detail out of the main instructions. Link supporting references from the instructions.
6. Validate frontmatter, names, and referenced paths with an available skill validator. Run any new executable helpers with appropriate sample inputs. Try a realistic task when it would meaningfully verify the workflow.
7. Update the README's skill list and increment the plugin's semantic version for a changed release. Check the diff and report the files changed, invocation example, and validation results.

Commit and push when the user's request authorizes publication; otherwise leave the changes available for review. Installing or updating the plugin is a separate action unless requested. This collection is public: exclude secrets, private team workflows, customer data, and private conversation transcripts.
