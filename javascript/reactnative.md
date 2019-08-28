React Native
============


Android Development Environment
-------------------------------

[Download Android Studio](https://developer.android.com/studio) and add Android SDK to system path.

```bash
export ANDROID_HOME=/path/to/Android/sdk

export PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools
```

[Download Gradle](https://gradle.org/releases/) and add to system path.

```bash
export PATH=$PATH:/path/to/gradle/bin
```

[Download JDK 8](https://adoptopenjdk.net/releases.html#x64_mac) and set environment variable.

```bash
export JAVA_HOME=/path/to/jdk8/Contents/Home
```


Installation
--------------------------------------------------

```bash
npm install -g react-native-cli
```

Usage
--------------------------------------------------

Create a new project.

```bash
react-native init HelloReactNative
```

Run the new project.

```bash
cd HelloReactNative

react-native run-android
```