The way to do this:
1. Clone or download the [Spawn Planet Code](https://github.com/Spacetime-Meta/spawn-planet2.0). 
2. Navigate to the `spawn-planet2.0/js/main.js`
3. There you can see on the line 14 we create a new Standard Virtual Environement (StdEnv) and call it VE `const VE = new StdEnv();`. Then on the line 20 we use the `init` method to initialize the environement with a new world and we give it a x,y,z location. Right now it should look something like this:

```
// ===== Virtual Env =====
VE.init('glb/spawnplanet.glb', 0, -20, 0);
```
