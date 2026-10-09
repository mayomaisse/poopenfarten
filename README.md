# BigWalkCraft

Play real Minecraft Java inside Big Walk: Minecraft's hand, hotbar, inventory, blocks, mobs, sounds and particles are composited into Big Walk's world.

**Experimental Windows development build.** The creator confirmed the combined view, mouse control, correct colors, improved responsiveness and idle-sleep fix in game. The latest native object/puzzle interaction extension compiles and passes bridge tests; its live scene test is pending.

## Download

Download **BigWalkCraft-Development.zip** from this repository using its **Download raw file** button, then extract it. It includes source code and prebuilt Big Walk connector DLLs.

This is not a one-click installer. The included local launchers depend on the original prepared development workspace. They will not work on a fresh computer without recreating its private game copy and build tools. A portable installer is still needed.

## Requirements

- Your own Windows Steam copy of Big Walk, tested with version1.6.0 / Unity6000.3.17f1, and your own Minecraft Java account.
- Minecraft1.21.1, Fabric Loader0.19.5 and Fabric API0.116.17+1.21.1. Newer Minecraft-specific items are not part of this pinned build.
- Direct3D11 for the Big Walk connector. Solo play only.
- A private Big Walk test copy with BepInEx6 IL2CPP build785 and generated interop libraries. Original Steam game files remain separate.
- Java25 for the included Gradle9.7.1 / Loom1.18.2 development build. Host source targets .NET6 and the generated Big Walk interop; native renderer builds with a Windows C++ toolchain.

The archive contains no Minecraft or Big Walk game files, textures, sounds, saves, account credentials, generated game interop assemblies or build caches. Obtain game content through your own installations and the official development tooling.

## Controls

- Standard Minecraft controls, E inventory, F5 view.
- R interacts with a native Big Walk target or picks up an object; hold for switches.
- V uses a held native item; G drops it.
- F8 hands control back to Big Walk; F8 in Big Walk returns to Minecraft.
- Use native controls for climbing, seated actions, gestures, native screens or throws requiring wind-up.

## Known limits

Big Walk scenery cannot be mined. Native Big Walk NPC combat is not connected to Minecraft mobs. Native puzzle interactions need further live testing. Minecraft uses its own private save and a distinct region for each Big Walk save. Frame transfer runs at half window width/height to reduce delay, so Minecraft content can look softer. Restart after changing window resolution.

## Source and validation

The archive's host/, native/ and guest/ directories contain the bridge source. docs/CONTRACT.md describes ownership and transport. TEST-STATUS.json, INTERACTION-TEST.json and protocol/renderer reports distinguish live confirmation from standalone checks.

For host builds, pass GamePath to the supplied project so it finds BepInEx/core and BepInEx/runtime-generated/interop from your own private copy. The guest includes its Gradle wrapper. Do not commit game-derived files or local caches.

## Credits

Guest adapted from [siddoff/Minecraft-Ring](https://github.com/siddoff/Minecraft-Ring), based on justbustin/minecraft-crossover-bridge. The upstream MIT notice is preserved in LICENSE-guest.txt. BepInEx, Harmony, Fabric and the game's own runtime power the integration. Development assisted by OpenAI Codex with the universal-modder toolkit.

The upstream guest retains its MIT license. No additional open-source license has been selected for the new host/renderer code. This is an unofficial community project; Minecraft and Big Walk belong to their respective creators.
