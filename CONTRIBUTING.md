# Contributing to Threlte

## Table of Contents
- [Ways to Contribute](#ways-to-contribute)
- [Contributing Workflow](#contributing-workflow)
- [Commit Convention](#commit-convention)
- [Understanding Issues and Labels](#understanding-issues-and-labels)
- [Understanding Changesets](#understanding-changesets)
- [Git Branches](#git-branches)
- [Getting Started Locally](#get-started-with-threlte-locally)
  
## Ways to Contribute

1. **Improve Documentation**: Fix incomplete or missing documentation, wording, examples, or explanations.
2. **Provide Feedback**: Let us know how you use Threlte and how it can be improved. Use GitHub Discussions or [Discord](https://discord.gg/EqUBCfCaGm) for this.
3. **Share Threlte**: Help us grow by sharing Threlte on social media platforms and with those who may find it beneficial.
4. **Contribute to Code**: Propose a new feature via [GitHub Issues](https://github.com/threlte/threlte/issues) or work on an [existing one](https://github.com/threlte/threlte/labels/help%20wanted).
5. **Code Reviews**: Help improve code quality through your reviews of the [source code](https://github.com/threlte/threlte).


## Contributing Workflow

1. **Identify Contribution**: Decide what you want to contribute.
2. **Discussion**: If you're proposing a new feature, discuss it with a maintainer on [Discord](https://discord.gg/EqUBCfCaGm).
3. **Work and Commit**: Follow our [commit conventions](#commit-convention).
4. **Submit a PR**: If everything is satisfactory, submit a Pull Request.
5. **Code Review and Merging**: Address review comments, and once approved, your PR will be merged.

## Commit convention

Threlte is a monorepo and it is important to write clear commit messages to keep the git history clean.

Commit messages should be clear to maintain a clean git history. This repository uses [changesets](https://github.com/changesets/changesets) to facilitate this process. Run `npx changeset` to be guided through the commit process.

## Understanding Issues and Labels

- `bug`: For issues where something isn't working.
- `contributions welcome`: If you have an idea, feel free to make a PR.
- `documentation`: For improving or adding to the documentation.
- `duplicate`: Used when an issue or pull request already exists.
- `enhancement`: For new feature requests.
- `good first contribution`: Issues that are suitable for newcomers.
- `organisation`: Pertains to Threlte organization and community issues.
- `support`: When asking for help.

# Understanding Changesets

Changesets are an integral part of how we handle versioning in Threlte, especially as we operate in a monorepo environment. A changeset is essentially an 'intent to change', holding key information such as what needs to be released, which version we are releasing at (based on semver), and a changelog entry for the released packages.

## How to Add a Changeset

1. **Run the Changeset Command**: Execute `npx changeset` or `yarn changeset` in your terminal.
2. **Package Selection**: If in a monorepo, you'll be prompted to select the packages affected by your changes.
3. **Versioning**: Choose an appropriate semver bump type (major, minor, or patch) for each selected package.
4. **Changelog Entry**: Write a concise message to accompany the changeset, detailing WHAT the change is, WHY it was made, and HOW it affects the users.
5. **Commit**: Commit the generated changeset file to your branch.

A detailed guide on adding changesets can be [found here](https://github.com/changesets/changesets/blob/main/docs/adding-a-changeset.md).

## Why Changesets are Important

Changesets ensure that you capture all the necessary information about a change when it is fresh in your mind. This is especially useful for contributors and maintainers when they go to batch and release these changes. For an in-depth understanding, refer to [this document](https://github.com/changesets/changesets/blob/main/docs/detailed-explanation.md).


## Git Branches

- `main`: Reflects the stable version published on npm.

## Get Started with Threlte Locally

1. **Editor Configuration**: Install the [`editorconfig`](https://editorconfig.org/) extension for your editor.
2. **VSCode Users**: Install the recommended extensions.
3. **Repository Setup**: Fork the [repository](https://github.com/threlte/threlte), clone or download your fork, and then run `pnpm run install:all` at the root.**(make sure to install with pnpm)**

### If Developing a Package **[e.g. packages/core, packages/extras]**

1. Run `pnpm run dev` in the repository root.
2. Implement the components or hooks in question. Changes are reflected instantaneously in dependent apps or packages.

### If Developing an App **[apps/docs]**

1. Run `pnpm run dev` in the repository root.
