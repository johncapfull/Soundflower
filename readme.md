# My fork of soundflower with some personal tweaks.

## How to build

- ```open Source/Soundflower.xcodeproj```
- Hit ▶️

## How to test

### Prerequisites (MacOS Catalina)

Disable System Integrity Protection.
Reset to recovery (hold Command+R while loading). Menu -> Utilities -> Terminal:
```csrutil disable```

Then reboot, go to console. Allow loading kext from any location:
```systemextensionsctl developer on```

### Testing

**Unload and remove old build (if any)**

```
sudo kextload -v /tmp/Soundflower.kext
sudo rm -R /tmp/Soundflower.kext
```

Copy and load new one
```
sudo cp -R Build/InstallerRoot/Library/Extensions/Soundflower.kext /tmp
sudo kextload -v /tmp/Soundflower.kext
```

## How to install

**Mount / in RW-mode**
```
sudo spctl --master-disable

sudo mount -uw
sudo killall Finder
```

**Copy to /System/Library/Extensions**

```sudo cp -r /tmp/Soundflower.kext /Library/Extensions```

**Reboot?**

**Profit!**