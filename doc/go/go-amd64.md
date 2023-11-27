# go-amd64

## How to run it?

```sh
docker run \
    -it \
    --name go-amd64 \
    cake233/go-amd64
```

## How to exec shell?

```sh
docker exec -it go-amd64 bash
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
    cake233/go-amd64 \
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

## go-amd64.toml

```toml
[main]
name = "go"
tag = ["latest", "2023-11-27"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_amd64_2023-11-27_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7f8beef0df3f7958effbcb96b8441b2f3accb2c0ac83f95c84b79b021f2cee90"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "828M"
tar_bytes = 867866112

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "159M"
zstd_bytes = 166148988

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20231113"
previous_tag = "2023-11-13"
previous_file = "go_amd64_2023-11-13_12-10-rootfs.tar.zst"
previous_sha256 = "98c97867a279e22f9ba0cb3c257a37035dfd79daa97dae799be8fedd761ed4c5"

current_version = "latest02"
current_date = "20231127"
old_file = "go_amd64_2023-10-16_12-12-rootfs.tar.zst"
old_sha256 = "03069170e20695586a97e33802cbe397bc5cd1b14f1541bad5a9bc80994ff715"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go_amd64_2023-11-27_12-09-rootfs.tar.zst
# SHA256SUM=7f8beef0df3f7958effbcb96b8441b2f3accb2c0ac83f95c84b79b021f2cee90
# BUILD_DATE=20231127
# BUILD_TAG=2023-11-27
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-11-27
begin = 2023-11-27 12:02:36.437296686+00:00
start-sync_0 = 12:04:21
start-zstd = 12:04:30
start-sync_1 = 12:09:16
end-sync_1 = 12:09:28
end = 2023-11-27 12:09:28.162541341+00:00

[server]
repo = "cake233/go-amd64"

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
LANG = "en_US.UTF-8"
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
ldd = 'ldd (Debian GLIBC 2.36-9+deb12u3) 2.36'
go = 'go version go1.21.4 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.21.4'

[other]
workdir = "/go"
```
