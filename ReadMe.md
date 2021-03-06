[![](https://jitpack.io/v/Kunzisoft/Android-SwitchDateTimePicker.svg)](https://jitpack.io/#Kunzisoft/Android-SwitchDateTimePicker) [![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-SwitchDateTimePicker-blue.svg?style=flat)](http://android-arsenal.com/details/1/4513)

# Android SwitchDateTime Picker

SwitchDateTime Picker is a library for select a *Date* object in dialog with a DatePicker (Calendar) and a TimePicker (Clock) in the same UI.

<img src="https://raw.githubusercontent.com/J-Jamet/Android-SwitchDateTimePicker/master/art/demo1.gif">

<img src="https://raw.githubusercontent.com/J-Jamet/Android-SwitchDateTimePicker/master/art/demo2.gif">

## Installation
Add the JitPack repository in your build.gradle at the end of repositories:
```
	allprojects {
		repositories {
			...
			maven { url "https://jitpack.io" }
		}
	}
```
And add the dependency
```
	dependencies {
	        compile 'com.github.Kunzisoft:Android-SwitchDateTimePicker:v1.0-rc.4'
	}
```

## Usage

### Colors
For colors, add attributes :
`
dateTimeColorBackground, dateTimeColorLabel, dateTimeColorValue, dateTimeColorIcon
`
in your **styles.xml**, for example :
```
<resources>
    <!-- Base application theme. -->
    <style name="SwitchDateTimeTheme" parent="Theme.AppCompat.Light.DarkActionBar">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/colorPrimary</item>
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
        <item name="colorAccent">@color/colorAccent</item>
        <item name="dateTimeColorBackground">@color/colorAccent</item>
        <item name="dateTimeColorLabel">#d7f7fc</item>
        <item name="dateTimeColorValue">#c4e4b3</item>
        <item name="dateTimeColorIcon">#ffffff</item>
    </style>
</resources>
```
Note : *colorAccent* change DatePicker and TimePicker color.

### SimpleDateFormat
You can specify a particular [*SimpleDateFormat*](https://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html) for value of DateTime with **setSimpleDateFormat(SimpleDateFormat format)**

### Sample
You can see
https://github.com/J-Jamet/Android-SwitchDateTimePicker/blob/master/sample/src/main/java/com/kunzisoft/switchdatetimesample/Sample.java
for complete sample.
```
// Initialize
SwitchDateTimeDialogFragment dateTimeDialogFragment = SwitchDateTimeDialogFragment.newInstance(
        getString(R.string.label_datetime_dialog),
        getString(R.string.positive_button_datetime_picker),
        getString(R.string.negative_button_datetime_picker)
);

// Assign values
dateTimeDialogFragment.setYear(2016);
dateTimeDialogFragment.setMonth(12);
dateTimeDialogFragment.setDay(1);
dateTimeDialogFragment.setHour(1);
dateTimeDialogFragment.setMinute(20);

// Set SimpleDateFormat
dateTimeDialogFragment.setSimpleDateFormat(new SimpleDateFormat("d MMM yyyy HH:mm", java.util.Locale.getDefault()));

// Set listener
dateTimeDialogFragment.setOnButtonClickListener(new SwitchDateTimeDialogFragment.OnButtonClickListener() {
    @Override
    public void onPositiveButtonClick(Date date) {
        // Date is get on positive button click
        // Do something
    }

    @Override
    public void onNegativeButtonClick(Date date) {
        // Date is get on negative button click
    }
});

// Show
dateTimeDialogFragment.show(getSupportFragmentManager(), "dialog_time");
```

## License

Copyright (c) 2016 JAMET Jeremy

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
