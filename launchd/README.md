# Run Kanata in the background on macOS

These two LaunchDaemons replace the two foreground Terminal processes:

- `com.wesleyboar.kanata-vhid.plist` runs the Karabiner virtual-HID daemon.
- `com.wesleyboar.kanata.plist` runs Kanata with `left-hand.kbd`.

Install them from this repository:

```sh
sudo cp launchd/com.wesleyboar.kanata-vhid.plist /Library/LaunchDaemons/
sudo cp launchd/com.wesleyboar.kanata.plist /Library/LaunchDaemons/
sudo chown root:wheel /Library/LaunchDaemons/com.wesleyboar.kanata-vhid.plist
sudo chown root:wheel /Library/LaunchDaemons/com.wesleyboar.kanata.plist
sudo chmod 644 /Library/LaunchDaemons/com.wesleyboar.kanata-vhid.plist
sudo chmod 644 /Library/LaunchDaemons/com.wesleyboar.kanata.plist
sudo launchctl bootstrap system /Library/LaunchDaemons/com.wesleyboar.kanata-vhid.plist
sudo launchctl bootstrap system /Library/LaunchDaemons/com.wesleyboar.kanata.plist
```

Verify:

```sh
sudo launchctl print system/com.wesleyboar.kanata-vhid
sudo launchctl print system/com.wesleyboar.kanata
```

After editing the config, reload Kanata with:

```sh
sudo launchctl kickstart -k system/com.wesleyboar.kanata
```

Stop and remove them with:

```sh
sudo launchctl bootout system/com.wesleyboar.kanata
sudo launchctl bootout system/com.wesleyboar.kanata-vhid
sudo rm /Library/LaunchDaemons/com.wesleyboar.kanata.plist
sudo rm /Library/LaunchDaemons/com.wesleyboar.kanata-vhid.plist
```
