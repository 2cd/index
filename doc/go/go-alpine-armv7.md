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
tag = ["alpine", "2023-02-06", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_armhf_2023-02-06_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "6c4f2062269ae8324d932108225380a67f179a307127934f775f0bdab212298c"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "267M"
tar_bytes = 279673344

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "70M"
zstd_bytes = 72936593

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230123"
previous_tag = "2023-01-23"
previous_file = "go-musl_armhf_2023-01-23_12-06-rootfs.tar.zst"
previous_sha256 = "3159943033f15e01d2032bc4871c79064238ab5b8f59688da83844293c5becb9"

current_version = "latest02"
current_date = "20230206"
old_file = "go-musl_armhf_2023-01-09_12-07-rootfs.tar.zst"
old_sha256 = "bfe3767055a4a23eae476092d60215a4d9f0abf629f1d7bc5ff50e0d89124943"
# edition 2021
# DISTRO_NAME=go_armhf
# ROOTFS_FILE=go-musl_armhf_2023-02-06_12-06-rootfs.tar.zst
# SHA256SUM=6c4f2062269ae8324d932108225380a67f179a307127934f775f0bdab212298c
# BUILD_DATE=20230206
# BUILD_TAG=2023-02-06
# STATUS=completed
# VERSION=latest02
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-02-06
begin = 2023-02-06 12:02:34.196775805+00:00
start-sync_0 = 12:03:36
start-zstd = 12:03:50
start-sync_1 = 12:06:42
end-sync_1 = 12:06:56
end = 2023-02-06 12:06:56.587003650+00:00

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
go = 'go version go1.20 linux/arm'
gofmt = '/usr/local/go/bin/gofmt: go1.20'

[other]
workdir = "/go"
```
