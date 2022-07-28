![](https://github.com/TutorialsAndroid/KAlertDialog/blob/master/sample/src/main/res/mipmap-xxhdpi/ic_launcher.png)

# New version released v18.0.19 on 28-07-22
## Changelogs
- Fixed issue in button color not changing
- Using Scalable DP library
- Added changing of font style
- Added changing of title and content color
### Read the changes in README

Alert Dialog ![API](https://img.shields.io/badge/API-19%2B-brightgreen.svg?style=flat) [![Known Vulnerabilities](https://snyk.io/test/github/TutorialsAndroid/KAlertDialog/badge.svg?targetFile=library%2Fbuild.gradle)](https://snyk.io/test/github/TutorialsAndroid/KAlertDialog?targetFile=library%2Fbuild.gradle) [![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-KAlertDiaog-blue.svg?style=flat)](https://android-arsenal.com/details/1/7588) [![License](https://img.shields.io/badge/License-Apache%202.0-green.svg)](https://opensource.org/licenses/Apache-2.0)
===================
AlertDialog for Android, a beautiful and material alert dialog to use in your android app.

`Older verion of this library has been removed please use new version of this library.`

## Will you buy a coffee for me

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.paypal.com/paypalme/tusharmasram)


## And Don't Forget To Follow Me On Instagram / Twitter

<p align="center">Follow me on instagram to stay up-to-date https://instagram.com/akshay.sunil.masram.1998
<p align="center">Follow me on twitter to stay up-to-date https://twitter.com/akshaysmasram98
    

## Contributors

[NassB (Nassim B.)](https://github.com/NassB)

**Library available at JitPack.io**

[![](https://jitpack.io/v/TutorialsAndroid/KAlertDialog.svg)](https://jitpack.io/#TutorialsAndroid/KAlertDialog)

`Latest version of this library is migrated to androidx`

## Features
- Materialistic alert dialog
- Change font style
- Change text color
- Change button color and background
- More features are comming soon

## ScreenShot
![](https://github.com/TutorialsAndroid/KAlertDialog/blob/master/art/device-2019-03-23-132617.png)

## Setup
The simplest way to use AlertDialog is to add the library as dependency to your build.

## Gradle

Add it in your root build.gradle at the end of repositories:

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}

Step 2. Add the dependency

	dependencies {
	        implementation 'com.github.TutorialsAndroid:KAlertDialog:v18.0.19'
	}

## Usage

**Show material progress**

    KAlertDialog pDialog = new KAlertDialog(this, KAlertDialog.PROGRESS_TYPE, 0);
    pDialog.getProgressHelper().setBarColor(Color.parseColor("#A5DC86"));
    pDialog.setTitleText("Loading");
    pDialog.setCancelable(false);
    pDialog.show();


You can customize progress bar dynamically with materialish-progress methods via **KAlertDialog.getProgressHelper()**:
- resetCount()
- isSpinning()
- spin()
- stopSpinning()
- getProgress()
- setProgress(float progress)
- setInstantProgress(float progress)
- getCircleRadius()
- setCircleRadius(int circleRadius)
- getBarWidth()
- setBarWidth(int barWidth)
- getBarColor()
- setBarColor(int barColor)
- getRimWidth()
- setRimWidth(int rimWidth)
- getRimColor()
- setRimColor(int rimColor)
- getSpinSpeed()
- setSpinSpeed(float spinSpeed)

A basic message：

    new KAlertDialog(this, 0)
        .setTitleText("Here's a message!")
        .show();

A title with a text under：

    new KAlertDialog(this, 0)
        .setTitleText("Here's a message!")
        .setContentText("It's pretty, isn't it?")
        .show();

A error message：

    new KAlertDialog(this, KAlertDialog.ERROR_TYPE, 0)
        .setTitleText("Oops...")
        .setContentText("Something went wrong!")
        .show();

A warning message：

    new KAlertDialog(this, KAlertDialog.WARNING_TYPE, 0)
        .setTitleText("Are you sure?")
        .setContentText("Won't be able to recover this file!")
        .setConfirmText("Yes,delete it!")
        .show();

A success message：

    new KAlertDialog(this, KAlertDialog.SUCCESS_TYPE, 0)
        .setTitleText("Good job!")
        .setContentText("You clicked the button!")
        .show();

A message with a custom icon：

    new KAlertDialog(this, KAlertDialog.CUSTOM_IMAGE_TYPE, 0)
        .setTitleText("Sweet!")
        .setContentText("Here's a custom image.")
        .setCustomImage(R.drawable.custom_img)
        .show();

To Hide Cancel And Confirm Button：

    new KAlertDialog(this, KAlertDialog.CUSTOM_IMAGE_TYPE, 0)
        .setTitleText("Sweet!")
        .setContentText("Here's a custom image.")
        .setCustomImage(R.drawable.custom_img)
        .setConfirmText("OK") //Do not call this if you don't want to show confirm button
        .setCancelText("CANCEL")//Do not call this if you don't want to show cancel button
        .show();

To Change the font of title and content：

    new KAlertDialog(this, alertType, R.font.yourFontName)

To Change the font of only title：

    .dialogTitleFont(R.font.yourFontName)

To Change the font of only content：

    .dialogContentFont(R.font.yourFontName)

To Change the color of title and content

    .setTitleColor(R.color.yourColorName)
    .setContentColor(R.color.yourColorName)

Bind the listener to confirm button：

    new KAlertDialog(this, KAlertDialog.WARNING_TYPE, 0)
        .setTitleText("Are you sure?")
        .setContentText("Won't be able to recover this file!")
        .setConfirmText("Yes,delete it!")
        .setConfirmClickListener(new KAlertDialog.KAlertClickListener() {
            @Override
            public void onClick(KAlertDialog sDialog) {
                sDialog.dismissWithAnimation();
            }
        })
        .show();

Show the cancel button and bind listener to it：

    new KAlertDialog(this, KAlertDialog.WARNING_TYPE, 0)
        .setTitleText("Are you sure?")
        .setContentText("Won't be able to recover this file!")
        .setCancelText("No,cancel plx!")
        .setConfirmText("Yes,delete it!")
        .showCancelButton(true)
        .setCancelClickListener(new KAlertDialog.KAlertClickListener() {
            @Override
            public void onClick(KAlertDialog sDialog) {
                sDialog.cancel();
            }
        })
        .show();

Customizing the alert dialog

    .confirmButtonColor(R.color.colorPrimary) // you can change the color of confirm button
    .cancelButtonColor(R.color.colorAccent) // you can change the color of cancel button
    .setContentTextSize(50) // you can change the content text size
    .setTitleText("<h2>Title</h2><br><p>Description here</p>") //you can use html in title text
    
    //This is how you can set dark theme to alert dialog box
    @Override
    protected void onCreate(Bundle savedInstanceState) {

        //sets the theme for app
        SharedPreferences sharedPreferences = this
                .getSharedPreferences("theme", Context.MODE_PRIVATE);
        final boolean dark = sharedPreferences.getBoolean("dark", false);
        setTheme(dark ? R.style.AppThemeDark : R.style.AppTheme);

        DARK_STYLE = dark; //this will apply dark theme to KAlertDialog Box

        super.onCreate(savedInstanceState);
        setContentView(R.layout.main_ui);
    }
  

And if you want to change the button corners with color create a drawable file

        <?xml version="1.0" encoding="utf-8"?>
        <selector xmlns:android="http://schemas.android.com/apk/res/android">
            <item android:state_pressed="true">
                <shape android:shape="rectangle">
                    <solid android:color="#FF5474" />
                    <corners android:radius="6dp"/>
                </shape>
            </item>
            <item>
                <shape android:shape="rectangle">
                    <solid android:color="#FF1744" />
                    <corners android:radius="6dp"/>
                </shape>
            </item>
        </selector>

And then call this method when you create drawable

      .confirmButtonColor(R.drawable.button_background) // you can change border and color of button
      
And if you want to hide Title Text and Content Text of alert dialog

	.setTitleText("Are you sure?") //just don't write this line if you want to hide title text
	.setContentText("Won't be able to recover this file!") // don't write this line if you want to hide content text

**Change** the dialog style upon confirming：

    new KAlertDialog(this, KAlertDialog.WARNING_TYPE, 0)
        .setTitleText("Are you sure?")
        .setContentText("Won't be able to recover this file!")
        .setConfirmText("Yes,delete it!")
        .setConfirmClickListener(new KAlertDialog.KAlertClickListener() {
            @Override
            public void onClick(KAlertDialog sDialog) {
                sDialog
                    .setTitleText("Deleted!")
                    .setContentText("Your imaginary file has been deleted!")
                    .setConfirmText("OK")
                    .setConfirmClickListener(null)
                    .changeAlertType(KAlertDialog.SUCCESS_TYPE);
            }
        })
        .show();
        
 ## License

* [Apache Version 2.0](http://www.apache.org/licenses/LICENSE-2.0.html)

```
Copyright 2019 KAlertDialog

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

 http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
       
