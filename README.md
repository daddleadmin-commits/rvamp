# Rvamp holding page

Static coming-soon page for `rvamp.me`, using the original logo exported from the supplied Figma brand file. The pub demo belongs in the separate `rvamp-sub` repository and Vercel project.

## Local preview

Run from this repository:

```sh
python3 -m http.server 4173 --bind 127.0.0.1
```

Open http://127.0.0.1:4173/. No dependencies or build command are required.

## Deployment status — 25 October 2026

- The user explicitly chose to keep this change as a preview. PR #1 remains open: https://github.com/daddleadmin-commits/rvamp/pull/1
- The default branch `main` has not been merged or changed for this holding-page release.
- Vercel project: `rvamp`, ID `prj_Qv8m1YZlM09Z9Q8yvwFCiNxLuHiX`, under the `daddle` team.
- This Vercel project is paused. Its default domain was checked and returns HTTP 503 with `DEPLOYMENT_PAUSED`.
- One initial source-file deployment (`dpl_FHom2Lw7oQGmoQB9hFnAuXAzSZgm`) unexpectedly received target `production` when the deployment API target was omitted. It is blocked from serving by the project pause. Cancellation was attempted after it had finished and was not available.
- A subsequent deployment with explicit target `staging` (`dpl_4DWm2UP1f9wuT7p2qqrcjvgcR8G6`) was blocked because the project is paused. There is no working hosted preview yet; use the local preview.
- GitHub integration is not linked to the `rvamp` Vercel project. The attempted API Git connection failed because a GitHub integration is required. Deployment source files came from the committed feature branch, with its Git metadata recorded in Vercel.
- `rvamp.me` is not attached to this project, and no apex DNS record was added. The Spaceship nameservers, email records, and existing `thebird` CNAME were not changed.

Before enabling hosted previews, resolve the initial production deployment and Git integration. Do not unpause the project or attach the live domain without checking its production state and obtaining the user's live-release approval. Use explicit `target: "staging"` for Vercel API previews; never omit the target.
