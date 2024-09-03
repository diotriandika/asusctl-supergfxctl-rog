# asusctl-supergfxctl-rog
Catatan Instalasi &amp; Manual Guide Asusctl &amp; Supergfxctl

## Instalasi Asusctl di Ubuntu 24.04
First, let's install the utilities we'll be working with:

```bash
$ sudo apt-get install build-essential make cmake git curl clang libudev-dev libudev-dev libgtk-3-dev libinput-dev libgbm-dev libsystemd-dev libseat-dev
```

The second step is to install the Rustlang:

```bash
$ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Next:

```bash
$ source "$HOME/.cargo/env"
```

We clone the repository and go to it:

```bash
$ git clone https://gitlab.com/asus-linux/asusctl.git
$ cd asusctl
```

And finally the build:

```bash
# if you're using xorg please consider to use this
$ make cargo build --features "rog-control-center/x11"

# if you're using wayland please consider to use this one
$ make

# then run
$ sudo make install
```

References:
- https://www.reddit.com/r/pop_os/comments/10feq40/asusctl_on_pop_os/
- https://gist.github.com/vijay-prema/cfcf8cc4085663b7bb48f34172c10629
- https://gitlab.com/asus-linux/asusctl
- https://asus-linux.org/
