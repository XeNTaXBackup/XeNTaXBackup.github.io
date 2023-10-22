## Post #1
- Username: Dark Watcher
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Dec 09, 2021 7:40 am
- Post datetime: 2021-12-09T00:08:24+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

Well, I think this discussion should be practically extinct, but I would like to ask for some help. I'm recently trying to extract models from MGS3. I tried to extract the contents contained in the .DAT file from the PS2 version, but it is encrypted and practically inaccessible even with DATTool and Konami DAT Utility.

After seeing on this forum that the PS3 HD version didn't have encryption like the PS2 one, I decided to give it a try. I was able to extract models and textures from the .PSARC files, but they were in .MDL and .TRI (possibly the 3D model and texture files respectively), and since 3DS Max doesn't read these file types, I decided to try to convert the MDL using Noesis with .MDL visualization plugin.

I've converted some models from .MDL to .OBJ and .FBX, but they appear untextured, with weird triangles (apparently wrong UV) and no change in basic structure. Before all that, I had already used the Ninja Ripper on the PS2 version (via PCSX2), but it resulted in absurdly deformed models. I was able to use Textmod to extract textures from weapons such as the Combat Knife and Patriot (very nostalgic).

I would really be grateful if anyone could help. It would be great to be able to get these original models, especially the weapons. Thanks  

Edit: Analyzing the models in 3DS Max, the problem appears to be in the Normals. In this case, the faces appear to be inverted. When I apply the Double Sided material, the model appears to be correct, but when I place the model in some engine, the triangles still have the Normals problem.
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-12-09T05:46:55+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

Use this: [https://github.com/Jayveer/MGS-MDL-Noesis](https://github.com/Jayveer/MGS-MDL-Noesis)
Instructions on the github page.

You might still get some odd flipped triangles, but you can just fix those in 3DS max quickly enough.
## Post #3
- Username: Dark Watcher
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Dec 09, 2021 7:40 am
- Post datetime: 2021-12-09T17:02:05+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

> Reply from lionheartuk ↑Thu Dec 09, 2021 1:46 pm at Thu Dec 09, 2021 1:46 pm
>
> 
Use this: https://github.com/Jayveer/MGS-MDL-Noesis
Instructions on the github page.

You might still get some odd flipped triangles, but you can just fix those in 3DS max quickly enough.

Thanks!! Now I'm able to visualize and export models with noesis, but the problem is that the exported model in .OBJ comes with broken polygons and no texture coordinates.
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-12-09T23:50:56+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

> Reply from Dark Watcher ↑Fri Dec 10, 2021 1:02 am at Fri Dec 10, 2021 1:02 am
>
> 
lionheartuk wrote: ↑Thu Dec 09, 2021 1:46 pm
Use this: https://github.com/Jayveer/MGS-MDL-Noesis
Instructions on the github page.

You might still get some odd flipped triangles, but you can just fix those in 3DS max quickly enough.


Thanks!! Now I'm able to visualize and export models with noesis, but the problem is that the exported model in .OBJ comes with broken polygons and no texture coordinates.

Weird, this tool should export them fine.
Its noesis you can export them as .fbx files, you aren't limited to obj.
Is it that triangles are broken or is it a backface culling issue? ie: the triangles are facing inward, if you turn on double sided materials/faces that should solve that issue.
Texture coordinates is strange though, does the model have no UV's at all?
## Post #5
- Username: Dark Watcher
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Dec 09, 2021 7:40 am
- Post datetime: 2021-12-10T01:57:53+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

> Reply from lionheartuk ↑Fri Dec 10, 2021 7:50 am at Fri Dec 10, 2021 7:50 am
>
> 
Dark Watcher wrote: ↑Fri Dec 10, 2021 1:02 am
lionheartuk wrote: ↑Thu Dec 09, 2021 1:46 pm
Use this: https://github.com/Jayveer/MGS-MDL-Noesis
Instructions on the github page.

You might still get some odd flipped triangles, but you can just fix those in 3DS max quickly enough.


Thanks!! Now I'm able to visualize and export models with noesis, but the problem is that the exported model in .OBJ comes with broken polygons and no texture coordinates.


Weird, this tool should export them fine.
Its noesis you can export them as .fbx files, you aren't limited to obj.
Is it that triangles are broken or is it a backface culling issue? ie: the triangles are facing inward, if you turn on double sided materials/faces that should solve that issue.
Texture coordinates is strange though, does the model have no UV's at all?

Well, I exported normally, both in .FBX and .OBJ, but triangles remain the same.

On 3DS Max, they turn white. I turned on the double sided material and they got the model textured correctly, but structurally the triangles still look the same, looking broken or something. Some triangles turn white and others turn black. In 3DS Max rendering, blacks are simply invisible, but "physically" are still there. The problem appears to be in the Normals. In this case, the faces appear to be inverted. When I apply the Double Sided material, the model appears to be correct, but when I place the model in some engine, the triangles still have the Normals problem.
## Post #6
- Username: Rackneh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2022 6:07 am
- Post datetime: 2022-05-17T22:24:28+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

Is there a chance either of you could help me get files from the PSarc files? I tried the Total Commander plugin and the original Psarc 1.4 extractor. Both gave me errors. 

The NinjaRip combined with the (slow af) PCSX2 model converter doesn't give me any meshes for now. Like you said the dat extractor didn't help me either.
## Post #7
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-05-19T00:49:40+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

> Reply from lionheartuk ↑Thu Dec 09, 2021 1:46 pm at Thu Dec 09, 2021 1:46 pm
>
> 
Use this: https://github.com/Jayveer/MGS-MDL-Noesis
Instructions on the github page.

You might still get some odd flipped triangles, but you can just fix those in 3DS max quickly enough.

Does this work with the PS3 version of MGS3? If not, what does?
## Post #8
- Username: Rackneh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2022 6:07 am
- Post datetime: 2022-05-19T22:04:40+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

> Reply from FWhyKay ↑Thu May 19, 2022 8:49 am at Thu May 19, 2022 8:49 am
>
> 
lionheartuk wrote: ↑Thu Dec 09, 2021 1:46 pm
Use this: https://github.com/Jayveer/MGS-MDL-Noesis
Instructions on the github page.

You might still get some odd flipped triangles, but you can just fix those in 3DS max quickly enough.


Does this work with the PS3 version of MGS3? If not, what does?

It does, but if you haven't extracted the PSarc file yet you need [https://totalcmd.net/plugring/PSARC.html](https://totalcmd.net/plugring/PSARC.html) you do need Total Commander for that plugin. If you don't want to use TotalCMD or compile it yourself I uploaded mine for you here [https://mega.nz/file/BjgBiDDY#5bS-Q0YGo ... xvuU8uDur4](https://mega.nz/file/BjgBiDDY#5bS-Q0YGouiUz1Vzn9IIsmvoPBK5Z1q_bxvuU8uDur4). If you do want to compile it yourself [https://github.com/AlexAltea/psarc-tool](https://github.com/AlexAltea/psarc-tool). 

If you have the psarc.66600 files, change the 66600 to 001, 66601 to 002 and so forth. Then use winrar on 001 to extract the mgs3.psarc file.

When you then have the mgs3.psarc you can drag it onto psarc.exe or TotalCMD to extract it and then use Noesis with the MDL plugin from Lionheart's reply to have the ability to extract MDL files. If you need any of the CMDL files: [download/file.php?id=12758](https://forum.xentax.com/download/file.php?id=12758),  as far as I've seen some things like big geometry is only in CMDL format.

If I'm correct the CMDL are the model raw data with no textures, MDL should be the model that doesn't require any touchups and has "black" textures.

If your model does need touch-ups, ask someone with blender experience to help you out. My friend worked me through the fix in 30 minutes or so.
(I will be making a YT tutorial for specifically that kind of model cleanup once I get a hang of it myself)

If you figure out how to rip textures let me know! if not, [https://gamebanana.com/mods/150247](https://gamebanana.com/mods/150247) This person uploaded a bunch of them in HD for the 3ds and they're all PNG format!

Extra: [https://www.deviantart.com/michaeljordy ... -677092895](https://www.deviantart.com/michaeljordy/art/MGS3-models-w-face-rigged-677092895), Some character models fully rigged and HQ camo textures. He says if you DM him he can give you the other characters. Though he might not have them anymore

Let me know how it goes and if you have any issues!
## Post #9
- Username: Rackneh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2022 6:07 am
- Post datetime: 2022-07-10T02:57:00+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

> Reply from AxelNoir ↑Thu May 19, 2022 8:49 am at Thu May 19, 2022 8:49 am
>
> 
lionheartuk wrote: ↑Thu Dec 09, 2021 1:46 pm
Use this: https://github.com/Jayveer/MGS-MDL-Noesis
Instructions on the github page.

You might still get some odd flipped triangles, but you can just fix those in 3DS max quickly enough.


Does this work with the PS3 version of MGS3? If not, what does?

After some work I got models to extract with their textures and skeletons from the PS2 rom reliably, PS3 not so much. 

If you're capable of re-adding the textures yourself afterwards, I found converting to the models to STL, repair them in [https://www.formware.co/onlinestlrepair](https://www.formware.co/onlinestlrepair) and then converting them back to FBX fixed the flipped normals. 
It does double the amount of vertices so for UE5 and Blender it's fine but I imagine less so for Unity.

Edit: For my current project using the files I tell Unity to render the meshes on both sides which is likely doing the same as the STL repair. If you wanna do the same in Unity and skip the repairing and rebinding textures: 
// In unity
1: Export the materials inside the model prefab out of the prefab, preferably in a dedicated material folder.
2: Select all materials, set "Render Face" in 'Surface Options' in the Inspector to Both and "Workflow Mode" to Specular
3: Allow Alpha clipping (this just allows transparancy for textures that Require it)
4: Under 'Surface Inputs', put "Y Tiling" on -1 (this is needed for MGS3 textures fsr)
5: Again under Surface Inputs, put "Smoothness" to 0 (This is needed because fsr Unity thinks all textures are smooth metallic)

Using Shagohod [https://github.com/Jayveer/Shagohod](https://github.com/Jayveer/Shagohod) on the PS2 files (using the dictionary) with [https://github.com/Jayveer/MGS-MDL-Noesis](https://github.com/Jayveer/MGS-MDL-Noesis) on the exported files worked magic for getting the exact models with textures. 

Unless someone rewrites the MDL plugin to work with the PS3 files, I think the PS2 files are gonna be our best shot.
## Post #10
- Username: Rackneh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2022 6:07 am
- Post datetime: 2022-07-12T21:19:37+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

Big update! 

1: Change your import settings in Unity to Legacy before you import the meshes. (this will put all mats in a different folder for easy changes)
2: Use ProBuilder to "probuilderize" the meshes
3: use the "conform normals" if you got randomly inverted faces.|

now you can adjust the faces's position in the editor, every mesh that uses a texture should all individually use a singular material file.
## Post #11
- Username: Dark Watcher
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Dec 09, 2021 7:40 am
- Post datetime: 2023-02-03T19:15:53+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

> Reply from Rackneh ↑Wed Jul 13, 2022 5:19 am at Wed Jul 13, 2022 5:19 am
>
> 
Big update! 

1: Change your import settings in Unity to Legacy before you import the meshes. (this will put all mats in a different folder for easy changes)
2: Use ProBuilder to "probuilderize" the meshes
3: use the "conform normals" if you got randomly inverted faces.|

now you can adjust the faces's position in the editor, every mesh that uses a texture should all individually use a singular material file.

Thank you very much!! This Normals problem is annoying.
## Post #12
- Username: Rackneh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2022 6:07 am
- Post datetime: 2023-04-12T00:13:14+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

EVEN BIGGER UPDATE

Thanks to ChatGPT, we managed to make a script to fix both static and boned meshes (exported using the Jayveer exporting plugin for Noesis) straight in Unity.

Export the models in FBX format

Tested in Unity 2021.3.3f1 (FBX export addon needed)
1: put the model you want fixed in the game scene, apply the script below to it's parented object.
2: right click the object and press export as FBX. 
3: profit!

The comments in the script below are just there in case you're using the assets with Unity's prefab system.

Before: 
After: 

```
/////////          MeshFixer v1.1         \\\\\\\\\\
//                                                \\
// Created by ChatGPT, Codex, Usling123 & Rackneh \\
//                                                \\
//               Made for MGS3 VR                 \\
//                                                \\
//                     GG ez                      \\
//                                                \\
///////////////////////// \\\\\\\\\\\\\\\\\\\\\\\\\\
using UnityEngine;

public class MeshFixer : MonoBehaviour
{
    public bool isFlipped = false;
    // You should always use prefabs.
    // Uncomment the 'isFlipped = true;' lines when applying this script to a prefab
    // Otherwise true will be the default state and the mesh won't be fixed on load

#if UNITY_EDITOR
    void OnValidate()
    {
        if (isFlipped == false)
        {
            FlipNormalsRecursive(transform);
            isFlipped = true;
        }
    }
#endif
    void Start()
    {
        if (isFlipped == false)
        {
            FlipNormalsRecursive(transform);
            isFlipped = true;
        }
    }
    void FlipNormalsRecursive(Transform parent)
    {
        MeshFilter meshFilter = parent.GetComponent<MeshFilter>();
        SkinnedMeshRenderer skinnedMeshRenderer = parent.GetComponent<SkinnedMeshRenderer>();
        for (int i = 0; i < parent.childCount; i++)
        {
            Transform child = parent.GetChild(i);
            FlipNormalsRecursive(child);
        }
        if (meshFilter == null && skinnedMeshRenderer == null)
        {
            return;
        }
        Mesh mesh = null;
        if (meshFilter != null)
        {
            mesh = meshFilter.sharedMesh;
        }
        else
        {
            mesh = skinnedMeshRenderer.sharedMesh;
        }
        if (mesh == null)
        {
            return;
        }

        Vector3[] normals = mesh.normals;

        for (int i = 0; i < normals.Length; i++)
        {
            normals[i] = -normals[i];
        }

        mesh.normals = normals;

        for (int m = 0; m < mesh.subMeshCount; m++)
        {
            int[] triangles = mesh.GetTriangles(m);
            for (int i = 0; i < triangles.Length; i += 3)
            {
                Vector3 triangleNormal = Vector3.Cross(
                    mesh.vertices[triangles[i + 1]] - mesh.vertices[triangles[i]],
                    mesh.vertices[triangles[i + 2]] - mesh.vertices[triangles[i]]
                ).normalized;

                if (Vector3.Dot(triangleNormal, normals[triangles[i]]) < 0)
                {
                    int temp = triangles[i + 1];
                    triangles[i + 1] = triangles[i + 2];
                    triangles[i + 2] = temp;
                }
            }
            mesh.SetTriangles(triangles, m);
        }
    }
}

```


Let me know if you have any questions!
## Post #13
- Username: Dark Watcher
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Dec 09, 2021 7:40 am
- Post datetime: 2023-04-13T01:36:24+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

> Reply from Rackneh ↑Wed Apr 12, 2023 8:13 am at Wed Apr 12, 2023 8:13 am
>
> 
EVEN BIGGER UPDATE

Thanks to ChatGPT, we managed to make a script to fix both static and boned meshes (exported using the Jayveer exporting plugin for Noesis) straight in Unity.

Export the models in FBX format

Tested in Unity 2021.3.3f1 (FBX export addon needed)
1: put the model you want fixed in the game scene, apply the script below to it's parented object.
2: right click the object and press export as FBX. 
3: profit!

The comments in the script below are just there in case you're using the assets with Unity's prefab system.

Before: 
After: 
Code: Select all///////////////////////// \\\\\\\\\\\\\\\\\\_\?\X\\
/////////          MeshFixer v1.1         \\\\\\\\\\
//                                                \\
// Created by ChatGPT, Codex, Usling123 & Rackneh \\
//                                                \\
//               Made for MGS3 VR                 \\
//                                                \\
//                     GG ez                      \\
//                                                \\
///////////////////////// \\\\\\\\\\\\\\\\\\\\\\\\\\
using UnityEngine;

public class MeshFixer : MonoBehaviour
{
    public bool isFlipped = false;
    // You should always use prefabs.
    // Uncomment the 'isFlipped = true;' lines when applying this script to a prefab
    // Otherwise true will be the default state and the mesh won't be fixed on load

#if UNITY_EDITOR
    void OnValidate()
    {
        if (isFlipped == false)
        {
            FlipNormalsRecursive(transform);
            isFlipped = true;
        }
    }
#endif
    void Start()
    {
        if (isFlipped == false)
        {
            FlipNormalsRecursive(transform);
            isFlipped = true;
        }
    }
    void FlipNormalsRecursive(Transform parent)
    {
        MeshFilter meshFilter = parent.GetComponent<MeshFilter>();
        SkinnedMeshRenderer skinnedMeshRenderer = parent.GetComponent<SkinnedMeshRenderer>();
        for (int i = 0; i < parent.childCount; i++)
        {
            Transform child = parent.GetChild(i);
            FlipNormalsRecursive(child);
        }
        if (meshFilter == null && skinnedMeshRenderer == null)
        {
            return;
        }
        Mesh mesh = null;
        if (meshFilter != null)
        {
            mesh = meshFilter.sharedMesh;
        }
        else
        {
            mesh = skinnedMeshRenderer.sharedMesh;
        }
        if (mesh == null)
        {
            return;
        }

        Vector3[] normals = mesh.normals;

        for (int i = 0; i < normals.Length; i++)
        {
            normals[i] = -normals[i];
        }

        mesh.normals = normals;

        for (int m = 0; m < mesh.subMeshCount; m++)
        {
            int[] triangles = mesh.GetTriangles(m);
            for (int i = 0; i < triangles.Length; i += 3)
            {
                Vector3 triangleNormal = Vector3.Cross(
                    mesh.vertices[triangles[i + 1]] - mesh.vertices[triangles[i]],
                    mesh.vertices[triangles[i + 2]] - mesh.vertices[triangles[i]]
                ).normalized;

                if (Vector3.Dot(triangleNormal, normals[triangles[i]]) < 0)
                {
                    int temp = triangles[i + 1];
                    triangles[i + 1] = triangles[i + 2];
                    triangles[i + 2] = temp;
                }
            }
            mesh.SetTriangles(triangles, m);
        }
    }
}


Let me know if you have any questions!

That's it. The problem that persisted for years has been resolved. Thanks a lot for the solution. Now everyone can access MGS3 assets without normals problems. We have a modding hero.
## Post #14
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2023-04-17T10:49:32+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

when will someone create a ripping tool for Metal Gear solid 5 and Metal Gear solid 6 in  this same manner?
## Post #15
- Username: Dark Watcher
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Dec 09, 2021 7:40 am
- Post datetime: 2023-04-20T01:11:51+00:00
- Post Title: Metal Gear Solid 3 PS2 and PS3 models ripping

> Reply from neonvega ↑Mon Apr 17, 2023 6:49 pm at Mon Apr 17, 2023 6:49 pm
>
> 
when will someone create a ripping tool for Metal Gear solid 5 and Metal Gear solid 6 in  this same manner?

I believe there is a converter to MGS5. MGS6 has not yet been released. And, apparently, it won't be soon.
## Post #16
- Username: Rackneh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2022 6:07 am
- Post datetime: 2023-04-21T19:39:25+00:00
- Post Title: Re: Metal Gear Solid 3 PS2 and PS3 models ripping

> Reply from Dark Watcher ↑Thu Apr 13, 2023 9:36 am at Thu Apr 13, 2023 9:36 am
>
> 
Rackneh wrote: ↑Wed Apr 12, 2023 8:13 am
EVEN BIGGER UPDATE

Thanks to ChatGPT, we managed to make a script to fix both static and boned meshes (exported using the Jayveer exporting plugin for Noesis) straight in Unity.

Export the models in FBX format

Tested in Unity 2021.3.3f1 (FBX export addon needed)
1: put the model you want fixed in the game scene, apply the script below to it's parented object.
2: right click the object and press export as FBX. 
3: profit!

The comments in the script below are just there in case you're using the assets with Unity's prefab system.

Before: 
After: 
Code: Select all///////////////////////// \\\\\\\\\\\\\\\\\\_\?\X\\
/////////          MeshFixer v1.1         \\\\\\\\\\
//                                                \\
// Created by ChatGPT, Codex, Usling123 & Rackneh \\
//                                                \\
//               Made for MGS3 VR                 \\
//                                                \\
//                     GG ez                      \\
//                                                \\
///////////////////////// \\\\\\\\\\\\\\\\\\\\\\\\\\
using UnityEngine;

public class MeshFixer : MonoBehaviour
{
    public bool isFlipped = false;
    // You should always use prefabs.
    // Uncomment the 'isFlipped = true;' lines when applying this script to a prefab
    // Otherwise true will be the default state and the mesh won't be fixed on load

#if UNITY_EDITOR
    void OnValidate()
    {
        if (isFlipped == false)
        {
            FlipNormalsRecursive(transform);
            isFlipped = true;
        }
    }
#endif
    void Start()
    {
        if (isFlipped == false)
        {
            FlipNormalsRecursive(transform);
            isFlipped = true;
        }
    }
    void FlipNormalsRecursive(Transform parent)
    {
        MeshFilter meshFilter = parent.GetComponent<MeshFilter>();
        SkinnedMeshRenderer skinnedMeshRenderer = parent.GetComponent<SkinnedMeshRenderer>();
        for (int i = 0; i < parent.childCount; i++)
        {
            Transform child = parent.GetChild(i);
            FlipNormalsRecursive(child);
        }
        if (meshFilter == null && skinnedMeshRenderer == null)
        {
            return;
        }
        Mesh mesh = null;
        if (meshFilter != null)
        {
            mesh = meshFilter.sharedMesh;
        }
        else
        {
            mesh = skinnedMeshRenderer.sharedMesh;
        }
        if (mesh == null)
        {
            return;
        }

        Vector3[] normals = mesh.normals;

        for (int i = 0; i < normals.Length; i++)
        {
            normals[i] = -normals[i];
        }

        mesh.normals = normals;

        for (int m = 0; m < mesh.subMeshCount; m++)
        {
            int[] triangles = mesh.GetTriangles(m);
            for (int i = 0; i < triangles.Length; i += 3)
            {
                Vector3 triangleNormal = Vector3.Cross(
                    mesh.vertices[triangles[i + 1]] - mesh.vertices[triangles[i]],
                    mesh.vertices[triangles[i + 2]] - mesh.vertices[triangles[i]]
                ).normalized;

                if (Vector3.Dot(triangleNormal, normals[triangles[i]]) < 0)
                {
                    int temp = triangles[i + 1];
                    triangles[i + 1] = triangles[i + 2];
                    triangles[i + 2] = temp;
                }
            }
            mesh.SetTriangles(triangles, m);
        }
    }
}


Let me know if you have any questions!


That's it. The problem that persisted for years has been resolved. Thanks a lot for the solution. Now everyone can access MGS3 assets without normals problems. We have a modding hero.

Thank you very much! It's really my pleasure  It would have never been possible without my friend Usling123 though, he's the real MVP.
## Post #17
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2023-04-22T16:51:13+00:00
- Post Title: Re: Metal Gear Solid 3 PS2 and PS3 models ripping

well to me metal gear solid ground zeros is mgs5 and metal gear solid phantom pain mgs6
## Post #18
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2023-04-24T04:23:42+00:00
- Post Title: Re: Metal Gear Solid 3 PS2 and PS3 models ripping

> Reply from neonvega ↑Sun Apr 23, 2023 12:51 am at Sun Apr 23, 2023 12:51 am
>
> 
well to me metal gear solid ground zeros is mgs5 and metal gear solid phantom pain mgs6

That is objectively wrong though, ground zeroes is the only one not numbered.
Phantom Pain is called MGSV, which is either V for Venom, or V being the roman numeral for 5, no matter how you cut it it isn't MGS6.
## Post #19
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2023-05-23T23:39:32+00:00
- Post Title: Re: Metal Gear Solid 3 PS2 and PS3 models ripping

> Reply from lionheartuk ↑Mon Apr 24, 2023 12:23 pm at Mon Apr 24, 2023 12:23 pm
>
> 
neonvega wrote: ↑Sun Apr 23, 2023 12:51 am
well to me metal gear solid ground zeros is mgs5 and metal gear solid phantom pain mgs6


That is objectively wrong though, ground zeroes is the only one not numbered.
Phantom Pain is called MGSV, which is either V for Venom, or V being the roman numeral for 5, no matter how you cut it it isn't MGS6.

as far as standalone title GZ is MGSV and P P is MGVI as far as standalone titles go
## Post #20
- Username: Rackneh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2022 6:07 am
- Post datetime: 2023-09-03T21:07:12+00:00
- Post Title: Re: Metal Gear Solid 3 PS2 and PS3 models ripping

Hey all!

If you're interested in helping in getting the MGS3 asset ripping working perfectly, and you have spirit, Add me on discord!

The current meshfixer script works almost perfectly when using direct lights but things like trees are still an issue. Baking lights on the meshes is an entire issue on it's own.

We think we may have an idea of fixing this, if you're proficient in english and think you have the spirit to help us figure this out, add me on discord! Discord username: "Rackneh"

If you have any experience in asset ripping or math in general you're above my skill level and you'd be a great help to our cause!

Update: We managed to make it do weld vertices by distance in the script, I now need help making a dedicated tool out of it!

-Rackneh
