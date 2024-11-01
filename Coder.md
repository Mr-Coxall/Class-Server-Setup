# Coder Server on Debian

## Install

- ensure you are NOT root while installing
https://coder.com/docs/install/cli

- do not forget to install docker and then add "coder" user to docker group
  - https://docs.docker.com/engine/install/linux-postinstall/

## Once Running

To run a Coder server:

  # Start Coder now and on reboot
  $ sudo systemctl enable --now coder
  $ journalctl -u coder.service -b

  # Or just run the server directly
  $ coder server

  Configuring Coder: https://coder.com/docs/admin/configure

To connect to a Coder deployment:

## Configure

/home/coder/.config/coderv2
