# Pivotal Developer Console

## Where is the book repo?
https://github.com/pivotal-cf/docs-book-developer-console

The book repo uses these branches:

* **master** builds from the **master** content branch in this repo.
Pipeline [here](https://concourse.run.pivotal.io/teams/cf-docs/pipelines/cf-services-edge?group=developer-console-edge).

[//]: # "* **Master** builds from the published content branches in this repo. Pipeline [here](https://concourse.run.pivotal.io/teams/cf-docs/pipelines/cf-services?group=developer-console)."

## Branches in this (content) repo

All documentation for the next unreleased version of Developer Console is in `master`.

Always make changes you want carried forward in the master branch. This includes:

* Unreleased features
* Doc bug fixes
* Doc reorganization or enhancement

| Branch Name| Use for… |
|------------| ---------|
| master     | v0.1 (staged here: http://docs.pivotal.io/developer-console/0-1/ and staged here: http://docs-pcf-staging.cfapps.io/developer-console/0-n/|


[//]: # "1. Always cherry-pick any changes to live branches into **master** if you want those changes carried forward.
2. If necessary, immediately cherry-pick/copy changes from **master** that you want to push immediately to production into the appropriate live branch above."

### Style Sheet

We need to decide on product name short forms:

| Term or product name | Notes |
|----------------------|-------|
|Pivotal Developer Console | `product_full`, the longest name |
|Developer Console     | `product_short`, the short name, use on the page after the long name has been used |
|PDC                   | `product_abbr`, use only where really necessary |
|PDC CLI tool          | Name of the CLI tool, use instead of "`pdc` CLI tool"|

## Pipelines

[//]: # "**Edge Pipeline**<br>
The `master` branch builds to the <br> <strong>cf-services-edge > developer-console-edge</strong> pipeline, and does not go to production until release time: [Edge pipeline](https://concourse.run.pivotal.io/teams/cf-docs/pipelines/cf-services-edge?group=developer-console-edge). <br>"

**Production Pipeline**<br>
All live branches build to the <strong>cf-services > developer-console</strong> pipeline,
and are manually pushed to production as needed: [Production pipeline](https://concourse.run.pivotal.io/teams/cf-docs/pipelines/cf-services?group=developer-console).

## How to Cherry-Pick from one Branch to Another
1. Make changes in the first branch (usually `master`), commit them, and then push them to the repo.
2. Copy part of the SHA for the above commit. To find this, you can do a `git log`, or look at the list of commits in the github repo.
3. Checkout the second branch, where you want to copy the changes you made in the first branch.
4. Run this command, using the SHA snippet you copied above:
    `git cherry-pick <SHA_SNIPPET>`<br><br>
    For example: `git cherry-pick 5dc22fe00`

    Do the cherry-pick immediately to lessen the chances of conflicts.
    Otherwise, you may need to resolve conflicts in order to complete the cherry-pick.

5. Do a `git push` after the cherry-pick is complete.<br><br>
