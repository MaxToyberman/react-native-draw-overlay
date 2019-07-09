
# react-native-draw-overlay
Ask for draw over other apps permission.

## Getting started

`$ npm install react-native-draw-overlay --save`

### Mostly automatic installation

`$ react-native link react-native-draw-overlay`

### Manual installation

#### Android

1. Open up `android/app/src/main/java/[...]/MainActivity.java`
  - Add `import com.reactlibrary.RNDrawOverlayPackage;` to the imports at the top of the file
  - Add `new RNDrawOverlayPackage()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-draw-overlay'
  	project(':react-native-draw-overlay').projectDir = new File(rootProject.projectDir, 	'../node_modules/react-native-draw-overlay/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      implementation project(':react-native-draw-overlay')
  	```
## Usage
add 
```xml
<uses-permission android:name="android.permission.SYSTEM_ALERT_WINDOW"/>
to AndroidManifest.xml
```
```javascript
import RNDrawOverlay from 'react-native-draw-overlay';

// TODO: What to do with the module?
RNDrawOverlay.askForDispalayOverOtherAppsPermission()
			 .then(res => {
				 // res will be true if permission was granted 
			 })
			 .catch(e => {
				 // permission was declined
			 })
```
  