# Assignment 2: Creating Interactive VR Experiences

**Due: Thursday, September 28, 11:59pm CDT**

In this assignment, you will create an interactive VR application using a library that implements common forms of locomotion and object interaction. You will also gain experience with development using WebXR, which provides a standardized pipeline for deploying immersive experiences in a web browser.

## Submission Information

You should fill out this information before submitting your assignment. 

1. **Ready for Grading**. When your assignment is complete, you should change the line below to YES and then push to GitHub. This will signal to the TA that your assignment is ready to be graded. If the submission is completed after the due date, the timestamp of the commit will be used to determine how many late points will be applied.

   `NO`

2. **Third Party Assets**. List the name and source of any third party assets that you added, such as models, images, sounds, or any other content used that was not created by you.

   `TO BE COMPLETED`

3. **Grading Instructions**. Please provide a brief description of your VR experience, identify the interaction techniques you implemented, and provide any usage instructions needed for the person grading your assignment.

   `TO BE COMPLETED`

4. **Wizard Bonus Functionality**. If you completed the bonus challenge, then please provide a brief description of the additional functionality that you would like us to consider for extra credit.

   `TO BE COMPLETED`

## Prerequisites

To work with this code, you will first need to install:

- [Godot Engine 4.1.2](https://godotengine.org/)
- [Immersive Web Emulator Browser Extension](https://github.com/meta-quest/immersive-web-emulator)

Note that this project was created using the most recent version of Godot released on October 4, 2023. Although it remains backwards compatible with 4.1.1, downloading the newest version of the engine is recommended to incorporate the latest bugfixes.

## Getting Started

The template project is pre-configured for WebXR and includes:

- Default skybox and scene lighting.
- XROrigin3D, XRCamera3D, and XRController3D objects for both the left and right hands. Note that neither controller has a MeshInstance3D attached yet, so they won't be visible to the user.
- The CanvasLayer, Button, and WebXR initialization script (attached to the Main node). 
- A 10x10 meter platform for the user to stand on, which includes a plane mesh and a CollisionShape3D object, which defines a collision volume that will prevent the user from dropping through the floor once gravity is added.

Your first step should be run the project in a web browser and confirm that it works with the immersive web emulator. Note that the first time, you will need to activate TLS in Editor->Editor Settings->Web. 

After you have the emulator working, then you can try viewing the project on the Quest. You will first need to identify the local IP address of your computer, which must be on the same network at the headset. You should replace `localhost` with this value on the same editor settings page referenced above. You should then be able to load the project using the web browser on the Quest. Note that for convenience, I like to use a URL shortener such as [z.umn.edu](https://z.umn.edu/) to make text entry easier in VR, but this is optional. 

If you run into trouble during any of these steps, please refer to the [lecture on WebXR](https://mediaspace.umn.edu/media/t/1_txfz039b) for a more detailed walkthrough or post a message to the `#assignment-2` channel on Slack.

## Part 1: Setup Godot XR Tools

In this assignment, you will be creating an interactive VR application using [Godot XR Tools](https://godotvr.github.io/godot-xr-tools/).  After installing this from the Godot Asset Library, you will need to make sure to activate the plugin in project settings as described [here](https://godotvr.github.io/godot-xr-tools/docs/setup/) and then **restart Godot**. This is very important; otherwise the controller interactions will not work!

Next, you should add virtual hands to the project, as demonstrated in class.  The XR tools include several different options for [hand models](https://godotvr.github.io/godot-xr-tools/docs/hand_models/), and you are also welcome to add your own custom materials. Note that you should use the low poly models because this will be running directly on the Quest!

## Part 2: Adding Direct Movement

The first interaction you should add to your project is [direct movement](https://godotvr.github.io/godot-xr-tools/docs/direct/) using the controller thumbstick.  When added as a child of the controller object, MovementDirect should work directly out of the box, and the plugin will automatically also create a PlayerBody for you.  However, you will likely need to change the `Input Action` specified on the object inspector from `primary` to `thumbstick`.

## Part 3: Create an Interactive VR Experience

The rest of this assignment is very open-ended.  Your goal is to select a couple more interactions provided by Godot XR Tools and use them to create your own interactive VR experience. Games are the most popular choice, but you are not strictly limited to just a game, and creativity is encouraged.

The specific requirements are as follows:

- The experience uses at least one additional **movement** method.  Turn does not count because it is trivial and not really separate from Direct Movement, but there are about 10 other movement providers to choose from!
- The experience uses at least one **interaction** method (Pickup Function or Pointer).
- The interactions are well-integrated into the objectives or gameplay of the VR experience.

For the last part, this means that you should think about *how* you can design the VR experience to take advantage of the specific techniques you selected. For example, a simple experience where the user just needs to walk around normally that just copy-and-pastes a different movement technique in its place would not be an example of thoughtful integration.  Here are a couple examples:

- A game that requires hitting targets at different heights and makes use of vertical locomotion methods (e.g., Climbing, Wall Walk) to achieve this goal.
- A game that requires traversing an environment with pits or obstacles that prevent normal walking could consider alternative locomotion methods (e.g., Glide, Grapple) to achieve this goal.

The key point is that the objectives for the user and the interaction techniques selected to achieve them should make sense together logically. 

Note that the expectations for this assignment are for a functional prototype of the interactions, not a complete game. You are not being graded based on criteria such as game narrative or artistic quality. This assignment will require creating a more complex virtual scene, and you can do so using only 3D mesh primitives. Of course, you are also welcome to use the Synty assets posted on Canvas or other third-party assets you find online. 

If you do choose to add third-party assets, make sure that you only use low poly meshes since this needs to run directly on the Quest. Although the visual quality of the assets is not part of the grading criteria, very complex 3D models could slow down your application and negatively impact the usability of the interaction techniques. Additionally, large file sizes will cause WebXR applications to load very slowly because they need to downloaded by the web browser at runtime.

## Rubric

Graded out of 20 points.

1. TBD

**Bonus Challenge:** For two points of extra credit, you can look ahead a bit at the documentation on [XR controller input](https://docs.godotengine.org/en/stable/tutorials/xr/xr_action_map.html) and add some interaction with the 3D objects using the hand-tracked controllers. This is an open-ended challenge, and creativity is encouraged! Make sure to describe any additional functionality at the top of this readme file so that we can properly test it during grading. (+2)

**Documentation:** Make sure to document any third party assets or code used in this assignment at the top of this readme file. One point will be deducted for using third party assets without attribution. This only refers to additional assets that you find on your own; you don't need to document anything that is already described in the assignment instructions. (-1)

## License

Material for [CSCI 5619 Fall 2023](https://canvas.umn.edu/courses/391288/assignments/syllabus) by [Evan Suma Rosenberg](https://illusioneering.umn.edu/) is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-nc-sa/4.0/).
