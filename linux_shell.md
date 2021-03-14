1. `sudo !!` - rerun last command with `sudo`

2. shortcuts
- `CTRL+K` - cut to the $
- `CTRK+U` - cut to the ^
- `CTRL+W` - cut word before cursor (ignoring symbols)
- `CTRL+Y` - paste
> `<some cmd without sudo><CTRL+U>sudo<CTRL+Y>`

3. use `less +F /var/log/syslog` instead of `tail -f`
- `CTRL+C` - get out of follow mode
- `SHIFT+F` - go to the bottom + reaattach
