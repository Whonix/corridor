# Tor traffic whitelisting gateway #

There are several transparently torifying gateways. They suffer from the same
problems:

- It's tricky to isolate circuits and issue NEWNYM signals, especially if
multiple client computers are involved.
- Any garbage software can pump identifiers into "anonymous" circuits, and
get itself exploited by malicious exit nodes.
- Trust is centralized to the gateway, which is bad enough when used by one
person, and just inappropriate when shared with strangers.

corridor takes a different approach. It allows only connections to Tor relays
to pass through (no clearnet leaks!), but client computers are themselves
responsible for torifying their own traffic. In other words, it is a filtering
gateway, not a proxying gateway.

You can think of it as defense in depth for your vanilla Tor Browser or Tails,
for your beautiful scary experimental Qubes proxying schemes, etc. Or invite
the hood to use your Wi-Fi without getting into trouble.

## How to install `corridor` using apt-get ##

1\. Download the APT Signing Key.

```
wget https://www.whonix.org/keys/derivative.asc
```

Users can [check the Signing Key](https://www.whonix.org/wiki/Signing_Key) for better security.

2\. Add the APT Signing Key.

```
sudo cp ~/derivative.asc /usr/share/keyrings/derivative.asc
```

3\. Add the derivative repository.

```
echo "deb [signed-by=/usr/share/keyrings/derivative.asc] https://deb.whonix.org trixie main contrib non-free" | sudo tee /etc/apt/sources.list.d/derivative.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `corridor`.

```
sudo apt-get install corridor
```

## How to Build deb Package from Source Code ##

Can be build using standard Debian package build tools such as:

```
dpkg-buildpackage -b
```

See instructions.

NOTE: Replace `generic-package` with the actual name of this package `corridor`.

* **A)** [easy](https://www.whonix.org/wiki/Dev/Build_Documentation/generic-package/easy), _OR_
* **B)** [including verifying software signatures](https://www.whonix.org/wiki/Dev/Build_Documentation/generic-package)

## Contact ##

* [Free Forum Support](https://forums.whonix.org)
* [Premium Support](https://www.whonix.org/wiki/Premium_Support)

## Donate ##

`corridor` requires [donations](https://www.whonix.org/wiki/Donate) to stay alive!
