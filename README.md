# Navidrome Migration Script

Normally, if you change the path to your music library, you will lose all of your ratings and play metadata (play counts, last played, etc).
This is because Navidrome sees new paths to your music, and will remove the old ones.
The purpose of this script is to update the paths in Navidrome so you can keep your metadata if you have to move your music library.

## What it does

To make Navidrome recognize your new library, you have to make your media files consistent.
This requires two things:

1. The media files should point to the new path
2. The ID of your the file should be md5sum(new path)

## How to use this script

Usage:

1. Stop Navidrome.
1. Make note of the original path to your music library.
   This is the `MusicFolder` (navidrome.toml) or `ND_MUSICFOLDER` (environment variable) property
1. Run the migration script: `python migrate.py PATH_TO_ORIGINAL_DB ORIGINAL_MUSIC_FOLDER PATH_TO_NEW_DB NEW_MUSIC_FOLDER`.
1. Change the `MusicFolder`/`ND_MUSICFOLDER` variable to point to the new location of your library.
1. Start Navidrome.
