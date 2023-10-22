## Post #1
- Username: Reaperex
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun May 05, 2019 6:53 am
- Post datetime: 2019-10-29T04:33:33+00:00
- Post Title: Ghost recon wildlands ARchive_neXt Errors viewing models and textures

Ghost recon wildlands ARchive_neXt Errors viewing models and textures

Hi does anybody know what I am doing wrong with this program, when I try to load a model or texture different errors pop up and I have to force close the application. I would love to find a fix as I want to port the clothes in to Fallout 

1.
Not a compressed DATAFILE
CP_ Head__TacMaskB_DiffuseMap is not a compressed DATAFILE, and its contents are unknown.

2.
Error writing model file!

index was outside the bounds of the array

   at ARchive_neXt.gw.createDDS(string imageinfo)
   at ARchive_neXt.gw.findMaterial(String searchID, TreeNode)
tNode)
    at ARchive_neXt.arxForm.arxFindMaterial(String matID)
   at ARchive_neXt.arxForm.arxCreateModel(TreeNode tNode)

3.

Error writing model!

Error in the application

  at Microsoft.DirectX.Direct3d.Mesh.FromFile(String filename,
MeshFlags, options, Device device, GraphicStream&
ajacency, ExtendedMaterial & materials, Effectinstance &
effects)
   at Microsoft.DirectX.Direct3d.Mesh.FromFile(String filename,
MeshFlags, options, Device device, ExtendedMaterial &
materials)
  at ARchive_neXt.arxForm.arxInitializeGraphics(String mdFile)

4.

Error drawing the mesh!

Object reference not set to an instance of an objects 

  at ARchive_neXt.arxForm.arxDrawMesh()
