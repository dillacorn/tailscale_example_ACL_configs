# Repository instructions for tailscale_example_ACL_configs

Applies to the Tailscale policy examples and documentation in this repository.

## Access-policy and security boundaries

- This repository provides **examples**, not verified live Tailscale ACL/grants or authoritative tailnet state. Inspect the exact example and its current syntax before editing; do not claim that a Git commit deploys a tailnet policy.
- Treat changes to who can reach which nodes, identities, ports, and services as security-sensitive. Preserve least privilege and explicitly scoped allow rules; never introduce broad wildcards, unrestricted `*:*` access, all-member/all-device grants, or public exposure as a convenience fix without explicit instruction and security review.
- Do not infer current tailnet member identities, device tags, node names, domain names, or groups from example text. Use placeholders where appropriate; do not print, store, or upload auth keys, API tokens, private keys, personal device inventories, or real infrastructure secrets.
- Prefer small, reviewable policy changes. When feasible, validate with the Tailscale policy validator/editor and meaningful allow/deny test cases before applying to a real tailnet.
- Policy-example edits, submitting a policy to Tailscale, and changing a live node's permissions are separate operations; obtain explicit authorization for actual external-policy deployment.

## Merge and release authorization

Operate autonomously within the user's approved scope. Do not add unnecessary repeat-approval checkpoints.

- Investigating, implementing, fixing, testing, committing scoped work to a feature branch, or preparing an ordinary review PR does **not** by itself authorize merging to the default branch, creating a tag, publishing a GitHub Release, distributing a build, or deploying to devices.
- An explicit instruction to merge, apply directly to `main`, tag, or release authorizes that named operation for the specified work. An approved release includes the necessary scoped merge unless the user specifies another target or restriction. Do not demand another approval for already-authorized steps.
- Authorization for an **unfinished** merge or release survives related small fixes, revisions, and testing pauses. If the user interrupts an approved release to correct something, "good to go", "working, continue", or a similarly clear signal may resume that same pending release without asking for the original approval again.
- Respect "wait", "hold off", and cancellations. A pause stops delivery until the user clearly resumes; cancellation withdraws approval. Materially different work, a changed release target, or an altered version beyond what was authorized requires renewed authorization.
- Approval is **single-use**: after the authorized merge/release finishes, it does not authorize another merge or release, including a follow-up patch. Positive feedback alone ("perfect", "that works") cannot start a new delivery operation when none is pending.
- The user may approve a merge or release without personally testing it. Run the available relevant static/automated checks, report meaningful failures, and distinguish automated validation from unperformed real-device/runtime tests. Do not impose user testing as an extra requirement if the user explicitly elects to proceed.
- Drafting release notes, suggesting a version, or preparing a branch/PR is not publication. Publishing workflows, temporary GitHub Actions release bridges, Git tags, Releases, uploads, and external release artifacts require the active authorization for that exact publication.
- Never equate approval for a GitHub Release with approval for unrelated distribution, production deployment, hardware changes, destructive data operations, credential exposure, or external-provider settings.

## Validation and delivery

- Check the exact example file format and parser expectations before asserting syntax correctness. Confirm intended allowed and denied traffic rather than assuming a syntactically valid file is secure.
- Do not publish a GitHub Release or invent a version merely because an ACL example was updated.
