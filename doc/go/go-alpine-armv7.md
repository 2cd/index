# go-alpine-armv7

## How to run it?

```sh
docker run \
    -it \
    --name go-alpine-armv7 \
    cake233/go-alpine-armv7
```

## How to exec shell?

```sh
docker exec -it go-alpine-armv7 bash
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
    cake233/go-alpine-armv7 \
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

## go-alpine-armv7.toml

```toml
[main]
name = "go"
tag = ["alpine", "2022-05-16", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_armhf_2022-05-16_12-07.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "a51c001d5b02f4eff10abfd5a4abc73c8a953821dbdc7b8758c6971bbf3a53a3"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "317M"
tar_bytes = 332288000

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "77M"
zstd_bytes = 80540647

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220502"
previous_tag = "2022-05-02"
previous_file = "go-musl_armhf_2022-05-02_12-07-rootfs.tar.zst"
previous_sha256 = "a8a4ed9ae4c1436b8d98da4240a5cdce23e93ed32ade9cd5c43f50f0bf01367b"

current_version = "latest02"
current_date = "20220516"
old_file = "go-musl_armhf_2022-04-18_12-07-rootfs.tar.zst"
old_sha256 = "f9c0a2823dff1fac2baf9d4e622c75fac2e1b33f5e3285f8df4613037f609f39"
# edition 2021
# DISTRO_NAME=go_armhf
# ROOTFS_FILE=go-musl_armhf_2022-05-16_12-07-rootfs.tar.zst
# SHA256SUM=a51c001d5b02f4eff10abfd5a4abc73c8a953821dbdc7b8758c6971bbf3a53a3
# BUILD_DATE=20220516
# BUILD_TAG=2022-05-16
# STATUS=completed
# VERSION=latest02
# END_TIME=12:07

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-05-16
begin = 2022-05-16 12:02:37.597281325+00:00
start-sync_0 = 12:03:35
start-zstd = 12:03:44
start-sync_1 = 12:06:59
end-sync_1 = 12:07:10
end = 2022-05-16 12:07:10.713355303+00:00

[server]
repo = "cake233/go-alpine-armv7"

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
LANG = "C.UTF-8"
PATH = "/go/bin:/usr/local/go/bin${PATH:+:${PATH}}"
GOPATH = "/go"

[version]
ldd = 'musl libc (armhf) Version 1.2.2'
go = 'go version go1.18.2 linux/arm'
gofmt = '/usr/local/go/bin/gofmt: go1.18.2'

[other]
workdir = "/go"
```
