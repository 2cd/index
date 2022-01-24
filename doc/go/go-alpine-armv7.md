# go-alpine-armv7

## How to run it?

```sh
docker run \
    -it \
    --name go-alpine-armv7 \
    cake233/go-alpine-armv7
```

## How to exec shell?

```sh
docker exec -it go-alpine-armv7 bash
```

## example

```sh
docker run \
    -t \
    --rm \
    -v "$PWD"/go-project:/app \
    -w /app \
    -e GOOS=linux \
    -e CGO_ENABLED=0 \
    cake233/go-alpine-armv7 \
    go build -trimpath --ldflags "-s -w -buildid=" -v -o main.bin
```

## readme.go
```go
// go run readme.go
package main

import "fmt"

func main() {
	var (
		country, proxy_site string
	)

	country = "China"
	proxy_site = "https://goproxy.cn"
	fmt.Printf("If you live in\x1b[%dm %v. \x1b[0m\n", 32, country)
	fmt.Printf("Then you can run the following\x1b[%dm commands. \x1b[0m\n", 31)

	fmt.Println("go env -w GO111MODULE=on")
	fmt.Printf("go env -w GOPROXY=%v,direct\n", proxy_site)
}
```

## go-alpine-armv7.toml

```toml
[main]
name = "go"
tag = ["alpine", "2022-01-24", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "go-musl_armhf_2022-01-24_12-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "906eeae26ebd26a413f7ec64d0d1880f397edf1f29670b62ab1d3bc4878bec3d"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "316M"
tar_bytes = 330990592

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "81M"
zstd_bytes = 84243083

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20211128"
previous_tag = ""
previous_file = ""
previous_sha256 = ""

current_version = "latest01"
current_date = "20220124"
old_file = ""
old_sha256 = ""
# edition 2021
# DISTRO_NAME=go_armhf
# ROOTFS_FILE=go-musl_armhf_2022-01-24_12-05-rootfs.tar.zst
# SHA256SUM=906eeae26ebd26a413f7ec64d0d1880f397edf1f29670b62ab1d3bc4878bec3d
# BUILD_DATE=20220124
# BUILD_TAG=2022-01-24
# STATUS=completed
# VERSION=latest01
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-24
begin = 2022-01-24 12:02:28.344108676+00:00
start-sync_0 = 12:03:29
start-zstd = 12:03:42
start-sync_1 = 12:05:16
end-sync_1 = 12:05:29
end = 2022-01-24 12:05:29.735958954+00:00

[server]
repo = "cake233/go-alpine-armv7"

[server.node1]
name = "cn"
current = false
previous = false
in_sync = false
split = false

[server.node2]
name = "tmoe"
current = false
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = false
previous = true
in_sync = false
split = false

[server.node4]
name = "docker"
current = true

# Environment variables  (●＞ω＜●)
[env]
LANG = "C.UTF-8"
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
ldd = 'musl libc (armhf) Version 1.2.2'
go = 'go version go1.18beta1 linux/arm'
gofmt = '/usr/local/go/bin/gofmt: go1.18beta1'

[other]
workdir = "/go"
```
