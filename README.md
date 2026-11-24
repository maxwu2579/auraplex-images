# Auraplex images

Docker images of [Auraplex](https://github.com/maxwu2579/auraplex), a business platform based on Huly (EPL-2.0).
All images of one release are built from the same commit and carry the same version.

## v5

Built from commit [`d893468afd`](https://github.com/maxwu2579/auraplex/commit/d893468afd), version **0.7.426** (footer shows `0.7.426 · v5`).

> **Update 2026-11-24:** `front-v5` was rebuilt from commit [`5dbf1d68a`](https://github.com/maxwu2579/auraplex/commit/5dbf1d68a) with phone display fixes. Only the front image changed; the other 14 images are the same and no extra workspace upgrade is needed.

| Image | Pull |
|---|---|
| front | `docker pull ghcr.io/maxwu2579/auraplex-images:front-v5` |
| server (transactor) | `docker pull ghcr.io/maxwu2579/auraplex-images:server-v5` |
| workspace | `docker pull ghcr.io/maxwu2579/auraplex-images:workspace-v5` |
| account | `docker pull ghcr.io/maxwu2579/auraplex-images:account-v5` |
| collaborator | `docker pull ghcr.io/maxwu2579/auraplex-images:collaborator-v5` |
| preview | `docker pull ghcr.io/maxwu2579/auraplex-images:preview-v5` |
| datalake (file service) | `docker pull ghcr.io/maxwu2579/auraplex-images:datalake-v5` |
| process (card automation) | `docker pull ghcr.io/maxwu2579/auraplex-images:process-v5` |
| fulltext (search) | `docker pull ghcr.io/maxwu2579/auraplex-images:fulltext-v5` |
| link-preview | `docker pull ghcr.io/maxwu2579/auraplex-images:link-preview-v5` |
| print | `docker pull ghcr.io/maxwu2579/auraplex-images:print-v5` |
| love (Office meetings) | `docker pull ghcr.io/maxwu2579/auraplex-images:love-v5` |
| whatsapp (WAHA or Meta API) | `docker pull ghcr.io/maxwu2579/auraplex-images:whatsapp-v5` |
| prospects-recognizer (optional) | `docker pull ghcr.io/maxwu2579/auraplex-images:prospects-recognizer-v5` |
| prospect-mail (optional) | `docker pull ghcr.io/maxwu2579/auraplex-images:prospect-mail-v5` |

Upgrading from v4:
1. Back up the database and storage.
2. Switch **all** images above to v5 together (including the ones new since v4: datalake, process, fulltext, link-preview, print, love) and stop the old front.
3. Run `upgrade-workspace <workspace uuid> --force` with the v5 tool/workspace image.
4. Check `/config.json`: `"VERSION":"0.7.426"` and `"RELEASE":"v5"`.

WhatsApp with WAHA: use `whatsapp-v5` and enter the WAHA URL and administrator key in the app (Settings → Integrations → **Service settings**, keys are write-only). Also set `WHATSAPP_WAHA_ALLOWED_ORIGINS`, `PROSPECTS_AI_ALLOWED_ORIGINS` (on the whatsapp service), `WHATSAPP_WAHA_WEBHOOK_URL`, and `SERVER_SECRET` for prospects-recognizer. WAHA: `devlikeapro/waha` 2026.6.1+ (`:chrome` to receive videos), engine WEBJS. Full notes: v5 release notes.

Keep object storage (MinIO / S3 / hulylake) and WAHA internal only.

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
