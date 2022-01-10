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
tag = ["alpine", "2022-01-10", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
x11_or_wayland = false

[file]
name = "go-musl_armhf_2022-01-10_12-05.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "4fb29869056bde9668e6601e4c7ad39704990dafcf4c70b15c2073c75d0f4050"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "316M"
tar_bytes = 331023360

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "81M"
zstd_bytes = 84223198

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211227"
previous_tag = "2021-12-27"
previous_file = "go-musl_armhf_2021-12-27_12-04-rootfs.tar.zst"
previous_sha256 = "668ccebcb5c148430eb4717224514f98052de30928544ed83a7338524d82b0dc"

current_version = "latest02"
current_date = "20220110"
old_file = "go-musl_armhf_2021-12-16_08-26-rootfs.tar.zst"
old_sha256 = "0d1a50622606d85f436e9a6d0f5d4a4db14559f5f91346809d6457afd4870bae"
# edition 2021
# DISTRO_NAME=go_armhf
# ROOTFS_FILE=go-musl_armhf_2022-01-10_12-05-rootfs.tar.zst
# SHA256SUM=4fb29869056bde9668e6601e4c7ad39704990dafcf4c70b15c2073c75d0f4050
# BUILD_DATE=20220110
# BUILD_TAG=2022-01-10
# STATUS=completed
# VERSION=latest02
# END_TIME=12:05

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-01-10
begin = 2022-01-10 12:02:28.868857880+00:00
start-sync_0 = 12:03:28
start-zstd = 12:03:41
start-sync_1 = 12:05:19
end-sync_1 = 12:05:33
end = 2022-01-10 12:05:33.090027020+00:00

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
