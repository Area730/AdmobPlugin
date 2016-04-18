-----------------
IOS common errors
-----------------

1. When you use old version of Unity(4.6 and lower) the included GoogleMobileAds.framework_ in folder *Assets/Plugins/IOS* will not be automatically linked to your XCode project. To solve this problem copy GoogleMobileAds.framework_ to the root of your exported project. 

.. _GoogleMobileAds.framework: https://developers.google.com/admob/ios/download

.. image:: _static/framework.png
    :align: center

2. After that you need to config your **build settings**  

| 
 
    2.1 Disable bit code 

    .. image:: _static/bitcode.png
        :align: center

| 

    2.2 Enable Modules (C and Objective-C) 
    
    .. image:: _static/modules.png
        :align: center


3. If you use xCode 7.2  or higher you could get the following error because of incompatibility new xCode and Unity generated files. 

.. image:: _static/Noreturn.png
    :align: center


to solve this problem just delete circled ```NORETURN``` statment. 