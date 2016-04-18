Admob Plugin
============


Import
------

* Download this plugin_ 
* Watch this_ tutorial: 
.. _plugin: https://www.assetstore.unity3d.com/en/#!/content/57268
.. _this: https://www.youtube.com/watch?v=S7F9enxcvTE

.. raw:: html

    <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; height: auto;">
        <iframe src="https://www.youtube.com/embed/S7F9enxcvTE" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe><br/>
    </div>

| 

* Or follow these steps: 


1. Drag Admob prefab from *Area730/Admob/Prefabs* into your scene. You need to add this prefab to your game only once as **AdmobManager** is a singleton. 


.. image:: _static/1.png
    :align: center

2. Set Admob unit ids and you are almost done 

.. image:: _static/2.png
    :align: center

3. To show banner  call *AdmobManager.Instance.RequestBanner(AdPosition position)* where position is **enum** and can be::

    AdPosition.Top
    AdPosition.Bottom
    AdPosition.TopLeft
    AdPosition.TopRight
    AdPosition.BottomLeft
    AdPosition.BottomRight

You can also specify the size of the banner as second parameter. The default size is **320x50**.
To show interstitial you have first to load it by calling **AdmobManager.Instance.RequestInterstitial()**. After the interstitial is loaded, the **OnInterstitialLoaded()** callbacks will be invoked. Admob prefab comes with default attached callback functions (see *Area730/Admob/Scripts/AdmobController.cs*). You can also add your own if you want. 

.. image:: _static/3.png
    :align: center

After the interstitial is loaded, you can show the ad by calling **AdmobManager.Instance.ShowInterstitial()**.  

Building projects
-----------------

After configuring your mediation you need to build your game to mobile devices. Sometimes it might cause some errors next section helps you to solve it.
