# update_qbittorrent_port
This script pulls the current open ProtonVPN port from Gluetun and sets it as the active port in qbittorrent.

Edit the qbittorrent and gluetun variables at the top of the script.

As of version 3.40 of Gluetun the control server requires authentication (please follow the documentation here: https://github.com/qdm12/gluetun-wiki/blob/main/setup/advanced/control-server.md).
For this script to work please setup authentication for the /v1/openvpn/portforwarded and /v1/publicip/ip endpoints.

Below is my Gluetun config.toml
```
[[roles]]
name = "qbittorrent"
# Define a list of routes with the syntax "Http-Method /path"
routes = ["GET /v1/openvpn/portforwarded", "GET /v1/publicip/ip"]
# Define an authentication method with its parameters
auth = "apikey"
apikey = ""
```
