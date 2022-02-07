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
tag = ["latest", "2022-02-07"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "go_arm64_2022-02-07_12-08.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "0b222fde56ad636b467adaf68dd5e15039c5d5f39494f99e46a6a12502130da0"

# zstd: [1-22]
zstd-level = 20

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "816M"
tar_bytes = 855552000

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "197M"
zstd_bytes = 205825444

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220124"
previous_tag = "2022-01-24"
previous_file = "go_arm64_2022-01-24_12-08-rootfs.tar.zst"
previous_sha256 = "47f0c8c6e321eb3bab03a8dc5d9e1673743f326457301ea371d24760263cc38f"

current_version = "latest02"
current_date = "20220207"
old_file = "go_arm64_2022-01-10_12-09-rootfs.tar.zst"
old_sha256 = "9801605ee09a23df6d898d2d6cbef136b6d8d5cb559377a4ce62a5860762a3d5"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2022-02-07_12-08-rootfs.tar.zst
# SHA256SUM=0b222fde56ad636b467adaf68dd5e15039c5d5f39494f99e46a6a12502130da0
# BUILD_DATE=20220207
# BUILD_TAG=2022-02-07
# STATUS=completed
# VERSION=latest02
# END_TIME=12:08

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-02-07
begin = 2022-02-07 12:02:33.219291168+00:00
start-sync_0 = 12:04:53
start-zstd = 12:05:10
start-sync_1 = 12:08:15
end-sync_1 = 12:08:34
end = 2022-02-07 12:08:34.816307402+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u2) 2.31'
go = 'go version go1.17.6 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.17.6'

[other]
workdir = "/go"
```
