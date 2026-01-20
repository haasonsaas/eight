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
# Login
eight login

# Status
eight status
eight status --json
eight status --side right    # Check partner's side

# Temperature control
eight temp 68F               # Fahrenheit
eight temp 20C               # Celsius
eight temp -30               # Raw level (-100 to 100)
eight temp 65F --side right  # Set partner's side

# On/Off
eight on
eight off
eight off --side right

# Presence detection
eight presence               # Both sides
eight presence --side left   # Specific side

# Sleep metrics
eight sleep                  # Last 7 days
eight sleep --days 30        # Last 30 days
eight sleep --json

# Alarms
eight alarms                 # List alarms
eight alarm-set 7:30         # Set alarm time
eight alarm-on               # Enable alarm
eight alarm-off              # Disable alarm

# Info
eight whoami
eight version

# Shell completions
eval "$(eight completion bash)"   # Bash
eval "$(eight completion zsh)"    # Zsh
eight completion fish > ~/.config/fish/completions/eight.fish
```

## Features

- **Temperature control** - Set bed temperature in Fahrenheit, Celsius, or raw levels
- **Presence detection** - Check if someone is in bed
- **Sleep metrics** - View sleep scores, HRV, heart rate, breathing rate
- **Alarms** - List, enable, disable, and set alarm times
- **Side selection** - Control either side of the bed with `--side`
- **Retry logic** - Automatic retry with exponential backoff for rate limits
- **Shell completions** - Tab completion for bash, zsh, and fish
- **JSON output** - Machine-readable output for scripting

## Config

Credentials stored at `~/.config/eight/config.json` (mode 600).
Token cached at `~/.config/eight/token.json` and auto-refreshes.

## Credits

API reverse-engineered from [pyEight](https://github.com/lukas-clarke/pyEight).
