# The Spacetime Community Standard Kit

The goal of this kit is to unify the way virtual environements are built in the spacetime metaverse while allowing complete freedom to the creators. Keep in mind this is not a final version. The controls will be adjusted continuously to accomodate all users and keep up with the latest trends. As of now, you can only customize the terrain and the avatar.

The way to do this:
1. Clone or download the [Spawn Planet Code](https://github.com/Spacetime-Meta/spawn-planet2.0).
![clone code](https://raw.githubusercontent.com/Spacetime-Meta/documentation/main/src/git_code_panel.png)

3. Navigate to the `spawn-planet2.0/js/main.js`
4. There you can see on the line 14 we create a new Standard Virtual Environement (StdEnv) and call it VE `const VE = new StdEnv();`. Then on the line 20 we use the `init` method to initialize the environement with a new world and avatar then we give it a x,y,z location. Right now it should look something like this:

```
// ===== Virtual Env =====
VE.init('glb/spawnplanet.glb', 'glb/vanguard.glb', 0, -20, 0);
```
