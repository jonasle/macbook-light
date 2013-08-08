macbook-light (mblight)
=======================
Installation
------------
### Arch Linux
Download the PKGBUILD (https://github.com/jonasle/macbook-light/blob/master/PKGBUILD) and 
run ```makepkg``` to create the package. Install the package using ```pacman -U mblight-x.x-x-any.pkg.tar.xz```
(replacing x.x-x with the version)
### Other distributions
Install the mblight script using (Pay attention to use the correct destination folders for your distribution)
```
install -Dm 755 mblight /usr/bin/mblight
install -Dm 755 mblight.service /etc/systemd/system/mblight.service
```

Usage
-----
After installation run as root to continuously update the keyboard and screen backlight.
```
mblight &
```

To run the systemd service use:
```
systemctl start mblight.service
```

The status of the service can be checked using:
```
systemctl status mblight.service
```

If you want to run the service at boot every time:
```
systemctl enable mblight.service
```

To-Do
-----
Check the issue list at: https://github.com/jonasle/macbook-light/issues?state=open
- [ ] Power management
- [ ] Allow manual setting of backlight
- [ ] Logging ?
- [ ] Allow one-time setting to remove the need to use Ctrl-C to kill the process after setting
