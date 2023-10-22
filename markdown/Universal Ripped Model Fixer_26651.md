## Post #1
- Username: Rackneh
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2022 6:07 am
- Post datetime: 2023-04-12T00:32:47+00:00
- Post Title: Universal Ripped Model Fixer

Hey all!

As a thanks to the general community here for helping me get into this stuff, I want to share our mesh fixing script.
Thanks to ChatGPT, we managed to make a script to fix both static and boned meshes, straight in Unity. We made it for MGS related meshes but it should work for pretty much every model out there.

Before: 
After: 

How to use:

Export the models in FBX format

Tested in Unity 2021.3.3f1 (FBX export addon needed)
1: put the model you want fixed in the game scene, apply the script below to it's parented object.
2: right click the object and press export as FBX. 
3: profit!

The comments in the script below are just there in case you're using the assets with Unity's prefab system.

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
