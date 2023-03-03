# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) and
[Common Changelog](https://common-changelog.org/).

This project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- Add CHANGELOG.md

## [1.1.0] - 2023-03-02

This release refactors documentation to Markdown, adds clear sub-requirements, introduces git conventions and automates
the deployment of new versions to GitHub Pages as a fast, simple and searchable static site.

### Changed

- Refactor v1.0.0 docs to Markdown
- Change requirement explanatory text to specific sub-requirements
- Change form for conditional requirements to "If [condition], [requirement]"
- Change curly quotation marks to straight quotation marks
- Change intention text to explanation text for requirement AG001-AG004

### Fixed

- Fix typos in terms, abbreviations and acronyms
- Fix British/American English spelling mistakes
- Fix capitalization
- Fix internal and external links
- Fix "API deployer" as "API server deployer" for requirement SD006

### Removed

- Remove broken links from docs
- Remove obsolete tables from requirement chapters

### Added

- Add "Overview" chapter to docs
- Add "Requirement status" section to Notational Conventions
- Add "Rules for writing requirements" section to Notational Conventions
- Add "Git Branch Naming Conventions" section to README
- Add "Git Commit Message Conventions" section to README
- Add "Release Notes" section to README
- Add "Writing Docs" section to README
- Add "Building Docs" section to README
- Add "Deploying Docs" section to README
- Add "Viewing Docs" section to README
- Add "Since version" to requirements
- Add external links to relevant topics in docs
- Add `MkDocs` static site generator
- Add `Material for MkDocs` theme
- Add `mike` versioning provider
- Add theme overrides
- Add analytics to site
- Add navigation to site
- Add search plugin to site
- Add cookie consent to site
- Add copyright notice to site
- Add social links to site
- Add "Privacy statement" link to site
- Add "Was this page helpful?" widget to page
- Add "Publish docs" workflow to GitHub Actions