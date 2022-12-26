# go-arm64

## How to run it?

```sh
docker run \
    -it \
    --name go-arm64 \
    cake233/go-arm64
```

## How to exec shell?

```sh
docker exec -it go-arm64 bash
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
    cake233/go-arm64 \
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

## go-arm64.toml

```toml
[main]
name = "go"
tag = ["latest", "2022-12-26"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_arm64_2022-12-26_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "088ced30c2f10aed28c341ea7397584b9bbee921a348245080a9c3d204feb7cb"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "852M"
tar_bytes = 893316608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "194M"
zstd_bytes = 202984101

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20221212"
previous_tag = "2022-12-12"
previous_file = "go_arm64_2022-12-12_12-10-rootfs.tar.zst"
previous_sha256 = "76dd4c625b0ce1d47736f0d0aacca92af9b4b848b6df97255cfb85ecfd53d217"

current_version = "latest01"
current_date = "20221226"
old_file = "go_arm64_2022-11-28_12-09-rootfs.tar.zst"
old_sha256 = "ff2a9cf99e4fe7af79723388843952d17d6752d89487eb85164258f83a697099"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2022-12-26_12-10-rootfs.tar.zst
# SHA256SUM=088ced30c2f10aed28c341ea7397584b9bbee921a348245080a9c3d204feb7cb
# BUILD_DATE=20221226
# BUILD_TAG=2022-12-26
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-12-26
begin = 2022-12-26 12:02:27.804269066+00:00
start-sync_0 = 12:04:54
start-zstd = 12:05:08
start-sync_1 = 12:09:56
end-sync_1 = 12:10:12
end = 2022-12-26 12:10:12.696544366+00:00

[server]
repo = "cake233/go-arm64"

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
go = 'go version go1.19.4 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.19.4'

[other]
workdir = "/go"
```
