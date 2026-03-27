# install.md

I want you to install Agent Skills for Nexudus for me. Execute all steps autonomously.

OBJECTIVE: Install the Nexudus agent skill so your agent can use the Nexudus CLI workflow for authentication, business management, product management, configuration, and diagnostics.

DONE WHEN: the Nexudus skill is installed in your agent and `npx skills list` shows it.

## TODO

- Install Nexudus skills
- Verify installation

## Step 0: Install skills

Install from the public GitHub repository:

```bash
npx skills add Nexudus-Ltd/nexudus-coworking-skills
```

Or install from the full repository URL:

```bash
npx skills add https://github.com/Nexudus-Ltd/nexudus-coworking-skills.git
```

To install for a specific agent:

```bash
npx skills add Nexudus-Ltd/nexudus-coworking-skills -a github-copilot
```

To install globally:

```bash
npx skills add Nexudus-Ltd/nexudus-coworking-skills -g
```

## Step 1: Verify

```bash
npx skills list
```

Expected: the `nexudus` skill is listed.

## Publishing Notes

The install command above works because the skill is published in a dedicated public repository.

The public repository is synced from the private CLI repository and only exposes the public skills payload.

If you are maintaining the skill, make changes in the private repository and republish from there.