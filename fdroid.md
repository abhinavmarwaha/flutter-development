Fork the frdoid data [repo](https://gitlab.com/fdroid/fdroiddata)

create a metadata file, 

in /metadata/com.package.name.yml

my app curator's build metadata for referance.

```
Categories:
  - Internet
  - Reading
License: GPL-3.0-or-later
AuthorName: Abhinav Marwaha
AuthorEmail: abhinavmarwaha@protonmail.com
AuthorWebSite: https://abhinavmarwaha.com
SourceCode: https://github.com/abhinavmarwaha/curator
IssueTracker: https://github.com/abhinavmarwaha/curator/issues
Changelog: https://github.com/abhinavmarwaha/curator/releases
Donate: https://github.com/abhinavmarwaha/curator#you-can-suppport-me-at
Liberapay: abhinavmarwaha
Bitcoin: bc1qfmwzy7qp97r9cnh7n9y4yze8t0lt7dyzyhtg07

AutoName: Curator

RepoType: git
Repo: https://github.com/abhinavmarwaha/curator

Builds:
  - versionName: 0.1.1
    versionCode: 1
    commit: v0.1.1
    output: build/app/outputs/apk/fdroid/release/app-fdroid-release.apk
    srclibs:
      - flutter@1.17.1
    prebuild: sed -i -e 's|git@github.com:|https://github.com/|' pubspec.lock pubspec.yaml
    build:
      - export PATH=$$flutter$$/bin:$PATH
      - flutter packages pub get
      - flutter pub run build_runner build
      - flutter config --no-analytics
      - flutter build apk --flavor fdroid

  - versionName: 0.9.1
    versionCode: 3
    commit: v0.9.1
    output: build/app/outputs/apk/fdroid/release/app-fdroid-release.apk
    srclibs:
      - flutter@1.22.5
    build:
      - export PATH=$$flutter$$/bin:$PATH
      - flutter packages pub get
      - flutter pub run build_runner build
      - flutter config --no-analytics
      - flutter build apk --flavor fdroid

MaintainerNotes: |-
    Builds will fail when the srclib ref of flutter and the version with which
    upstream has been built with differ.

AutoUpdateMode: None
UpdateCheckMode: None
CurrentVersion: 0.9.1
CurrentVersionCode: 3
```

*find all tags [here](https://f-droid.org/en/docs/Build_Metadata_Reference/)*

# Screenshots and other information about app

Create a /fastlane folder in your app repo

inside the folder ->

```
├── en-US                       (en-US is the F-Droid fallback language)
│   ├── short_description.txt   (short description, max 80 chars, mandatory)
│   ├── full_description.txt    (full app description, mandatory)
│   ├── title.txt               (app name)
│   ├── video.txt               (URL to a video introducing the app)
│   ├── images
│   │   ├── icon.png            (app icon, mandatory if your app doesn't include any png icon)
│   │   ├── featureGraphic.png  (promo banner, shown on top of the app desc in F-Droid client; landscape)
│   │   ├── tvBanner.png        ("icon" for TV devices, currently not used)
│   │   ├── phoneScreenshots
│   │   │   ├── 1.png
│   │   │   ├── 2.png
│   │   │   ...
│   │   ├── sevenInchScreenshots/
│   │   ├── tenInchScreenshots/ (you may add different screenshots for different screen sizes)
│   │   ├── tvScreenshots/
│   │   └── wearScreenshots/
│   └── changelogs
│       ├── 100000.txt          (must correspond to versionCode, literally, no padding)
│       ├── 100100.txt          (if the version code was set to 100100)
│       └── 100101.txt          (maximum size: 500 characters)
└── ru                          (other locale codes)
    ...                         (localized metadata is always preferred by the client)
    └── changelogs
        └── 100100.txt
```

[reference](https://f-droid.org/en/docs/All_About_Descriptions_Graphics_and_Screenshots/)

