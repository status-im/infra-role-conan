# Description

This is a deployment [Conan](https://conan.io/) server, which is a decentralized and multi-platform
package manager.

# Details

Conan runs as a container on the host and exposes port `9300` which is the proxied via Nginx to regular HTTPS via `443`.

The backups are generated __TODO__ and uploaded to a Digital Ocean space. For configuration details see [`defaults/main.yml`](./defaults/main.yml).

# Usage

Simply point Conan at the HTTPS endpoint:
```bash
conan remote add status-repo https://conan.status.im/
```
And add your user for repo access:
```bash
% conan user admin --remote=status-repo                                                    [11/01/18 13:55:04]
Please enter a password for "admin" account: 
Changed user of remote 'status-repo' from 'None' (anonymous) to 'admin'
```

# Docker Image

The image used is custom because we wanted to use GUnicorn for hosting the server
It comes from the [`infra-utils`](https://github.com/status-im/infra-utils/tree/master/conan) repo.

# Documentation

* https://hub.docker.com/r/cguenther/conan-server/
* https://docs.conan.io/en/latest/uploading_packages/running_your_server.html
* https://docs.conan.io/en/latest/uploading_packages/uploading_to_remotes.html

# Known Issues

* Backups of repo
