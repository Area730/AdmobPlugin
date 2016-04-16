# Import
To start using [this plugin](https://www.assetstore.unity3d.com/en/#!/content/57268) please watch 
tutorial.

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/S7F9enxcvTE/0.jpg)](https://www.youtube.com/watch?v=S7F9enxcvTE)

 Or follow these steps:


1 Drag Admob prefab from `Area730/Admob/Prefabs` into your scene. You need to add this prefab to your game only once as `AdmobManager` is a singleton. 

![](_static/1.png)

2 Set Admob unit ids and you are almost done

![](_static/2.png)


3 To show banner  call ` AdmobManager.Instance.RequestBanner(AdPosition position)` where position is `enum` and can be:
```c#
AdPosition.Top
AdPosition.Bottom
AdPosition.TopLeft
AdPosition.TopRight
AdPosition.BottomLeft
AdPosition.BottomRight
```
You can also specify the size of the banner as second parameter. The default size is 320x50.
To show interstitial you have first to load it by calling `AdmobManager.Instance.RequestInterstitial()`. After the interstitial is loaded, the `OnInterstitialLoaded()` callbacks will be invoked. Admob prefab comes with default attached callback functions (see `Area730/Admob/Scripts/AdmobController.cs`). You can also add your own if you want. 

![](_static/3.png)

After the interstitial is loaded, you can show the ad by calling `AdmobManager.Instance.ShowInterstitial()`. 


# Building projects
After configuring your mediation you need to build your game to mobile devices. Sometimes it might cause some errors this section helps you to solve it

## IOS common errors

1. When you use old version of Unity(4.6 and lower) the included [GoogleMobileAds.framework](https://developers.google.com/admob/ios/download) in folder `Assets/Plugins/IOS` will not automatically linking to your project. To solve this problem copy [GoogleMobileAds.framework](https://developers.google.com/admob/ios/download) to the root of your exported project.
![GoogleMobileAds must be included to libraries](_static/framework.png) 

2. After that you need to config your **build settings** 

 2.1 Disable bit code ![Disable bitcode](_static/bitcode.png)
 2.2 Enable Modules (C and Objective-C) ![Enable modules](_static/modules.png)

3. If you use xCode 7.2  or higher you could get the following error because of incompatibility new xCode and Unity generated files.
![NORETURN](_static/Noreturn.png)
to solve this problem just delete circled ```NORETURN``` statment.

## Android common errors
1. When you trying to build your `apk` unity might throw build error. It might be caused of old Android API Level. The latest version of Admob library requires API Level 23. To download this packages go to you **Android SDK**(the path for it find here)![Android SDK path](_static/androidSDKPath.png)

Then install packages from SDK manager.
![SDK view](_static/SDK.png)

If you have another errors please contact us support@area730.com