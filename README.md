# gitlab-merge-helper

### Gitlab api doc 
https://docs.gitlab.com/api/rest/ 

### Parts of algorithm

First - we need to get `master` branch so as to find last commit SHA
https://docs.gitlab.com/api/branches/#get-single-repository-branch

Second - we need to create new branch from `master` from previously
received commit SHA https://docs.gitlab.com/api/branches/#create-repository-branch (or we can just provide `master` as branch name)
I presume branch type is just a UX feature, and how we can 
create a branch with name like `release/0.x.x`? 
Also we need to check if branch `release/0.x.x` exists already?

Third - if (release-)branch is created ok, we need to retarget branch 
we work on to (release-)branch. (SEE IN browser console?)

Fourth - merge branch into (release-)branch.
https://docs.gitlab.com/api/merge_requests/#merge-a-merge-request

Fifth - provide a link to create a PR. Where to find this link???

### App arguments

Console run is `mergeapp branch-name project release-version` where

- `branch-name` - task that should be prepared for release
- `project` - project for which task is released
- `release-version` - release version of project

Example run:
`mergeapp task/ER-1301 er 0.121.3`


from task name `task/EPD-100` we can extract project (EPD)
but sometimes we merge same task to different systems, so
we need to provide project name explicitly. And I think 
project name should be required so as we cannot merge task to
another project.




