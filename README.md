# homebrew-rkdeveloptool

🧰 Homebrew Tap for Rockchip flashing and debugging tools.

## 📦 Included Formulae

### 🔧 rkdeveloptool

Tool for flashing and debugging Rockchip devices over USB.

- **Version:** 1.32
- **Source:** [rockchip-linux/rkdeveloptool](https://github.com/rockchip-linux/rkdeveloptool)
- **Note:** Version 1.32 corresponds to commit `304f073752fd25c854e1bcf05d8e7f925b1f4e14`, as the upstream project does not use Git tags or releases.

## 💻 Installation

```bash
brew tap IgorKha/rkdeveloptool
brew trust --formula IgorKha/rkdeveloptool/rkdeveloptool
brew install rkdeveloptool
```

### Homebrew Trust Warning

Recent versions of Homebrew require explicit trust for third-party taps.

If you see a message like:

```text
Error: Refusing to load formula igorkha/rkdeveloptool/rkdeveloptool from untrusted tap igorkha/rkdeveloptool.
```

run:

```bash
brew trust --formula IgorKha/rkdeveloptool/rkdeveloptool
```

Or to trust the entire tap:

```bash
brew trust IgorKha/rkdeveloptool
```

and then retry the installation/upgrade.

## 📖 Documentation

- 📘 [Official Rockchip Wiki](https://opensource.rock-chips.com/wiki_Rkdeveloptool)
- 📘 [Radxa Docs – rkdeveloptool usage](https://docs.radxa.com/en/template/module/radxa-os/low-level-dev/rkdeveloptool)

These guides include examples of flashing, reading device info, writing images, and more.

## 🛠️ Basic Usage

> [!IMPORTANT]
> If your rockchip device is not detected, try connecting it via usb 2.0 adapter or usb hub.

```bash
# List connected Maskrom devices
rkdeveloptool ld

# Download loader (loader must be appropriate for your device)
rkdeveloptool db <loader>

# Write image to device at offset 0
rkdeveloptool wl 0 <image>
```

> [!NOTE]
>
> - Compressed files must be extracted before flashing.
> - Only one device/storage medium should be connected; multiple targets are not supported.
> - To flash multiple devices simultaneously, use `upgrade_tool`.

📦 **Loader & Image Downloads**:

- rkbin repo: [rockchip-linux/rkbin](https://github.com/rockchip-linux/rkbin/tree/master)
- Radxa: [https://dl.radxa.com](https://dl.radxa.com)
- Rockchip BSP: [https://opensource.rock-chips.com/wiki_Boot_option#Download](https://opensource.rock-chips.com/wiki_Boot_option#Download)
