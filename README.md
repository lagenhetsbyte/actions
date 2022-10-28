# Github actions
This is a collection of shared actions.

## slackmsg
Sends message to slack, used for changelogs.

Example usage from BytesansokanApi, Note that we change channelId based on if the project is connected to Bytesansökan or Lägenhetsbyte.
channels saved in organization secrets,
BA: SLACK_BA_CHANGELOG_CHANNEL_ID
LB: SLACK_LB_CHANGELOG_CHANNEL_ID
```
name: Write to changelog channel

on: 
  push:
    branches:
      - master

jobs:
  call-slack-workflow:
    uses: lagenhetsbyte/actions/.github/workflows/slackmsg.yml@master
    secrets:
      channelId: ${{ secrets.SLACK_BA_CHANGELOG_CHANNEL_ID }}
      slackToken: ${{ secrets.SLACK_GITHUB_ACTIONS_TOKEN }}
```
