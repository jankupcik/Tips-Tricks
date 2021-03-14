1. `sudo !!` - rerun last command with `sudo`

2. copy & paste
- `CTRL-K` - cut to the $
- `CTRK-U` - cut to the ^
- `CTRL-W` - cut word before cursor (ignoring symbols)
- `CTRL-Y` - paste
> `<some cmd without sudo><CTRL+U>sudo<CTRL+Y>`

3. `CTRL-X-E` - continue editing your current shell line in a text editor (uses $EDITOR, i.e. EDITOR=vim must be called)

4. `ALT-.` - paste previous command's argument (useful for running multiple commands on the same resource)
> `ping 8.8.8.8`\
> `telnet <ALT-.>`

5. use `less +F /var/log/syslog` instead of `tail -f`
- `CTRL-C` - get out of follow mode
- `SHIFT-F` - go to the bottom + reaattach
