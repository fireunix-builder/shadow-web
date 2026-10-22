# Shadow Web Builder

Public build and release automation for the private
`fireunix-app/shadow-web` repository.

The source is checked out only on an ephemeral GitHub-hosted runner with a
repository-scoped, read-only deploy key (`SOURCE_DEPLOY_KEY`). Dependencies are installed with `npm ci`,
source maps are rejected, and only the production `dist` output is published.
Private source files and project build directories are never cached or
uploaded.

GitHub Releases are written back to the private web repository with a short-lived installation token of the
`fireunix-publisher` GitHub App (`RELEASE_APP_CLIENT_ID` /
`RELEASE_APP_PRIVATE_KEY` secrets), scoped to that one repository. This public repository never hosts
Releases.
The requested release tag must already exist in the private web repository.
