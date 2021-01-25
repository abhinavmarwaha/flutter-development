# Widgets

In flutter everything is a widget
Widgets describe what their view should look like given their current configuration and state.

## Stateful
have something that changes 

## Stateless
no datan that changes

## Basic Widgets

*Widgets Catalog*: https://flutter.dev/docs/development/ui/widgets

### Text
styled text widget

### Row, Column
flexible horizontal and vertical widgets

### Stack
can put widgets on top of each other in this linear layout

### Container
rectangular visual element 
* can be decorated with a BoxDecoration, such as a background, a border, or a shadow
* can also have margins, padding, and constraints applied to its size. 
* can be transformed in three dimensional space using a matrix.

### GridView
Lays widgets out as a scrollable grid.

### ListView
Lays widgets out as a scrollable list

### Card 
Organizes related info into a box with rounded corners and a drop shadow.

### ListTile
Organizes up to 3 lines of text, and optional leading and trailing icons, into a row.


## Maerial Components
Top most level widget should always be a material app.
each activity/screen should be a scaffold which provides app bar.

## Handling gestures

Gesture Detector

# State

After calling createState() on the StatefulWidget, the framework inserts the new state object into the tree and then calls initState() on the state object.

When a state object is no longer needed, the framework calls dispose() on the state object

# Keys
Use keys to control which widgets the framework matches up with other widgets when a widget rebuilds. By default, the framework matches widgets in the current and previous build according to their runtimeType and the order in which they appear. With keys, the framework requires that the two widgets have the same key as well as the same runtimeType.

# Global Keys
Use global keys to uniquely identify child widgets.

# Layout

https://flutter.dev/docs/development/ui/layout

# Navigation and routing

https://medium.com/flutter/learning-flutters-new-navigation-and-routing-system-7c9068155ade

# firebase

https://firebaseopensource.com/projects/firebaseextended/flutterfire/

# Sqlite

theming

# Futures and async tasks


# Notifications

native and firebase messaging