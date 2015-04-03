Kivy
====


Installation
--------------------------------------------------

Install SDL2. Kivy 1.9 and above uses SDL2 as its window and graphics provider:

```bash
sudo apt-get install build-essential libsdl2-dev libsdl2-ttf-dev libsdl2-image-dev libsdl2-mixer-dev
```

Install the Gstreamer library. It's used as a video provider:

```bash
sudo apt-get install libgstreamer1.0-dev gstreamer1.0-x
```

Install Cython. Make sure to install Cython 0.21 as Kivy doesn't support newer versions of Cython yet:

```bash
pip install Cython==0.21
```

(Optional) Install Pillow. It's one of Kivy's image providers:

```bash
pip install Pillow
```

Install Kivy:

```bash
pip install Kivy
```

Usage
--------------------------------------------------

Creating a Python distribution:

```bash
./distribute.sh -m "pyjnius kivy"
```

Creating an Android package (APK):

```bash
./build.py --dir [/path/to/project]       \
--presplash [/path/to/project/splash.jpg] \
--icon [/path/to/project/icon.png]        \
--install-location preferExternal         \
--package [com.mycompany.myapp]           \
--orientation [portrait]                  \
--name "[My Project]"                     \
--version [0.1]                           \
debug
```

Options:

#./build.py --dir <path to your app>
#           --name "<title>"
#           --package <org.of.your.app>
#           --version <human version>
#           --icon <path to an icon to use>
#           --orientation <landscape|portrait>
#           --permission <android permission like VIBRATE> (multiple allowed)
#           <debug|release> <installd|installr|...>


Installing the Android package:

```bash
./adb install -r [/path/to/python-for-android/dist/default/bin/MyProject-0.1-debug.apk]
```

Launching the Android emulator:

```bash
emulator -avd <avd_name> -gpu on
```
