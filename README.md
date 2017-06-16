# Mapbox Tango Unity example

Example which integrates Google’s Project Tango SDK with the Mapbox Unity SDK to create an augmented reality experience on an Android phone with Mapbox maps.
This is the result of @Guardiola31337 and @danesfeder [Mapbox GL Hack Friday](https://github.com/mapbox/gl-internal/issues/665) project.

---

## Notes

At the WWDC keynote on Monday (6/5/2017), one of Apple’s announcements was a new framework called ARKit, allowing iOS developers to create augmented reality experiences. A day after the announcement, everyone saw this [awesome example](https://twitter.com/heyadam/status/872278723700994048).

Pablo and I set out to create the same type of example, but on Android with [Google’s Tango SDK for Unity](https://developers.google.com/tango/apis/unity/) and the [Mapbox Unity SDK](https://www.mapbox.com/install/unity/).  

**Step 1 - Setup:**
We only had one Tango compatible device (**Lenovo Phab 2 Pro)**, which Pablo borrowed from a friend.  So Pablo took most of his morning to address setting up the environment and getting a simple example working. There were some conflicts between the Unity Android plugin, Tango and Mapbox SDKs (libraries included twice and issues with different target versions) which were [solved](https://stackoverflow.com/questions/44521406/unity-project-with-mapbox-and-project-tango#answer-44524572) tweaking the AndroidManifest and removing the duplicated dependencies.

**Step 2 - Kitty Example:** 
After Pablo had the environment up and running, we first wanted to learn the Tango SDK and how it works with Unity to create AR experiences before we began integrating the Mapbox Unity SDK. We followed this [example](https://developers.googleblog.com/2016/05/bringing-virtual-cats-to-your-world.html) and learned how Tango can detect surfaces in an environment and places objects on them (like cats):

![meow](https://user-images.githubusercontent.com/1668582/27236836-d1f9db7e-52c6-11e7-9bf7-64868416762b.gif)

**Step 3 - Replace cats with the Mapbox Unity SDK:**
Our final goal was to have a Mapbox `GameObject` centered in a room that we can walk around and look at through the Android phone.  We followed the [mesh generation tutorial](/doc/Mesh-Generation-Tutorial-cn81Hk1AYGoraEIvjWQQF) to create a map and add a 3D mesh factory for extrusions or terrain:

![SF city view](https://user-images.githubusercontent.com/1668582/27236817-c36155c4-52c6-11e7-92c9-4e8295d2ac38.gif)

**What we learned:**
With neither of us having prior experience with Unity or the development environment, we found most of our issues trying to figure out how to move objects and how they would move in reference to the `TangoCamera`.  We spent most of the day with the camera starting off in the middle of the ocean or in the side of the building.  @Siyu S actually helped us out at the end of the day to move the camera to the correct position - it was awesome to see everything work after that.

**Extra ball:**

![Mount Fuji](https://user-images.githubusercontent.com/1668582/27236888-10ed26ba-52c7-11e7-9278-e6009bceba56.gif)
