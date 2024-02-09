
# GitHub Actions Demo


## Workflow Overview

The `GitHub Actions Demo` workflow is triggered by any `push` event to the repository. It performs a series of echo commands to display information about the event, the runner, and the job. Additionally, it checks out the repository code and lists the files in the repository directory on the runner. This demo is designed to help new users understand how GitHub Actions works and how it can be utilized for CI/CD processes and beyond.

### Key Features Demonstrated

- Triggering workflows on push events.
- Using built-in variables to display event, runner, and repository details.
- Checking out code in GitHub Actions.
- Listing files in the working directory on the runner.

## Setting Up the Demo

To set up this demo in your own GitHub repository, follow these steps:

1. **Fork or Clone This Repository**: Start by forking or cloning this repository to your GitHub account.

2. **Navigate to the Actions Tab**: In your repository on GitHub, navigate to the "Actions" tab and click on "New workflow".

3. **Set Up the Workflow**: Instead of choosing a pre-configured workflow template, select "set up a workflow yourself". Copy and paste the content of the demo workflow from below into the new workflow file.

```yaml
name: GitHub Actions Demo
run-name: ${{ github.actor }} is testing out GitHub Actions 🚀
on: [push]
jobs:
  Explore-GitHub-Actions:
    runs-on: ubuntu-latest
    steps:
      - run: echo "🎉 The job was automatically triggered by a ${{ github.event_name }} event."
      - run: echo "🐧 This job is now running on a ${{ runner.os }} server hosted by GitHub!"
      - run: echo "🔎 The name of your branch is ${{ github.ref }} and your repository is ${{ github.repository }}."
      - name: Check out repository code
        uses: actions/checkout@v4
      - run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
      - run: echo "🖥️ The workflow is now ready to test your code on the runner."
      - name: List files in the repository
        run: |
          ls ${{ github.workspace }}
      - run: echo "🍏 This job's status is ${{ job.status }}."
```

1. Commit the Workflow File: Save the workflow file in the .github/workflows directory of your repository. Name it something like demo_workflow.yml.

2. Trigger the Workflow: Make a change in your repository and push it to GitHub. This push event will trigger the workflow.

### Observing the Workflow in Action
After pushing your changes, you can see the workflow in action by:

* Going to the "Actions" tab of your GitHub repository.
* Clicking on the latest run of the "GitHub Actions Demo" workflow.
* Observing the output of each step in the job.

This demo provides a foundational understanding of how GitHub Actions operates, offering insights into the potential applications of this powerful CI/CD tool.

### Conclusion
GitHub Actions offers a versatile platform for automating workflows, running tests, and deploying applications. This demo is just the beginning of what you can achieve with GitHub Actions in your development projects. Explore further to discover how GitHub Actions can streamline your CI/CD pipelines and automate your workflows.
