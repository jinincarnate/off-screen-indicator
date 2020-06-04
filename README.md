# off-screen-indicator
A simple solution for implementing target indicator, waypoint or HUD navigation system in unity.

## Asset store asset is outdated by one commit on 4th June 2020, will remove this statement when its updated on asset store.
[![Unity](https://img.shields.io/static/v1?style=for-the-badge&label=Unity%20Asset%20Store&labelColor=181717&message=Download&color=green&logo=Unity&logoColor=white)](https://assetstore.unity.com/packages/slug/71799)
Will always try to keep the asset store version updated but you can always get the latest version from the Repository.

## Steps to setup up the targeting system

* Open a unity project and import the ‘Off Screen Target Indicator’ package.
* Open the scene in which you want to add the ‘Off screen target indicator’.
* Add a new Canvas to the ‘Hierarchy’. Make sure to set the canvas ‘Render Mode’ to ‘Screen Space – Overlay’.
* Right click on the above canvas and add a panel as a child to it. (You can rename the panel if you want to ‘Off screen indicator panel’).
* Set the alpha of the above panel to zero. (You can do so by changing the ‘alpha’ value of the ‘Color’ property in the ‘Image’ script of the panel).
* Add the ‘OffScreenIndicator.cs’ script form the ‘Pixel Play/Scripts/OffScreenIndicator/’ folder to the above panel. (You can do so by dragging and dropping the script from the scripts folder to the panel or clicking the ‘Add Component’ button and typing ‘OffScreenIndicator’ and selecting it).
* In the same way add ‘ArrowObjectPool.cs’ and ‘BoxObjectPool.cs’ scripts to the panel. And assign the values of the ‘Pooled Object’ properties for both the scripts by dragging and dropping the ‘Arrow Indicator’ and ‘Box Indicator’ prefabs respectively from the ‘Pixel Play/Prefabs/’ folder in those empty values.
* Now drag and drop the ‘Target.cs’ script form the scripts folder to all the target game objects in the scene and adjust the various values of the script properties as you see fit.
* For testing you can add the provided ‘ExtendedFlyCam.cs’ script to your ‘Main camera’ and hit ‘Play’.

**NOTE : To enable/disable the indicator at runtime for a target in the scene just enable/disable the target script on your target gameobject.(The targets get dynamically added and removed from the targets list as you enable or disable them in the scene).**

**NOTE: There is a ‘DefaultExecutionOrder’ attribute added on the ‘OffscreenIndicator’ class and the ‘Target’ class. Make sure that the attribute’s value of ‘OffscreenIndicator’ class should be always less than the ‘Target’ class, so that the ‘OffscreenIndicator.cs’ would always run before the ‘Target.cs’.**

## Modifying or creating your own arrow and box prefabs
* To modify the ‘Arrow’ or the ‘Box Indicator’ prefabs, select the prefabs in the ‘Assets’ folder.
* As you will see these are simple ‘UI image’ components with a ‘UI text’ component added as a child to it.
* You can change the size of the prefabs by adjusting the ‘Width’ and ‘Height’ properties of the ‘Rect transform’ 
* You can change the sprites for the arrow and box prefabs by dragging and dropping your own sprite in the ‘source image’ field for the ‘Image’ script component.
* If you are creating your own prefabs, make sure to attach the ‘Indicator.cs’ script from the scripts folder to both the prefabs.
* Also choose the value for the ‘Indicator Type’ field for the Indicator component(added in previous step).

**NOTE:
Make sure the sprite you use for the arrow prefab, its orientation should be the same as the default white arrow sprite image provided i.e, its tip should be pointing towards the middle right.**

