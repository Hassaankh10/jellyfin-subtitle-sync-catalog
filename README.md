# Subtitle Sync for Jellyfin

Subtitle Sync aligns external SRT subtitles to the first audio track and saves a **Synced** copy alongside the original. The current build targets Jellyfin Server 12.4.

1. In **Dashboard → Plugins → Repositories**, add **Subtitle Sync** using this URL:

   ```text
   https://raw.githubusercontent.com/Hassaankh10/jellyfin-subtitle-sync-catalog/main/manifest.json
   ```
2. Open **Catalog**, install **Subtitle Sync**, and restart Jellyfin. If Subtitle Sync is already installed, run **Update Plugins** before restarting.
3. Open **Dashboard → Plugins → Subtitle Sync**. Check the engine and select your libraries under **Settings**, then click **Run now**. **Overview** shows live progress, and **Libraries** shows the results by library.
4. Select the **Synced** track after the library picks it up. Add a **Daily** trigger in **Scheduled Tasks** to run automatically.

Version 0.2.0 bundles ffsubsync for standard glibc-based Linux on x86-64 and ARM64. Keep the Jellyfin config volume when recreating the Docker container. If you previously set `JELLYFIN_FFSUBSYNC` to a location that disappears when the container is replaced, remove the override from the container configuration to use the bundle.

Other platforms can use ffsubsync from the service's PATH or `JELLYFIN_FFSUBSYNC`. Jellyfin needs write access to the subtitle directories.
