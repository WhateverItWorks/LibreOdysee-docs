This page describes multiple methods to install LibreOdysee. The recommended method for production use is to install LibreOdysee using Docker/Docker-Compose.

## Docker
Use `git` to clone the repository.
```sh
git clone https://github.com/WhateverItWorks/LibreOdysee
```

Copy the config file and edit it.
```sh
mkdir data
cp config.example.yml data/config.yml
nano data/config.yml
```

You can also edit `docker-compose.yml` and build from source.

You can now run LibreOdysee. 🎉
```sh
sudo docker-compose up -d --build
```
