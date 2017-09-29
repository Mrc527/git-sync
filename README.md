# git-sync
The aim of this project is to replicate a git branch of the upstream repository to another branch of a target repository.

This is similar to Syncing a fork with the upstream, difference is that in this case you dont want the fork to access directly the upstream repository.

## Real case scenario
I use this script in my company to allow a customer to have access to only approved versions of the code.
We've a separate git repo for the customer and each time the private repository is tagged, the code must be released to the customer, force-pushing it to a target branch.

This way the customer can freely access his repository and, by creating branches, customise our code as well.

## How it works
GIT-Sync is a server-side git hook script, which is cloning the upstream, adding the target remote and pushing to the target branch.

## Setup

This hook uses Bash. Make sure it is installed.

#### Local installation 

In a local --bare git repository, this hook must be placed in the hooks directory in the git directory.
If an update hook exists, the content of this hook must be pasted into the existing.
Alternatively, the pre-recieve hook can be used.

#### Gitlab installation
http://gitlab.org/

Locate the path to the given repository, copy the pre-recieve hook into the hooks directory.
Run "chmod a+x pre-recieve" to make it executable.
If this hook should be activated on more than a few repositories, consider placing it in a central place and
link to it.

