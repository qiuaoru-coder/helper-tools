---
name: github-first-publish
description: Guide first-time or non-expert GitHub users from a local project to a safe, understandable, publicly or privately shared repository. Use for first publication, step-by-step GitHub guidance, repository preparation, initial push, release setup, or a readiness audit; do not use for routine feature development or advanced repository administration unrelated to publishing.
---

# GitHub First Publish

Help the user reach a verified publishing outcome, not merely complete a memorized checklist. Determine the current state, skip completed or irrelevant work, and adapt to the available interface: local Git, GitHub CLI, an authenticated browser, or manual guidance.

## Select the working mode

- **Guided mode:** Default when the user is new to GitHub, asks for one step at a time, or is operating the interface themselves. Give one bounded action, its purpose, and the visible success signal. Wait for the user to report completion before advancing.
- **Assisted mode:** Use when the user asks the agent to prepare files or perform authorized local and GitHub operations. Inspect before editing, make scoped changes, verify each material operation, and pause only for missing authority or a decision that changes the result.
- **Audit mode:** Use when a repository already exists and the user wants to know what is missing or why it is difficult to discover, understand, install, or use. Report findings by impact and distinguish required fixes from optional polish.

Do not force the user through all modes. Preserve their preferred pace throughout the task.

## Establish the starting state

Infer what can be safely discovered and ask only for material unknowns:

- the local project folder or existing repository URL;
- the intended GitHub account or organization;
- repository name and public/private visibility;
- what the project does and who should use it;
- whether a repository or Git history already exists;
- whether the user wants guidance or authorized execution.

Before prescribing actions, inspect available state with read-only checks. If the user is looking at an unfamiliar page, ask for a screenshot or the exact visible text instead of assuming the current GitHub layout.

For stage selection and branching rules, read [references/publish-flow.md](references/publish-flow.md).

## Protect the project before publishing

Before the first push or any change to public visibility, review publication risk. Do not expose secret values while checking them. Never publish files merely because they are present in the project folder.

At minimum, check for:

- credentials, tokens, private keys, environment files, and local configuration;
- personal information, internal URLs, private notes, logs, databases, or backups;
- copyrighted, confidential, licensed, paid, or third-party material the user may not have permission to redistribute;
- generated build output, caches, editor state, and unnecessarily large binaries;
- unrelated files accidentally mixed into the project.

Read [references/repository-readiness.md](references/repository-readiness.md) before preparing or approving a publication. If a risk is found, name the affected path and type of risk without reproducing the sensitive content.

## Prepare a repository others can understand

Create or improve only the files justified by the project. Common deliverables include:

- a clear `README.md` stating purpose, audience, prerequisites, installation, first use, examples, limitations, and support route;
- an appropriate `.gitignore` based on the actual stack;
- a license only after the user chooses or confirms the intended reuse terms;
- dependency manifests, example configuration, or setup instructions when required to reproduce use;
- contribution, security, citation, or conduct files when the audience and project maturity justify them.

Do not fabricate compatibility, test status, benchmarks, screenshots, community adoption, or project maturity. Mark unverified claims as unverified or omit them.

## Publish with state-aware checks

Follow the route in [references/publish-flow.md](references/publish-flow.md). Key invariants:

1. Resolve the exact repository target and visibility before creating or pushing.
2. Preserve existing work, branches, remotes, and unrelated user changes.
3. Never use force push, destructive reset, broad deletion, history rewriting, or secret removal from history without a separate explanation and explicit authorization.
4. Inspect remote state before connecting or pushing to an existing repository.
5. Confirm success from GitHub, not only from a local command exit code.
6. Treat profile repositories, organization repositories, forks, templates, and ordinary project repositories as different cases.

When an operation fails or the interface differs, read [references/troubleshooting.md](references/troubleshooting.md). Do not repeat an unchanged failing action.

## Finish with a usable handoff

Verify the repository from a visitor's perspective:

- the correct files and default branch are visible;
- README instructions can be followed by a new user;
- repository description, topics, website link, and social preview are accurate when used;
- public/private visibility matches the user's choice;
- secrets and unintended files are absent;
- an installation or first-use path has been tested where practical;
- optional Issues, Discussions, Releases, tags, branch protection, and security features match the project's needs.

Conclude with what was published, the repository URL when available, any remaining risks, and only the next useful improvement. In guided mode, do not declare completion until the user confirms the final verification step.

## Boundaries

- Exclude project-specific cleanup steps unless inspection shows the same issue in the current project.
- Do not treat one user's repository structure, topic, account settings, or past mistake as a universal requirement.
- Do not require every optional GitHub feature for a first release.
- Do not claim ownership, licensing rights, or permission to publish on the user's behalf.
- Keep the core workflow portable; platform-specific metadata or integrations may be ignored by other Agent Skills-compatible tools.
