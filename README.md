# trestlebot-demo-ssp
Testing and demonstrating trestlebot in various configurations for SSPs

# Example with a default main branch

- Automated pushes to main with updates
- Automated and ad-hoc upstream content sync (workflow dispatch via webhook)
- Regenerate SSP Markdown upstream changes are created on a PR to view the impact of the changes

# What is missing

- SSP automated versioning [update](https://github.com/RedHatProductSecurity/trestle-bot/issues/186)
- The develop branch. This example uses GitHub flow to keep it more lightweight.

# Ideas
- An automated dry-run [option](https://github.com/RedHatProductSecurity/trestle-bot/issues/181). It may be generally useful to know if a markdown changes is going to cause assemble to fail before it merged.
- SSP report generation (i.e using SSP filter in CI)

