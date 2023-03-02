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