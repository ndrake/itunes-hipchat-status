# iTunes/Spotify to Atlassian HipChat Status

A simple application that takes the current track and artist from iTunes or Spotify and updates your [Atlassian HipChat](https://www.atlassian.com/software/hipchat) status to reflect.

## Requirements

- While the application is written in Google Go, it will spawn a process that utilizes AppleScript to check iTunes/Spotify for the current track. So any OSX should do but this is tested against the latest release, 10.9.
- Compilation requires Google Go 1.5+
- Atlassian HipChat account

## Installation

The application uses only the standard Go libraries so installation is as simple as compiling the binary on your platform; assuming your GOROOT and GOPATH are setup correctly.

```
$ git clone https://github.com/christianvozar/itunes-hipchat-status.git
$ go build
```

## Usage

From the commandline you can utilize the application by passing in your HipChat username and [authentication token](https://www.hipchat.com/docs/apiv2/auth).
```
./itunes-hipchat-status -user=yourname@domain.com -token=XXXXXXXXXXXXXXXXXXXXXXXXXX
```

A more appropriate usage is to schedule the updater to run on a cron schedule of every 3 minutes. (Every 3 minutes is due to the rate limits imposed by the HipChat API)
