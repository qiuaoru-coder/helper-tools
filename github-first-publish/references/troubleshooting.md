# Troubleshooting first publication

Use the matching section only when that failure occurs. Re-inspect state before retrying.

## The GitHub page does not match the instructions

GitHub UI labels and placement change. Ask the user for the exact visible text or a screenshot. Identify the page type, account context, repository state, and available controls before giving the next click. Offer a CLI route only if it is appropriate for the user's comfort and authentication state.

## Repository already exists

Determine whether it belongs to the intended owner and whether it contains commits. Inspect its default branch and files. Do not assume an empty local project may overwrite it. Choose among connecting to the empty remote, reconciling histories, using a different name, or publishing to the existing repository only after the user selects the intended outcome.

## Remote contains an initial README or license

This creates distinct local and remote histories. Explain the conflict. Prefer a safe fetch and merge/rebase plan that preserves both sides when appropriate. Never use force push merely to make the error disappear.

## Authentication failed

Identify the transport and tool: browser session, GitHub CLI, HTTPS credential, SSH key, or integration. Do not ask the user to paste a token into chat. Use the tool's secure sign-in flow and recheck the authenticated account before retrying.

## Permission denied or repository not found

Check the remote URL, authenticated account, repository owner, collaborator permission, organization policy, and SSO authorization. A private repository may appear “not found” when access is missing.

## Push rejected because the branch is behind

Fetch and inspect divergence. Preserve both local and remote work. Do not pull or rebase blindly when uncommitted changes or unfamiliar commits exist. Explain the chosen reconciliation method.

## Files are missing after push

Check the pushed branch, default branch, ignored files, nested repositories/submodules, Git LFS pointers, and whether files were staged and committed. Do not add ignored credentials or generated files merely to make the file count match.

## A sensitive file was committed

Stop further sharing. Determine whether it was only staged, committed locally, pushed privately, or exposed publicly. Remove it from the intended tree, add appropriate ignore rules, and rotate any exposed credential. Treat history cleanup as a separate operation requiring a scoped plan and explicit authorization.

## Large file rejected

Identify whether the file belongs in source control. Consider removal, Git LFS, a GitHub Release asset, package registry, dataset host, or external download instructions. Do not split or compress a file merely to evade a platform limit without considering usability and licensing.

## README images or links are broken

Check path case, relative paths, branch names, URL encoding, moved files, and whether the asset is actually committed. Verify in GitHub's rendered view, not only a local preview.

## The user cannot find a button

Do not send a longer list of guessed locations. Ask for the current page title and screenshot, then give one next action. If the control is permission- or plan-dependent, explain that constraint and provide the nearest supported alternative.

## The repository is public but hard to discover

Check whether the project has a specific description, relevant topics, a clear audience, truthful examples, an accurate social preview, a usable release, and links from the owner's profile or other legitimate channels. Do not promise stars or recommend keyword stuffing, artificial engagement, or spam promotion.
