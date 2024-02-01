Ionic Framework
===============


Installation
------------

Install the Ionic CLI.

```bash
npm install -g @ionic/cli

# Install to a different directory.
npm install -g @ionic/cli --prefix=/path/to/directory
```

Usage
-----

Create a new Vue project. Available starter templates:

* aws
* tabs
* blank
* super
* sidemenu
* tutorial
* conference

```bash
ionic start MySampleProject tabs --type vue --capacitor
```

Run the new project.

```bash
cd MySampleProject
```

```bash
ionic serve
```

Capacitor Plugins
-----------------

Installing capacitor plugins.

```bash
npm install @capacitor/camera @capacitor/storage @capacitor/filesystem
```

Mobile Build (Android)
----------------------

Set environment variables.

```bash
export JAVA_HOME=$HOME/Applications/jdk-17.jdk/Contents/Home

export ANDROID_SDK_ROOT=$HOME/Library/Android/sdk

export PATH=$PATH:$ANDROID_SDK_ROOT/tools/bin
export PATH=$PATH:$ANDROID_SDK_ROOT/platform-tools
export PATH=$PATH:$ANDROID_SDK_ROOT/emulator
```

Check that an Android device is connected.

```bash
adb devices
```

Create a production build.

```bash
ionic build
```

Create an Android project.

```bash
ionic capacitor add android
```

Update the Android build

```bash
ionic capacitor copy android
```

Update the native build

```bash
ionic capacitor sync
```

Open the project in Android Studio

```bash
ionic capacitor open android
```