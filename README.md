# Loopback Alias

Creates an alias on the loopback interface (lo0) with the IP 10.254.254.254 on Mac OS X.

## Installation
You can manually install or use the install script

### Install script
    $ ./install

#### Manual Installation

1. Install the plist to: `/Library/LaunchDaemons/com.runlevel1.lo0.10.254.254.254.plist`
2. Set mode: `chmod 0644 /Library/LaunchDaemons/com.runlevel1.lo0.10.254.254.254.plist`
3. Set owner: `sudo chown root:wheel /Library/LaunchDaemons/com.runlevel1.lo0.10.254.254.254.plist`
4. Load: `sudo launchctl load /Library/LaunchDaemons/com.runlevel1.lo0.10.254.254.254.plist`

The alias will automatically be created at startup from then on.

You can confirm the alias was created with `ifconfig`:

```
/tmp ❯❯❯ ifconfig lo0
lo0: flags=8049<UP,LOOPBACK,RUNNING,MULTICAST> mtu 16384
       	options=3<RXCSUM,TXCSUM>
       	inet6 ::1 prefixlen 128
       	inet 127.0.0.1 netmask 0xff000000
       	inet6 fe80::1%lo0 prefixlen 64 scopeid 0x1
       	inet 10.254.254.254 netmask 0xff000000
       	nd6 options=1<PERFORMNUD>
```
