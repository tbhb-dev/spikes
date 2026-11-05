# Spikes

This public repository holds time-boxed technical spikes for tbhb-dev work. Each spike states a question and keeps the runs that answer it. It contains only new, clean work. A private counterpart exists for spikes that can't be public.

## Layout

Spikes live in namespaces under `spikes/`: one per tbhb-dev project, plus `spikes/_/` for general work that belongs to no one project. Each spike is a directory `spikes/<namespace>/s-NNNNNN-<slug>/`, numbered from its namespace's own counter and zero-padded to six digits, with the ID `<namespace>/S-NNNNNN`, such as `afakt/S-000001`. The main document is `README.md`, and runs go in the same directory.

## Workflow

Every spike lands through a pull request. See [AGENTS.md](AGENTS.md) for the setup and the rules.

## Checks

Bazel runs every gate from tbhb-dev/rules: `bazelisk test //...`.
