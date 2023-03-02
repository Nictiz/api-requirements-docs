# API Requirements for Dutch Healthcare

This repository contains the source files for the API Requirements for Dutch Healthcare documentation.

This specification has been developed as part of the [Nictiz](https://nictiz.nl/) API strategy.

## Git Conventions

Contributors **MUST** understand the importance of writing readable and consistent Git branch names and commit messages.

### Git Branch Naming Conventions

Contributors **MUST** follow a very lean and simple Git branch naming convention that makes it easy to correlate the
relevant working branch with each task in the [issue tracker](https://github.com/Nictiz/api-requirements-docs/issues).
These rules are in line with GitHub's approach when
[creating a branch to work on an issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-a-branch-for-an-issue).

1. Start branch names with the issue ID
    * If there is no issue, use `noref`
2. Add a short and actionable description of the task
3. Use hyphens as word separators

```
reference-description-in-kebab-case

noref-add-contributing-docs
120-fix-publish-workflow
```