# Git style guide

## 1. Commits
### 1.1. Message

Commit messages contain a single line with no more than 100 characters ideally.

The commit message must follow this format: 

* `:commit_type_emoji_code:(context/subcontext): description`

    * e.g. :bug:(db/connection_string): parametrized conn string to change according to the environment dev/prod

The beggining of the message leads with an emoji to quikcly identify the commit pourpose, follwed by the "context",
which is a combination of one or more words separated by "/" that tell us what part of the code or function was modified.
The description of the commit summarizes your modifications. Verbs should be written in their imperative form.


### 1.2. Types

Commit types are necesarry to help us avoid massive commits that change different non-related parts of the code.
It helps us debug faster or track the modifications with more granularity.
The commit types we use are described below with their corresponding emoji identifier


|Commit type                | Emoji identifier                  | Purpose                                                                       |
|---------------------------|-----------------------------------|-------------------------------------------------------------------------------|
|    feat                   |:sparkles:         (`:sparkles:`)  |Un nuevo feature                                                               |
|    fix                    |:bug:              (`:bug:`)       |La corrección de un bug                                                        |
|    docs                   |:books:            (`:books:`)     |Cambios en la documentación                                                    |
|    style                  |:lipstick:         (`:lipstick:`)  |Cambios que no afectan el significado del código (espacios, indentación, etc.) |
|    refactor               |:art:              (`:art:`)       |Un cambio en el código que no agrega una funcionalidad ni corrige un bug       |
|    perf                   |:repeat:           (`:repeat:`)    |Cambios en el código que sólo mejoran la performance                           |
|    test                   |:pencil:           (`:pencil:`)    |Adds, removes, corrects or enhances tests                                      |
|    conf                   |:wrench:           (`:wrench:`)    |Changes to config files                                                        |
|    chore                  |:broom:            (`:broom:`):    |Changes to the build process, maintenance and auxiliary tools                  |
|    rm                     |:skull:            (`:skull:`):    |Deprecated code                                                                |

----


### 2. Workflow

### 2.1. Main Branches
At all times the project should have the following branches.
* `main:`                   This branch contains the code that has been tested and is ready to be deployed.
* `dev:`                    This branch contains code that's ready to become part of the main branch. Pull requests that make it to this branch must fully be tested.

#### 2.1.1 (Optional)
* `release/x.x.x:`          This branch is born from the `main` branch, and marks a milestone with a set of features.

### 2.2. Working Branches
Branches should be named after their purpose with the following syntax `type/context`.
Context should identify what/where you are working. For example the name of a component, feature or file.
* `fix/data_normalization`
* `style/topbar`
* `feat/readme`

***:warning: All branches should be deleted after being merged :warning:***

### 2.3 Pull Requests
To integrate branch `B` into branch `A` you must folllow the next steps:

**1**. Merge the latest version of `A` into `B` and check that the code still works

**2**. Create the pull request(PR) from `B` to `A` and assign a reviewer

**3**. If the PR has comments, fix/modify the code to fix the issues.

**4**. Update your Pull request with the corresponding modifications

**5**. Delete branch after it is merged into development

