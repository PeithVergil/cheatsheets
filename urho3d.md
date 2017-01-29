Urho3D
======


Compiling
--------------------------------------------------

Set environment variable.

```bash
export URHO3D_HOME=/path/to/build/directory
```

Install dependencies.

```bash
sudo apt-get install \
    build-essential \
    cmake \
    libx11-dev \
    libxrandr-dev \
    libasound2-dev \
    freeglut3-dev \
    libmirclient-dev \
    libxkbcommon-dev \
    libreadline6-dev
```

Creating a debug build for Linux.

```bash
./cmake_generic.sh /path/to/build/debug -DCMAKE_BUILD_TYPE=Debug -DURHO3D_SAMPLES=0

# Minimal build
./cmake_generic.sh /path/to/build/debug -DCMAKE_BUILD_TYPE=Debug -DURHO3D_ANGELSCRIPT=0 -DURHO3D_SAMPLES=0 -DURHO3D_TOOLS=0 -DURHO3D_LUA=0
```

Creating a release build for Linux.

```bash
./cmake_generic.sh /path/to/build/release -DCMAKE_BUILD_TYPE=Release -DURHO3D_SAMPLES=0
```

Creating a build for Android.

```bash
./cmake_android.sh -DURHO3D_ANGELSCRIPT=0 -DURHO3D_SAMPLES=0 -DURHO3D_LUA=0
```
