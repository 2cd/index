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
tag = ["latest", "2022-07-11"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_arm64_2022-07-11_12-12.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "7dd38b14af30535a88cac592a52a77a1ec46888c75f57ce438dc1fed20a19195"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "831M"
tar_bytes = 870749184

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "190M"
zstd_bytes = 198745286

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220627"
previous_tag = "2022-06-27"
previous_file = "go_arm64_2022-06-27_12-10-rootfs.tar.zst"
previous_sha256 = "a87c811528e4eb84c46fc4c0b0706e46f30297166dc872c151d18a0c0f629e18"

current_version = "latest02"
current_date = "20220711"
old_file = "go_arm64_2022-06-13_12-12-rootfs.tar.zst"
old_sha256 = "23898611b037545c88a8ba13e342340f989a9fdaa13e1d9c5d7e3769aeb6e269"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2022-07-11_12-12-rootfs.tar.zst
# SHA256SUM=7dd38b14af30535a88cac592a52a77a1ec46888c75f57ce438dc1fed20a19195
# BUILD_DATE=20220711
# BUILD_TAG=2022-07-11
# STATUS=completed
# VERSION=latest02
# END_TIME=12:12

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-11
begin = 2022-07-11 12:02:34.135063600+00:00
start-sync_0 = 12:06:16
start-zstd = 12:06:42
start-sync_1 = 12:12:17
end-sync_1 = 12:12:39
end = 2022-07-11 12:12:39.801221802+00:00

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
ldd = 'ldd (Debian GLIBC 2.31-13+deb11u3) 2.31'
go = 'go version go1.18.3 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.18.3'

[other]
workdir = "/go"
```
