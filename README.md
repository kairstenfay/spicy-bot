# Slack Spicy Bot

Required environment variables:
* `SLACK_TOKEN` (Hint: starts with `xoxb-*`. This is a secret which must be kept private.)
* `SLACK_CHANNEL` (Hint: retrieved using the `conversations.list` method.)
  * **#test**: C01K04A6A6R
  * **#sraerche-spicy**: CPQ2SDF8S

Required Bot token scopes:
* `channels:history`
* `channels:read`
* `chat:write`
* `incoming-webhook`

To run:

    ./bin/run


This wrapper script calls, in sequence, the following scripts:
* `./bin/read-from-slack` - gets recent history from a specified Slack channel
* `./bin/rate-spicy-takes` - parses given channel history and outputs computed text
* `./bin/post-to-slack` - posts an arbitrary text payload to a specified Slack channel

Each of these scripts can be invoked independently outside of the `./bin/run` wrapper script.
