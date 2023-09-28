# change-detector

## Installing

1. Install dependencies via: `pip3 install -Ur requirements.txt`
1. Create a [Pushover](https://pushover.net) application to get a token (and, a user id)

## Configuring

Create a JSON file in the running user's home directory called `.change-detector.json`

```
> cat ~/.change-detector.json
{
    "url": "css selector",
    "another_url": "its css selector"
}
```

The CSS selector will take the HTML for that element its children. You'll get alerted if anything changes within that entire DOM tree.

## Running

I run this via cron on a Raspberry Pi:

```
*/15 * * * * PUSHOVER_USER=<user> PUSHOVER_TOKEN=<token> /home/pi/change-detector/detect >/var/log/change-detector.log 2>&1
```
