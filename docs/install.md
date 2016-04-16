
# Import
To start using [this plugin](https://www.assetstore.unity3d.com/en/#!/content/57268) please watch [this](https://www.youtube.com/watch?v=S7F9enxcvTE) tutorial. Or follow these steps:


1 Drag Admob prefab from `Area730/Admob/Prefabs` into your scene. You need to add this prefab to your game only once as `AdmobManager` is a singleton. 

![](https://www.dropbox.com/s/e1ojjhmewycn2bu/1.png?raw=1)

2 Set Admob unit ids and you are almost done

![](https://www.dropbox.com/s/tiqm17u1nh19uin/2.png?raw=1)


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

![](https://www.dropbox.com/s/segyabyt9pa38iw/3.png?raw=1)

After the interstitial is loaded, you can show the ad by calling ```c# AdmobManager.Instance.ShowInterstitial()```. 


#Building projects
After configuring your mediation you need to build your game to mobile devices. Sometimes it might cause some errors this section helps you to solve it

##IOS common errors

1. When you use old version of Unity(4.6 and lower) the included [GoogleMobileAds.framework](https://developers.google.com/admob/ios/download) in folder `Assets/Plugins/IOS` will not automatically linking to your project. To solve this problem copy [GoogleMobileAds.framework](https://developers.google.com/admob/ios/download) to the root of your exported project.
![GoogleMobileAds must be included to libraries](https://www.dropbox.com/s/iuuk2cz33v3wrvc/framework.png?raw=1) 

2. After that you need to config your **build settings** 

 2.1 Disable bit code ![Disable bitcode](https://www.dropbox.com/s/ro13o7xdypg8u68/bitcode.png?raw=1)
 2.2 Enable Modules (C and Objective-C) ![Enable modules](https://www.dropbox.com/s/1f55jq0fycbpja8/modules.png?raw=1)

3. If you use xCode 7.2  or higher you could get the following error because of incompatibility new xCode and Unity generated files.
![NORETURN](https://www.dropbox.com/s/jjdlkhzjw146t1s/Noreturn.png?raw=1)
to solve this problem just delete circled ```NORETURN``` statment.

##Android common errors
1. When you trying to build your `apk` unity might throw build error. It might be caused of old Android API Level. The latest version of Admob library requires API Level 23. To download this packages go to you **Android SDK**(the path for it find here)![Android SDK path](https://www.dropbox.com/s/wyjzs6rs3wf27qv/androidSDKPath.png?raw=1)

Then install packages from SDK manager.
![SDK view](https://www.dropbox.com/s/6kmrwnxajnthjl7/SDK.png?raw=1)

If you have another errors please contact us support@area730.com

