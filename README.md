# update_qbittorrent_port
This script pulls the current open ProtonVPN port from Gluetun and sets it as the active port in qbittorrent. Credit to fizzxed for initial script (https://gist.github.com/fizzxed/958d8cdfa4dad8a97651afce4d74efce)

As of version 3.40 of Gluetun the control server requires authentication (please follow the documentation here: https://github.com/qdm12/gluetun-wiki/blob/main/setup/advanced/control-server.md).
For this script to work please setup authentication for the /v1/openvpn/portforwarded and /v1/publicip/ip endpoints.

Below is my Gluetun config.toml
```
[[roles]]
name = "qbittorrent"
routes = ["GET /v1/openvpn/portforwarded", "GET /v1/publicip/ip"]
auth = "apikey"
apikey = ""
```


Edit the qbittorrent and gluetun variables at the top of the script.
Run a cronjob.
Done.


