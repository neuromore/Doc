#Visualizations & Games

We believe that neurofeedback applications can be more than just adapting the screen brightness or the volume of the audio.
That's why we've added interactive experiences and games to neuromore Studio that you can access through the "Visualizations" pane in the top bar or through the eye icon in the _Session Control_ window.
![Visualizations](../neuromoreStudio/Images/Visualizations/visualizations.png)
![Visualizations](../neuromoreStudio/Images/Visualizations/session_control_vis.png)

Every game has a set of controllable feedback parameters that can be controlled from your classifier using the _Custom Feedback_ node.
You can see an example of controlling various parameters of your game
For each existing visualization you can find the available feedback parameters below. Scroll down if you want to build your own experiences using Unity.

![Visualizations](../neuromoreStudio/Images/Visualizations/custom_feedback_osc.png)

##Existing Visualizations

###Cartoon Town
Drive a little car through a cartoon style town. The feedback will control the speed of the car while it automatically moves through the city. Ideal for kids.
![Cartoon Town](../neuromoreStudio/Images/Visualizations/cartoon_town.gif)
###Infinite Tunnel
Immmerse yourself into the infinite tunnel. Enable the space ship with smoke effects for more variation. Feedback changes color and camera speed.
![Infinite Tunnel](../neuromoreStudio/Images/Visualizations/infinite_tunnel.gif)

###Forest Walk
![Forest Walk](../neuromoreStudio/Images/Visualizations/forest_walk.gif)

Enjoy the peace and connect to nature while you're slowly walking through the forest.

###Tropical Island
![Tropical Island](../neuromoreStudio/Images/Visualizations/tropical_island.gif)
Master controlling the sky and sea. The tropical island visualization adapts the weather from a sunny beach to a tropical storm based on the feedback. Waves will push against the beach while palm trees fight against the wind.

##Controllable feedback parameters

In the available visualizations you can control a variety of different parameters. Just add a _Custom Feedback_ node to your classifier, enable _Send OSC Messages_ and set the _OSC address_ to any of the values below.

###Movement
/movement-speed (for Cartoon Town, Infinite Tunnel & Forest Walk)

###Environment
/weather-sun

/weather-rain

/weather-wind (Tropical Island only)

/weather-fog (Forest Walk only)

/weather-clouds (Forest Walk only)

/pollution (Cartoon Town only)

/crops (Cartoon Town only)

###Audio
/audio/volume

###Camera
/camera/blur

/camera/vignetting

/camera/sepia

/camera/grayscale

/camera/water/freeze

/camera/water/amount

/camera/fade-color-a

/camera/fade-color-r

/camera/fade-color-g

/camera/fade-color-b

##Building your own Games in Unity

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
