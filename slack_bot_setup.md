* go to https://api.slack.com/apps
* Click 'Create New App'
* Select 'From an app manifest'
* Choose the workspace to create the app in
* paste the following manifest in:

```yaml
_metadata:
  major_version: 1
  minor_version: 1
display_information:
  name: Deploy Bot
  description: Post deployment notifications
  background_color: "#336699"
features:
  bot_user:
    display_name: Deploy Bot
    always_online: true
  app_home:
    home_tab_enabled: false
    messages_tab_enabled: false
oauth_config:
  scopes:
    bot:
      - chat:write
      - chat:write.public
```

* Click 'Create'
* Click 'Install to Workspace'
* Scroll down and choose an icon for the bot
* Go to 'OAuth & Permissions' and copy the 'Bot User OAuth Token'
* Add it to Github secrets under 'DEPLOY_BOT_SLACK_TOKEN'
* Right click on the channel you want to post to and click 'Copy Link'. Store
  the last part of this under 'DEPLOY_BOT_SLACK_CHANNEL'.
