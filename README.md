# Reza-planet-VR-environment
Weird, Cool, and Fun space to see some animals, attend a science class or stare at the stars
![thumbnail](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/db427b75-b329-4770-a541-f7aa34c7605e)

**Step 1:** Setting up the project  

**Step 2:**  Creating a scene and saving it in your directory for the project in the scene’s folder.
![Saving scene 1](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/09178d03-5956-4bed-a45c-4ba944414454)

**Step 3:** Importing ProBuilder from package manager

![package manager (probiulder) and XR interaction 2](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/e92ed334-2091-4aea-a772-0226b5ef2d00)

![adding probuilder window 3](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/2cca77cf-1a8f-4c8c-9510-c764ca373c54)

The image shows how to access the probuilder window. On the top menu bar, go to Tools>ProBuilder>ProBuilder window. 
Plane shape was added to create a floor for our scene which was chosen from new shape option in ProBuilder window.
![stairs added and circumference experiment 4](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/45ce7490-49f5-466a-914c-3316984b3ecd)

**Step 4:** Downloading and importing assets from the Unity asset store by selecting Add to My Assets> Open in Unity.
![showing how assets are downloaded and added to unity for import](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/985d2335-6364-4616-a746-f08693ca6b9a)

Clicking Import on the main package manager tab and, once the pop-up window apears, click import all to use desired assets including prefabs, materials, and textures.
![adding assets](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/bde35540-f752-49e8-9dd4-dcfa1467d6a1)

**Step 5:** Building the environment
Stairs were added and I experimented with the circumference of the stairs which would turn it to the side and bend the stairs. However, for the final implementation, I decided to use normal stairs (i.e. circumference = 0) and use scaling, rotation, and moving tools to create a staircase with an arch and a platform on the top which would allow our character to jump down to the pool (diving platform). Vertex snapping was used to ensure precise object placement.
For ease of use, stairs were duplicated using ctrl/cmd + d but this can also be done by right-clicking on the object and selecting duplicate from the drop-down menu.
For the arch, face selection was used to elongate the top and create the shape shown in the image.
![arch was added and face selection feature was used to elongate a side of it (8)](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/621c916e-65c0-4dda-9841-9459d7f0f3cf)

During the first build, I noticed planes were not suitable as stairs’ connectors as they can only be seen from one side so I replaced some floors represented by planes with cubes.
The scene was saved every few minutes to ensure that the work would not be lost if there was a problem with the device. Walls were placed to make a classroom and a garage. Office props were used to decorate the classroom and planes were added as the classroom roof to make it easier to edit inside the room (planes in Unity are visible from only one side).
Images on the wall were made by dragging jpeg/png files from our assets onto planes to represent informative posters. A plane as a roof was also added for the garage. This allows us to view inside the rooms clearly from a higher point of view.
low-poly office props and materials were added by rendering them into URP  through Edit>Rendering>Materials>Convert Selected Built-in Materials to URP. 
Image![lowpoly office props and textures were added by rendering and turning them into UDP default version 13](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/083bed2f-5d85-4d8a-8697-d1181ba2a0bf)

**Step 6:** Changing the Sky view. The skybox environment was changed by downloading the Space Sky package and importing it to the assets. It was then dragged into the sky. This changed the external view of the environment.
![sky was added (9)](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/0dd0c925-53ec-4249-b5eb-339190935c46)

**Step 7:** Further environment development. Fences were added to create a small zoo with imported prefabs of animals. A tiger, cow, bear, duck, and two chickens were added to the scene by dragging the prefabs onto the scene.
![adding fence (10)](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/02bb5d83-9797-400a-8ff5-16ebbdf46b41)

An exterior swimming pool was added, however, the existing prefab had no water inside. I augmented the original prefab with water by making a plane and imposing an image of water on the surface of the plane. I also made a poly shape using the ProBuilder package to be used as a stargazing platform.
![prefab pool- water added as a plane later on by imposing a water texture(from pictures) 18](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/c5a1aee0-35fb-4858-bae5-95ea5c53b42b)

**Step 8:** Extra Feature [Audio]
(Disclaimer: In hindsight, I now know there is a better/correct way of adding audio, however, this is how I initially discovered it could be added for my purpose.) 
Appropriate audio was added to individual objects using a singular audio object. To do this, I clicked ‘+’ in the hierarchy window and selected an Audio Source for it. Once the audio appeared in the hierarchy window, I dragged the audio object under the parent cars object. I did this thinking the audio object would be applied to other individual/child car objects under the parent (representing a collection of) cars. However, upon inspection, I soon realised that audio was not added to each car object, but instead, a single audio was added for the object representing the group of car objects. The benefit of moving the audio object as a child of the parent car object is that I can now easily locate the audio associated with cars. 
Audio files were downloaded and added to assets. Finally, the soundtrack can be dropped on the AudioClip option in the Audio Source menu.
![Audio source was added to tiger object as a child (14)](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/a331568e-6877-4bc8-a439-a9aaa2cfa3dd)

The audio was optimised by changing the spatial blend to 3D ticking loop and play on awake. I also reduced the logarithmic maximum range for the sound from 500 to 10 to reduce noise clutter - this resulted in the scene being more realistic as the sound now increases as the character gets closer to the objects (adhering to the Doppler effect). ‘Gizmos’, located on the right-hand side of the scene menu, can be toggled on to make the sound setting range easier to work as this enables us to drag the sides of the projected sphere to increase or decrease the range.

**Step 9:** Turning directional light to baked mode (Area) and changing the lighting setting for objects by enabling Contribute Global Illumination.

**Step 10:** Adding XR Interaction Toolkit and XR Plugin management 
In Edits>Project Setting>XR plug-in management we need to make sure Oculus is ticked so we can connect the game to the headset when the play button is pressed in the Unity hub
in the project settings, the player tab is found and under the configuration setting input was set to new

**Step 11:** Extra Feature Addition of Text
The classroom, garage, and zoo were labelled with the addition of text using the ‘+’ in the Hierarchy window, clicking on the 3D Object>Text - TextMeshPro. Different font setting including making text bold, italic, and adding underline can be found in the Main Settings. Colour can be changed by changing the Vertex Colour in the Main Settings or Face Colour under Extra Settings. Wrapping (highlighted in blue in the picture) can be enabled or disabled to make the text flow onto the next line or fit in one line respectively.
![Adding text and enable and disable wrapping mode](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/3e94e675-c5e1-4d6d-8e47-2cf0eed8b2ff)

**Step 12**: First Build
The project was built for testing. To do this we go to File>Build Setting.  
![Screenshot (28)](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/a8baf758-b864-4810-9fbf-57b0116e32b3)

**Step 13:** During experiments with the first version, there was a tunnelling vignette when moving as default which is to stop motion sickness. I decided to hide it (ticked off) as my environment is quite small and also it is not visually appealing to have a tunnel vision when moving in our environment. To do this we need to click on the arrow left side of XR Rig (XR origin). Click on the drop-down arrow for the main camera to find the tunneling vignette and finally tick it off on the inspector window.
![tunneling vingete diasabled 17](https://github.com/Rezvision/Reza-s-planet-VR-environment/assets/147525543/b1e3d20c-5a68-4da9-a1e2-fbb3cf24bb1c)

**Step 14:** The following components were added to the XR origin: Locomotion System, Teleportation Provider, Character Controller, and character Controller Driver.
XR left hand default controller is used to add the controllers. Right controller is used for turning and teleportation. The left controller is used for movement (locomotion).
The main plane was selected and under the inspector window, a teleportation area was added as a component and its interaction layer mask was changed to “everything”

**Final Notes:** Build versions and final edits 

Multiple issues seen in version 5 were solved in the final version (version 7).
The issues included: 
1- Teleportation area was not possible in the rooms even though the floor plane had a teleportation area as a component. This was fixed by changing the interaction layer map to everything for the planes in the rooms (previously only the main plane had the correct option for the interaction layer map).

2- Some gaps between walls and floors were fixed by moving or resizing the objects. Also, some of the text added onto the walls was too far away from the wall - this was again fixed by relocating the text object

3- As the stairs were still quite difficult for the character to climb after the fourth build, I increased the step number from 15 to 20, making each step shorter in height. 

4- The audio had some issues - sometimes the audio was too quiet, or other times not even playing. It was deducted that this problem was caused due to using the logarithmic curve and setting the minimum distance to 0. This would decrease the audio too sharply to near zero as the distance changes. To solve this, in some cases, I changed the volume rolloff settings inside the inspector window to linear, and in other cases, I kept the logarithmic volume rolloff but changed the minimum distance to 0.2.

5- Spotlights were added to the garage to enhance the environment and sound was added to the stargazing platform.
