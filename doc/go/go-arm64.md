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
tag = ["latest", "2022-03-16"]
os = "debian"
release = "stable"
arch = "arm64"
platform = "linux/arm64"
x11_or_wayland = false

[file]
name = "go_arm64_2022-03-16_07-56.tar.zst"

version = "0.0.0-alpha.2"

# This value can be used to verify the integrity of the file
sha256 = "0c5d2f557764ee204efbd145d5e959f10cc691397291d5d209925c372064d59d"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "830M"
tar_bytes = 869828608

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "190M"
zstd_bytes = 198486611

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220307"
previous_tag = "2022-03-07"
previous_file = "go_arm64_2022-03-07_12-13-rootfs.tar.zst"
previous_sha256 = "0ae743330893a039039144dc24b31bac4abeed4ad455189f07b605aa86b51c1e"

current_version = "latest01"
current_date = "20220316"
old_file = "go_arm64_2022-03-01_19-01-rootfs.tar.zst"
old_sha256 = "f65a12e99ff4f362c750453f558c024a1ca9804684ae2794658a08fc12df07af"
# edition 2021
# DISTRO_NAME=go_arm64
# ROOTFS_FILE=go_arm64_2022-03-16_07-56-rootfs.tar.zst
# SHA256SUM=0c5d2f557764ee204efbd145d5e959f10cc691397291d5d209925c372064d59d
# BUILD_DATE=20220316
# BUILD_TAG=2022-03-16
# STATUS=completed
# VERSION=latest01
# END_TIME=07:56

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-03-16
begin = 2022-03-16 07:48:43.645601235+00:00
start-sync_0 = 07:51:21
start-zstd = 07:51:39
start-sync_1 = 07:56:39
end-sync_1 = 07:56:58
end = 2022-03-16 07:56:58.902032026+00:00

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
go = 'go version go1.18 linux/arm64'
gofmt = '/usr/local/go/bin/gofmt: go1.18'

[other]
workdir = "/go"
```
