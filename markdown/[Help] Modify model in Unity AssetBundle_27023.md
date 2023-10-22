## Post #1
- Username: KuloKuro
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 27, 2023 4:25 am
- Post datetime: 2023-07-26T20:44:06+00:00
- Post Title: [Help] Modify model in Unity AssetBundle

So basically I want to modify the model packed in this assetbundle, my initial idea was to extract the AB by AssetStudio, do the modification, and repack it again in Unity. But it turns out AssetStudio will do more processes to the original .prefab file and .fbx file when extracting (like ripping .prefab into single MonoBehaviour script). I'm wondering what is the correct way to do modding.

Here is the ab file: [https://drive.proton.me/urls/3TW825EFD0#oM47oPQXTtR0](https://drive.proton.me/urls/3TW825EFD0#oM47oPQXTtR0)
## Post #2
- Username: rna98mod
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 02, 2021 8:08 am
- Post datetime: 2023-09-11T18:55:18+00:00
- Post Title: [Help] Modify model in Unity AssetBundle

You can use tools/programs called UABE or UABEA to edit the asset, you can find it on github. For the modding process, the steps are:

1. extract and export the model using AssetStudio (.fbx)
2. Edit the exported model in any 3D modeling software. Then export the edited model to .fbx again.
3. Open Unity Editor and create a new empty 3D project (NOTE : Use the same Unity version which the game used. If the game uses Unity 2018.x, then you need to install Unity Editor 2018.x)
4. Import or just Drag & drop the edited .fbx to Unity Editor
5. Create new scene file (or you can use the existing one)
6. Add the imported .fbx to the scene (just drag & drop the .fbx inside project window to scene or hierarchy window)
7. Save the current scene file.
8. Go to File -> Build Settings...
9. Add the scene file to "Scene in Build" section
10. Click Build
11. After the build process finishes, go to that build directory, then open the bundle file with UABE or UABEA
12. Find the edited mesh asset, then use "Export Raw" options to export the asset
13. Open the original game bundle file with UABE or UABEA which contain the asset you want to mod/replace
14. Find the mesh asset you want to replace, then use "Import Raw" option, replace it with the exported mesh asset (which contain the edited model)
15. After finish importing, save the bundle into different file (in case you need the original bundle file)
16. Copy the saved bundle to your game folder, if its inside .obb then use Zarchiver, if its inside .apk then use ApkEditor. For PC just replace the original bundle with the edited/modified one inside the game folder.

By the way, i only did modding in a game that uses unity 2018.x, there are many asset type that can be replaced (text, texture, mesh, character that contain rig, animation, and scene) using UABE 2.2 stable d. I haven't try modding game that uses unity 2019.x and above, you can try the latest version of UABE (3.0 beta 1) or UABEA for newer games.
