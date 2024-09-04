# asusctl-supergfxctl-rog
Notes for `asusctl` and `supergfxctl` tools

## Asusctl Installation on Ubuntu 24.04 (ROG Zephyrus G15)
First, Install all utilities and depedencies that we'll needed.

```bash
$ sudo apt-get install build-essential make cmake git curl clang libudev-dev libudev-dev libgtk-3-dev libinput-dev libgbm-dev libsystemd-dev libseat-dev
```

Next, install Rustlang.

```bash
$ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
And run command below to configuring the PATH environment variable

```bash
$ source "$HOME/.cargo/env"
```

Now clone from the asusctl repository and move to asusctl directory

```bash
$ git clone https://gitlab.com/asus-linux/asusctl.git
$ cd asusctl
```

Lastly build with `cargo build` or `make`

```bash
# if you're using xorg please consider to use this
$ cargo build --features "rog-control-center/x11"

# if you're using wayland please consider to use this one
$ make

# then run
$ sudo make install
```
> If error appear while running `sudo make install` try to use `make` instead of `cargo build` then reboot your computer.
> If the issue persist or rog-control-center wont open, try to switch to wayland then back to xorg.


#### Optional

Install an up to date pipewire version and bluetooth audio support

```bash
sudo add-apt-repository ppa:pipewire-debian/pipewire-upstream
sudo apt install pipewire
sudo apt install libspa-0.2-bluetooth
```

References:
- https://www.reddit.com/r/pop_os/comments/10feq40/asusctl_on_pop_os/
- https://gist.github.com/vijay-prema/cfcf8cc4085663b7bb48f34172c10629
- https://gitlab.com/asus-linux/asusctl
- https://asus-linux.org/
