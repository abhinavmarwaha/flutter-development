# key

put key in android/app/key.jks

android/key.properties

```
storePassword=<>
keyPassword=<>
keyAlias=key
storeFile=key.jks
```

android/app/build.gradle

```
def keystoreProperties = new Properties()
def keystorePropertiesFile = rootProject.file('key.properties')
if (keystorePropertiesFile.exists()) {
    keystoreProperties.load(new FileInputStream(keystorePropertiesFile))
}
```

in android {}

```
    signingConfigs {
       release {
           keyAlias keystoreProperties['keyAlias']
           keyPassword keystoreProperties['keyPassword']
           storeFile keystoreProperties['storeFile'] ? file(keystoreProperties['storeFile']) : null
           storePassword keystoreProperties['storePassword']
       }
    }


    buildTypes {
        release {
            signingConfig signingConfigs.release
        }
    }
```