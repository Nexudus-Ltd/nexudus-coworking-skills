# install.md

I want you to install Agent Skills for Nexudus for me. Execute all steps autonomously.

OBJECTIVE: Install the Nexudus agent skill so your agent can use the Nexudus CLI workflow for authentication, business management, product management, configuration, and diagnostics.

DONE WHEN: the Nexudus skill is installed in your agent and `npx skills list` shows it.

## TODO

- Install Nexudus skills
- Verify installation

## Step 0: Install skills

If this skill is published from a public GitHub repository at `nexudus/skills`, install it with:

```bash
npx skills add nexudus/skills
```

If the skill still lives in a differently named repository, install from the full repository URL instead:

```bash
npx skills add https://github.com/nexudus/nexudus-coworking-cli
```

To install for a specific agent:

```bash
npx skills add nexudus/skills -a github-copilot
```

To install globally:

```bash
npx skills add nexudus/skills -g
```

## Step 1: Verify

```bash
npx skills list
```

Expected: the `nexudus` skill is listed.

## Publishing Requirement

The shorthand form `npx skills add nexudus/skills` depends on the GitHub repository location, not just the skill contents.

To support that exact command you need:

1. A public GitHub repository at `https://github.com/nexudus/skills`.
2. The skill committed somewhere the installer discovers, such as `skills/nexudus/SKILL.md`.

If those conditions are not met, the installer can still use a full Git URL or GitHub URL.