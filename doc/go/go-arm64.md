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
tag = ["latest", "2022-04-04"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "go_arm64_2022-04-04_11-11.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "39fc977216a9581b4ba754dcc114df0c5da9c0fae273729396a3c462efdd63aa"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "830M"
tar_bytes = 869830144

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "190M"
zstd_bytes = 198531216

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220321"
previous_tag = "2022-03-21"
previous_file = "go_arm64_2022-03-21_12-11-rootfs.tar.zst"
previous_sha256 = "ca21819f82b1695ff3d26299fded63c072a5c3cf4b17cffea299f9fe7081b6ce"

current_version = "latest01"
current_date = "20220404"
old_file = "go_arm64_2022-03-16_07-56-rootfs.tar.zst"
old_sha256 = "0c5d2f557764ee204efbd145d5e959f10cc691397291d5d209925c372064d59d"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2022-04-04_11-11-rootfs.tar.zst
# SHA256SUM=39fc977216a9581b4ba754dcc114df0c5da9c0fae273729396a3c462efdd63aa
# BUILD_DATE=20220404
# BUILD_TAG=2022-04-04
# STATUS=completed
# VERSION=latest01
# END_TIME=11:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-04-04
begin = 2022-04-04 11:02:31.162592506+00:00
start-sync_0 = 11:05:23
start-zstd = 11:05:38
start-sync_1 = 11:11:13
end-sync_1 = 11:11:32
end = 2022-04-04 11:11:32.724704637+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
go = 'go version go1.18 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.18'

[other]
workdir = "/go"
```
