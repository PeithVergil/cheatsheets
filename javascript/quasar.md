Quasar
======


Installation
------------

Install the Quasar CLI.

```bash
npm install -g @quasar/cli

# Install to a different directory.
npm install -g @quasar/cli --prefix=/path/to/directory
```

Usage
-----

Create a new project.

```bash
quasar create MySampleProject
```

Run the new project.

```bash
cd MySampleProject
```

```bash
quasar dev
```

Creating a new layout.

```bash
quasar new layout MyLayout
```

Creating a new page.

```bash
quasar new page MyPage
```

Creating a new store module.

```bash
quasar new store MyStore
```

Creating a new component.

```bash
quasar new component MyComponent
```

Creating a new boot file.

```bash
quasar new boot MyPlugin
```

Upgrade
-------

Check for upgradable packages.

```bash
quasar upgrade
```

Perform the actual upgrade

```bash
quasar upgrade --install
```

Android Development
-------------------

[Download Android Studio](https://developer.android.com/studio) and add Android SDK to system path.

```bash
export PATH=$PATH:/path/to/Android/sdk/tools:/path/to/Android/sdk/platform-tools

export ANDROID_HOME=/path/to/Android/sdk
```

[Download Gradle](https://gradle.org/releases/) and add to system path.

```bash
export PATH=$PATH:/path/to/gradle/bin
```

[Download JDK 8](https://adoptopenjdk.net/releases.html#x64_mac) and set environment variable.

```bash
export JAVA_HOME=/path/to/jdk8/Contents/Home
```

Cordova
-------

Add Cordova mode.

```bash
quasar mode add cordova
```

Add platforms

```bash
cd src-cordova/

cordova platform add android
cordova platform add ios
```

Star development

```bash
quasar dev -m android
quasar dev -m ios
```