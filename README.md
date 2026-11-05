# Spikes

This public repository holds time-boxed technical spikes for tbhb-dev work. Each spike states a question and keeps the runs that answer it. It contains only new, clean work. A private counterpart exists for spikes that can't be public.

## Layout

Each spike is a directory under `spikes/`, named `s-N-<slug>`. Its main document is `README.md`, and its runs go in the same directory.

## Workflow

Every spike lands through a pull request. See [AGENTS.md](AGENTS.md) for the setup and the rules.

## Checks

Bazel runs every gate from tbhb-dev/rules: `bazelisk test //...`.
