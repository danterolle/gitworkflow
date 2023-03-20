# Gitflow, Conventional Commits and Semantic Versioning

These notes are based on the following document: https://nvie.com/posts/a-successful-git-branching-model/ and indeed although it is an "old" article, it can still be useful. This document is intended as a guideline for managing future projects. Some of the terms used in that article will be replaced with more current ones. It is recommended that you read this entire document.

1. [Development Process](#development-process)
2. [Conventional Commits](#conventional-commits)
3. [Semantic Versioning](#semver)

## What does "Gitflow" mean?

Gitflow is a branching and versioning model for source code management based on the use of Git as a version control system. It is a structured approach to Git workflow management and helps keep code clean, organized, and easily maintainable. Its usefulness will be described in the following paragraphs. 

## Why should it be used?

There are several reasons why you should consider using Gitflow for your code management. Firstly, it provides a clear and well-defined structure for collaborating on source code so that team members can work collaboratively and productively. Additionally, it helps ensure that code is maintained in a manageable and maintainable format, reducing the risk of errors and conflicts.

## How does it work?

The process of using Gitflow involves the use of two branches: `main` and `dev`. 

The `main` branch is intended to contain the stable version of the code, while the `dev` branch is used to integrate the work of team members and to test the code in a *development environment*. 

Every time you work on a new feature or modification, you create a new **feature branch** from the dev branch. When work on the feature is complete, the feature branch is merged into the dev branch using a **pull request**. 

Once all features have been merged into the dev branch and the code has been tested, a new **release branch** is created from the dev branch to prepare the code for distribution. 

Finally, once the release branch has been tested and approved, it is merged into the main branch for distribution.

# Development Process

### 1. Initializing the Git repository

Initialize a new Git repository on your local computer and upload your source files to it.

### 2. Creating the `dev` branch

Create a new development branch called `dev` from the `main` branch.

### 3. Creating `feature` branches

Create a new feature branch from the dev branch for each new feature or bug fix. Use a descriptive name for the feature branch that helps identify its purpose. Use the prefix `feature/` + the name of the branch with the new feature. 

### 4. Developing features

Work on the `feature branch` to develop the feature or fix the bug.

### 5. Creating a pull request

Once the feature or bug fix is complete, create a **pull request** from the feature branch to the `dev` branch. This will help review and discuss the changes made.

### 6. Code review

Team members review and discuss the changes made to the feature or bug fix in the pull request. If necessary, further changes are made.

### 7. Pull request approval

Once the feature or bug fix has been approved, the pull request is merged into the `dev` branch.
### 8. Creating the `release` branch

When all planned features for a release have been merged into the dev branch and the code has been tested, create a new release branch from the dev branch. Assign a unique version number to the release branch.

### 9. Final development

Any necessary bug fixes or final modifications are made on the release branch.

### 10. Testing

The code on the release branch is tested to ensure it functions as expected and there are no errors.

### 11. Creating the release tag

When the release branch has been tested and approved, create a new **release tag** from the release branch to mark the software version.

### 12. Merging to the `main` branch

Finally, the `release` branch is merged into the `main` branch for distribution. This marks the end of the development cycle and the software is deployed in production.

# Conventional Commits

[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) provide a naming convention system for labeling commits in a consistent and meaningful way, making it easier to read and understand the Git log and the changes made to the project. Using a standard convention helps maintain good code organization and facilitates collaboration among development team members.

`<type>[optional scope]: <short description>`

## Conventional Commit prefixes

- feat: adding a new feature
- fix: fixing a bug
- docs: changes to documentation
- style: code changes that don't affect the meaning (e.g. white-space, formatting, etc...)
- refactor: code changes that neither fix a bug nor add a feature
- perf: changes that improve performance
- test: adding or modifying tests
- build: changes to build process or tools (e.g. updating dependencies)
- ci: changes to CI configuration files
- chore: other changes that don't modify source code or test files
- revert: reverting a previous commit

## optional scope

Optional scopes in Conventional Commits are an optional section that provides additional context about the change made. The scope field is separated from the commit type and description by an open and closed parenthesis and should be written in lowercase.

The scope field can provide additional information about the location of the change within the code or the specific component of the system that was modified. This can be particularly useful in larger projects where there are many parts of the code and multiple contributors. The use of optional scopes in Conventional Commits depends on the needs of the project and the preferences of the development team. In some cases, the scope can be extremely useful in providing greater clarity about the changes made, while in other cases it may be less relevant.

Example:

`feat(api): add new REST API`

## BREAKING CHANGE prefix

The prefix **BREAKING CHANGE** can be used to indicate that the commit introduces a change that breaks compatibility with previous versions of the application or library. This prefix should only be used if the change is "breaking" in nature and requires significant code changes to continue functioning properly.

When using the BREAKING CHANGE prefix, the commit description should provide a detailed description of the change and the modifications necessary to adapt to the new features or changes made. Additionally, the description should include a note about the nature of the change and why it was necessary.

# SemVer

[SemVer](https://semver.org/) is a convention for versioning software, based on three main numbers: MAJOR, MINOR, and PATCH. 

- MAJOR: the main version number, indicating an incompatible version that requires significant migration to adapt to.

- MINOR: the version number indicating the introduction of new features without breaking compatibility with previous versions.

- PATCH: the version number indicating the correction of bugs or minor issues without changing features or compatibility.

The version of software according to Semver is indicated in the MAJOR.MINOR.PATCH format. For example, version 1.2.3 indicates the first major version of the software, with the second minor version and the third patch.

## How should these "indicators" be managed?

- When introducing a breaking change with previous versions, the MAJOR version number should be incremented.

- When introducing new features without breaking compatibility, the MINOR version number should be incremented.

- When correcting bugs or minor issues without changing features, the PATCH version number should be incremented.

- When releasing a new version, the version number should be updated in all configuration and documentation files that refer to the software version.
