# Notes

`setapikey.py` is a pythonic way of setting the OCTOPRINT_APIKEY should that be preferable to develop with or for. Mostly I just wrote it as a first method and would like to keep it around for future reference.

In `start.sh` I currently opt to use [jq](https://stedolan.github.io/jq/), a sed-like json processor as follows:

```bash
FILE="$HOME/.config/octodash/config.json"
TMP=$(mktemp)
jq ".config.octoprint.accessToken |= \"$OCTOPRINT_APIKEY\"" < $FILE > $TMP && mv $TMP $FILE
```
