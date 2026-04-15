## Flytedesk Open Source
This organization maintains Ruby gems and shared automation used across Flytedesk projects.
### Repositories
- [`automatic_namespaces`](https://github.com/Flytedesk/automatic_namespaces)
- [`pack_api`](https://github.com/Flytedesk/pack_api)
- [`debounced`](https://github.com/Flytedesk/debounced)
- [`flaky`](https://github.com/Flytedesk/flaky) (published to RubyGems as `flaky-friend`)
### Shared Workflows
The org-level `.github` repository contains reusable GitHub Actions workflows for gem release automation:
- one-shot release via `reusable-ruby-gem-release.yml` (bump version, tag, create GitHub Release)
- gem build and publish to RubyGems via `reusable-ruby-gem-publish.yml` using `RUBYGEMS_API_KEY`
