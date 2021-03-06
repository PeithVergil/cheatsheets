Cordova
=======


Installation
--------------------------------------------------

#### Install Cordova
`sudo npm install -g cordova`

#### Update Cordova
`sudo npm update -g cordova`

#### Creating a project
`cordova create [myapp] [com.example.myapp] [MyApp]`

#### Adding a mobile platform
`cordova platform add android`

#### Running the app
```bash
cordova run android
cordova run android --debug
cordova run android --release
```


Plugins
--------------------------------------------------

Installing a plugin.

```bash
cordova plugin add cordova-plugin-splashscreen
```


Ionic Framework
--------------------------------------------------

#### Install Ionic
`sudo npm install -g ionic`

#### Create project
`ionic start [myapp] sidemenu`

#### Project template options
* tabs
* blank
* sidemenu

#### Add mobile platform
`ionic platform add android`

#### Mobile platform options
* ios
* android

#### Build for a specific platform
`ionic build android`

#### Run the app on an emulator
`ionic emulate android`