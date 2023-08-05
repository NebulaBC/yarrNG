# yarrNG

[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)

![Go](https://img.shields.io/badge/go-%2300ADD8.svg?style=for-the-badge&logo=go&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)

**yarrNG** is yarr but upgraded.

I have serious respect for projects that achieve their goal and become feature-complete, such as the original yarr or projects like runit... that said, even though I *love* yarr I also have some things I would like it to have for it to be *feature complete for me*.

I have more ideas rolling around my head, but here is my TODO list for now:

- [ ]  Importable fonts
   - Incomplete, but now has my preferred font (Comic Mono) as an option. The rest of this is still planned.
- [X]  Standalone PWA support for iOS
   - Added empty service worker to enable standalone mode on iOS
- [ ]  Multi-account support
- [ ]  Custom themes
- [ ]  Hashed passwords for accounts

## running

This is not anywhere near complete, but it's in a functioning state with the features listed.

You can build this project pretty easily by running `make build_linux` for linux.

I personally use Docker, and I've already published an image to Docker Hub. If you'd like to use Docker you can use my pre-built image if you're on ARM64 (Don't worry, multi arch builds coming soon.). Otherwise you may have to build your own image. Here's the docker compose for mine:
```
version: '3.3'
services:
    yarr:
        volumes:
            - './data:/data'
        environment:
            - YARR_DB=/data/yarr.db
            - YARR_AUTH=username:password
        image: nebulabc/yarrng:latest-arm
        network_mode: "host"
```

## credits

[yarr](https://github.com/nkanaev/yarr) the original.  
[Feather](http://feathericons.com/) for icons.