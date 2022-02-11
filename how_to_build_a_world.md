# how to build a world

In the end, a link to your world is the only thing you need to connect your environement to the Spacetime Meta. This mean you have no limitation on how to build your world. You can use any of the solutions proposed here or you can use your own way.

We still have to agree on the metaverse standards. One thing that is sure is that these standards will simply extend the already existing web standards and best practices. This means you wont have to use anything else than some javascript, html and css.

We strongly recomend 3D environements but you can always link to a classic 2D website like this page you are reading. Note that download links will be blacklisted.  

Here is a list of the recomended solutions to build your 3D world:
1. Build the world directly in WebGL using a js library like threejs or babylonjs.
2. Build the world using unity/unreal and export it to WebGL.
3. Use a service to create and host your world.

## Build with Three.js or Babylon.js
This is the most difficult way to build the 3D world since you will have do do a lot of coding. On the other side, this is the recomended solution if you are building app that that connects to the blockchain and/or IPFS since you will have more granular control on the code.

Examples with Threejs:: https://threejs.org/examples/ 
Examples with Babylonjs: https://www.babylonjs.com/games/ 

## Avatars (storing animating rigging)


If you plan on making avatars for the metaverse, you need to understand that one of the important parts of the standard is that we all agree on storing, animating, and rigging our avatars the same way. Until the standard is agreed on we can only suggest a way to do it without the certitude that THIS will be the standard.

Our top choices choice for rigging and animating avatars is blender and mixamo 

Blender:
You can do everything with blender. See all what you can do here:
https://www.blender.org/features/animation/

Mixamo:
They're a web-based service that helps developers rig and animate 3D characters by making rigging and animation easier. A developer can upload the mesh for a character, place joint locators and locator rings to figure out how to make the character move, and then run Mixamo's auto-rigging software. 

They have free services but also offer a premium access for 1500$ annually for more serious game development studios.
Owned by Adobe Systems.

## metaverse semeless integration

This is the part that will happen behind the scenes. The objective is for it to be flawless enough to “trick” the user into believing he is still on the same webpage (when in fact he go redirected)

Let's take an easy exemple. When you click “enter” on the spacetime map, it will open the link to your webpage. This page will have a loading period. If instead of a standard loading scenes you can choose to put an animation of a spaceship landing on the exact planet the user just clicked on… This will make the transition between spacetime and your website more seamless.






## Use a service.  
The is the recomended solution for the average metaverse enjoyer. The best known services available now are:  
1. **[Muse](https://www.muse.place/)**.  
Muse in a user-friendly metaverse creation app. One of its cool features is that they have maps like museums that you can customize easily for free. 

2. **[Spacial](https://spatial.io/)**.  
Spacial is a metaverse itself that has been in development since 2016. They have multiplayer features with live voice chat. They also offer many paying services for people who want a turnkey 3D environnement. They have a connection with metamask.
 
The consequence of using services:
These services are great to have something quickly, but you will never truly own your 3D environment. If the service provider starts charging for some features, you’ll have no choice but to pay or lose your world. 






## Frequently asked questions

**Can I use something else?**  
Answer is yes, you can build your stuff with the software that you want. As long as you can host your 3D environment on a webpage.The important part is that people don't have to download you game or world before playing. 

**Now that I have a virtual environement, how to connect it to spacetime meta?**   
See the documentation [here](https://github.com/Spacetime-Meta/documentation/blob/main/post_on_the_map.md)


