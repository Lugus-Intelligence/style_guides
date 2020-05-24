# Git style guide

## 1. Commits
### 1.1. Message

Commit messages contain a single line with no more than 100 characters ideally.

The commit message must follow this format: 

* `:commit_type_emoji_code:(context/subcontext): description`

    * e.g. :bug:(db/connection_string): parametrized conn string to change according to the environment dev/prod

The beggining of the message leads with an emoji to quikcly identify the commit pourpose, follwed by the "context",
which is a combination of one or more words separated by "/" that tell us what part of the code or function was modified.
The description of the commit summarize your modifications.


### 1.2. Types

Commit types are necesarry to help us avoid massive commits that change different non-related parts of the code.
It helps us debug faster or track the modifications with more granularity.
The commit types we use are described below with their corresponding emoji identifier


|Commit type          		| Emoji identifier 					| Pourpose                                                                      |
|---------------------------|-----------------------------------|-------------------------------------------------------------------------------|
|    feature 				|:sparkles:    		(`:sparkles:`)	|Un nuevo feature																|
|    bugfix	 				|:bug:              (`:bug:`)		|La corrección de un bug														|
|    docummentation	 		|:books:       		(`:books:`)		|Cambios en la documentación													|
|    styling 				|:lipstick:			(`:lipstick:`)	|Cambios que no afectan el significado del código (espacios, indentación, etc.)	|
|    refactor 				|:art:              (`:art:`)		|Un cambio en el código que no agrega una funcionalidad ni corrige un bug		|
|    optimization 			|:repeat:          	(`:repeat:`)	|Cambios en el código que sólo mejoran la performance							|
|    testing 				|:pencil:       	(`:pencil:`)	|Agrega, corrige o mejora tests													|
|    configurations 		|:wrench:			(`:wrench:`)	|Cambios al proceso de build y herramientas auxiliares							|
|    security 				|:lock:             (`:lock:`)		|Security upgrades, fixes														|
|    dependency				|:link:				(`:link:`)		|Changes to the libraries used (upgrade/downgrade/new)							|
|    deprecation 			|:skull:            (`:skull:`):	|Mark code as deprecated to be removed in future versions						|

----


### 2. Workflow
### 2.1. Branch Types

We work using a methodology called gitflow. That being said, we use 6 branch types:

* `master:` 				This branch contains commits with all the release versions, The code here has been fully tested and is ready to be deployed.
* `hotfix/bug_name:` 		This branch is born from `master`. This branches must die ASAP, they fix a problem detected on a release version that made it to master.
* `development:` 			This branch comes from `master`, it contains code that's ready to become part of a release. Pull requests that make it to this branch must fully be tested.
* `release/x.x.x:`			This branch is born from `develop`. All minor modifications needed to take the code to a production version x.x.x must be performed here.
* `feat/feature_name:` 		Feature branches are born from the `develop`, they contain code for new functionalities.
* `bugfix/bug_name:		This branch is born from `develop`. Bug fix branches have a short life-spawn and their pourpose is to solve problems from buggy features that made it to development.

### 2.2 Pull Requests
To integrate branch `B` into branch `A` you must folllow the next steps:

**1**. Merge the latest version of `A` into `B` and check that the code still works

**2**. Create the pull request(PR) from `B` to `A` and assign a reviewer

**3**. If the PR has comments, fix/modify the code to fix the issues.

**4**. Update your Pull request with the corresponding modifications

**5**. Delete branch after it is merged into development
