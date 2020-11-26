in pubsec.yaml

firebase_core: ^0.5.0+1
  firebase_analytics: 6.0.0
  firebase_auth: 0.18.1+2
  cloud_firestore: 0.14.0+2
  firebase_storage: ^5.0.0-dev.3
  firebase_crashlytics: 0.2.3

in adnroid/build.gradle

in builscript.depencies

```
    classpath 'com.google.gms:google-services:4.3.4'
    classpath 'com.google.firebase:firebase-crashlytics-gradle:2.3.0'
```

android/app/build.gradle

root
```
apply plugin: 'com.google.gms.google-services'
apply plugin: 'com.google.firebase.crashlytics'
```

in  dependicies
```
    implementation platform('com.google.firebase:firebase-bom:25.12.0')
    implementation 'com.google.firebase:firebase-analytics-ktx'
    implementation 'com.android.support:multidex:1.0.3'
    implementation 'com.google.firebase:firebase-crashlytics-ktx'
```

in adnroid.defaultconfig

```
    targetSdkVersion 29
    multiDexEnabled true
```
