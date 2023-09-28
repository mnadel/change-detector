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

## Running

```
*/15 * * * * PUSHOVER_USER=<user> PUSHOVER_TOKEN=<token> /home/pi/change-detector/detect >/var/log/change-detector.log 2>&1
```
