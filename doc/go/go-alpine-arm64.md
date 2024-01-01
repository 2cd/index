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
tag = ["alpine", "2024-01-01", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_arm64_2024-01-01_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "f7ede93e65b3ace11cfd25c1360af5f88f69721a248496ed9503a694bd31b8b5"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "244M"
tar_bytes = 254972928

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "40M"
zstd_bytes = 41695745

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20231127"
previous_tag = "2023-11-27"
previous_file = "go-musl_arm64_2023-11-27_12-06-rootfs.tar.zst"
previous_sha256 = "fa4b733d5524277f628b286442947e5f7d224472d3a4dfcbfdb6fcfb457c06cc"

current_version = "latest01"
current_date = "20240101"
old_file = "go-musl_arm64_2023-11-13_12-06-rootfs.tar.zst"
old_sha256 = "039c84d5f50ab0ce1739a38c6527ed9c6918a9e82fdeeea36edf70114a4e9abc"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go-musl_arm64_2024-01-01_12-06-rootfs.tar.zst
# SHA256SUM=f7ede93e65b3ace11cfd25c1360af5f88f69721a248496ed9503a694bd31b8b5
# BUILD_DATE=20240101
# BUILD_TAG=2024-01-01
# STATUS=completed
# VERSION=latest01
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2024-01-01
begin = 2024-01-01 12:02:33.854854925+00:00
start-sync_0 = 12:03:40
start-zstd = 12:03:48
start-sync_1 = 12:05:53
end-sync_1 = 12:06:00
end = 2024-01-01 12:06:00.653672535+00:00

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
ldd = 'musl libc (aarch64) Version 1.2.4_git20230717'
go = 'go version go1.21.5 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.21.5'

[other]
workdir = "/go"
```
