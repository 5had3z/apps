# Default Helm-Values

TrueCharts is primarily build to supply TrueNAS SCALE Apps.
However, we also supply all Apps as standard Helm-Charts. In this document we aim to document the default values in our values.yaml file.

Most of our Apps also consume our "common" Helm Chart.
If this is the case, this means that all values.yaml values are set to the common chart values.yaml by default. This values.yaml file will only contain values that deviate from the common chart.
You will, however, be able to use all values referenced in the common chart here, besides the values listed in this document.

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env.RUST_SERVER_STARTUP_ARGUMENTS | string | `"-batchmode -load -nographics +server.secure 1"` | `"Rust Server Startup Args"` |
| env.RUST_SERVER_IDENTITY | string | `"docker"` | `"Mainly used for the name of the save directory"` |
| env.RUST_SERVER_PORT | int | `"{{ .Values.service.main.ports.main.targetPort }}"` | `""Rust server port""` |
| env.RUST_SERVER_SEED | int | `12345` | `"The server map seed"` |
| env.RUST_SERVER_WORLDSIZE | int | `3500` | `"The map size"` |
| env.RUST_SERVER_NAME | string | `"TrueCharts Dedicated Server"` | `"The publicly visible server name"` |
| env.RUST_SERVER_MAXPLAYERS | int | `100` | `"Maximum players on the server"` |
| env.RUST_SERVER_DESCRIPTION | string | `"This is a Rust server running with TrueCharts!"` | `"The publicly visible server description"` |
| env.RUST_SERVER_URL | string | `https://hub.docker.com/r/didstopia/rust-server/` | `"The publicly visible server website"` |
| env.RUST_SERVER_BANNER_URL | string | `""` | `"The publicly visible server banner image URL"` |
| env.RUST_SERVER_SAVE_INTERVAL | int | `600` | `"Amount of seconds between automatic saves"` |
| env.RUST_RCON_WEB | int | `1` | `"Set to 1 or 0 to enable or disable the web-based RCON server"` |
| env.RUST_RCON_PORT | int | `"{{ .Values.service.main.ports.rcon.targetPort }}"` | `"RCON server port"` |
| env.RUST_APP_PORT | int | `"{{ .Values.service.main.ports.rapp.targetPort }}"` | `"Rust+ companion app port"` |
| env.RUST_BRANCH | string | `""` | `"Sets the branch argument to use, eg. set to "-beta prerelease" for the prerelease branch"` |
| env.RUST_UPDATE_CHECKING | int | `0` | `"Set to 1 to enable fully automatic update checking, notifying players and restarting to install updates"` |
| env.RUST_UPDATE_BRANCH | string | `"public"` | `"Set to match the branch that you want to use for updating, ie. "prerelease" or "public", but do not specify arguments like "-beta""` |
| env.RUST_START_MODE | int | `0` | `"Determines if the server should update and then start (0), only update (1) or only start (2)"` |
| env.RUST_OXIDE_ENABLED | int | `0` | `"Set to 1 to automatically install the latest version of Oxide"` |
| env.RUST_OXIDE_UPDATE_ON_BOOT | int | `1` | `"Set to 0 to disable automatic update of Oxide on boot"` |
| image.pullPolicy | string | `"Always"` | `"Pull latest image from repository on startup"` |
| image.repository | string | `"didstopia/rust-server"` | `"Repository where to pull image"` |
| image.tag | string | `"latest@sha256:f520cf1d4d5be0cb6a447140630fe80f97e22ead3d2218c92180021ba5455ed4"` | `"Image tag"` |


All Rights Reserved - The TrueCharts Project
