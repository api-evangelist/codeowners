# CODEOWNERS (codeowners)

CODEOWNERS is the file format originally introduced by GitHub and later adopted by GitLab, Bitbucket Cloud, Gitea, and Azure Repos that lets a repository declare which individuals or teams are responsible for a path or pattern within the codebase. Platforms use it to auto-request reviews on pull/merge requests, enforce required approvals via branch protection or push rules, and route pings on issues. The file is plain text with one rule per line - a glob pattern followed by one or more owner handles (`@username` or `@org/team`) or email addresses.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/codeowners/refs/heads/main/apis.yml)

## Scope

- **Type:** Index (Standard)
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Access Control
- Automation
- Code Review
- Governance
- Repository File
- Standards

## Status

- **Status:** De facto convention (GitHub-originated)
- **Canonical host:** GitHub Docs
- **Created:** 2025-01-01
- **Modified:** 2026-04-26

## Supported Platforms

| Platform | Locations | Notes |
| --- | --- | --- |
| [GitHub](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners) | `.github/CODEOWNERS`, `CODEOWNERS`, `docs/CODEOWNERS` | Original format |
| [GitLab](https://docs.gitlab.com/user/project/codeowners/reference/) | `.gitlab/CODEOWNERS`, `CODEOWNERS`, `docs/CODEOWNERS` | Adds section headers, optional approvals, required counts |
| [Bitbucket Cloud](https://support.atlassian.com/bitbucket-cloud/docs/code-owners/) | `CODEOWNERS` | |
| [Gitea](https://docs.gitea.com/usage/code-owners) | `.gitea/CODEOWNERS`, `CODEOWNERS`, `docs/CODEOWNERS` | |
| [Azure Repos](https://learn.microsoft.com/en-us/azure/devops/repos/git/branch-policies) | branch policy | Configured via branch policies, not a file |

## Syntax Rules

- One pattern per line
- Pattern is a fnmatch-style glob (e.g. `*.js`, `/docs/`, `src/api/**/*.ts`)
- Owners follow the pattern, separated by whitespace: `@user`, `@org/team`, or email
- Comments start with `#`
- Blank lines are ignored
- **Last matching pattern wins**
- Invalid lines are silently skipped
- File size limit is 3 MB on GitHub

## Owner Types

- GitHub username: `@username`
- GitHub team: `@org/team-name`
- Email address (some platforms)

## Example

```text
# All files default to platform team
*       @example-org/platform

# Frontend
/web/   @example-org/frontend

# API surface
/api/openapi/  @alice @bob @example-org/api-governance
*.proto        @example-org/grpc-platform

# Security-sensitive paths require security team review
/auth/  @example-org/security
```

## Best Practices

- Place CODEOWNERS in `.github/` to keep it adjacent to other GitHub metadata
- Use teams instead of individuals for resilience and on-call rotation
- Order rules from broad to specific so specific patterns override
- Combine with branch protection: "Require review from Code Owners"
- Validate with a CI step (e.g., `codeowners-validator`)
- Document each section with a comment header

## Validators and Tooling

- [mszostok/codeowners-validator](https://github.com/mszostok/codeowners-validator)
- [hmarr/codeowners](https://github.com/hmarr/codeowners)
- [beaugunderson/codeowners](https://github.com/beaugunderson/codeowners)

## Related Repository Files

- `.github/CODEOWNERS`
- `CODE_OF_CONDUCT.md`
- `CONTRIBUTING.md`
- `SECURITY.md`
- Branch protection rules (server-side)

## Common Properties

- [GitHub Specification](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners)
- [GitLab Reference](https://docs.gitlab.com/user/project/codeowners/reference/)
- [Bitbucket Cloud Docs](https://support.atlassian.com/bitbucket-cloud/docs/code-owners/)
- [Gitea Docs](https://docs.gitea.com/usage/code-owners)
- [Azure Repos Branch Policies](https://learn.microsoft.com/en-us/azure/devops/repos/git/branch-policies)
- [Sample CODEOWNERS (dotnet/samples)](https://github.com/dotnet/samples/blob/main/.github/CODEOWNERS)
- [Validator Tool](https://github.com/mszostok/codeowners-validator)

## Notes

CODEOWNERS is plain text with no machine-readable schema. No OpenAPI specification, JSON-LD vocabulary, Spectral ruleset, or Naftiko capability bundle is published for this profile because there is no API or structured contract to validate; lint with the dedicated validators above.

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
