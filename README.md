# GitHub Workflow Actions Lab

## Workflows

### Workflow 1: Dependent Jobs (`dependent-jobs.yml`)
Triggers on push to `main`. Demonstrates sequential job execution using the `needs` key.
- `build` runs first
- `test` runs only after `build` succeeds
- `deploy` runs only after `test` succeeds

### Workflow 2: Multi-Platform Testing (`multi-platform.yml`)
Triggers on pull requests to `main`. Runs three jobs **in parallel** on different operating systems
with no dependencies between them.

## Key Concepts Demonstrated
- **`needs`**: Creates a dependency between jobs, enforcing execution order
- **`runs-on`**: Specifies the OS runner for a job (ubuntu-latest, windows-latest, macos-latest)
- **`uses`**: Pulls in a reusable action (e.g. `actions/checkout@v4`)
- **Parallel execution**: Jobs without `needs` run simultaneously

## Challenges
- `.github` folder is hidden on Windows; created it via Git Bash with `mkdir -p .github/workflows`
- YAML indentation must be consistent — used spaces, not tabs