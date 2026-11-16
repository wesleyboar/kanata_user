# TODO

- [x] On the `wpersonal` macOS account, grant `/opt/homebrew/bin/kanata` Input Monitoring and Accessibility permissions, then verify the shared LaunchDaemons with `sudo launchctl print system/com.wesleyboar.kanata-vhid` and `sudo launchctl print system/com.wesleyboar.kanata`.
- [x] On the `wbomar` macOS account, trust the shared repo in Git, then replace the old home-folder checkout with a symlink to the shared one (the LaunchDaemon already loads the shared config; the old checkout is now stale):
  1. `git config --global --add safe.directory /Users/Shared/_accessibility/kanata_user`
  2. Check the old checkout (`~/Code/_accessibility/kanata_user`) for commits or changes missing from the shared repo (`git -C ~/Code/_accessibility/kanata_user status` and `git log`). Copy over anything worth keeping first.
  3. `mv ~/Code/_accessibility/kanata_user ~/Code/_accessibility/kanata_user.bak`
  4. `ln -s /Users/Shared/_accessibility/kanata_user ~/Code/_accessibility/kanata_user`
  5. Verify with `ls -l ~/Code/_accessibility/kanata_user` and `git -C ~/Code/_accessibility/kanata_user status`.
  6. Delete `kanata_user.bak` once nothing is missing.
