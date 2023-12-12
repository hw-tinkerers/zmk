# Zephyr™ Mechanical Keyboard (ZMK) Firmware

[![Discord](https://img.shields.io/discord/719497620560543766)](https://zmk.dev/community/discord/invite)
[![Build](https://github.com/zmkfirmware/zmk/workflows/Build/badge.svg)](https://github.com/zmkfirmware/zmk/actions)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v2.0%20adopted-ff69b4.svg)](CODE_OF_CONDUCT.md)

[ZMK Firmware](https://zmk.dev/) is an open source ([MIT](LICENSE)) keyboard firmware built on the [Zephyr™ Project](https://www.zephyrproject.org/) Real Time Operating System (RTOS). ZMK's goal is to provide a modern, wireless, and powerful firmware free of licensing issues.

Check out the website to learn more: https://zmk.dev/.

You can also come join our [ZMK Discord Server](https://zmk.dev/community/discord/invite).

To review features, check out the [feature overview](https://zmk.dev/docs/). ZMK is under active development, and new features are listed with the [enhancement label](https://github.com/zmkfirmware/zmk/issues?q=is%3Aissue+is%3Aopen+label%3Aenhancement) in GitHub. Please feel free to add 👍 to the issue description of any requests to upvote the feature.

Steps to setup toolchain:

1. Install west

For macos and windows users:

```
pip3 install -U west
```

For Linux users:

```
pip3 install --user -U west
```

2. Verify West is installed (For Linux and Windows users):

```
west --version
```

This should print a message like "West version: v0.14.0". If it prints an error instead, make sure ~/.local/bin is on your PATH environment variable.

You can add it with these commands (For linux users):

```
echo 'export PATH=~/.local/bin:"$PATH"' >> ~/.bashrc
source ~/.bashrc
```

You can add it with these commands (For Windows users):

```
$Scripts = python -c "import sysconfig; print(sysconfig.get_path('scripts'))"
$Path = [Environment]::GetEnvironmentVariable('PATH', 'User')
[Environment]::SetEnvironmentVariable('PATH', "$Path;$Scripts", 'User')
$env:PATH += ";$Scripts"
```

3. Get source code:

```
git clone git@github.com:hw-tinkerers/zmk.git
```

4. setup the workspace

```
cd zmk
```

```
west init -l app/
```

```
west update
```

```
west zephyr-export
```

For mac and windows users:

```
pip3 install -r zephyr/scripts/requirements.txt
```

For linux users:

```
pip3 install --user -r zephyr/scripts/requirements.txt
```

5. Build your code after customixing your keymap or default:
   To know more about customizing keymaps visit [this](https://github.com/hw-tinkerers/tr60-zmk-config) link
   You have successfully setup your worksapce.
   To build your code to flash to TR60 keyboard, run this command.

```
west build -p auto -b tr60 app/
```

6. Copy your uf2 file to desktop to flash to your keyboard

```
cp build/zephyr/zmk.uf2 ~/Desktop
```
