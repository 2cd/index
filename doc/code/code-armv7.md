# code-armv7

## How to build and run it?

### Full

#### create a dockerfile

```sh
_TMP=$TMPDIR/tmp/code-docker
mkdir -pv $_TMP
cd $_TMP
```


```Dockerfile
cat >init.dockerfile<<-'EndOfDockerfile'
FROM cake233/code-amd64:latest

ARG _LC
ENV LANG="${_LC}.UTF-8" \
    TZ=UTC

RUN localedef \
    -c \
    -i "$_LC" \
    -f UTF-8 \
    -A /usr/share/locale/locale.alias \
    ${_LC}.UTF-8

# create a new group & user
ARG _GROUP
ARG _GID
RUN groupadd --non-unique \
    --force \
    --gid "$_GID" \
    "$_GROUP"

ARG _USER
ARG _UID
RUN useradd --non-unique \
    --gid "$_GID" \
    --uid "$_UID" \
    --groups sudo \
    --create-home \
    --shell /bin/bash \
    "$_USER"

# change password
ARG _ROOT_PASSWD
ARG _MY_PASSWD
RUN printf "%s\n" \
    "root":"$_ROOT_PASSWD" \
    "$_USER":"$_MY_PASSWD" | chpasswd -

ARG MY_HOME="/home/$_USER"

WORKDIR "$MY_HOME"

ARG CODE_DIR=".config/code-server"
ARG CODE_CONF="$CODE_DIR/config.yaml"
ARG _CODE_PASSWD

RUN code-server --version \
    && cat "$HOME/$CODE_CONF" \
    && sed -E \
    -e "s@(bind-addr:).*@\1 0.0.0.0:8080@" \
    -e "s@(password:).*@\1 $_CODE_PASSWD@" \
    -i "$HOME/$CODE_CONF" \
    && mkdir -pv "$MY_HOME/$CODE_DIR" \
    && cp -v "$HOME/$CODE_CONF" "$MY_HOME/$CODE_CONF" \
    && chown -Rv "$_UID":"$_GID" "$MY_HOME/.config" \
    && cat "$HOME/$CODE_CONF"

USER "$_UID":"$_GID"

CMD ["code-server"]
EndOfDockerfile
```

#### set env

```sh
# en_US, zh_CN, es_ES, de_DE, etc.
# _LC=en_US
_LC=${LANG%.*}

# If LANG or _LC is empty, then _LC=C
_LC=${_LC:-C}

_UID=$(id -u)
# It is not recommended or necessary to use root(uid=0).
case "$_UID" in
0)
    _UID=1002
    _GID=1002
    _USER=moe
    ;;
*)
    _GID=$(id -g)
    _USER=$(whoami)
    ;;
esac
_GROUP="$_USER"

_Root_passwd="123456780_this_password_is_too_simple"
_My_passwd="0_123_456_789-Oh-No-My_password_can_not_be_that_simple."
_Code_passwd="You_should_set_a_complex_password_and_if_you_need_to_expose_the_service_to_the_internet_then_you_can_use_the_nginx_reverse_proxy-code:8080"

if [ -n "$(command -v pwgen)" ]; then
    _Code_passwd=$(pwgen -snc1 200)
elif [ -n "$(command -v apt-get)" ];then
    sudo apt update
    sudo apt install pwgen -y
    _Code_passwd=$(pwgen -snc1 300)
fi

_Code_image_tag="code-image"

export _LC _UID _GID _USER _GROUP _Root_passwd _My_passwd _Code_passwd _Code_image_tag
```

#### build container

```sh
docker build \
    --pull \
    -f ./init.dockerfile \
    --build-arg _LC="$_LC" \
    --build-arg _USER="$_USER" \
    --build-arg _GROUP="$_GROUP" \
    --build-arg _UID="$_UID" \
    --build-arg _GID="$_GID" \
    --build-arg _ROOT_PASSWD="$_Root_passwd" \
    --build-arg _MY_PASSWD="$_My_passwd" \
    --build-arg _CODE_PASSWD="$_Code_passwd" \
    -t "$_Code_image_tag" \
    .
```

#### run

```sh
# test1

_Host_tcp_port=18080
# docker run -it --rm -p "$_Host_tcp_port":8080 "$_Code_image_tag" bash

# test2
_Shared_dir="$HOME/.local/share/code-shared-dir"
mkdir -pv "$_Shared_dir/hello-world"

docker run \
    --restart always \
    --name code \
    -v "$_Shared_dir":"/home/$_USER/shared_dir" \
    -p "$_Host_tcp_port":8080 \
    "$_Code_image_tag" &

sleep 3

docker exec -t code sh -c 'bat -pp ~/.config/code-server/config.yaml'

# Get ip(v4) address
# ip -4 a
# Open your browser, and type the address
# ip:port
# For example, assume your ip is 172.x.x.y, port is 18080, then the address is http://172.x.x.y:18080
```

### Lite

Do we really have to use such tedious steps as above?

No! Although the steps are similar to those above, they are much simpler.

#### copy the necessary folder to the temporary directory

```sh
TMP=$TMPDIR/tmp/code-docker
mkdir -pv $TMP
cd $TMP
docker pull cake233/code-armv7
docker run -t --rm -v $TMP:/tmp/init cake233/code-armv7 sh -c "cp -fpv /root/* /tmp/init"
```

#### set env

```sh
editor 0.set || nano 0.set

. 0.set
```

#### build

```sh
. 1.build
```

#### run

```
. 2.run
```


## code-armv7.toml

```toml
[main]
name = "code"
tag = ["latest", "2022-07-11", "vsc", "vscode", "web"]
os = "debian"
release = "sid"
arch = "armhf"
platform = "linux/arm/v7"
xorg_or_wayland = false
syntax_version = "0.0.0-alpha.4"

[file]
name = "code_armhf_2022-07-11_12-10.tar.zst"

# This value can be used to verify the integrity of the file
sha256 = "8f1da2121159b98d1d76bfe6448c981f32fc29bab392ca7cea28061fbae4f505"

# zstd: [1-22]
zstd-level = 22

[file.size]
# Installed size ??? tar-size
# Installed size is approximately equal to the size of the tar file
tar = "480M"
tar_bytes = 502429696

# Space occupied ??? tar-size + zstd-size
# You will need to prepare a large enough space before installation.
zstd = "90M"
zstd_bytes = 93332988

[compatibility]
compatible_mode = true

previous_version = "latest01"

# The value is &str, not int
previous_date = "20220627"
previous_tag = "2022-06-27"
previous_file = "code_armhf_2022-06-27_12-12-rootfs.tar.zst"
previous_sha256 = "cc7868e7b983b672ec7f5a5315c52aeb31c77495a8674d26e2786399f57684d7"

current_version = "latest02"
current_date = "20220711"
old_file = "code_armhf_2022-06-13_12-11-rootfs.tar.zst"
old_sha256 = "8342c29d53965a8198747b9e02c80aba39424437046f64ae06f94a8f6b47ea05"
# edition 2021
# DISTRO_NAME=code_armhf
# ROOTFS_FILE=code_armhf_2022-07-11_12-10-rootfs.tar.zst
# SHA256SUM=8f1da2121159b98d1d76bfe6448c981f32fc29bab392ca7cea28061fbae4f505
# BUILD_DATE=20220711
# BUILD_TAG=2022-07-11
# STATUS=completed
# VERSION=latest02
# END_TIME=12:10

[time]
format = "rfc-3339"
zone = "UTC"
date = 2022-07-11
begin = 2022-07-11 12:02:28.742187327+00:00
start-sync_0 = 12:07:04
start-zstd = 12:07:29
start-sync_1 = 12:10:31
end-sync_1 = 12:10:41
end = 2022-07-11 12:10:41.217386781+00:00

[server]
repo = "cake233/code-armv7"

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

# Environment variables  (??????????????)
[env]
LANG = "en_US.UTF-8"

[version]
ldd = 'ldd (Debian GLIBC 2.33-8) 2.33'
code = '4.5.0 02b9d7ee856e31d9008d1ff24a175ff03b49010e with Code 1.68.1'

[port]
tcp = [8080]
```
