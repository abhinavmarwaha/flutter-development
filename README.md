This is not a cookbook.

# Cookbooks

* https://medium.com/ionicfirebaseapp/flutter-cookbook-24b1f7b11e50
* https://github.com/devsmranjan/flutter-cookbook
* https://flutter.dev/docs/cookbook

# Essential concepts to Learn

* Widgets
* State - pragmatic aproach 
  * https://www.youtube.com/watch?v=d_m5csmrf7I
  * https://medium.com/super-declarative/understanding-state-management-and-why-you-never-will-dd84b624d0e
* provider package
* layouts
* common widgets 
* futures and async tasks
* modularity
* structure

backend

* models in [firebase]() - serialization, deserilastion
* security

Misc

* Singleton :: constructers

## themeing

https://flutter.dev/docs/cookbook/design/themes

## Provider :

https://pub.dev/packages/provider

https://www.youtube.com/watch?v=3tm-R7ymwhc

https://www.youtube.com/watch?v=vFxk_KJCqgk&t=457s

https://stackoverflow.com/questions/56580988/flutter-state-is-lost-on-hot-reload-when-using-provider

https://github.com/rrousselGit/provider/issues/347

## Forms

https://flutter.dev/docs/cookbook/forms/validation

# End to End development

Write down some key points of the app idea you have

Questions to ask ->

* Will I use it everday?
* Why is it needed ?
* What it is?
* How the app is resolving the pain point?

Then make exact UI/UX in figma. (If possible share these and ask people if they will use it)

Now have version 0.1 -> minimum features that you can build quickly

Then start making the app

* Make folder structures, architecture and then code whatever is needed
* Build .. Iterate build ( when 1 feature is there and you are satisfied)
* Take feedback ASAP.

Iterate

Release repeat.

# Anti-Features

You should also define what the app shouldn't have.

# States to consider

* Unauthenticated
* Authenticated
* Data Loading
* Loaded data
* Blank data
* Internet Connectivity Issues
* Admin stuff (CRUD)

# CRUD

It is important to add functionality of CRUD of data in yur app. Sometimes 2 functionalities can do 1 thing and vice versa like updating can be done through delete and create.

* Create
* Read
* Update
* Delete

# Project structure

The general structure of apps that I create is:

```
root
    utils
    models
    providers
    services
    screeens
        auth
            widgets
    global-widgets
assets
file-assets
constants
    colors
    strings
    dimensions
```

* utils -> like toast messages, date parsers.. etc things you need
* models -> data serializers/deserializers... data dart classes
* providers -> provider files conaining state logic
* services -> data fetching logic, dbhelpers, API callers like firebase etc
* screens -> the UI of screens
  * widgets subfolder for using in a category of screens like auth
* global-widgets -> widgets used globally
* assets -> the files that you want to import in-app.
* file-assets -> assets of the project like logo, feature gaphic etc .. those not needed in-app.
* constants
  * colors -> all the colors you need ... dark mode + light mode
  * strings -> db columns names, firebase collection names etc 
  * dimensions -> font sizes, button sizes etc

# Import Graphics

## Custom Icons

Icons that only have one color, should be used as a custom icon
[This](https://medium.com/codechai/how-to-use-custom-icons-in-flutter-834a079d977) is a nice guide for it.
Site to use [fluttericon.com](fluttericon.com)

## images

You can import from [assets](https://flutter.dev/docs/development/ui/assets-and-images) or cache a network [image](https://pub.dev/packages/optimized_cached_image).

## vectors

SVG files can save a lot of space but rendering takes some time you can use the [flutter-svg package](https://pub.dev/packages/flutter_svg)

# Best Practices

* const -> add consts wherever you can to decrease paint times
* cache images -> use package
* cache http requests 
* cache data
* modularity
* MVVM Architecture

# Essential Micro feedbacks

It is essential to give feedback to users. You can have creative ways for user feedback but I mostly use:

* Toast messages
* Snackbar

Feedbacks include

* sign in error messages
* internet connectivity issues
* etc

if Your app is internet-driven entirely you can have a default screen of not connectivity.

# Testing

* All Screens
* Different Android versions
* Release and debug build
* package versions

# Release Checklist

* icon
* name
* dependcies
* key

# Some code gists

* [internet_connectivity](/gists/internet_connectivity_check.md)
* [key](/gists/key.md)
* [theming](gists/theming.md)
* [Adding to F-Droid](fdroid.md)

# Awesome Packages for common things

* [Audio Service](https://pub.dev/packages/audio_service)
* [Shared Preferences](https://pub.dev/packages/shared_preferences)
* [SQL DB](https://pub.dev/packages/sqflite)
* [Optimized Cached Image](https://pub.dev/packages/optimized_cached_image)
* [local Notifications](https://pub.dev/packages/flutter_local_notifications)
* [Permissions Handler](https://pub.dev/packages/permission_handler)

# Github README essentials

* [Badges](https://shields.io/) -> bulds, versions, funding, downloads etc
* logo and feature graphic
* contribution guide
* license

# VsCode Extensions

* [dart class generator](https://marketplace.visualstudio.com/items?itemName=BendixMa.dart-data-class-generator)
* [Bracket Pair Colorizer 2](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2)

# Books on building software

* [Shape up](https://basecamp.com/shapeup)
* [Getting real](https://basecamp.com/books/getting-real)
