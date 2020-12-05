add to pubsec

firebase_messaging: any

in manifest 

```
<intent-filter>
    <action android:name="FLUTTER_NOTIFICATION_CLICK" />
    <category android:name="android.intent.category.DEFAULT" />
</intent-filter>
```

in app level build.gradel , dependencies

```
    implementation 'com.google.firebase:firebase-messaging-ktx:21.0.0'
```


 final FirebaseMessaging _firebaseMessaging = FirebaseMessaging();

  FirebaseMethods._();

  factory FirebaseMethods() => _instance;

  static final FirebaseMethods _instance = FirebaseMethods._();

  bool _initialized = false;

  Future<void> init() async {
    if (!_initialized) {
      _firebaseMessaging.requestNotificationPermissions();
      _firebaseMessaging.configure();

      String token = await _firebaseMessaging.getToken();
      print("FirebaseMessaging token: $token");

      _initialized = true;
    }
  }