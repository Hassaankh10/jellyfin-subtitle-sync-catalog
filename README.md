# Subtitle Sync for Jellyfin

Subtitle Sync aligns external SRT subtitles to the first audio track and saves a **Synced** copy alongside the original. The current build targets Jellyfin Server 12.4.

1. In **Dashboard → Plugins → Repositories**, add **Subtitle Sync** with this URL:

   ```text
   https://raw.githubusercontent.com/Hassaankh10/jellyfin-subtitle-sync-catalog/main/manifest.json
   ```
2. Open **Catalog**, install **Subtitle Sync**, and restart Jellyfin.
3. Install ffsubsync 0.5.1 in the environment where Jellyfin runs. Put it on the service's PATH or set the service environment variable `JELLYFIN_FFSUBSYNC` to the executable's absolute path. Restart Jellyfin after changing its environment. The service needs write access to each subtitle directory.
4. Run **Dashboard → Scheduled Tasks → Synchronize external SRT subtitles**. Select the **Synced** track in playback after the next library scan. Add a **Daily** trigger if you want automatic runs.
