# eight

Control your Eight Sleep Pod from the terminal.

## Install

```sh
curl -o /usr/local/bin/eight https://raw.githubusercontent.com/haasonsaas/eight/main/eight
chmod +x /usr/local/bin/eight
```

Requires Python 3.7+.

## Usage

```sh
# Login (stores credentials securely)
eight login

# Show current status
eight status

# Turn on/off
eight on
eight off

# Set temperature
eight temp 68F    # Fahrenheit
eight temp 20C    # Celsius
eight temp -30    # Raw level (-100 to 100)

# Show user ID
eight whoami

# JSON output
eight status --json

# Logout
eight logout
```

## Config

Credentials stored at `~/.config/eight/config.json` with 600 permissions.
Token cached at `~/.config/eight/token.json` and auto-refreshes.

## Credits

API reverse-engineered from [pyEight](https://github.com/lukas-clarke/pyEight).
