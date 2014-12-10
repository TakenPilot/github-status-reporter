Github Status Reporter
======================

Updates build status on Github from a script.

##Install

```bash
npm install -g github-status-reporter
```

##Usage

```bash
export GITHUB_TOKEN=<github_token>
github-status-reporter --user <repo_user> --repo <repo_name> --branch <branch_name> --state <failure|pending|success>
```

###Example

To update github.com/TakenPilot/github-status-reporter to a success state

```bash
export GITHUB_TOKEN=ABCDEFGHIJKLMNOPQRSTUVWXYZ
github-status-reporter --user TakenPilot --repo github-status-reporter --branch master --state success
```


###Example 2

To update github.com/TakenPilot/github-status-reporter to a pending state with extra message

```bash
export GITHUB_TOKEN=ABCDEFGHIJKLMNOPQRSTUVWXYZ
github-status-reporter --user TakenPilot --repo github-status-reporter --branch master --state success /
  --target-url='http://github.com/TakenPilot/github-status-reporter' --description='Waiting for unit tests'
```

##API

###Token

Security Token of account that can access the repo and has enough permissions to change its status.  Can be set as an environment variable as `GITHUB_TOKEN`.

`github-status-reporter --token ABCDE ...`

###User

The user or organisation of the repo, so `johnsmith/some-repo` would be.  Can be set as an environment variable as GITHUB_USER.

`github-status-reporter --user johnsmith --repo some-repo ...`

###Repo

The repo to update

`github-status-reporter --repo repo-name ...`

###Sha

Either sha or branch are required to identify the commit to set the status of.  If sha is not 40 characters, it's assumed to be a branch name.  Can be set as an environment variable as GITHUB_SHA.

`github-status-reporter --sha 4eb9e0fd807f95473dc7207c556014215c40ec3b ...`

`github-status-reporter --sha master ...`

###Branch

Either Sha or Branch are required to identify the commit to set the status of.  Can be set as an environment variable as GITHUB_BRANCH.

`github-status-reporter --branch master ...`

###State

The state to set the build status to, i.e., pending, success, failure, etc.  Can be set as an environment variable as GITHUB_STATE.

`github-status-reporter --state success ...`

###Description

Optional message along with the status.

`github-status-reporter --description 'tests failed' ...`

###Target-Url

Optional link for when someone clicks on the build status.

`github-status-reporter --target-url 'jenkins.example.com/build/1524' ...`


