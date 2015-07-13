Install

    sudo npm install -g ionic
    sudo npm install -g cordova

Platform

    ionic platform add android

Install Android SDK

    /path/to/android/sdk/tools/android

Edit

    vim www/js/app.js

    token : '__YOUR_TOKEN_';

    adMobId.banner       = '__YOUR_BANNER_KEY_';
    adMobId.interstitial = '__YOUR_INTERSTITIAL_KEY_'; // Full Page

Run

    export ANDROID_HOME=/path/to/android/sdk/tools/android/SDK
    make run

Error fix

    ? Cannot read property 'Keyboard' of undefined
    > cordova plugin add com.ionic.keyboard

    ? Failed to load resource: the server responded with a status of 404 (Not Found)
    > ionic plugin add cordova-plugin-whitelist

Other remarks

    ? How to add splash screen
    > ionic resources
    > cordova plugin add cordova-plugin-splashscreen

    ? How to bulid release apk
    > ionic build --release android

    ? Generate new key into existing keystore
    > keytool -genkey -v -keystore /path/to/app/KeyStore.jks -alias tautapp -keyalg RSA -keysize 2048 -validity 10000

    ?
    > jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore /path/to/app/KeyStore.jks /path/to/app/app-unsigned.apk tautapp
    > /path/to/android/sdk/build-tools/21.1.1/zipalign -v 4 /path/to/app/app-unsigned.ap /path/to/app/app-signed.ap
