# Repository readiness and publication safety

Read this before preparing a first publication or changing a repository to public.

## Publication boundary

Confirm the repository root is the intended project, not a home directory, downloads folder, workspace root, or broad parent folder. Check for nested projects and unrelated files. Do not initialize, stage, or recursively operate on a broad target whose scope is unclear.

## Sensitive material

Look for risk by filename, configuration pattern, Git tracking state, and relevant file content. Common examples include:

- `.env` and environment-specific variants;
- API keys, access tokens, passwords, session cookies, webhook secrets, and service-account credentials;
- SSH, TLS, signing, wallet, or other private keys;
- cloud credentials and local credential stores;
- production databases, exported user data, logs, crash dumps, and backups;
- internal hostnames, private endpoints, employee/customer details, addresses, phone numbers, or email lists.

Avoid printing sensitive values. Report the file path and risk category. If a secret may already have been committed or pushed, removing the file is not sufficient: recommend rotating/revoking the secret and assess whether history cleanup is needed. History rewriting is a separate high-impact operation and requires explicit authorization.

## Rights and redistribution

Check whether the project contains material the user may not be allowed to publish:

- paid or copyrighted books, PDFs, courses, images, music, fonts, datasets, or source assets;
- employer, client, school, or internal project content;
- proprietary code or copied code with incompatible terms;
- third-party binaries or model files with redistribution restrictions;
- trademarks or personal likenesses used without appropriate rights.

Do not make a legal conclusion when rights are unclear. Isolate the material, describe the uncertainty, and ask the user to confirm permission or replace it with a distributable reference, excerpt, placeholder, or download instruction.

## Repository hygiene

Exclude files that add risk or noise unless intentionally required:

- build output, dependency caches, virtual environments, package caches;
- editor state, OS metadata, temporary files, coverage output, and local logs;
- archives, duplicate exports, screenshots containing personal information;
- large binaries better suited to Releases, Git LFS, or an external distribution channel.

Generate `.gitignore` rules from the actual project stack. Review currently tracked files because adding an ignore rule does not untrack files already committed.

## README truthfulness

A useful first-release README normally answers:

- What is this?
- Who is it for?
- What problem does it solve?
- What is required before use?
- How is it installed or opened?
- What is the smallest successful example?
- What is not supported or not yet verified?
- Where should users report problems?
- Under what terms may it be reused?

Do not claim “production ready,” “secure,” “fully tested,” “works everywhere,” or similar conclusions without evidence.

## License decision

Do not choose a license solely because it is popular. Ask what the user intends others to be able to do, including commercial use, modification, redistribution, attribution, patent grants, and sharing modifications. If the user is unsure, explain common options briefly and point to authoritative license text. Do not invent or casually modify standard license wording.

No license generally does not mean unrestricted reuse. Make the consequence understandable to a first-time publisher.

## Functional readiness

Use the cheapest meaningful verification available:

- run existing tests or build commands when safe and relevant;
- verify referenced files and internal links;
- try the documented installation or first-use path in a clean or isolated context when practical;
- confirm dependency versions and example commands match the repository;
- distinguish verified platforms from expected but untested platforms.

If verification cannot be performed, state exactly what remains unverified.

## Final publication gate

Publishing can proceed when:

- repository root, owner, name, and visibility are resolved;
- no known secret or private-data blocker remains;
- redistribution rights are adequate or uncertain material is excluded;
- staged files have been reviewed;
- the project has a truthful explanation and usable first step;
- the selected remote route will not overwrite existing work.
