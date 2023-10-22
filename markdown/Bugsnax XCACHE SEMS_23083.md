## Post #1
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-11-29T08:11:51+00:00
- Post Title: Bugsnax XCACHE SEMS

Bugsnax uses the Irrlicht Engine.
Most textures are DDS DXT5 with normals being BC5U.
Materials are plain text .mtl files.
Models are .objcache and .xcache with the header SEMS.

There is some information on the irrlicht site and forumn but it does not seem to be a common format or have existing importers.

Samples [https://mega.nz/folder/fOAxjSrb#DI61taQ3F2Zo6neF14fm4g](https://mega.nz/folder/fOAxjSrb#DI61taQ3F2Zo6neF14fm4g)
## Post #2
- Username: danne2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 29, 2015 9:50 am
- Post datetime: 2020-11-30T20:22:32+00:00
- Post Title: Bugsnax XCACHE SEMS

The game shipped with PDBs and I did some RE. The files are all binary serialized into Irrlicht's internal formats (ISkinnedMesh, IAnimatedMesh, SMesh).
My RE skills aren't quite up to par, but for anyone who has those skills...

You can find the giant function that does all this serializing by going to ??_C@_0BK@HDIDGINI@?4?4?4?4Writing?5Binary?5Me and then just tracing upwards.

The load function is ?loadMesh@@YAXPEBDPEAPEAVIAnimatedMesh@scene@irr@@PEAUThreadMeshInfo@@@Z and the write function is ?writeMesh@BinaryMeshWriter@@UEAA_NPEAVIWriteFile@io@irr@@PEAVIMesh@scene@4@H@Z.

You also have createMeshFromBinary@BinaryMeshLoader@@QEAAPEAVIAnimatedMesh@scene@irr@@PEAVIReadFile@io@4@_N@Z


If anyone with the skills wants to take a stab at it, that's probably all you need.
