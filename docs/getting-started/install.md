> **💡 Tip:** Use [Caddy](https://caddyserver.com/) as your web server for better performance and simplified setup. [Learn more >](https://bcow.xyz/posts/why-you-should-replace-nginx)

This page describes multiple methods to install Librarian. The recommended method for production use is to install Librarian using Docker.

> See [this](/docs/getting-started/nginx-issues.md) if you are using NGINX.

## Docker
Docker images for Librarian are available on [Codeberg](https://codeberg.org/librarian/-/packages/container/librarian/latest) for `linux/amd64` and `linux/arm64`. To get started, [install Docker](https://docs.docker.com/engine/install/) if it is not already installed.

Use `git` to clone the repository.
```sh
git clone https://codeberg.org/librarian/librarian
```

Copy the config file and edit it.
```sh
mkdir data
cp config.example.yml data/config.yml
nano data/config.yml
```

You can also edit `docker-compose.yml` if you want to change ports or build from source.

You can now run Librarian. 🎉
```sh
sudo docker compose up -d
```

## Build from source
If you need to make changes to the source code or do development, follow these instructions.

> Librarian is licensed under the [AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.en.html) and requires all source code modifications to be published under the same license.

You will need to use Go 1.16 or later. Follow the instructions to [install Go](https://go.dev/doc/install). If you are using Fedora or Arch Linux, you can also use your distribution's package manager to install Go (Ubuntu and Debian do not have recent Go versions, these will not work).

Use `git` to clone the repository.
```sh
git clone https://codeberg.org/librarian/librarian
```

Copy the config file and edit it.
```sh
cp config.example.yml config.yml
```

To run Librarian without building, use `go run main.go`.

To build a binary, use the following command. This will build a binary that can be used on any distro (for Linux), you can also cross-compile for different architectures and operating systems using the `GOARCH` and `GOOS` environment variables.
```
CGO_ENABLED=0 go build -ldflags "-X codeberg.org/video-prize-ranch/rimgo/pages.VersionInfo=$(date '+%Y-%m-%d')-$(git rev-list --abbrev-commit -1 HEAD)"
```