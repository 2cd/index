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
tag = ["latest", "2022-03-07"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "go_arm64_2022-03-07_12-13.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "0ae743330893a039039144dc24b31bac4abeed4ad455189f07b605aa86b51c1e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "830M"
tar_bytes = 869616640

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "190M"
zstd_bytes = 198456660

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220301"
previous_tag = "2022-03-01"
previous_file = "go_arm64_2022-03-01_19-01-rootfs.tar.zst"
previous_sha256 = "f65a12e99ff4f362c750453f558c024a1ca9804684ae2794658a08fc12df07af"

current_version = "latest02"
current_date = "20220307"
old_file = "go_arm64_2022-02-07_12-08-rootfs.tar.zst"
old_sha256 = "0b222fde56ad636b467adaf68dd5e15039c5d5f39494f99e46a6a12502130da0"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2022-03-07_12-13-rootfs.tar.zst
# SHA256SUM=0ae743330893a039039144dc24b31bac4abeed4ad455189f07b605aa86b51c1e
# BUILD_DATE=20220307
# BUILD_TAG=2022-03-07
# STATUS=completed
# VERSION=latest02
# END_TIME=12:13

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-07
begin = 2022-03-07 12:02:37.608585905+00:00
start-sync_0 = 12:05:47
start-zstd = 12:06:11
start-sync_1 = 12:12:56
end-sync_1 = 12:13:20
end = 2022-03-07 12:13:20.797766454+00:00

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
go = 'go version go1.18rc1 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.18rc1'

[other]
workdir = "/go"
```
