# Note:

There are two deprecation notices for this workflow.  Resolution is in progress.

https://github.blog/changelog/2022-10-11-github-actions-deprecating-save-state-and-set-output-commands/

https://github.blog/changelog/2022-09-22-github-actions-all-actions-will-begin-running-on-node16-instead-of-node12/

# logs

This is a  GitHub Action that will capture an Organization's audit logs and store them in the repository where the Action is running.  The schedule is "Daily at 8am".  If you increase to multiple times a day, you will need to modify the written audit log filename to be more fine grained.

The solution requires the `logcapture.yml` file to be located in `.github/workflows/` folder and the following four secrets created:

`PAT_TOKEN` - the Personal Access Token used to connect to the Org.  It only requires the security scope "read:org".

`ORG_NAME` - the name of the Organization to run the action against.

`USERNAME` - the username used during a commit of the newly created log.  I suggest you reference the username where the PAT exists.

`EMAIL` - the email address used during a commit of the newly created log.

For me, this is an interim solution until GitHub Log Streaming becomes generally available.

GitHub Actions (and its GITHUB_TOKEN secret) requires read/write access to the repo.
