# Ellisthion's Fabric Modpack

Howdy. You're here because you've made a blood oath of allegiance to me. Thanks for that. Now here's some Minecraft.

## Modpack

[Download current modpack](https://github.com/Ellisthion/minecraft-fabric-1.19/releases/latest)

[View the changelog](/CHANGELOG.md)

# Client Setup

## Fresh Install

### Set up launcher

1. Get your modded launcher. I recommend [PolyMC](https://polymc.org/).
2. Point it at your Java 17 instance. If you've already installed Minecraft vanilla, it will have installed Java 17... somewhere. The standard launcher puts things in AppData or something. If you run vanilla, Task Manager will show the javaw.exe process for Minecraft, and you can use Open File Location to find it.
3. Up the min and max ram. I put 6144 MB.

### Set up instance

We are using a modpack file to automatically set up your modded Minecraft instance, including the Fabric mod loader.

Each instance is treated as totally separate so things like graphics settings and controls aren't copied between, unfortunately.

1. Click Add Instance
2. Choose import from zip, and import the latest modpack file. Note that it defaults to filtering by .zip files, but our modpack is in .mrpack format.
3. It should automatically download all the mods and set up the instance.
4. Once it's ready, click Launch

## Updating

Updating is currently a little fiddly.

1. In PolyMC, create a new instance, importing the new modpack file

That's sorta it. You can just use that new instance. But if you want to keep your options:

1. In your original instance, DELETE your `config` and `mods` folders
2. Copy in those folders from the new instance

# Server Setup

## Fresh Server

1. Set up a Fabric server as per Fabric's instructions
2. Set up a client instance in PolyMC with the modpack
3. Copy the `config` and `mods` folders from your client instance to the server directory

Adjust your java args. The "best" arguments are hotly discussed, but I'd recommend something like:

`-server -Xms8G -Xmx8G -XX:+UnlockExperimentalVMOptions -XX:+UseZGC -XX:+ZProactive -XX:ZCollectionInterval=600 -XX:+UseLargePages -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -XX:+ParallelRefProcEnabled -XX:+PerfDisableSharedMem`

You can tweak the first couple of params for different RAM. Generally you want the Xms and Xmx (min and max) to be equal because of Java garbage collection things.

Launch the server. It should "just work". If it doesn't, complain bitterly on WhatsApp.

## Updating

1. Set up a new client instance
2. DELETE the server's `config` and `mods` folders
3. Copy those folders from the new client instance into the server folder

If I've tested the update correctly, it should "just work". If it doesn't, complain bitterly on WhatsApp.

### Editing the world

If you need to delete parts of the world, use [Amulet](https://www.amuletmc.com/).

#### Safe zones for deleting thing
- Overworld: `{ x: -1600, z: -200 } to { x: 1100, z: 1200 }`
- Nether: `{ x: -200, z: 40 } to { x: -70, z: 150 }`
- End: `{ x: -150, z: -130 } to { x: 400, z: 150 }`
