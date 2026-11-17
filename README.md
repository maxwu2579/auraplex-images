# Auraplex images

Docker images of [Auraplex](https://github.com/maxwu2579/auraplex), a business platform based on Huly (EPL-2.0).
All images of one release are built from the same commit and carry the same version.

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
