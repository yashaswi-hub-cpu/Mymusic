# My Music

A private, offline music player for Android. Plays only the files on your phone.

## What it does

- Plays only music you add from your phone. The app has no internet permission, so it cannot connect to YouTube, artists, or anything else.
- Make your own folders (named whatever you like) and add songs to them from your Downloads.
- Remembers the last folder, song and second you were on, and shows it paused when you reopen the app.
- Keeps playing with the screen off and while you use other apps (foreground media service, notification controls, lock screen controls, headphone buttons).
- Plays the original file as-is, with no re-encoding or effects.
- Background: choose a photo from your gallery, or pick a theme pack (Midnight, Sunset, Forest, Ocean, Rose, Paper).
- Release build is shrunk and optimized with R8.

## Build the APK with GitHub (no computer needed)

1. Create a new GitHub repository (private is fine) and upload all files from this folder, keeping the structure. The `.github/workflows/build.yml` file must be included.
2. Open the **Actions** tab. The **Build APK** workflow runs on every push (or press **Run workflow**).
3. When it finishes (about 5 to 8 minutes the first time), open the run and download the **MyMusic-apk** artifact. Unzip it to get `app-release.apk`.
4. Install it on your phone. Allow "install unknown apps" for your browser or file manager when asked.

## Using it

1. Open the app, tap the folder+ button, name a folder.
2. Open the folder, tap +, and pick songs. The picker opens at Downloads.
3. Tap a song to play.
4. Tap the palette button to change theme or set a gallery photo as the background.

## Code map

- `Store.kt` : saves folders, last played, theme and background on the phone.
- `PlaybackService.kt` : the background player (Media3 ExoPlayer).
- `MainActivity.kt` : connects the screen to the player.
- `Ui.kt` : all screens, theme packs, and the player bar.
