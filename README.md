# Helper Tools

[中文说明](README.zh-CN.md)

Practical, reusable Agent Skills that help non-experts complete real software workflows safely and one step at a time.

## Included Skill

| Skill | Use it when you need to | Typical result |
| --- | --- | --- |
| [github-first-publish](github-first-publish/) | Publish a first project to GitHub, prepare an existing repository, or audit whether a repository is ready to share | A state-aware publishing path, safety checks, repository setup, remote verification, and a clear next step |

## What Makes It Different

`github-first-publish` is not a fixed 20-step tutorial. It first identifies the user's current state, skips completed or irrelevant work, and chooses among three modes:

- **Guided mode:** gives a beginner one bounded action at a time and waits for confirmation;
- **Assisted mode:** prepares files and performs authorized local or GitHub operations;
- **Audit mode:** reviews an existing repository for publication blockers and useful improvements.

The Skill checks for secrets, private information, redistribution risks, unrelated files, destructive Git operations, unclear licensing, and unverified claims before treating a repository as ready.

## Best Inputs

A simple request is enough:

~~~text
Use $github-first-publish.

I want to publish my first project to GitHub.
I am new to GitHub, so give me one step at a time and wait for me to confirm each step.
~~~

For a more tailored result, also provide:

- the local project folder or existing repository URL;
- what the project does and who it is for;
- the intended GitHub account, repository name, and public/private visibility;
- whether the user wants step-by-step guidance, assisted execution, or an audit;
- a screenshot or exact error text when the interface does not match expectations.

## What You Can Get

- publication-readiness and sensitive-file checks;
- a truthful README, appropriate `.gitignore`, and license decision support;
- safe local Git and remote repository setup;
- first push and GitHub-side verification;
- About, Topics, Releases, Issues, Discussions, security, and branch-setting recommendations;
- troubleshooting for authentication, divergent histories, missing files, large files, and changed GitHub UI;
- a visitor-perspective final review and the next most useful improvement.

## Installation

Download the ready-to-install package:

- [Download github-first-publish.zip](https://github.com/qiuaoru-coder/helper-tools/releases/latest/download/github-first-publish.zip)

Clone this repository, then copy the Skill folder into the directory used by your agent.

### Codex

~~~bash
git clone https://github.com/qiuaoru-coder/helper-tools.git
mkdir -p ~/.codex/skills
cp -R helper-tools/github-first-publish ~/.codex/skills/
~~~

### Claude Code

~~~bash
git clone https://github.com/qiuaoru-coder/helper-tools.git
mkdir -p ~/.claude/skills
cp -R helper-tools/github-first-publish ~/.claude/skills/
~~~

### Cursor

Copy the folder to `~/.cursor/skills/` for user-level use or `.cursor/skills/` inside a project. Cursor can also discover compatible Skills in `.codex/skills/` and `.claude/skills/`.

### WorkBuddy and other compatible agents

Import the `github-first-publish` folder as a local Skill, or copy it to the product's Agent Skills directory. The portable core is `SKILL.md` plus `references/`; `agents/openai.yaml` is optional OpenAI-facing metadata and may be ignored by other products.

## Boundaries

The Skill cannot grant GitHub permissions, determine ownership of third-party material, guarantee security, or promise repository discovery and stars. Public publishing still requires the user's authority, correct account access, and a final review of the files being shared.

## License

Released under the [MIT License](LICENSE).

Issues and concrete workflow feedback are welcome. If the Skill helps you publish your first project, consider starring the repository.
