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

### Git Commit Message Conventions

Contributors **MUST** follow seven common rules for writing a great Git commit message:

1. Separate subject from body with a blank line
2. Limit the subject line to 50 characters
3. Capitalize the subject line and each paragraph
4. Do not end the subject line with a period
5. Use the imperative mood in the subject line: "Fix bug", not "Fixed bug"
6. Wrap the body at 72 characters
7. Use the body to explain what and why, not how

#### Imperative mood

*Imperative mood* means "spoken or written as if giving a command or instruction". Git itself uses the imperative mood
whenever it creates a commit on your behalf: `Merge branch 'name'`, `Revert "Add item"`.

The first word in your commit message will typically be one of these: `Add`, `Create`, `Refactor`, `Fix`, `Release`,
`Document`, `Modify`, `Update`, `Remove`, `Delete`.

> It should complete the sentence: "If applied, this commit will [your subject line here]"

#### Example

```
Summarize changes in around 50 characters or less

More detailed explanatory text, if necessary. Wrap it to about 72
characters or so.

Explain the problem that this commit is solving. Focus on why you
are making this change as opposed to how (the code explains that).

Further paragraphs come after blank lines.

 - Bullet points are okay, too
 
 - Typically a hyphen is used for the bullet, preceded by a single
   space, with blank lines in between
```

Not every commit messages necessitates the use of both a subject and a body. A single line indicating the subject can be
sufficient in some cases, especially when the change is so little that no more context is required.

## Release Notes

We use
[GitHub Releases](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository)
to trigger [deployment](#deploying-docs) of new versions of documentation to GitHub Pages and to create a formatted
changelog. The release notes must tell someone what upgrading will do. It communicates an *intent* of change.

This project embraces the guiding principle of [Keep a Changelog](https://keepachangelog.com/) and
[Common Changelog](https://common-changelog.org/) that changelogs must be written by humans and for humans. Spending a
modest amount of time on writing a changelog saves every reader twice as much time.

### Rules for Writing Release Notes

Contributors **MUST** adhere to the following general guidelines when writing release notes:

- The same type of changes should be grouped:
   - `Added` for new features
   - `Changed` for changes in existing functionality
   - `Deprecated` for soon-to-be removed features
   - `Removed` for now removed features
   - `Fixed` for any bug fixes
- Each category heading must be followed by (and only by) an unnumbered Markdown list. Each item in the list should be a
  single line that must start with a change, followed by one or more references if available: `(#1, #2)`.
- Write a change using the imperative mood. It must start with a present-tense verb, for example (but not limited to)
  `Add`, `Support`, `Refactor`, `Document`, `Fix`, `Deprecate`. Git commits follow the same convention.
- Each change must be self-describing, as if no category heading exists.
- Sort changes by importance and skip changes that are not important.
- Breaking changes must be prefixed in bold with `**Breaking:**` and should be listed before other changes (per
  category).

### Release Notes Markdown

The release notes are written in Markdown. The "Release title" that is entered as part of the standard GitHub release
management process is considered to be the `h1` heading (`# Heading level 1` in Markdown). Release notes must start with
a second-level Markdown heading.

```
## Overview

Summarize changes this release brings.

## Changelog

### Changed

- **Breaking:**: change applicable role of requirement SD001

### Fixed

- Fix publish workflow ([#120](https://github.com/owner/name/issues/120))

### Added

- Add "Rules for writing requirements" section
```

## Writing Docs

Documentation source files are written in Markdown. Markdown is a simple and easy-to-use markup language for creating
formatted text using a plain-text editor. Visit open-source reference guide
[The Markdown Guide](https://www.markdownguide.org/) to learn more about Markdown.

### Rules

For the sake of readability, contributors **MUST** wrap lines at **120** characters. This does not apply to Markdown
headings and tables (Extended Syntax). Refer to your IDE/text editor's documentation on how to configure visual guides.