## TravisCI-Telegam-Bot

Telegram bot, which will notify you each time, when your Travis CI build is done.

### Usage
You can type `/help` or `/how` to get more information about how it works.

You should send the link to your Travis CI repository. After that, a bot will listen for new builds and will notify you each time when your build is done.

### How it works
When you sending your Travis CI repository link, bot making the HTTP request to get the current state of build. Then it storing number of current build and then creating a new variable with the same value. Then it making new HTTP request each 7 seconds to get current information, and then it's parsing JSON and assigning a current number of build to `currBuiltNumber`. If `currBuiltNumber` number equal `prevBuiltNumber`, then nothing has been changed. Else it's checking if a build has been done by getting a value of `last_build_finished_at`. If `last_build_finished_at` does not equal `null` then it means that new build just has been finished and it will send you a message with some basic information about your build.

#### Contributing
If you find any issues, please feel free to contribute to [repository issues](https://github.com/artemgurzhii/TravisCI-Telegam-Bot/issues)