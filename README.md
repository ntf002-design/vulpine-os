# Vulpine OS (based on the BlueBuild Base Images Repo)

This repo and images are based off of base images maintained by the BlueBuild org and built with the BlueBuild CLI. These images come with batteries included and were modeled after the [Ublue Main Images](https://github.com/ublue-os/main) before they were reduced in scope. Thanks to [Ublue](https://universal-blue.org/) for giving us a good starting point!

Vulpine OS is just a personal project of mine to create a semi-declarative Fedora image prior to eventually swapping out my Windows-Debian dual-boot setup. Braches will be based on Fedora OS. Main, as of right now, is Fedora 43. Vulpine OS runs a combination of LXQt and Sway, for a hybrid classic/tiling desktop experience, not often published with regular BlueBuild base images or Distro spins.
Vulpine OS is based on fedora-base-nvidia-latest.

## Images

| Recipe                                          | Image                                                        | Versions    |
|-------------------------------------------------|--------------------------------------------------------------|-------------|
| recipe/fedora-base-latest.yml                   | ghcr.io/blue-build/base-images/fedora-base                   | 44 (latest) |
| recipe/fedora-base-nvidia-latest.yml            | ghcr.io/blue-build/base-images/fedora-base-nvidia            | 44 (latest) |
| recipe/fedora-base-nvidia-gts.yml               | ghcr.io/blue-build/base-images/fedora-base-nvidia            | 43 (gts)    |
| recipe/recipe.yml (soon vulpine43.yml)          | ghcr.io/ntf002-design/vulpine-os                             | 43 (gts)    |

## Installation

To rebase an existing atomic Fedora installation to the latest build:

- First rebase to the unsigned image, to get the proper signing keys and policies installed:
  ```
  bootc switch ghcr.io/ntf002-design/vulpine-os:latest
  ```
- Reboot to complete the rebase:
  ```
  systemctl reboot
  ```
- Then rebase to the signed image, like so:
  ```
  bootc switch --enforce-container-sigpolicy ghcr.io/ntf002-design/vulpine-os:latest
  ```
- Reboot again to complete the installation
  ```
  systemctl reboot
  ```