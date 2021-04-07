# Commitlint and Commitizen

Demonstration project that uses commitlint and commitizen in combination to enforce good  quality
commit messages, that comply with conventional commit standards.

[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](https://commitizen.github.io/cz-cli/)

## What does this do?

When ```npm install``` is run, commitlint and associated dependencies will be installed to the
local ```node_modules``` folder. Once dependency resolution is complete, husky will be called,
which will install the git hooks used to lint commit messages after every commit using
```commitlint```, and also run the ```commitizen``` wizard to make it easy for users to create
a properly formatted commit message that's compliant with conventional commit standards.

Commitizen will automatically recognise jira issues contained within the branch name, and
populate the issue number at the appropriate place in the interactive prompts. It will also
give you a chance to indicate whether this is a breaking change, and add additional metadata
that's used by jijra smart commits to automatically transition issues, log time spent etc
(assuming the smart commits integration has been enabled).

## Usage

1. Checkout the repository.

2. Run the following command from the repository root, to resolve dependencies and configure the
    git hooks. You only need to do this the first time you checkout the repo -

    ```
    $ npm install
        
    > semantic-release-poc@1.0.0 prepare
    > husky install
    
    husky - Git hooks installed
    
    up to date in 10s
    
    82 packages are looking for funding
        run `npm fund` for details
    ```

3. Follow standard git workflows. When you commit a change, you'll be presented with a wizard that
    will ask a series of questions, and generate the commit message according to conventional commit
    standards, and what's been defined in commitlint.config.js.
    
    This is fully compliant with jira smart commits, and will auto-detect the jira issue number if
    it's contained in the branch name.

    ```
    $ git add .
    $ git commit
    cz-cli@4.2.3, semantic-release-poc@1.0.0

    ? Select the type of change that you're committing: docs:     Documentation only changes
    ? What is the scope of this change (e.g. component or file name): (press enter to skip)
    ? Write a short, imperative tense description of the change:
    [------------------------------------------------------------------------] 66 chars left
    docs: placeholder for shareable config
    ? Provide a longer description of the change: (press enter to skip)
    Added a placeholder (commented out line) to use a shareable configuration for commitlint, rather than having to specify the config across multiple commitlint.config.js files, in multiple repos.
    ? Are there any breaking changes? No
    ? Does this change affect any open issues? No

    Commit preview:

       ┌───────────────────────────────────────────────────────┐
       │                                                       │
       │   docs: placeholder for shareable config              │
       │                                                       │
       │   Added a placeholder (commented out line) to use a   │
       │   shareable configuration for commitlint, rather      │
       │   than having to specify the config across multiple   │
       │   commitlint.config.js files, in multiple repos.      │
       │                                                       │
       └───────────────────────────────────────────────────────┘
    
    ? Are you sure that you want to commit? Yes
    [master 41a2a85] docs: placeholder for shareable config
    1 file changed, 5 insertions(+)
    ```

## References

- [Shareable configuration](https://github.source.internal.cba/fowliena/commitlint-cba)
- [CommitLint](https://commitlint.js.org/)
- [Commitizen](https://commitizen-tools.github.io/commitizen/)
- [ESLint](https://eslint.org/)
- [Prettier](https://prettier.io)
- [Conventional Changlog for Jira Adapter](https://github.com/digitalroute/cz-conventional-changelog-for-jira)
- [Husky](https://typicode.github.io/husky/#/)
- [Jira Smart Commits](https://support.atlassian.com/jira-software-cloud/docs/process-issues-with-smart-commits/)
