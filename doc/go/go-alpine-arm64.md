# go-alpine-arm64

## How to run it?

```sh
docker run \
    -it \
    --name go-alpine-arm64 \
    cake233/go-alpine-arm64
```

## How to exec shell?

```sh
docker exec -it go-alpine-arm64 bash
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
    cake233/go-alpine-arm64 \
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

## go-alpine-arm64.toml

```toml
[main]
name = "go"
tag = ["alpine", "2022-06-27", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_arm64_2022-06-27_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "683772404b6538e0190390490b1ed6ac4be393d06e1a241b78c063ef91dd356a"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "334M"
tar_bytes = 350003200

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "78M"
zstd_bytes = 81205800

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220613"
previous_tag = "2022-06-13"
previous_file = "go-musl_arm64_2022-06-13_12-06-rootfs.tar.zst"
previous_sha256 = "56ec375b1025cd60d719dd724120be74a903720e9df2be8c974766229b2d17eb"

current_version = "latest01"
current_date = "20220627"
old_file = "go-musl_arm64_2022-05-30_12-07-rootfs.tar.zst"
old_sha256 = "c7709aacdf8afa6c345baa96fae2f25f29be08086cc5ac70bd77feb85c0f1bf2"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go-musl_arm64_2022-06-27_12-06-rootfs.tar.zst
# SHA256SUM=683772404b6538e0190390490b1ed6ac4be393d06e1a241b78c063ef91dd356a
# BUILD_DATE=20220627
# BUILD_TAG=2022-06-27
# STATUS=completed
# VERSION=latest01
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-27
begin = 2022-06-27 12:02:33.310717916+00:00
start-sync_0 = 12:03:22
start-zstd = 12:03:31
start-sync_1 = 12:06:20
end-sync_1 = 12:06:29
end = 2022-06-27 12:06:29.402956285+00:00

[server]
repo = "cake233/go-alpine-arm64"

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
ldd = 'musl libc (aarch64) Version 1.2.3'
go = 'go version go1.18.3 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.18.3'

[other]
workdir = "/go"
```
