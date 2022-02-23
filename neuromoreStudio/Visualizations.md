#Visualizations & Games

##Existing Visualizations

###Cartoon Town

Controllable feedback parameters:

###Infinite Tunnel

Controllable feedback parameters:

###Forest Walk

Controllable feedback parameters:

###Tropical Island

Controllable feedback parameters:

##Building Custom Visualizations in Unity

<add video>

###Download and Installation
To enable you to build games and multisensory neurofeedback experiences we have developed an open source neuromore Unity prefab.
To add neurofeedback to your games you need to download the neuromore prefab from the Unity asset store and add it to your project.
We also have a [repository with an example project](https://github.com/neuromore/studio-visualizations-free) where you can get inspired how you can use the neuromore prefab.

###How do I use the Unity prefab?
We recommend to have a look at the [forest walk](https://github.com/neuromore/studio-visualizations-free) where the weather and the movement speed of the camera are controlled using feedback parameters in neuromore Studio.
The way this works is that the neuromore prefab communicates with neuromore Studio over the [OSC protocol](./OSC.md) and dispatches how to control the application based on the feedback parameter.

Let's see how that looks like in action: open the forest meditation scene in Unity (make sure you have all the [dependencies](https://github.com/neuromore/studio-visualizations-free/README.md) downloaded) and start the scene in Unity.
Now go to neuromore Studio and open a classifier with OSC output nodes. To get started you can use the _FirstFocusTrainer_ from the [_GettingStarted_](./Tutorial_GettingStarted.md) example that you can find in the backend file system under _examples->GettingStarted->FirstFocusClassifierTestSystem_).

Start a session in neuromore Studio using the _Session Control_ widget. You will now see the weather and the camera speed update in real time in the forest scene in Unity.

###Which feedback parameters can I use?
Some pre-configured feedback parameters that you can use out of the box are

- /weather-sun
- /weather-rain
- /weather-fog
- /weather-clouds
- /movement-speed
- /session/level
- /session/points
- /audio/volume
  You can find the full mapping of pre-defined OSC feedback parameters under _Assets->Resources->neuromore Prefab->Scripts->Network->OSCMapping.cs_.
  There you can also add custom mappings whose functionality you can then add to the WorldController.cs file (under \_Assets->Resources->neuromore Prefab->Scripts->WorldController.cs).
