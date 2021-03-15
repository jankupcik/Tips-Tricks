Shortcuts
=========

| shortcut   |     |
| ---------- | --- |
| `CTRL-D`   | exit shell session |
| `CTRL-L`   | `clear` |
| `CTRL-A`   | move to ^ |
| `CTRL-E`   | move to $ |
| `ALT-B`    | move backward one word |
| `ALT-F`    | move forward one word |
|            |   |
| `CTRL-K`   | cut to the $ |
| `CTRK-U`   | cut to the ^ |
| `CTRL-W`   | cut word before cursor (ignoring symbols) |
| `CTRL-Y`   | paste <br> `<some cmd without sudo> <CTRL+U> sudo <CTRL+Y>` |
|            |    |
| `CTRL-F`   | searching through shell history<br>`CTRL-G` to cancel |
| `CTRL-X-E` | continue editing ther current shell line in a text editor <br>(uses $EDITOR, i.e. EDITOR=vim must be called) |
| `ALT-.`    | paste previous command's argument (useful for running multiple commands on the same resource)<br>`ping 8.8.8.8`<br>`telnet <ALT-.>`


- `sudo !!` - rerun last command with `sudo`

- use `less +F /var/log/syslog` instead of `tail -f`
  - `CTRL-C` - get out of follow mode
  - `SHIFT-F` - go to the bottom + reaattach

- `reset` terminal
- `history`

[Enable](https://www.youtube.com/watch?v=GqoJQft5R2E) VI mode for shell: `set -o vi` to .bash_profile

https://www.shellcheck.net/
