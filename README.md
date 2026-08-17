# github-template

![GitHub issues](https://img.shields.io/github/issues-raw/ivan-pinatti/github-template?logo=Github&style=for-the-badge)
![GitHub Sponsors](https://img.shields.io/github/sponsors/ivan-pinatti?logo=Github&style=for-the-badge)

A GitHub template repository: the baseline for a new repo, with
pre-commit, dependency automation, review automation, and the usual
community files already wired up. Click **Use this template** above to
create a new repository from this one.

## What you get

- **Pre-commit**, consuming the checklists published by
  [ivan-pinatti/pre-commit-checklists](https://github.com/ivan-pinatti/pre-commit-checklists)
  through a single `repo:` entry and a `rev:` pin: see
  [.pre-commit-config.yaml](.pre-commit-config.yaml).
- **PR validation**: a workflow that runs pre-commit on every pull request,
  auto-commits fixes it can make itself, posts the result as a PR comment,
  and applies labels from [.github/labeler.yml](.github/labeler.yml). See
  [.github/workflows/pull-request.yml](.github/workflows/pull-request.yml).
- **Auto tag and release**: every push to `main` (what a merged PR
  produces) computes the next version from Conventional Commit prefixes,
  tags it, and creates a GitHub release. See
  [.github/workflows/new-tag-and-release.yml](.github/workflows/new-tag-and-release.yml).
- **Dependabot**, watching `.pre-commit-config.yaml` and every
  `.github/workflows/*.yml` action pin. See
  [.github/dependabot.yml](.github/dependabot.yml).
- **Renovate**, enabled generically as a catch-all for whatever Dependabot
  does not cover once the project has real dependencies. See
  [.github/renovate.json5](.github/renovate.json5).
- **CodeRabbit**, reviewing pull requests once they leave draft state. See
  [.coderabbit.yaml](.coderabbit.yaml).
- **Issue and pull request templates**, a stale-issue policy, a
  `CODEOWNERS` file, and a `FUNDING.yml`, all under
  [.github/](.github/).
- **Community files**: [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md),
  [CONTRIBUTING.md](CONTRIBUTING.md), [SECURITY.md](SECURITY.md),
  [LICENSE.md](LICENSE.md) (Apache License 2.0), and
  [NOTICE.md](NOTICE.md).

## What this template deliberately does not include

This repository is meant to be generic and language-agnostic, so it does
not bake in any one project type's tooling: no language-specific linter
configuration, no build system, no test runner, no `dependabot.yml`
ecosystem beyond `pre-commit` and `github-actions`. Once you know what
the new project is written in, add the pieces that fit it, for example a
language-specific pre-commit checklist id (`checklist-dev-python`,
`checklist-dev-shell`, and so on, see
[pre-commit-checklists' hook catalogue](https://github.com/ivan-pinatti/pre-commit-checklists/blob/main/docs/hook-catalogue.md))
and a matching Dependabot ecosystem block.

## Using this template

1. Click **Use this template** at the top of this repository's GitHub
   page, and create your new repository.
2. Clone it, then find and replace the placeholders below (search for
   `REPLACE_ME` across the tree to find them all):
   - [CITATION.cff](CITATION.cff): project title, abstract, repository
     URL, and keywords.
   - [llms.txt](llms.txt): project name, description, key files, and tech
     stack.
   - This README: project name, description, and badges.
3. Update the `rev:` pin in [.pre-commit-config.yaml](.pre-commit-config.yaml)
   to the latest release tag of `pre-commit-checklists`, then run:

   ```shell
   pre-commit install
   pre-commit run --all-files
   ```

4. Add a language-specific pre-commit checklist id, and a matching
   Dependabot ecosystem in [.github/dependabot.yml](.github/dependabot.yml),
   once you know what the project is written in.
5. Decide whether the default [LICENSE.md](LICENSE.md) (Apache License 2.0)
   is the right choice for the new project, and replace it if not.
6. Delete this section, and the section above it, once the new project has
   its own README content to replace them with.

## License

[![license](https://img.shields.io/github/license/ivan-pinatti/github-template?style=plastic)](LICENSE.md)

See [LICENSE.md](LICENSE.md) for full details.

## Contribute / Donate

If you use this template, entirely or partially, or get inspired by it,
consider buying me a coffee or a beer, I would really appreciate it:
[buymeacoffee.com/ivan.pinatti](https://www.buymeacoffee.com/ivan.pinatti).
