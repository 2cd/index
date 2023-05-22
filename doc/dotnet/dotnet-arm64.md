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
tag = ["latest", "2023-05-22", ".NET", "dotnet-sdk"]
os = "arch"
release = "latest"
arch = "arm64"
platform = "linux/arm64"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "dotnet_arm64_2023-05-22_12-33.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "1c36ee7b2d4eeac0f11c74ac90266c9e8e1c2a761241cdda65791b148cb9ad70"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ≈ tar-size
# Installed size is approximately equal to the size of the tar file
tar = "1.8G"
tar_bytes = 1838830080

# Space occupied ≈ tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "411M"
zstd_bytes = 430472102

[compatibility]
compatible_mode = true

previous_version = "latest02"

# The value is &str, not int
previous_date = "20230508"
previous_tag = "2023-05-08"
previous_file = "dotnet_arm64_2023-05-08_12-40-rootfs.tar.zst"
previous_sha256 = "f90970d029a0256253c66fe34ef48e90a7a6a1f6628d1ea9f0a5deec7b6502bc"

current_version = "latest01"
current_date = "20230522"
old_file = "dotnet_arm64_2023-04-24_12-34-rootfs.tar.zst"
old_sha256 = "bad619836e5a9312cbf2504213f09586adbf2bd5e061a5210a8d64ac3b0a1c4b"
# edition 2021
# DISTRO_NAME=dotnet_arm64
# ROOTFS_FILE=dotnet_arm64_2023-05-22_12-33-rootfs.tar.zst
# SHA256SUM=1c36ee7b2d4eeac0f11c74ac90266c9e8e1c2a761241cdda65791b148cb9ad70
# BUILD_DATE=20230522
# BUILD_TAG=2023-05-22
# STATUS=completed
# VERSION=latest01
# END_TIME=12:33

[time]
format = "rfc-3339"
zone = "UTC"
date = 2023-05-22
begin = 2023-05-22 12:02:38.036954151+00:00
start-sync_0 = 12:21:23
start-zstd = 12:22:13
start-sync_1 = 12:32:50
end-sync_1 = 12:33:22
end = 2023-05-22 12:33:22.444217796+00:00

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
git = 'git version 2.40.1'
dotnet = '7.0.302'
powershell = 'PowerShell 7.3.4'
dotnet_info = '''
.NET SDK:
 Version:   7.0.302
 Commit:    990cf98a27

Runtime Environment:
 OS Name:     archarm
 OS Version:  
 OS Platform: Linux
 RID:         linux-arm64
 Base Path:   /usr/local/dotnet/sdk/7.0.302/

Host:
  Version:      7.0.5
  Architecture: arm64
  Commit:       8042d61b17

.NET SDKs installed:
  7.0.302 [/usr/local/dotnet/sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 7.0.5 [/usr/local/dotnet/shared/Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 7.0.5 [/usr/local/dotnet/shared/Microsoft.NETCore.App]

Other architectures found:
  None

Environment variables:
  DOTNET_ROOT       [/usr/local/dotnet]

global.json file:
  Not found

Learn more:
  https://aka.ms/dotnet/info

Download .NET:
  https://aka.ms/dotnet/download
'''

[other]
cmd = "/usr/local/powershell/pwsh"
```
