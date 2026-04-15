# Shared GitHub Workflows

Reusable GitHub Actions workflows for Flytedesk Ruby gem repositories.

## Reusable workflows

- `reusable-ruby-gem-release.yml`
  - One-shot release. Runs the spec suite, bumps `lib/<gem>/version.rb`,
    updates `Gemfile.lock`, tags `v<version>`, and creates a GitHub Release.
    Callers invoke it from a `workflow_dispatch` in their own `cd.yml` and
    pass the new semver version. Requires a `RELEASE_TOKEN` secret
    (fine-grained PAT owned by a repo admin) so the push and release
    creation bypass the main-branch ruleset and the `release: published`
    event cascades to the publish workflow.
- `reusable-ruby-gem-publish.yml`
  - Builds and publishes a gem to RubyGems using the org-level
    `RUBYGEMS_API_KEY`. Triggered on `release: published` in each gem repo.

## Consumers

- [pack_api](https://github.com/Flytedesk/pack_api)
- [debounced](https://github.com/Flytedesk/debounced)
- [automatic_namespaces](https://github.com/Flytedesk/automatic_namespaces)
- [flaky](https://github.com/Flytedesk/flaky)
