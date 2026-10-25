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
- The unintended production deployment was deleted, the project was resumed, and the production deployment list was verified empty.
- Working staging URL: https://rvamp-staging-daddle.vercel.app/ . It points to Preview deployment `dpl_EuK2GMapgHcbpT8ZckE3k38DkuFh`, built from commit `b8f9dbaa756324a7e725335e3d16b4e62ff19703` on `codex/rvamp-holding-page`.
- The staging URL requires Vercel authentication. The authenticated page returned HTTP 200, its robots meta and `X-Robots-Tag` both specify `noindex, nofollow`, `robots.txt` disallows all crawling, and the hosted logo matches the local Figma export byte for byte.
- GitHub integration is not linked to the `rvamp` Vercel project yet. The current Preview was deployed with the authenticated CLI from the committed feature branch. Git pushes alone do not currently deploy this project.
- `rvamp.me` is not attached to this project, and no apex DNS record was added. The Spaceship nameservers, email records, and existing `thebird` CNAME were not changed.

## Repeatable preview deployment

Commit and push the feature branch to this repository first. Inspect the explicit project, then deploy to Preview:

```sh
npx --yes vercel@65.2.0 project inspect rvamp --scope daddle --non-interactive
npx --yes vercel@65.2.0 deploy --project prj_Qv8m1YZlM09Z9Q8yvwFCiNxLuHiX --scope daddle --environment preview --non-interactive --yes --json
```

After confirming the new deployment is ready and is a Preview, update the `rvamp-staging-daddle.vercel.app` alias to it. Use `vercel curl` with the exact deployment or staging URL for authenticated verification; an HTTP 200 from a login page is not verification of the site.

The CLI's `--environment preview` is explicit. For the separate Vercel API tool, use `target: "staging"`; it rejects `"preview"` and omitting the target previously created a production deployment. Do not merge to `main`, promote to production, or attach the live domain without explicit user approval.
