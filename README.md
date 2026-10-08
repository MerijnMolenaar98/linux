# Ubuntu Server Setup Scripts

A small collection of Linux scripts, tested on an Ubuntu server hosted on AWS.

## Prerequisites

Place your key pair file (`keypair.pem`) in the project's root folder.

> ⚠️ Never commit your `.pem` file. Add it to `.gitignore`.

## Connecting to your AWS instance

```bash
ssh -i your-key-name.pem username@ip-address
```

## Recommended tools

Install these once you're logged in to the server.

### ufw

A simple firewall. Allow SSH **before** enabling it, so you don't lock yourself out.

```bash
sudo apt update && sudo apt install ufw -y
sudo ufw allow ssh
sudo ufw enable
```

### fail2ban

Blocks IP addresses after too many failed login attempts.

```bash
sudo apt update && sudo apt install fail2ban -y
```

### unattended-upgrades

Enable automatic updates.

```
sudo apt update
sudo apt install unattended-upgrades

sudo dpkg-reconfigure --priority=low unattended-upgrades

```
