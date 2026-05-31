# Azure Test Lab Notes

This fork is part of the Azure Test Lab incident-generation portfolio as the normal application baseline. It gives demos a quiet comparison point for build, deployment, request, and app telemetry before intentionally noisy vulnerable-app or atomic scenarios are introduced.

## Current Lab Workflow

The `Azure Test Lab Baseline Smoke` workflow is manual only. It performs a local GitHub Actions validation loop:

1. Restore and build the .NET application.
2. Publish the web app to a local artifact folder.
3. Run the app bound to `127.0.0.1` on the GitHub-hosted runner.
4. Send benign requests to `/` and `/Home/Privacy`.
5. Upload a smoke report, captured responses, and app log.

The workflow does not deploy to Azure, expose a public endpoint, or mutate lab resources.

## Next Implementation Steps

- Use this app as the baseline path for normal CI/CD and request telemetry.
- Add Azure deployment only after the lab access pattern and telemetry destination are agreed.
- Keep scripted requests boring and repeatable so they can be compared with Juice Shop and Atomic Red Team signals.
- Record workflow run IDs and telemetry observations in the control-plane lab documentation.