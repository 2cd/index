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
tag = ["alpine", "2022-06-13", "musl-libc", "musl"]
os = "alpine"
release = "stable"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "go-musl_armhf_2022-06-13_12-06.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "df731661ee01057437092f054e0458b2fb43018b88a4583f9cb484c3b31e17f1"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "317M"
tar_bytes = 332316672

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "77M"
zstd_bytes = 80574635

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220530"
previous_tag = "2022-05-30"
previous_file = "go-musl_armhf_2022-05-30_12-06-rootfs.tar.zst"
previous_sha256 = "1e03520a8f254654f0da5e61b2768df4cc745fa5df3af9870364e1c54ad8aedc"

current_version = "latest02"
current_date = "20220613"
old_file = "go-musl_armhf_2022-05-16_12-07-rootfs.tar.zst"
old_sha256 = "a51c001d5b02f4eff10abfd5a4abc73c8a953821dbdc7b8758c6971bbf3a53a3"
# edition 2021
# DISTRO_NAME=go_armhf
# ROOTFS_FILE=go-musl_armhf_2022-06-13_12-06-rootfs.tar.zst
# SHA256SUM=df731661ee01057437092f054e0458b2fb43018b88a4583f9cb484c3b31e17f1
# BUILD_DATE=20220613
# BUILD_TAG=2022-06-13
# STATUS=completed
# VERSION=latest02
# END_TIME=12:06

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-06-13
begin = 2022-06-13 12:02:34.308959154+00:00
start-sync_0 = 12:03:26
start-zstd = 12:03:36
start-sync_1 = 12:06:40
end-sync_1 = 12:06:50
end = 2022-06-13 12:06:50.650661451+00:00

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
ldd = 'musl libc (armhf) Version 1.2.3'
go = 'go version go1.18.3 linux/arm'
gofmt = '/usr/local/go/bin/gofmt: go1.18.3'

[other]
workdir = "/go"
```
