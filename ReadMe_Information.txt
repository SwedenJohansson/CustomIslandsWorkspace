CustomIslandsWorkspace-main - tools for building islands in the Unity Editor (the "old way")
=========================================================================================

  >>> OBSOLETE (confirmed by FranzFischer, 2026-09-23): the project's goal is to build islands in the
  >>> in-game editor, not in Unity, so this export tool is no longer needed. Kept only for reference.

WHAT IT IS
  Unity helper files from https://github.com/FranzFischer78/CustomIslandsWorkspace
  (last updated 2022-08). Before the in-game editor existed, creators built an island
  as a Unity scene using Raft's extracted game assets, then exported it as an
  AssetBundle (.assets file) that the mod can spawn in game. This is NOT the in-game
  editor and NOT a complete Unity project - it's a set of files you drop into a
  Unity project that contains Raft's extracted game files.

WHAT'S IN HERE
  Editor\IslandBundleBuilder.cs     Adds menu "Assets > Custom Islands > Build island bundle":
                                    pick a scene (must have exactly ONE root object) and it
                                    exports <scene>.assets into Assets/AssetBundles.
  Editor\CreateAssetBundles.cs      Generic "Assets > Build AssetBundles" menu item.
  Editor\WaterDummyAdder.cs         Empty placeholder for a future tool.
  customislandtools.unitypackage    The same editor tools packaged for easy import.
  customislandtools\WaterDummy\     A water placeholder prefab to delete before export.
  ScriptFixRaftExport.bat           After extracting Raft's game files (e.g. with AssetRipper),
                                    replaces broken decompiled scripts with Raft's real DLLs.
  Scenes\                           Example island scenes (demo.unity = the demo island).
  AssetBundles\                     Example exported bundles (samplescene.assets, test.assets).
  ChunkSpawnerRule.asset            A copy of Raft's island spawn rule asset (research).
  (GameFiles\ is expected here but is not included - it's the extracted Raft assets.)

HOW TO USE (original workflow, from the 2022 wiki)
  1. Extract Raft's game files into a Unity project (tutorial video:
     https://youtu.be/yXEyORwdyWw). Run ScriptFixRaftExport.bat.
  2. Import customislandtools.unitypackage.
  3. Build your island in a scene with a single root GameObject.
  4. Assets > Custom Islands > Build island bundle.
  5. Put the resulting .assets into <Raft>\mods\DynamicIslands\ and in game run
     SpawnCustomLandmark <filename-without-.assets> (host only).

NOTE
  Bundles here were built with Unity 2019.3.5f1. Raft now runs Unity 2021.3.45, so
  new bundles should most likely be built with 2021.3.45 going forward.
  Wiki: https://github.com/FranzFischer78/CustomIslandsWorkspace/wiki/Exporting-a-custom-island
