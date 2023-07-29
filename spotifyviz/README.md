## WebOS ##

### Good page for docs ###
https://webostv.developer.lge.com/develop/tools/cli-dev-guide#ares-generate

### Generate Hosted WebApp ###

`ares-generate --list`
Tells you all the options

`ares-generate -t hosted_webapp ./SpotifyViz`
Points to an external site, webapp is effectively a container for a url pointing to your app.

The above creates an `index.html` file that you'll update with the webapp's url

#### Package ####
For development (and debugging) run `ares-package --no-minify ./SpotifyViz`

For production, use `ares-package ./SpotifyViz`


### Deploy to local LG WEBOS ###

#### Get list of tv devices ####
Find out the name of your device
`ares-setup-device --list`

#### Install onto device ####
`ares-install --device avt-lg ./com.domain.app_0.0.1_all.ipk`


#### Remove from device ####
`ares-install --device avt-lg --remove com.domain.app`


#### Launch #####
`ares-launch --device avt-lg com.domain.app`


#### Debug (aka inspect) ####
Launch the app, then run `ares-inspect --device avt-lg --app com.domain.app --open`


#### Close ####
`ares-launch --device avt-lg --close com.domain.app`

### All In One ###
`ares-package --no-minify ./spotifyviz && ares-install --device avt-lg ./com.domain.app_0.0.3_all.ipk && ares-inspect --device avt-lg --app com.domain.app --open`

### Simulator Commands ###
No need to build, you can install the folder directly
`ares-launch -s 23 ./spotifyviz`
