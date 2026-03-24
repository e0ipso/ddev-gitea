[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/e0ipso/ddev-gitea/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/e0ipso/ddev-gitea/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/e0ipso/ddev-gitea)](https://github.com/e0ipso/ddev-gitea/commits)
[![release](https://img.shields.io/github/v/release/e0ipso/ddev-gitea)](https://github.com/e0ipso/ddev-gitea/releases/latest)

# DDEV Gitea

## Overview

This add-on integrates Gitea into your [DDEV](https://ddev.com/) project.

## Installation

```bash
ddev add-on get e0ipso/ddev-gitea
ddev restart
```

After installation, make sure to commit the `.ddev` directory to version control.

## Usage

| Command | Description |
| ------- | ----------- |
| `ddev describe` | View service status and used ports for Gitea |
| `ddev logs -s gitea` | Check Gitea logs |

## Advanced Customization

To change the Docker image:

```bash
ddev dotenv set .ddev/.env.gitea --gitea-docker-image="ddev/ddev-utilities:latest"
ddev add-on get e0ipso/ddev-gitea
ddev restart
```

Make sure to commit the `.ddev/.env.gitea` file to version control.

All customization options (use with caution):

| Variable | Flag | Default |
| -------- | ---- | ------- |
| `GITEA_DOCKER_IMAGE` | `--gitea-docker-image` | `ddev/ddev-utilities:latest` |

## Credits

**Contributed and maintained by [@e0ipso](https://github.com/e0ipso)**
