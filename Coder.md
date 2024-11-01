# Coder Server on Debian for Local use in Classroom

## Install
- install Debian Server (no desktop) as normal
- ensure you are NOT root while installing
https://coder.com/docs/install/cli

- do not forget to install docker and then add "coder" user to docker group
  - https://docs.docker.com/engine/install/linux-postinstall/

## Once Installed

To run Coder server as a service:
```sh
sudo systemctl enable --now coder
journalctl -u coder.service -b
```

## Configure

- /etc/coder.d/coder.env
```sh
CODER_HTTP_ADDRESS=# Coder must be reachable from an external URL for users and workspaces to connect.
CODER_HTTP_ADDRESS="10.100.204.204:3000"
CODER_ACCESS_URL="http://10.100.204.204:3000"
CODER_PG_CONNECTION_URL=
CODER_TLS_CERT_FILE=
CODER_TLS_ENABLE=
CODER_TLS_KEY_FILE=

# Run "coder server --help" for flag information.

# for GitHub Auth
CODER_OAUTH2_GITHUB_ALLOW_SIGNUPS=true
CODER_OAUTH2_GITHUB_ALLOWED_ORGS="MTHS-ICS3U"
CODER_OAUTH2_GITHUB_CLIENT_ID="xxx"
CODER_OAUTH2_GITHUB_CLIENT_SECRET="yyy"
```

## GitHub Login

- in above example I have enabled GitHub login for ORG: MTHS-ICS3U
- you must create an "OAuth App" under "Developer Settings" in GitHub
  - "Homepage URL": http://10.100.204.204:3000
  - "Authorization Callback URL": http://10.100.204.204:3000
