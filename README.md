# What is this repo about?😆

BY @Mariodevs
This is a telegram bot writen in python for mirroring files on the internet to our beloved Google Drive.

# Inspiration 
This project is heavily inspired from @out386 's telegram bot which is written in JS.

# Features supported:
- Mirroring direct download links to google drive
- Download progress
- Upload progress
- Download/upload speeds and ETAs
- Docker support
- Uploading To Team Drives.
- Index Link support
- Service account support
- Mirror all youtube-dl supported links
- Mirror telegram files


# How to deploy in Heroku?
Hit the deploy to heroku button and follow the further instructions in the screen:

**NB: Usage of Aria2 may leads to the suspension of your heroku account so deploy at your own risk.**
heroku

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?)


 

## Getting Google OAuth API credential or SECRET_JSON

- Visit the [Google Cloud Console](https://console.developers.google.com/apis/credentials)
- Go to the OAuth Consent tab, fill it, and save.
- Go to the Credentials tab and click Create Credentials -> OAuth Client ID
- Choose Other and Create.
- Visit [Google API page](https://console.developers.google.com/apis/library)
- Search for Drive and enable it if it is disabled
- Finally, run the script to generate SECRET_JSON for Google Drive

```
pip install oauth2client
```
```
python3 generate_drive_token.py
```
OR use online terminal

[![Run](https://img.shields.io/badge/Run%20Online-Red)](https://gdrive-auth.cw4rr10r.repl.run)

**Termux:**

``` pkg install python wget ```

``` wget https://raw.githubusercontent.com/CW4RR10R/python-aria-mirror-bot/master/generate_drive_token.py ```

``` pip install oauth2client ```

``` python3 generate_drive_token.py ```
___

NB: Usage of Aria2 may leads to the suspension of your heroku account so deploy at your own risk. Steps: API_HASH: https://my.telegram.org API_ID: https://my.telegram.org AUTH_CHATS: @MissRose_bot BOT_TOKEN: @BotFather Google Drive: https://www.google.com/drive/ INDEX_URL: https://github.com/maple3142/GDIndex/ Cloud Flare : cloudflare.com OAuth API credential: https://console.cloud.google.com SECRET_JSON : https://gdrive-auth.cw4rr10r.repl.run/ SESSION_STRING: https://gen-session.cw4rr10r.repl.run/ Note: You can limit maximum concurrent downloads by changing the value of MAX_CONCURRENT_DOWNLOADS in aria.sh. By default, it's set to 2




Fill up rest of the fields in app.json. Meaning of each fields are discussed below:
- **BOT_TOKEN** : The telegram bot token that you get from @BotFather
- **GDRIVE_FOLDER_ID** : This is the folder ID of the Google Drive Folder to which you want to upload all the mirrors.
- **DOWNLOAD_DIR** : The path to the local folder where the downloads should be downloaded to
- **DOWNLOAD_STATUS_UPDATE_INTERVAL** : A short interval of time in seconds after which the Mirror progress message is updated. (I recommend to keep it 5 seconds at least)  
- **OWNER_ID** : The Telegram user ID (not username) of the owner of the bot
- **AUTO_DELETE_MESSAGE_DURATION** : Interval of time (in seconds), after which the bot deletes it's message (and command message) which is expected to be viewed instantly. Note: Set to -1 to never automatically delete messages
- **IS_TEAM_DRIVE** : (Optional field) Set to "True" if GDRIVE_FOLDER_ID is from a Team Drive else False or Leave it empty.
- **USE_SERVICE_ACCOUNTS**: (Optional field) (Leave empty if unsure) Whether to use service accounts or not. For this to work see  "Using service accounts" section below.
- **INDEX_URL** : (Optional field) Refer to https://github.com/maple3142/GDIndex/ The URL should not have any trailing '/'
- **API_ID** : This is to authenticate to your telegram account for downloading Telegram files. You can get this from https://my.telegram.org DO NOT put this in quotes.
- **API_HASH** : This is to authenticate to your telegram account for downloading Telegram files. You can get this from https://my.telegram.org
- **SESSION_STRING** : Session string generated by running:

```
pip install pyrogram tgcrypto
```
```
python3 generate_string_session.py
```
OR use online terminal

[![Run](https://img.shields.io/badge/Run%20Online-Red)](https://test.Starkgang.repl.run)

**Termux:**

``` pkg install python wget ``` (if not installed earlier)

``` wget https://raw.githubusercontent.com/CW4RR10R/python-aria-mirror-bot/master/generate_string_session.py ```

``` pip install pyrogram tgcrypto ```

``` python3 generate_string_session.py ```

___

Note: You can limit maximum concurrent downloads by changing the value of MAX_CONCURRENT_DOWNLOADS in aria.sh. By default, it's set to 2
 


# Youtube-dl authentication using .netrc file
For using your premium accounts in youtube-dl, edit the netrc file (in the root directory of this repository) according to following format:
```
machine host login username password my_youtube_password
```
where host is the name of extractor (eg. youtube, twitch). Multiple accounts of different hosts can be added each separated by a new line
