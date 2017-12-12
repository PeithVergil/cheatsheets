Godot
=====


Compiling from source
---------------------

Install dependencies.

```bash
sudo apt-get install build-essential \
pkg-config \
libx11-dev \
libpulse-dev \
libasound2-dev \
libxcursor-dev \
libxinerama-dev \
libgl1-mesa-dev \
libglu-dev \
libfreetype6-dev \
libssl-dev \
libudev-dev \
libxrandr-dev
```

Start compiling.

```bash
scons platform=x11
```

Delete obsolete file.

```bash
rm drivers/unix/os_unix_global_settings_path*
rm core/globals_default*
```
