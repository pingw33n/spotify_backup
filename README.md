# Spotify Backup

This is a tool that backs up public Spotify playlists into GitHub repository using GitHub Actions for automation. 
The playlists are written in CSV format and stored normally as a text file in Git repository, so there's full history
of changes. You can find live example here: https://github.com/pingw33n/spotify_backup_data/tree/main/data/playlists

## How to use

1. You need to have Spotify App created. Any app will work, no extra authorization is required. 

   To create Spotify App go to https://developer.spotify.com/dashboard/applications, log in with your Spotify account.
   Click "CREATE AN APP", name it as you like (e.g. "Backup"). On the app's page there's Client ID and Client Secret
   that needs to be used later.
2. Fork [this](https://github.com/pingw33n/spotify_backup) repository by clicking "Fork".
3. Go to repository "Settings" -> "Secrets". Add `CLIENT_ID`, `CLIENT_SECRET` (from Spotify App) and `USER_ID` (Spotify
   username) by clicking "New repository secret". You can find Spotify username in the account page 
   https://www.spotify.com/us/account/overview/.
4. Go to repository "Actions" tab, enable workflows by clicking the green button. GitHub requires each workflow to be 
   enabled explicitly, click "Spotify Backup" on the left and click "Enable workflow". The yellow exclamation icon 
   should change into normal workflow icon.

Now the backup job should be scheduled to run at the beginning of each hour. For some reason it may take more than 
an hour for the first run. Each run will appear on the "Actions" tab and you will get email notification for failed
runs (which sometimes happens due to transient issues on GitHub side).
