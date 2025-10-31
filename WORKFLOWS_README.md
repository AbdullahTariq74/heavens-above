# Workflows for heavens-above (assignment submission)

Included workflows:
- .github/workflows/ci.yml
- .github/workflows/deploy-vercel.yml
- .github/workflows/scheduled-tasks.yml
- .github/workflows/dependency-updates.yml
- .github/workflows/code-review.yml
- .github/workflows/documentation.yml
- .github/workflows/custom-workflow.yml
- .github/dependabot.yml

Short summary:
- CI: installs deps, runs lint/tests, uploads artifacts.
- Deploy (Vercel): builds and runs `npx vercel --prod` using repo secret VERCEL_TOKEN.
- Scheduled tasks: runs `node run.js` daily and commits changes if any.
- Dependency updates: Dependabot configured daily; PRs tested by workflow.
- Code review: CodeQL, lint, tests on PRs.
- Documentation: deploys docs/ to GitHub Pages (if present).
- Custom: auto-generate simple release notes on creation.

Secrets required:
- VERCEL_TOKEN (for Vercel deploy) — add in GitHub repo settings → Secrets → Actions.

How to view results:
- GitHub → Actions → choose workflow → open run → expand steps for logs.
- Artifacts available at the top-right of run details as "Artifacts".
- Code scanning results viewable at Security → Code scanning alerts.
