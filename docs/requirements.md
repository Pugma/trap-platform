# Requirements

## Goal

Reproduce what [traPtitech/manifest](https://github.com/traPtitech/manifest) does for each app with a single TrapApp, without losing existing capabilities.\
Keep the TrapApp interface simple.\
Apps that do not fit may stay on plain manifests.

## Differences from current manifests

- Rename envs to match common terminology
  - `*-dev` becomes **staging**
    - Existing `*-dev` domains are kept for now; when renamed, both old & new domains are served during a transition period
  - The fixed `staging` instance of the preview chart is abolished, since it duplicates `*-dev`
- Non-production envs (stg & preview) prefer the node `eee101.tokyotech.org`

## Out of scope

- NeoShowcase apps (`ns-apps`, `ns-dev-apps`)
- Infrastructure components (e.g. MinIO, Gitea act-runner)

## Planned

- Preview envs (replacing `.common/preview-ui*`)
- Per-app databases & backups, using OSS operators
- Migration to Gateway API without changing the TrapApp spec
