# Module 11 mentor demonstration

1. Start Jenkins with the commands in [`../jenkins/README.md`](../jenkins/README.md) and open `http://localhost:8080`.
2. Show the `module11-ui-tests` and `module11-api-tests` jobs created by the startup script.
3. Open each job configuration and show its Git checkout of `rusikmihajlan/module11`, the matching `Jenkinsfile`, and the pipeline trigger `H */2 * * *`.
4. Click **Build Now** once for each job, then show the checkout, `npm ci`, and test command in Console Output.
5. Show each job's two-hour schedule and the completed build results.

The UI job runs headless Chromium; the API job runs the booking API lifecycle tests. Jenkins keeps the two suites in independent jobs.
