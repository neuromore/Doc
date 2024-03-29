# How to Give Users Feedback?

Neuromore Studio offers you three ways to give users neuro- and bio-feedback:

1. Using one of our already existing **interactive games** (e.g., controlling the speed of a car or the weather)
2. Using a state machine and the integrated experience window (e.g., controlling the volume or screen brightness of a video or an audio file)
3. Controlling through any application of your choice using the OSC interface (e.g., we provide a Unity plugin but you could also use Ableton or a write a script for a Raspberry Pi to control the lights in your home).

Below we'll show you how to build experiences using the built-in visualizations, the experience window, and the Unity plugin. For more information about the OSC integration see the OSC section.

## Using Pre-Built Games and Visualizations

The fastest way to create a neurofeedback experience is using one of the pre-built games and visualizations that come with the Studio.

At the moment we have 4 visualizations that you can access through the "Visualizations" pane in the top bar of the Studio or through the eye icon in the _Session Control_ window.
![Visualizations](../neuromoreStudio/Images/Visualizations/visualizations.png)
![Visualizations](../neuromoreStudio/Images/Visualizations/session_control_vis.png)

### What Visualizations Exist?

#### Cartoon Town

Drive a little car through a cartoon style town. The feedback will control the speed of the car while it automatically moves through the city. Ideal for kids.
![Cartoon Town](../neuromoreStudio/Images/Visualizations/cartoon_town.gif)
####Infinite Tunnel
Immmerse yourself into the infinite tunnel. Enable the space ship with smoke effects for more variation. Feedback changes color and camera speed.
![Infinite Tunnel](../neuromoreStudio/Images/Visualizations/infinite_tunnel.gif)

#### Forest Walk

![Forest Walk](../neuromoreStudio/Images/Visualizations/forest_walk.gif)

Enjoy the peace and connect to nature while you're slowly walking through the forest.

####Tropical Island
![Tropical Island](../neuromoreStudio/Images/Visualizations/tropical_island.gif)
Master controlling the sky and sea. The tropical island visualization adapts the weather from a sunny beach to a tropical storm based on the feedback. Waves will push against the beach while palm trees fight against the wind.

### How to Start a Visualization?

When you start a visualization by clicking on it in the visualization selection, it will prompt you to select the settings like screen resolution and graphics quality. 

![Visualization Settings](../neuromoreStudio/Images/Visualizations/vis_settings.png)

When you click on "Play" you will notice that the screen is blank and only shows the "neuromore" logo in the bottom left corner (see below). This is expected behaviour as the visualizations only become visable, when a session is running in the Studio. 

To start a visualization, you hence need to open a classifier or design file and click on "Go" in the “Session Control”. Then go back to the window running the visualization and enjoy controlling wind and weather, movement speed and other effects using the power of your mind. :)

![Blank Screen](../neuromoreStudio/Images/Visualizations/blank_screen.png)

### How can I Control the Feedback in the Visualizations?

Every game has a set of controllable feedback parameters that can be controlled from your classifier through _Custom Feedback_ nodes. 

#### Studio 1.7.0 and Later
From neuromore Studio 1.7.0 onwards, it will be possible to use specific feedback nodes from the _Output_ pane in the classifier menu. This makes it very easy to control specific available parameters like Speed, Volume, Screen Brightness, Weather, etc. by just dragging the node into the classifier and connecting it to your signal processing pipeline.

![Available Feedback Nodes](../neuromoreStudio/Images/Visualizations/feedback_nodes.png)

#### Before Studio 1.7.0

Before Studio 1.7.0, you can control various parameters of your game like the weather or the movement speed of a car using _Custom Feedback_ nodes that you drag into the classifier. Neuromore Studio communicates with the visualizations through the OSC interface: that means that for each parameter you want to control you need to specify the OSC address of the _Custom Feedback_ node by double clicking it. Also make sure that _Send OSC Msgs_ is enabled.

For each existing visualization you can find the available feedback parameters below. Scroll down if you want to build your own games and experiences using Unity.

![Visualizations](../neuromoreStudio/Images/Visualizations/custom_feedback_osc.png)

### What Feedback Parameters Can I Control?

In the available visualizations you can control a variety of different parameters. Just add a _Custom Feedback_ node to your classifier, enable _Send OSC Messages_ and set the _OSC address_ to any of the values below.

####Movement
/movement-speed (for Cartoon Town, Infinite Tunnel & Forest Walk)

####Environment
/weather-sun

/weather-rain

/weather-wind (Tropical Island only)

/weather-fog (Forest Walk only)

/weather-clouds (Forest Walk only)

/pollution (Cartoon Town only)

/crops (Cartoon Town only)

####Audio
/audio/volume

####Camera
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

## How Can I Create Experiences with Video and Audio Feedback?

Let's say you want to build an experience where the user can control the screen brightness of a video using neurofeedback. Also you want to give them the choice which video to play, ask them how long they want to train or record a baseline before starting the experience.

For that neuromore Studio offers you to configure the application flow using the _State Machine_ that then controls the experience in the built-in experience window.
On the right you can see such an experience in which the user is first prompted to select how long they want to train their focus before controlling the screen brightness of a video with neuro-feedback. For the full example see our _Getting Started_ section.

![Experience window](../neuromoreStudio/Images/Visualizations/experience_window.gif)

## How Can I Build My Own Games?

### Building Your Own Games in Unity
To enable you to build games and multisensory neurofeedback experiences we have developed an open source neuromore Unity prefab.
To add neurofeedback to your games you need to download the neuromore prefab from [this repository](https://github.com/neuromore/studio-visualizations-free) and add it to your project. where you can get inspired how you can use the neuromore prefab.

### How Do I Use the Unity Prefab?

[Here is a video](https://www.youtube.com/watch?v=-kPzBAyA-og) that shows you the process of adding neurofeedback to your Unity games.

We recommend to have a look at the [Forest Scene example](https://github.com/neuromore/studio-visualizations-free) to get inspiration on how to use the prefab. In the Forest Scene you can control the weather and the movement speed of the camera using feedback OSC parameters from neuromore Studio.
The way this works is that the neuromore prefab communicates with neuromore Studio over the OSC protocol and dispatches how to control the application based on the feedback parameter.

Let's see how that looks like in action: open the forest scene in Unity and start the scene in Unity.
Now go to neuromore Studio and open a classifier with OSC output nodes. To get started you can use the _FirstFocusTrainer_ from the [_GettingStarted_](./Tutorial_GettingStarted.md) example that you can find in the backend file system under _examples->GettingStarted->FirstFocusClassifierTestSystem_).

Start a session in neuromore Studio using the _Session Control_ widget. You will now see the weather and the camera speed update in real time in the forest scene in Unity.

### What Feedback Parameters Can I Use?
In the forest scene you can also get a great inspiration how to implement feedback actions. Some pre-configured feedback parameters that work in the Forest Scene are

- /weather-sun

- /weather-fog

- /weather-clouds

- /movement-speed

- /session/level

- /session/points

- /audio/volume

  You can find the full mapping of pre-defined OSC feedback parameters under _Assets->Resources->neuromore Prefab->Scripts->Network->OSCMapping.cs_.
  There you can also add custom mappings whose functionality you can then add to the WorldController.cs file (under \_Assets->Resources->neuromore Prefab->Scripts->WorldController.cs).

Happy developing!
