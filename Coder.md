# Coder Server on Debian

## Install

https://coder.com/docs/install/cli

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
