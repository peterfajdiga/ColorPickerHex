# ColorPickerHex
A color picker preference for Android that enables selecting colors using sliders or hexadecimal color codes.

It is heavily based on [notification light settings from CyanogenMod](https://github.com/CyanogenMod/android_packages_apps_Settings "CyanogenMod's android_packages_apps_Settings").


## Installation
1. Copy contents into app/libs/ColorPickerHex inside of your project. If you're using git with your project, I recommend cloning this repo as a submodule like so:
```
git submodule add https://github.com/peterfajdiga/ColorPickerHex.git app/libs/ColorPickerHex
```

2. Add the following two lines to settings.gradle:
```
include ':ColorPickerHex'
project(':ColorPickerHex').projectDir = new File('app/libs/ColorPickerHex/colorpickerhex')
```

3. Add the following line to app/build.gradle's *dependencies* block:
```
compile project(":ColorPickerHex")
```


## Usage
Simply use peterfajdiga.colorpickerhex.ColorPreference in your xml file containing your preferences. Example:
```
<peterfajdiga.colorpickerhex.ColorPreference
        android:defaultValue="0xff000000"
        android:key="pref_itemcolor"
        android:title="Item color"
        app:editAlpha="false"/>
```
The color is stored as an integer. Set *editAlpha* to *true* if you want to enable editing the alpha (opacity) component of the color. If set to *false* (default), then the stored color will be fully opaque.
