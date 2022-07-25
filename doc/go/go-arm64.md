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
tag = ["latest", "2022-07-25"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go_arm64_2022-07-25_12-11.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "903b0be9e25c23effa8a7ca2e0edf6b4ad413ebf052bfe10bfbd368a32f9e036"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "831M"
tar_bytes = 870941696

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "190M"
zstd_bytes = 198781419

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220711"
previous_tag = "2022-07-11"
previous_file = "go_arm64_2022-07-11_12-12-rootfs.tar.zst"
previous_sha256 = "7dd38b14af30535a88cac592a52a77a1ec46888c75f57ce438dc1fed20a19195"

current_version = "latest01"
current_date = "20220725"
old_file = "go_arm64_2022-06-27_12-10-rootfs.tar.zst"
old_sha256 = "a87c811528e4eb84c46fc4c0b0706e46f30297166dc872c151d18a0c0f629e18"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2022-07-25_12-11-rootfs.tar.zst
# SHA256SUM=903b0be9e25c23effa8a7ca2e0edf6b4ad413ebf052bfe10bfbd368a32f9e036
# BUILD_DATE=20220725
# BUILD_TAG=2022-07-25
# STATUS=completed
# VERSION=latest01
# END_TIME=12:11

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-25
begin = 2022-07-25 12:02:38.120206808+00:00
start-sync_0 = 12:05:09
start-zstd = 12:05:23
start-sync_1 = 12:11:13
end-sync_1 = 12:11:30
end = 2022-07-25 12:11:30.523447623+00:00

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
go = 'go version go1.18.4 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.18.4'

[other]
workdir = "/go"
```
