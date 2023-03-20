# Gitflow notes

These notes are based on the following document: https://nvie.com/posts/a-successful-git-branching-model/ and indeed although it is an "old" article, it can still be useful. This document is intended as a guideline for managing future projects. Some of the terms used in that article will be replaced with more current ones. It is recommended that you read this entire document.

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

1. Initializing the Git repository: Initialize a new Git repository on your local computer and upload your source files to it.
2. Creating the `dev` branch: Create a new development branch called `dev` from the `main` branch.
3. Creating `feature` branches: Create a new feature branch from the dev branch for each new feature or bug fix. Use a descriptive name for the feature branch that helps identify its purpose. Use the prefix `feature/` + the name of the branch with the new feature. 
4. Developing features: Work on the `feature branch` to develop the feature or fix the bug.
5. Creating a pull request: Once the feature or bug fix is complete, create a **pull request** from the feature branch to the `dev` branch. This will help review and discuss the changes made.
6. Code review: Team members review and discuss the changes made to the feature or bug fix in the pull request. If necessary, further changes are made.
7. Pull request approval: Once the feature or bug fix has been approved, the pull request is merged into the `dev` branch.
8. Creating the `release` branch: When all planned features for a release have been merged into the dev branch and the code has been tested, create a new release branch from the dev branch. Assign a unique version number to the release branch.
9. Final development: Any necessary bug fixes or final modifications are made on the release branch.
10. Testing: The code on the release branch is tested to ensure it functions as expected and there are no errors.
11. Creating the release tag: When the release branch has been tested and approved, create a new **release tag** from the release branch to mark the software version.
12. Merging to the `main` branch: Finally, the `release` branch is merged into the `main` branch for distribution. This marks the end of the development cycle and the software is deployed in production.
