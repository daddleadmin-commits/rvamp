# Rvamp / Daddle project instructions

## Repository and domain ownership

| Site | GitHub repository | Intended live domain |
| --- | --- | --- |
| Rvamp holding page | `daddleadmin-commits/rvamp` | `rvamp.me` |
| Fictional The Bird Pub demo | `daddleadmin-commits/rvamp-sub` | `thebird.rvamp.me` |

- Use a separate Vercel project for each repository, under the `daddle` team.
- Verify the current Git remote, Vercel team/project, linked repository, branch, and target domain before pushing or deploying. Do not infer ownership from a Hello World page, a folder name, or previous chat claims.
- These mappings are the intended configuration. Inspect Vercel before claiming the projects, domains, or release gates are configured.
- Keep this project separate from WSN / Sanseart and other repositories.

## Development and release workflow

- Follow: local work → GitHub feature branch → Vercel preview/staging → review → explicitly approved live release.
- Use `codex/` as the prefix for new working branches. Commit and push completed work to the correct repository so it is preserved in Git.
- Routine work belongs on feature branches and preview/staging deployments. Verify checks and review the preview before a live release.
- Keep a stable staging URL for each site when configuring the deployment workflow; Vercel preview URLs are sufficient until staging is configured.
- Treat merges or pushes to the production branch as potential live deployments. Do not merge to that branch, deploy to production, or promote a deployment without explicit user authorization for the release.
- Do not assume staging or release protection exists. Verify the actual Vercel/Git configuration before relying on it.

## Domains and email

- The domain is `rvamp.me`, not `revamp.me`.
- Keep the existing nameservers and registrar DNS hosting. Preserve the current email forwarding and all mail-related DNS records.
- Configure only the web records required for the intended Vercel projects, using the exact values Vercel provides. Inspect existing records before changing them.

## Content and indexing

- The Rvamp holding page should use the user's logo and simple “Coming soon” copy. Logo reference: https://www.figma.com/design/WnNAZ3Ss3MpWh53SUA4a6Q/BRAND?node-id=2503-86
- Keep the pub demo fictional: use The Bird Pub name and our own bird logo. Do not use The Hawke's photos.
- The Hawke's menu may be used as demo input when showing the demo to him.
- Keep the pub demo and all preview/staging deployments out of search results using a robots meta `noindex`, an `X-Robots-Tag` response header, and `robots.txt` with `Disallow: /`. These are indexing controls, not access protection.
- Preserve the existing indexing controls on the holding page unless the user requests a change.
