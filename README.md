[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/e0ipso/ddev-gitea/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/e0ipso/ddev-gitea/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/e0ipso/ddev-gitea)](https://github.com/e0ipso/ddev-gitea/commits)
[![release](https://img.shields.io/github/v/release/e0ipso/ddev-gitea)](https://github.com/e0ipso/ddev-gitea/releases/latest)

# DDEV Gitea

## Overview

This add-on installs the [tea CLI](https://gitea.com/gitea/tea) into your [DDEV](https://ddev.com/) web container, giving you command-line access to Gitea servers from inside your project.

It downloads the latest `tea` binary during image build, places it on the container's PATH, and bind-mounts your host `~/.config/tea/config.yml` so that your Gitea server logins and credentials are available inside the container.

## Installation

```bash
ddev add-on get e0ipso/ddev-gitea
ddev restart
```

After installation, make sure to commit the `.ddev` directory to version control.

## Usage

| Command | Description |
| ------- | ----------- |
| `ddev exec tea login list` | List configured Gitea server logins |
| `ddev exec tea repos ls` | List repositories on your default Gitea server |
| `ddev exec tea issues ls` | List issues in the current repository |
| `ddev ssh` then `tea` | Use tea interactively inside the container |

## Host Configuration

The add-on mounts `~/.config/tea/config.yml` from your host into the container. To set up tea on your host first:

```bash
# Install tea on your host (if not already installed)
# See https://gitea.com/gitea/tea/releases

# Add a Gitea server login
tea login add --name my-server --url https://your-gitea.example.com --token YOUR_TOKEN
```

Once configured on the host, the same logins will be available inside the DDEV container.

## Credits

**Contributed and maintained by [@e0ipso](https://github.com/e0ipso)**
