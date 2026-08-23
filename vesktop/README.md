# Vesktop "Glass" theme template

`glass.template.css` is rendered to
`~/.config/vesktop/themes/glass.theme.css` by `~/.local/bin/theme-from-wallpaper`
on every wallpaper change, so Discord recolours along with waybar and swaylock.

## Why this is not under `.config/vesktop/`

`install.sh` symlinks every entry in `.config/*` into `$HOME`. Symlinking
`~/.config/vesktop` would point Vesktop's whole profile at this repo -- session
data and login tokens included -- so only the template lives here, outside
`.config/`, and it is linked individually:

    ln -sfn "$PWD/vesktop/glass.template.css" ~/.config/vesktop/glass.template.css

## Enabling

In Vesktop: Settings -> Themes -> enable **Glass**. Vesktop must also have
`"transparent": true` in `~/.config/vesktop/settings/settings.json`, and needs a
full restart afterwards -- Electron fixes window transparency at creation time,
so a reload will not apply it.
