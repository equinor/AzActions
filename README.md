# AzActions - Trying to make things easier

We have decided to create custom actions that provide a simpler approach by default, while keeping the flexibility of advanced scenarios through use of inputs.
For details on why we chose to create a custom action, please review the action documentation. Each of them have a "Why use this module?" segment in their readme.

| Action name (link to doc)                                     | Description                   | Status                                                                                                                                                                         | Latest version                                                                                                                                                                                                                                            | Last update                                                                                                   | Size                                                                                       | Issues                                                                                                                                                                                                                                                           |
| :------------------------------------------------------------ | :---------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------ | :----------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [equinor/AzVariables](https://github.com/equinor/AzVariables) | Manage workflow variables     | [![Action-Test](https://github.com/equinor/AzVariables/actions/workflows/Action-Test.yml/badge.svg)](https://github.com/equinor/AzVariables/actions/workflows/Action-Test.yml) | ![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/equinor/AzVariables?label=Stable) ![GitHub tag (latest SemVer pre-release)](https://img.shields.io/github/v/tag/equinor/AzVariables?color=orange&include_prereleases&label=Pre-release) | ![GitHub last commit (branch)](https://img.shields.io/github/last-commit/equinor/AzVariables/main?label=main) | ![GitHub repo size](https://img.shields.io/github/repo-size/equinor/AzVariables?label=%20) | [![GitHub issues](https://img.shields.io/github/issues/equinor/AzVariables)](https://github.com/equinor/AzVariables/issues) [![GitHub pull requests](https://img.shields.io/github/issues-pr/equinor/AzVariables)](https://github.com/equinor/AzVariables/pulls) |
| [equinor/AzConnect](https://github.com/equinor/AzConnect)     | Connect to Azure              | [![Action-Test](https://github.com/equinor/AzConnect/actions/workflows/Action-Test.yml/badge.svg)](https://github.com/equinor/AzConnect/actions/workflows/Action-Test.yml)     | ![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/equinor/AzConnect?label=Stable) ![GitHub tag (latest SemVer pre-release)](https://img.shields.io/github/v/tag/equinor/AzConnect?color=orange&include_prereleases&label=Pre-release)     | ![GitHub last commit (branch)](https://img.shields.io/github/last-commit/equinor/AzConnect/main?label=main)   | ![GitHub repo size](https://img.shields.io/github/repo-size/equinor/AzConnect?label=%20)   | [![GitHub issues](https://img.shields.io/github/issues/equinor/AzConnect)](https://github.com/equinor/AzConnect/issues) [![GitHub pull requests](https://img.shields.io/github/issues-pr/equinor/AzConnect)](https://github.com/equinor/AzConnect/pulls)         |
| [equinor/AzGather](https://github.com/equinor/AzGather)       | Gather Azure environment info | [![Action-Test](https://github.com/equinor/AzGather/actions/workflows/Action-Test.yml/badge.svg)](https://github.com/equinor/AzGather/actions/workflows/Action-Test.yml)       | ![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/equinor/AzGather?label=Stable) ![GitHub tag (latest SemVer pre-release)](https://img.shields.io/github/v/tag/equinor/AzGather?color=orange&include_prereleases&label=Pre-release)       | ![GitHub last commit (branch)](https://img.shields.io/github/last-commit/equinor/AzGather/main?label=main)    | ![GitHub repo size](https://img.shields.io/github/repo-size/equinor/AzGather?label=%20)    | [![GitHub issues](https://img.shields.io/github/issues/equinor/AzGather)](https://github.com/equinor/AzGather/issues) [![GitHub pull requests](https://img.shields.io/github/issues-pr/equinor/AzGather)](https://github.com/equinor/AzGather/pulls)             |
| [equinor/AzModules](https://github.com/equinor/AzModules)     | Deploy resources to Azure     | [![Action-Test](https://github.com/equinor/AzModules/actions/workflows/Action-Test.yml/badge.svg)](https://github.com/equinor/AzModules/actions/workflows/Action-Test.yml)     | ![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/equinor/AzModules?label=Stable) ![GitHub tag (latest SemVer pre-release)](https://img.shields.io/github/v/tag/equinor/AzModules?color=orange&include_prereleases&label=Pre-release)     | ![GitHub last commit (branch)](https://img.shields.io/github/last-commit/equinor/AzModules/main?label=main)   | ![GitHub repo size](https://img.shields.io/github/repo-size/equinor/AzModules?label=%20)   | [![GitHub issues](https://img.shields.io/github/issues/equinor/AzModules)](https://github.com/equinor/AzModules/issues) [![GitHub pull requests](https://img.shields.io/github/issues-pr/equinor/AzModules)](https://github.com/equinor/AzModules/pulls)         |
| [equinor/AzUtilities](https://github.com/equinor/AzUtilities) | Installs utilities on runner  | [![Action-Test](https://github.com/equinor/AzUtilities/actions/workflows/Action-Test.yml/badge.svg)](https://github.com/equinor/AzUtilities/actions/workflows/Action-Test.yml) | ![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/equinor/AzUtilities?label=Stable) ![GitHub tag (latest SemVer pre-release)](https://img.shields.io/github/v/tag/equinor/AzUtilities?color=orange&include_prereleases&label=Pre-release) | ![GitHub last commit (branch)](https://img.shields.io/github/last-commit/equinor/AzUtilities/main?label=main) | ![GitHub repo size](https://img.shields.io/github/repo-size/equinor/AzUtilities?label=%20) | [![GitHub issues](https://img.shields.io/github/issues/equinor/AzUtilities)](https://github.com/equinor/AzUtilities/issues) [![GitHub pull requests](https://img.shields.io/github/issues-pr/equinor/AzUtilities)](https://github.com/equinor/AzUtilities/pulls) |

## Input handling

Most of our actions will start with loading environment variables, named the same as the different action inputs. This can be seen as setting the default values
for the actions within a workflow, reducing the need of repeating them throughout the workflow. After environment variables are loaded, the inputs are gathered
and merged with the inputs overriding the defaults from environment variables. If default values are provided in the inputs section of the action definition,
this will also override the gathered environment variables.

> Note!
>
> This override mechanism will only be used for a specific call of the action, and will not store the overridden value back to the corresponding environment variable.

Used together with [equinor/AzVariables](https://github.com/equinor/AzVariables) and a variables file which can be stored as code and loaded,we try to reduce
the duplication specifying inputs.

## Repo automation

To automate setup of our action we use:

| App name                                                          | Configuration                  | Description                                                                                           |
| :---------------------------------------------------------------- | :----------------------------- | :---------------------------------------------------------------------------------------------------- |
| [Release Drafter](https://probot.github.io/apps/release-drafter/) | `.github/release-drafter.yml`  | Drafts your next release notes as pull requests are merged.                                           |
| [Work In Progress](https://probot.github.io/apps/wip/)            | Use 'WIP or 'wip' in PR title. | Prevent merging of Pull Requests with "WIP" in the title                                              |
| [Request Info](https://probot.github.io/apps/request-info/)       | `.github/config.yml`           | Automatically requests more info on issues and pull requests with the default title or an empty body. |
| [Settings](https://probot.github.io/apps/settings/)               | `.github/settings.yml`         | Repo configuration as code.                                                                           |

## How to contribute

Coming soon.

## Code of Conduct

Coming soon.

## Code quality and guidelines

Coming soon.
