# State-aware publishing flow

Use these stages as a decision map. They are not a fixed numbered tutorial. Enter at the earliest unfinished stage and skip anything already verified.

## 1. Clarify the outcome

Resolve:

- project source: local folder, existing Git repository, or existing GitHub repository;
- target owner and repository name;
- public or private visibility;
- intended audience and primary language;
- guided, assisted, or audit mode.

If visibility or target account is unknown, do not create the remote repository yet. If the user clearly asked for a public or private repository under a known account, do not ask them to reconfirm the same choice repeatedly.

## 2. Inspect the local project

Prefer read-only discovery first:

- list the project root and identify the actual source boundary;
- inspect Git status, current branch, remotes, ignore rules, and recent history when Git exists;
- identify stack, dependency files, build/test instructions, and generated output;
- check whether nested repositories, submodules, large files, or symlinks change the plan;
- preserve unrelated and uncommitted user changes.

If the supplied folder is overly broad, stop and narrow the repository root before initializing Git or staging files.

## 3. Run the publication gate

Apply the checks in `repository-readiness.md`. Classify findings:

- **Blocker:** likely secret, private data, missing permission, wrong repository target, or destructive conflict. Resolve before publishing.
- **Required:** project would not install, run, or be understood without the change.
- **Recommended:** materially improves discovery, trust, or maintenance.
- **Optional:** polish that can wait until after the first release.

Never lower a blocker to optional merely to complete the workflow.

## 4. Prepare the minimum viable repository

The minimum depends on the project, but usually includes:

- the intended project files and a correct `.gitignore`;
- a README with a truthful first-use path;
- a license decision for public repositories when reuse terms matter;
- sample configuration rather than live secrets;
- tests or a manual verification method appropriate to the project.

Do not create empty governance files or copied boilerplate that does not apply.

## 5. Establish local Git state

Choose the non-destructive route:

- If no Git repository exists, initialize at the confirmed project root.
- If Git exists, keep its history and inspect the current branch and remotes.
- Stage only reviewed files.
- Review the staged file list and diff summary before the first commit.
- Use a clear initial or publication commit message.

Do not silently rename branches, replace remotes, or squash history.

## 6. Establish the GitHub repository

Use the user's available method:

- authenticated browser;
- GitHub CLI if installed and authenticated;
- another authorized GitHub integration;
- manual instructions if no authenticated tool is available.

When local history already exists, creating an empty remote usually avoids unnecessary merge conflicts. If the remote was initialized with a README, license, or `.gitignore`, inspect both histories and explain the safe reconciliation route instead of forcing a push.

Before the first push, verify:

- owner and repository name;
- visibility;
- remote URL;
- branch being pushed;
- no blockers remain in the publication gate.

## 7. Push and verify remotely

After pushing, verify on GitHub:

- expected commit and files are present;
- default branch is correct;
- README renders correctly and links resolve;
- visibility is correct;
- no unintended file is visible;
- installation or usage instructions correspond to the published content.

Do not treat `git push` success alone as completion.

## 8. Improve discovery and trust

Apply only what helps the project's audience:

- concise About description;
- relevant topics, without keyword stuffing;
- website or documentation link;
- social preview image;
- Issues, Discussions, templates, or contribution guidance;
- security policy and dependency/security scanning;
- branch protection for collaborative or higher-risk projects;
- release tag and release notes when users need a stable downloadable version.

For a first publication, separate launch blockers from later improvements.

## 9. Visitor test and handoff

Review as a stranger who has no conversation context:

1. Can they tell what the project is within a few seconds?
2. Can they identify who it is for and why it is useful?
3. Can they install or try it without guessing?
4. Can they understand limitations and obtain support?
5. Are licensing and contribution expectations clear enough for the intended use?

Finish with the repository URL, verified outcome, unresolved risks, and the single most valuable next improvement.

## Guided-mode response shape

For a novice asking for one step at a time, each turn should contain:

- **Current step:** one bounded action;
- **Why:** one short reason;
- **Success signal:** what the user should see;
- **If different:** ask for the exact text or a screenshot.

Do not include several future actions in the same turn. A short warning is allowed when it prevents an immediate mistake.
