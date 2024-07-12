# Custom Pwnagotchi Plugins
This repositry contains all of my custom-made pwnagotchi plugins (the ones that were finished). You can set them up using the following guide(s) or if you know what to do, the setup is also included in each file. If you found any bugs or have an issue, you can report them [here](https://github.com/xentrify/custom-pwnagotchi-plugins/issues/new/choose)
# Adding these plugins to your pwnagotchi
Add to `/etc/pwnagotchi/config.toml` :
```bash
main.custom_plugin_repos = [
 "https://github.com/evilsocket/pwnagotchi-plugins-contrib/archive/master.zip",
 "https://github.com/xentrify/custom-pwnagotchi-plugins/archive/master.zip"
]
```

Next, `sudo pwnagotchi plugins update` and `sudo pwnagotchi plugins list`.

Now you should be able to continue with configuring the plugins using the next section.
# Plugins
## Aftershake
A plugin that handles everything after a handshake. AircrackOnly, Hashie, Quickdic, etc. All in one.
### Pwnagotchi Configuration
**Required:**
```toml
main.plugins.gps.enabled = true # GPSD can also be used, same for my iphone_gps plugin.
main.plugins.gps.device = "/dev/ttyUSB0"
main.plugins.gps.speed = 19200

main.plugins.aftershake.enabled = true
```
**Optional:**
```toml
main.plugins.aftershake.wordlist_folder = "/root/custom_folder/" # (default: "/root/wordlist_folder/")
main.plugins.aftershake.hashie = true # (default: false)
main.plugins.aftershake.face = "(>.O)" # (default: "(◕.◕)")
```
## iPhone_GPS
Saves GPS coordinates whenever an handshake is captured. Uses your iPhone's GPS via website requests and Shortcuts.
### Pwnagotchi Configuration
**Required:**
```toml
main.plugins.iphone_gps.enabled = true
```
**Optional:**
```toml
main.plugins.iphone_gps.use_last_loc = true # (default: false)
main.plugins.linespacing = 15 # (default: 10)
```
### Phone Configuration (required!)
Set up this [this shortcut](https://routinehub.co/shortcut/19128/) to send the GPS from your iPhone. Optionally, you can make it run whenever the pwnagotchi connects via bluetooth.

For the location sending to work you will need a stable connection with your iPhone and pwnagotchi using bt-tether.


# Credits
* [PwnPeter](https://github.com/PwnPeter) for the easy plugin configuration part.
* junohea.mail@gmail.com for the `hashie-hcxpcapngtool` plugin
* pwnagotchi@rossmarks.uk for the `quickdic` plugin
* evilsocket@gmail.com for the `aircrackonly` plugin
* @nagy_craig for the `display-password` plugin

# License
This repositry is licensed under the GPL 3 license.
