# Auraplex images

Docker images of [Auraplex](https://github.com/maxwu2579/auraplex), a business platform based on Huly (EPL-2.0).
All images of one release are built from the same commit and carry the same version.

## v4

Built from commit [`875c88cd42`](https://github.com/maxwu2579/auraplex/commit/875c88cd42), version **0.7.426** (footer shows `0.7.426 · v4`).

| Image | Pull |
|---|---|
| front | `docker pull ghcr.io/maxwu2579/auraplex-images:front-v4` |
| server (transactor) | `docker pull ghcr.io/maxwu2579/auraplex-images:server-v4` |
| workspace | `docker pull ghcr.io/maxwu2579/auraplex-images:workspace-v4` |
| account | `docker pull ghcr.io/maxwu2579/auraplex-images:account-v4` |
| collaborator | `docker pull ghcr.io/maxwu2579/auraplex-images:collaborator-v4` |
| preview | `docker pull ghcr.io/maxwu2579/auraplex-images:preview-v4` |
| whatsapp (optional) | `docker pull ghcr.io/maxwu2579/auraplex-images:whatsapp-v4` |
| prospects-recognizer (optional) | `docker pull ghcr.io/maxwu2579/auraplex-images:prospects-recognizer-v4` |
| prospect-mail (optional) | `docker pull ghcr.io/maxwu2579/auraplex-images:prospect-mail-v4` |

Upgrading from v3:
1. Back up the database and storage.
2. Switch all core images (front, server, workspace, account, collaborator, preview) to v4 together and stop the old front.
3. Run `upgrade-workspace <workspace uuid> --force` with the v4 tool/workspace image (the version number is unchanged, so this is not automatic).
4. Check `/config.json`: `"VERSION":"0.7.426"` and `"RELEASE":"v4"`.

The in-app QR scanner needs the site on **https** (browsers only allow the camera there).

## v3

Built from commit [`b067c863c4`](https://github.com/maxwu2579/auraplex/commit/b067c863c461e482945bd8c2c563179bc26378da), version **0.7.426**.

| Image | Pull |
|---|---|
| front | `docker pull ghcr.io/maxwu2579/auraplex-images:front-v3` |
| server (transactor) | `docker pull ghcr.io/maxwu2579/auraplex-images:server-v3` |
| workspace | `docker pull ghcr.io/maxwu2579/auraplex-images:workspace-v3` |
| account | `docker pull ghcr.io/maxwu2579/auraplex-images:account-v3` |
| collaborator | `docker pull ghcr.io/maxwu2579/auraplex-images:collaborator-v3` |
| preview | `docker pull ghcr.io/maxwu2579/auraplex-images:preview-v3` |
| whatsapp (optional) | `docker pull ghcr.io/maxwu2579/auraplex-images:whatsapp-v3` |
| prospects-recognizer (optional) | `docker pull ghcr.io/maxwu2579/auraplex-images:prospects-recognizer-v3` |
| prospect-mail (optional) | `docker pull ghcr.io/maxwu2579/auraplex-images:prospect-mail-v3` |

Deploy all core images (front, server, workspace, account, collaborator, preview) together.
After deploying, `/config.json` must show `"VERSION":"0.7.426"`.
