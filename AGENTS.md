# Agent instructions

This is tbhb-dev/spikes, the public repository of time-boxed technical spikes for tbhb-dev work. It's public and contains only new, clean work. A private counterpart exists for spikes that can't be public. Never copy content from it into this repository.

## Standing rules

- Everything here is public. Never write a private repository's name, a private host name, tailnet details, an internal URL, or anything from private work. Refer to a machine by its role, such as `test-service` or `public-resolver`.
- Never write a public IP address in a commit, a pull request, or a report. The `public-ipv4` gitleaks rule enforces this.
- Never open credential files, print secrets, or commit secret values. Secrets live in 1Password only.

## Running a spike

Keep each spike in `spikes/s-N-<slug>/`, with the main document as `README.md`. The number comes from this repository's own counter, S-1, S-2, and so on. @tbhb assigns the number, so don't pick one yourself.

- Keep runs and reruns beneath the spike's directory.
- Read the question, prompt, dependencies, and existing evidence before running anything.
- Honor each run's host, cost, privilege and failure bounds, and get authorization when the spike requires it.
- Keep measured, reported, inferred, and unproved claims distinct.
- Spikes inform design decisions, and the repository a decision concerns records it. Don't edit another repository's documentation from here.
- Write each Markdown paragraph on one line.

## Commits and pull requests

- Branch first, as `spike/s-N-<slug>`. Every change lands through a pull request.
- Use Conventional Commits and a plain `git commit`, without `Signed-off-by` or `Co-authored-by`, and fill every section of `.github/PULL_REQUEST_TEMPLATE.md`.

## Checks

Run `mise install` and `bazelisk run //:bazel_env`, which builds the `.bazel_env/bin` shims the git hooks call, then `prek install`. Every gate is a Bazel test from tbhb-dev/rules, which `bazelisk test //...` runs, and `bazelisk run //:format` rewrites files into their canonical format. The pre-commit hooks run the same gates. To build against a local rules clone, put `common --override_module=tbhb_rules=<path to a rules clone>` in `.bazelrc.user`.
