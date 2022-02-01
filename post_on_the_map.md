# How to build/customize a planet on the Spacetime Meta map.

Spacetime Meta Map Actual Official Link: https://www.spacetimemeta.io/map.html

**The map is still in heavy developement! Please be aware that there will be constant updates to this documentation and you might have to update your app/chunk to keep up with the latest methods**

As of 2022-01-28, the process is still a manual upload of your metadata to the [metadata repo](https://github.com/Spacetime-Meta/spacetime-metadata/blob/main/test_data). This process will be updated on the mint date.

To connect a website to the metaverse, you will need the following 5 things:

1. **Your 3D icon**  
This part is optional, if you dont put anything, the loader will generate a default planet for your location.
If you want to customize the appearance of your icon/planet, you will need a 3D model in the .gltf/.glb file format.  
Once loaded in the map, you model will be scaled down to 1mx1mx1m so it is recomemded you keep that in mind to avoid weird scaling.  

2. **Your project logo**  
This should be a square image, idealy 64x64.

3. **Banner image**  
This should be a 1920x1080 image.

4. **Link to your app**  
This is the link people will follow when entering your planet.

5. **Name to display**  
This is the short text that appears when users mouse over your planet.

![interface map](https://raw.githubusercontent.com/Spacetime-Meta/documentation/main/src/map_interface_components.png)

Once you have all 4 items, you need to host them somewhere. There are many options to make your content available, but the one we recomend is [IPFS](https://ipfs.io/). All you need is the url for each of these items. Then you insert the urls in the following template 

```
{
  "SpacetimeMeta":{
    "name":"Spacetime Meta",
    "prtl":"https://spacetime-meta.github.io/spawn-planet2.0/",
    "img":"https://cdn.discordapp.com/attachments/874011464996909088/927263231133745152/This_could_be_your_home.png",
    "logo":"https://ipfs.io/ipfs/QmfD8B3U5pzKDxV5XC2SbmysVWUwDvQ4eVLrZuUfJMBGEt",
    "iconType":".gltf",
    "gltf": "QmSKSkeKt5mrpSUZbcndCyHC4j3BXC52HfxTAtJ6bSG72m"
  }
}
```
Once you are done preparing your metadata, we recomend you validate it using a [JSON validator](https://jsonlint.com/). Your complete matadata should look something like this:
```
{
  "SpacetimeMeta":{
    "name":"Spacetime Meta",
    "prtl":"https://spacetime-meta.github.io/spawn-planet2.0/",
    "img":"https://cdn.discordapp.com/attachments/874011464996909088/927263231133745152/This_could_be_your_home.png",
    "logo":"https://ipfs.io/ipfs/QmfD8B3U5pzKDxV5XC2SbmysVWUwDvQ4eVLrZuUfJMBGEt",
    "iconType":".gltf",
    "gltf": "QmSKSkeKt5mrpSUZbcndCyHC4j3BXC52HfxTAtJ6bSG72m"
  }
}
```

**Have difficulty updating your planet?**  
Join our [Official Discord](https://discord.gg/wtRMBXw2bd) and ask question. Someone will help you.

