Phonegap
========


Installation
--------------------------------------------------

#### Install phonegap
`sudo npm install -g phonegap`

#### Update phonegap
`sudo npm update -g phonegap`

#### Download Android SDK
`http://developer.android.com/sdk/index.html`

#### Set Android SDK
`export ANDROIDSDK=/home/pvergil/Apps/android-sdk-linux`

#### Set JAVA_HOME
`export JAVA_HOME=/usr/lib/jvm/java-7-openjdk-i386`


Creating an app
--------------------------------------------------
`phonegap create hello com.example.hello HelloWorld`


Building an app
--------------------------------------------------
    cd hello
    phonegap build android


Updating an app
--------------------------------------------------
`phonegap platform update android`


Installing an app to emulator or device
--------------------------------------------------
`phonegap install android`

Running an app on the emulator or device
--------------------------------------------------
`phonegap run android`