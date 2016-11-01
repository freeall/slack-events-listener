# slack-events-listener
Easy to user web server which emits all events received from Slack Events API. It handles the intial verification with Slack and emits all events posted to you by Slack.

## How To
`npm install slack-events-listener`

The module returns an `EventEmitter` which emits `slack_event` events which contain the whole JSON payload from Slack.

```javascript
const slackEvents = require('slack-events-listener')({
  eventUrl: '/slack_event',                      // required
  verificationToken: '<your application token>', // required
  port: 1234                                     // optional, defaults to 3000
});

slackEvents.on('slack_event', console.log);
```

## Options

- `eventUrl` *Required. The path that you should point the Slack Events API towards*
- `verificationToken` *Required. Find this variable in your Slack application settings*
- `port` *Optionanl, defaults to 3000. Which port should the webserer bind to*

## Payload format
List of payloads is available at https://api.slack.com/events-api#event_types
