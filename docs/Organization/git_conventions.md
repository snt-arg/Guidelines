# Git Conventions

Your best friend when writing software. Git is a distributed version control
system that allows multiple developers to track changes, collaborate,
and manage code history efficiently.

## Why?

The use of Git should be your number one tool if you do any type of software development.
If you are reading this guide, the chances that you already are in our GitHub organization
are high. In case you did not know, any software that you work on, whether already existing
or new should all be hosted on our [organization](https://github.com/snt-arg){:target="\_blank"}.

In order to maintain a good consistency across all repositories in our organization,
some conventions are encouraged to be followed. The conventions not only help you
to manage your development, such as finding where things were added, fixed or even
roll back to a working state are one the main key advantages. In addition, by following
these conventions, you will be helping others and make use of automated tools
to generate good CHANGELOGs for instance.

## Repositories

- Name your repository with some meaning.
- In case a repository is used for versioning workspaces, it should be named with the project
  name and carry the `_ws` suffix. Such an example is the [tello_ws](https://github.com/snt-arg/tello_ws){:target="\_blank"}.
- Consider having a `.gitignore` file. You can use a generator [here](https://www.toptal.com/developers/gitignore){:target="\_blank"}
- Each repository should contain a **README** which should give some docs about the project
  and some guides to use the software.

## Branches

### Recommended Branching Strategy with CI/CD Pipeline

This approach leverages a CI/CD pipeline, eliminating the need for a `dev` branch. The `main` branch is **continuously** updated.

When developing a new feature or fixing a bug, create a separate branch for the task. Once the work is complete, create a pull request to merge it into the `main` branch. This PR will be run through the CI/CD pipeline, which will perform tests, verify code compilation, and more. If any checks fail, the pull request cannot be merged into the `main` branch.

### Legacy Branching Strategy (Still Useful)

Each repository should have at least two branches: `main` (or `master`) and `dev`. The `main` branch should always contain a stable version of the software, while the `dev` branch serves as the development branch where all new changes are made.

When starting the implementation of a new feature or fixing a bug, you **should** create a new branch dedicated to the new feature or fix. This branch should be created **from the `dev` branch**.

Once a branch has fulfilled its purpose, create a pull request (PR) and assign it to another team member for code review and merging into the `dev` branch.

!!! hint

    Once the `dev` branch is stable, the same should be merged to the `main` branch by **creating a PR**.

### Branch Naming Examples

Each new branch should have a prefix followed by a descriptive name. Here are some examples:

1. `feat/add-login-page`: Work involving adding a login page feature.
2. `fix/typo-in-header`: Focus on fixing a typo found in the header section.
3. `refactor/restructure-database`: Work involving refactoring or restructuring the database architecture.
4. `docs/update-readme`: Updating the project's README documentation.
5. `test/add-unit-tests`: Adding unit tests to the project.
6. `style/change-button-color`: Changing the color of buttons in the user interface.
7. `hotfix/fix-security-vulnerability`: A critical fix for a security vulnerability.
8. `chore/clean-up-unused-code`: Cleaning up unused code or files in the project.

## Commits

Commits should be well-scoped and frequent. Each commit message should reflect on a change that
has been performed, where the message should be short and straight to the point. In case some
more details are needed, you can make use of the body of the message to write more details.

Here is how a commit message should be structured:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

The types of commits can be: `feat`, `fix`, `chore` ...

!!! info

    For more details and why you should use convey to using this convention can be found [here](https://www.conventionalcommits.org/en/v1.0.0/)

## Visibility

All repository created should be set to private. This is because you do not own your repository but in fact it's the University of Luxembourg. Nevertheless, that does not mean you cannot make it open-source. If you want to make it open-source please have a discussion with Holger or Jose-Luis.

## License

In case you desire to make your project open-source, your repository should have
a license. This license is usually selected by the TTO (Technology Transfer Office) , after a full investigation
of your repo, to see if it passes all checks.

Nevertheless, you could already create a license file when creating the repo.
The license that will be applied will most likely be [GPL-3.0](https://opensource.org/license/gpl-3-0){:target="\_blank"}.

## CI/CD

To learn how to use GitHub actions, please follow their (guide)[https://docs.github.com/en/actions].
