# dotnet-amd64

## Example

```sh
TMP="/tmp/hello"
mkdir -p "$TMP"

docker run \
    -t \
    --rm \
    -v "$TMP":/app \
    -w /app \
    cake233/dotnet-amd64 \
    dotnet new console -o world

docker run \
    -t \
    --rm \
    -v "$TMP"/world:/app \
    -w /app \
    cake233/dotnet-amd64 \
    dotnet run --verbosity 4
```

## How to exec shell?

```sh
docker run \
    -it \
    --name dotnet-amd64 \
    cake233/dotnet-amd64
```

You can also specify the absolute path to the shell.

```sh
docker exec -it dotnet-amd64 /usr/local/powershell/pwsh
```


## dotnet-amd64.toml

```toml
[main]
name = "dotnet"
tag = ["latest", "2022-09-12", ".NET", "dotnet-sdk"]
os = "arch"
release = "latest"
arch = "amd64"
platform = "linux/amd64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "dotnet_amd64_2022-09-12_12-18.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "ee681f1660b39f4ce67622064584fdc571dcd017e2d0cb54c8d9428caae0397e"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.7G"
tar_bytes = 1742790656

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "407M"
zstd_bytes = 425828375

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20220829"
previous_tag = "2022-08-29"
previous_file = "dotnet_amd64_2022-08-29_12-17-rootfs.tar.zst"
previous_sha256 = "3e0be5a4636e17533e92d0181f1a9d9dd04871ad071400afb830c21aaac80110"

current_version = "latest01"
current_date = "20220912"
old_file = "dotnet_amd64_2022-08-15_12-18-rootfs.tar.zst"
old_sha256 = "441a40f585a2cdfe8bccbec70f4db608f5a665d6e481237192f0612ab126bbd3"
# edition 2021
# DISTRO_NAME=dotnet_amd64
# ROOTFS_FILE=dotnet_amd64_2022-09-12_12-18-rootfs.tar.zst
# SHA256SUM=ee681f1660b39f4ce67622064584fdc571dcd017e2d0cb54c8d9428caae0397e
# BUILD_DATE=20220912
# BUILD_TAG=2022-09-12
# STATUS=completed
# VERSION=latest01
# END_TIME=12:18

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-09-12
begin = 2022-09-12 12:02:32.573593918+00:00
start-sync_0 = 12:06:54
start-zstd = 12:07:48
start-sync_1 = 12:18:13
end-sync_1 = 12:18:49
end = 2022-09-12 12:18:49.694783134+00:00

[server]
repo = "cake233/dotnet-amd64"

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
ldd = 'ldd (GNU libc) 2.36'
git = 'git version 2.37.3'
dotnet = '6.0.400'
powershell = 'PowerShell 7.2.6'
dotnet_info = '''
.NET SDK (reflecting any global.json):
 Version:   6.0.400
 Commit:    7771abd614

Runtime Environment:
 OS Name:     arch
 OS Version:  
 OS Platform: Linux
 RID:         arch-x64
 Base Path:   /usr/local/dotnet/sdk/6.0.400/

global.json file:
  Not found

Host:
  Version:      6.0.8
  Architecture: x64
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
