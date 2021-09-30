### Github Actions
GitHub Actions are event-driven, meaning that you can run a series of commands after a specified event has occurred. For example, every time someone creates a pull request for a repository, you can automatically run a command that executes a software testing script.

GitHub Actions uses YAML syntax to define the events, jobs, and steps. These YAML files are stored in your code repository, in a directory called .github/workflows.

#### The components of GitHub Actions

* Workflows - The workflow is an automated procedure that you add to your repository.The workflow can be used to build, test, package, release, or deploy a project on GitHub.

* Jobs - A job is a set of steps that execute on the same runner. By default, a workflow with multiple jobs will run those jobs in parallel. You can also configure a workflow to run jobs sequentially (e.g. lint -> build -> test)

* Steps - A step is an individual task that can run commands in a job.

* Events - An event is a specific activity that triggers a workflow ( e.g. PR)

```
# example of workflow in learn-github-actions.yml

name: learn-github-actions
on: [push]
jobs:
  check-bats-version:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v2
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```