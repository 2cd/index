# dotnet-arm64

## Example

```sh
TMP="/tmp/hello"
mkdir -p "$TMP"

docker run \
    -t \
    --rm \
    -v "$TMP":/app \
    -w /app \
    cake233/dotnet-arm64 \
    dotnet new console -o world

docker run \
    -t \
    --rm \
    -v "$TMP"/world:/app \
    -w /app \
    cake233/dotnet-arm64 \
    dotnet run --verbosity 4
```

## How to exec shell?

```sh
docker run \
    -it \
    --name dotnet-arm64 \
    cake233/dotnet-arm64
```

You can also specify the absolute path to the shell.

```sh
docker exec -it dotnet-arm64 /usr/local/powershell/pwsh
```


## dotnet-arm64.toml

```toml
[main]
name = "dotnet"
tag = ["latest", "2022-08-29", ".NET", "dotnet-sdk"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "dotnet_arm64_2022-08-29_12-30.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "502a13ee0bd1df382348afcd84faa52c1ae319894bce3b7a817c371d17ced93f"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1720290304

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "385M"
zstd_bytes = 403698994

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220815"
previous_tag = "2022-08-15"
previous_file = "dotnet_arm64_2022-08-15_12-28-rootfs.tar.zst"
previous_sha256 = "fff76d0354865c812a141c63e6d51a74816fbcffb1524c45c67f2b31b7eb9690"

current_version = "latest02"
current_date = "20220829"
old_file = "dotnet_arm64_2022-07-04_13-52-rootfs.tar.zst"
old_sha256 = "24d62b85fd51a064d09f6c4b151f388f49be8cc6019229f368b17a8e18bdc911"
# edition 2021
# DISTRO_NAME=dotnet_arm64
# ROOTFS_FILE=dotnet_arm64_2022-08-29_12-30-rootfs.tar.zst
# SHA256SUM=502a13ee0bd1df382348afcd84faa52c1ae319894bce3b7a817c371d17ced93f
# BUILD_DATE=20220829
# BUILD_TAG=2022-08-29
# STATUS=completed
# VERSION=latest02
# END_TIME=12:30

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-08-29
begin = 2022-08-29 12:02:28.973250022+00:00
start-sync_0 = 12:19:05
start-zstd = 12:19:50
start-sync_1 = 12:30:03
end-sync_1 = 12:30:34
end = 2022-08-29 12:30:34.271341756+00:00

[server]
repo = "cake233/dotnet-arm64"

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
PATH = "/usr/local/powershell:/usr/local/dotnet/bin${PATH:+:${PATH}}"
DOTNET_ROOT = "/usr/local/dotnet"
DOTNET_RUNNING_IN_CONTAINER = true
ASPNETCORE_URLS = ""
DOTNET_GENERATE_ASPNET_CERTIFICATE = false
DOTNET_USE_POLLING_FILE_WATCHER = true
Logging__Console__FormatterName = ""
NUGET_XMLDOC_MODE = "skip"

[version]
ldd = 'ldd (GNU libc) 2.35'
git = 'git version 2.37.2'
dotnet = '6.0.400'
powershell = 'PowerShell 7.2.6'
dotnet_info = '''
.NET SDK (reflecting any global.json):
 Version:   6.0.400
 Commit:    7771abd614

Runtime Environment:
 OS Name:     archarm
 OS Version:  
 OS Platform: Linux
 RID:         linux-arm64
 Base Path:   /usr/local/dotnet/sdk/6.0.400/

global.json file:
  Not found

Host:
  Version:      6.0.8
  Architecture: arm64
  Commit:       55fb7ef977

.NET SDKs installed:
  6.0.400 [/usr/local/dotnet/sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 6.0.8 [/usr/local/dotnet/shared/Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 6.0.8 [/usr/local/dotnet/shared/Microsoft.NETCore.App]

Download .NET:
  https://aka.ms/dotnet-download

Learn about .NET Runtimes and SDKs:
  https://aka.ms/dotnet/runtimes-sdk-info
'''

[other]
cmd = "/usr/local/powershell/pwsh"
```
