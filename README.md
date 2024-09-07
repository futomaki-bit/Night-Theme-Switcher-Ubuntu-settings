# Night-Theme-Switcher-Ubuntu-settings

Night-Theme-Switcher-Ubuntu-settings
Night Theme Switcher by rmnvgr \
https://extensions.gnome.org/extension/2236/night-theme-switcher/

This extension greets Ubuntu users with a warning:

> ⚠️ Ubuntu is not supported due to their heavily patched GNOME components that conflict with the extension ⚠️

While the extension might work, some apps don't switch between dark and light mode.

### To fix this: ###

1. Open the extension's settings.
2. Go to Commands (bottom bar).
3. Enable Run commands and add the following commands:
   
**Sunrise:**
```bash
gsettings set org.gnome.desktop.interface gtk-theme Yaru
gsettings set org.gnome.desktop.interface color-scheme prefer-light
gsettings reset org.gnome.shell.ubuntu color-scheme
```

**Sunset:**
```bash
gsettings set org.gnome.desktop.interface gtk-theme Yaru-dark
gsettings set org.gnome.desktop.interface color-scheme prefer-dark 
gsettings reset org.gnome.shell.ubuntu color-scheme  
```

### Optional:
Personally, I like to add night-light during dark mode but not in light mode. Add an extra line

To turn off Night Light:
```bash
gsettings set org.gnome.settings-daemon.plugins.color night-light-enabled false
```
To turn on Night Light:
```bash
gsettings set org.gnome.settings-daemon.plugins.color night-light-enabled true
```
