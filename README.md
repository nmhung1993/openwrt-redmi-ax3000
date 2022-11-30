# openwrt-redmi-ax3000

Openwrt for Redmi AX3000 / Xiaomi CR8806 / Xiaomi CR8808

| Device        | Status   |
| :-:           | :-:      |
| Redmi AX3000  | Not test |
| Xiaomi CR8806 | ✔️      |
| Xiaomi CR8808 | Not test |

## How to build

OS: `Ubuntu 20.04 (focal)`

```bash
# Install dependents
sudo add-apt-repository ppa:npalix/coccinelle
sudo apt update
sudo apt install build-essential clang flex g++ gawk gcc-multilib gettext \
  git libncurses5-dev libssl-dev python3-distutils rsync unzip zlib1g-dev \
  coccinelle

# Clone this repo
git clone https://github.com/hzyitc/openwrt-redmi-ax3000
cd openwrt-redmi-ax3000

# Update and install feeds
./scripts/feeds update -a
./scripts/feeds install -a

# Configure
make menuconfig

# Download
make -j16 download

# Build
make -j$(nproc)
```

## Related link

[`openwrt/openwrt`](https://github.com/openwrt/openwrt) - Openwrt offical

[`qsdk`](https://git.codelinaro.org/clo/qsdk) - QSDK offical

[`quic/qca-sdk-nss-fw`](https://github.com/quic/qca-sdk-nss-fw) - NSS firmware

[`quic/upstream-wifi-fw`](https://github.com/quic/upstream-wifi-fw) - WiFi firmware

[`qca/qca-swiss-army-knife`](https://github.com/qca/qca-swiss-army-knife) - BDF tools

[`Telecominfraproject/wlan-ap`](https://github.com/Telecominfraproject/wlan-ap) - another Openwrt which support `ipq50xx`
