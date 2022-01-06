# logs

This is a  GitHub Action that will capture an Organization's audit logs and store them in the repository where the Action is running.  The schedule is "Daily at 8am".  If you increase to multiple times a day, you will need to modify the written audit log filename to be more fine grained.

The solution requires the `logcapture.yml` file to be located in `.github/workflows/` folder and the following four secrets created:

`PAT_TOKEN` - the Personal Access Token used to connect to the Org.  It requires the security scopes "repo" and "read:org".

`ORG` - the name of the Organization to run the action against.

`USERNAME` - the username used during a commit of the newly created log.  I suggest you reference the username where the PAT exists.

`EMAIL` - the email address used during a commit of the newly created log.
