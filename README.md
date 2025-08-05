# merge-deploy-action-demo
Be able to fast forward merge without a pull request in the GitHub GUI.


A solution to [How to merge branches on github.com without doing pull request?](https://stackoverflow.com/questions/24276409/how-to-merge-branches-on-github-com-without-doing-pull-request) using `actions/github-script@v5`, see [here for action](https://github.com/JEFuller/merge-deploy-action-demo/blob/26df2e798b74782bcb1be586024cdcdd984b2440/.github/workflows/update-other.yml#L7-L19).

Trigger it manually via the [action's page](https://github.com/JEFuller/merge-deploy-action-demo/actions/workflows/update-other.yml):

<img width="878" height="423" alt="Screen Shot 2025-08-05 at 11 36 40" src="https://github.com/user-attachments/assets/c635a35b-2158-4ffa-b689-91b2e5927ffe" />

---

Note: if you have e.g. a [`deploy.yml`](https://github.com/JEFuller/merge-deploy-action-demo/blob/26df2e798b74782bcb1be586024cdcdd984b2440/.github/workflows/deploy.yml) with an `on: push` it will not be trigged (since `updateRef` isn't technically a `push`).


But that can be triggered automaticall using `actions/github-script@v5`, see [here](https://github.com/JEFuller/merge-deploy-action-demo/blob/26df2e798b74782bcb1be586024cdcdd984b2440/.github/workflows/update-other.yml#L21-L32).

Note: the deploy workflow will need to be updated to `on: [push, workflow_dispatch]`:

<img width="513" height="231" alt="Screen Shot 2025-08-05 at 11 38 28" src="https://github.com/user-attachments/assets/020ec622-4fc5-4bb2-b493-400bc585b23c" />
