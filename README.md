Slack Invite Page
------------

A tiny web app to add open inviting to your Slack team, inspired by [this](https://levels.io/slack-typeform-auto-invite-sign-ups/) and [this](http://socket.io/slack/).

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

## Setting
Populate `config.js` with your information, or better yet, set ENV vars

* `community`: your community or team name to display on join page.
* `slackUrl` : your slack team url (ex: socketio.slack.com)
* `slacktoken` : access token of slack.
  You can generate it in <https://api.slack.com/web#auth>.
  **Generate the token as admin user, not owner.**
  If you generate the token in owner user, `missing_scope` error will occurr.
* `inviteToken`: an optional security measure - if it is set, then that token will be required to get invited.
  Intended to be provided in person, on a whiteboard, etc.

  You can test your token via curl:

  ```shell
   curl -X POST 'https://YOUR-SLACK-TEAM.slack.com/api/users.admin.invite' \
   --data 'email=EMAIL&token=TOKEN&set_active=true' \
   --compressed
  ```

## Run
[Node.js](http://nodejs.org/) is unfortunately required.

```shell
$ git clone git@github.com:bayareadads/slack-join-page.git
$ cd slack-join-page
$ npm install
$ bin/www
```

Test locally at: <http://localhost:3000>.
