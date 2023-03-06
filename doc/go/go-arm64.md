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
tag = ["latest", "2023-03-06"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_arm64_2023-03-06_12-09.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a7ec5aea99d6eeb60f7bcca12bcdf3b948455531458ba2e7b45b7cf297cad105"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "759M"
tar_bytes = 795819520

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "182M"
zstd_bytes = 190267704

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20230220"
previous_tag = "2023-02-20"
previous_file = "go_arm64_2023-02-20_12-10-rootfs.tar.zst"
previous_sha256 = "87cc0cfc220037ffb13be78a9069f76f1659ebc56c03094cd783df84b8e5b426"

current_version = "latest02"
current_date = "20230306"
old_file = "go_arm64_2023-02-06_12-09-rootfs.tar.zst"
old_sha256 = "442254a8f27d7c9ab9918ab05fd2df482d30f2d29833cc1ddfd0872f39cd70a3"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2023-03-06_12-09-rootfs.tar.zst
# SHA256SUM=a7ec5aea99d6eeb60f7bcca12bcdf3b948455531458ba2e7b45b7cf297cad105
# BUILD_DATE=20230306
# BUILD_TAG=2023-03-06
# STATUS=completed
# VERSION=latest02
# END_TIME=12:09

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-06
begin = 2023-03-06 12:02:34.479926280+00:00
start-sync_0 = 12:04:42
start-zstd = 12:04:54
start-sync_1 = 12:09:30
end-sync_1 = 12:09:45
end = 2023-03-06 12:09:45.307453503+00:00

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
go = 'go version go1.20.1 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.20.1'

[other]
workdir = "/go"
```
