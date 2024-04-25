React Native
============


Android Development Environment
-------------------------------

[Download Android Studio](https://developer.android.com/studio) and add Android SDK to system path.

```bash
export ANDROID_HOME=$HOME/Library/Android/sdk

export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

[Download Gradle](https://gradle.org/releases/) and add to system path.

```bash
export PATH=$PATH:/path/to/gradle/bin
```

[Download JDK 8](https://adoptopenjdk.net/releases.html#x64_mac) and set environment variable.

```bash
export JAVA_HOME=/path/to/jdk8/Contents/Home
```


iOS Development Environment
---------------------------

Install CocoaPods.

```bash
sudo gem install cocoapods
```


Installation
--------------------------------------------------

```bash
npm install -g react-native-cli
```

Uninstalling an existing package.

```bash
npm uninstall -g react-native-cli @react-native-community/cli
```

Usage
--------------------------------------------------

Create a new project.

```bash
npx react-native@latest init HelloReactNative
```

Run the new project.

```bash
cd HelloReactNative

npm run ios
npm run android
```