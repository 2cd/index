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
tag = ["latest", "2021-12-27"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
x11_or_wayland = false

[file]
name = "go_amd64_2021-12-27_12-09.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "f65561de778fd185675664568a9018a9a3a2b1982e6ac6c5a5a9b9b0a94cfb6c"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "965M"
tar_bytes = 1011769856

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "228M"
zstd_bytes = 238494299

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20211216"
previous_tag = "2021-12-16"
previous_file = "go_amd64_2021-12-16_08-30-rootfs.tar.zst"
previous_sha256 = "4d8b831a03f5f39f1c6a7443d38411f0b6033f6785b1df9b43df0ac3daaf9424"

current_version = "latest02"
current_date = "20211227"
old_file = "go_amd64_2021-12-08_01-12-rootfs.tar.zst"
old_sha256 = "8cb91f8903a793724020ef1faa6b7975fa141d225b31dcd0ef660d6e2cbcfa92"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go_amd64_2021-12-27_12-09-rootfs.tar.zst
# SHA256SUM=f65561de778fd185675664568a9018a9a3a2b1982e6ac6c5a5a9b9b0a94cfb6c
# BUILD_DATE=20211227
# BUILD_TAG=2021-12-27
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2021-12-27
begin = 2021-12-27 12:02:51.608474185+00:00
start-sync_0 = 12:03:47
start-zstd = 12:04:13
start-sync_1 = 12:08:58
end-sync_1 = 12:09:24
end = 2021-12-27 12:09:24.544059444+00:00

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
LANG = "en_US.UTF-8"
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u2) 2.31'
go = 'go version go1.18beta1 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.18beta1'

[other]
workdir = "/go"
```
