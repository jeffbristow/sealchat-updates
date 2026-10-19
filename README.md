# sealchat-updates

Where **Seal Chat** and **Seal Chat Web** get their updates.

Seal Chat (1.7.0+) and Seal Chat Web (1.2.0+) get their updates only from here: they read [`update.json`](update.json) (this works through Tor), then download the files from this repository's version folder (for example [`v1.8.2/`](v1.8.2)).

## Is this safe?

Every file has a `.sig` signature next to it, made with Seal Chat's private key. That key is kept offline and never stored here. The apps refuse any file whose signature or checksum is wrong. So this repository can make an update unavailable, but it can't change what gets installed.

## What's here

| File | What it is |
| --- | --- |
| `update.json` | The newest version and where to download it. It has the same format as the website's `update.php`. |
| `v<version>/` | `SealChat-<version>.sealchat` (the app update, for Windows, macOS and Linux), `SealChat-Web-<version>.zip` (Seal Chat Web), and a `.sig` for each. |

## Publishing a release (maintainer)

1. Save the new version, links and checksums in the website's `admin.php`.
2. In `admin.php`, go to **GitHub updates** and click **Download update.json**.
3. Here, add a folder `v<version>` with the four files and replace `update.json`. You can use **Add file → Upload files** (25 MB per file), or run `build/publish-mirror.sh update.json <the four files>` from the Seal Chat source.
