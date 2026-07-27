# Shadow Web Builder

Public build and release automation for the private
`fireunix-app/shadow-web` repository.

The source is checked out only on an ephemeral GitHub-hosted runner with a
repository-scoped, read-only PAT. Dependencies are installed with `npm ci`,
source maps are rejected, and only the production `dist` output is published.
Private source files and project build directories are never cached or
uploaded.

GitHub Releases are written back to the private web repository through a
separate single-repository write token. This public repository never hosts
Releases.
The requested release tag must already exist in the private web repository.
