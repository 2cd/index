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
tag = ["alpine", "2022-10-03", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_armhf_2022-10-03_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "44ff5c2080135266714fcf7cbcee01ce2fd5bded78162d97320400ead43952b3"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "341M"
tar_bytes = 356517376

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "82M"
zstd_bytes = 85242164

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220919"
previous_tag = "2022-09-19"
previous_file = "go-musl_armhf_2022-09-19_12-07-rootfs.tar.zst"
previous_sha256 = "25194666314456271e11c825e39303eb8d1593897e6e5dbf04354b8847141ae0"

current_version = "latest01"
current_date = "20221003"
old_file = "go-musl_armhf_2022-09-05_12-07-rootfs.tar.zst"
old_sha256 = "5e989dc6f98be2dd9b1a663c5bc61eb39d532aed533f56754348b12b98834bf5"
# edition 2021
# DISTRO_NAME=go_armhf
# ROOTFS_FILE=go-musl_armhf_2022-10-03_12-07-rootfs.tar.zst
# SHA256SUM=44ff5c2080135266714fcf7cbcee01ce2fd5bded78162d97320400ead43952b3
# BUILD_DATE=20221003
# BUILD_TAG=2022-10-03
# STATUS=completed
# VERSION=latest01
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-10-03
begin = 2022-10-03 12:02:25.675232391+00:00
start-sync_0 = 12:03:26
start-zstd = 12:03:38
start-sync_1 = 12:06:48
end-sync_1 = 12:07:00
end = 2022-10-03 12:07:00.678750232+00:00

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
current = true
previous = true
in_sync = false
split = false

[server.node3]
name = "azure"
current = true
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
ldd = 'musl libc (armhf) Version 1.2.3'
go = 'go version go1.19.1 linux/arm'
gofmt = '/usr/local/go/bin/gofmt: go1.19.1'

[other]
workdir = "/go"
```
