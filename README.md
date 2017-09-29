# git-sync
The aim of this project is to replicate a git branch of the upstream repository to another branch of a target repository.

This is similar to [Syncing a fork](https://help.github.com/articles/syncing-a-fork/) with the upstream, difference is that in this case you dont want the fork to access directly the upstream repository.

## Real case scenario
I use this script in my company to allow a customer to have access to only approved versions of the code.
We've a separate git repo for the customer and each time the private repository is tagged, the code must be released to the customer, force-pushing it to a target branch.

This way the customer can freely access his repository and, by creating branches, customise our code as well.

## How it works
GIT-Sync is a server-side git hook script, which is cloning the upstream, adding the target remote and pushing to the target branch.

## Setup

This hook uses Bash. Make sure it is installed.

#### Local installation 

* Copy the post-recieve.d hook into the hooks directory.
* Run "chmod a+x git-sync" to make it executable.

#### Gitlab installation
http://gitlab.org/

* Locate the hooks path (usually /opt/gitlab/embedded/service/gitlab-shell/hooks/), copy the post-recieve.d hook into the hooks directory.
* Run "chmod a+x git-sync" to make it executable.


