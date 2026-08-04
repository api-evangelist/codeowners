# CODEOWNERS (codeowners)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
