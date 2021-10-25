# Creating your first application with neuromore Studio

## What we will build - A simple focus trainer using an OpenBCI headset

In this small tutorial we will build a basic focus trainer using an OpenBCI headset from scratch. The application will first ask the user for how long they want to train before showing a video whose sharpness depends on the user's alpha channel activity measured using the OpenBCI.

## A neuromore application in a nutshell

A neuro-/ bio-feedback application in neuromore consists of 3 parts:

1. a **classifier** in which we define the **signal processing pipeline**. Here we can do all sorts of operations on the data coming from biosensors, from simple filtering over fourier transformations to ... In our example we will analyse the current amplitude on the alpha band and stream it into a variable.
2. a **state machine** in which you define the **application logic**. In our example we will here define the flow from starting the experience over selecting the training duration to adapting the video image based on the current amplitute on the alpha band.
3. the **actual experience** that your user will interact with. This can be an **application using simple widgets available in neuromore Studio** as in this example, a **game built in Unity**, or an **app running on a mobile phone**.

## Creating a blank project in neuromore Studio

Projects are stored in the **neuromore back-end file system**. When you first open neuromore Studio you will find a window in the top-right corner where you can see example projects.
To create a new project, let's create a folder with the name of your project.

## Creating a new classifier

Classifiers and state machines are stored in separate files. Let's select your new project folder and create a new classifier file.

Designing the signal processing pipeline

## Adding a biosensor to read data from

In the _Input_ category you have a variety of devices to choose from. Drag the OpenBCI device into your classifier to start designing the signal processing pipeline.

## Designing the signal processing pipeline

In the Input category you have a variety of devices to choose from. Drag the OpenBCI device into your classifier to start desining the signal processing pipeline.

To get the alpha band activity we first need to link our EEG channel to a Fast Fourier Transformation (FFT) node. Drag the FFT node in and connect it to the EEG output of the OpenBCI device.
