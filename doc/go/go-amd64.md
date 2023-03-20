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
tag = ["latest", "2023-03-20"]
os = "debian"
release = "stable"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_amd64_2023-03-20_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ee595446950d3eb53d5faab4171aa366ccbd8b703003a6cea0145cfefac3965f"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "790M"
tar_bytes = 827526144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "184M"
zstd_bytes = 191923812

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230306"
previous_tag = "2023-03-06"
previous_file = "go_amd64_2023-03-06_12-10-rootfs.tar.zst"
previous_sha256 = "390102cfa736a1d9b0cd2f1377de5649f0d3db1c0d90ff6b12a7de1c3536b320"

current_version = "latest01"
current_date = "20230320"
old_file = "go_amd64_2023-02-20_12-09-rootfs.tar.zst"
old_sha256 = "53d1e04be57f5fd3c94b1380c7d4c9cb34aed08fc845bd327aadbbd7cb96339f"
# edition 2021
# DISTRO_NAME=go_amd64
# ROOTFS_FILE=go_amd64_2023-03-20_12-10-rootfs.tar.zst
# SHA256SUM=ee595446950d3eb53d5faab4171aa366ccbd8b703003a6cea0145cfefac3965f
# BUILD_DATE=20230320
# BUILD_TAG=2023-03-20
# STATUS=completed
# VERSION=latest01
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-03-20
begin = 2023-03-20 12:02:37.686697737+00:00
start-sync_0 = 12:03:49
start-zstd = 12:04:38
start-sync_1 = 12:10:10
end-sync_1 = 12:10:27
end = 2023-03-20 12:10:27.306005086+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u5) 2.31'
go = 'go version go1.20.2 linux/amd64'
gofmt = '/usr/local/go/bin/gofmt: go1.20.2'

[other]
workdir = "/go"
```
