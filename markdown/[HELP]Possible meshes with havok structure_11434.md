## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-04-19T22:57:29+00:00
- Post Title: [HELP]Possible meshes with havok structure

I'm still working on killzone models but some meshes are lost. The vertex aren't in the vertex buffer section but the textures , uv and indices are in the file.

I have suspicions with this section of the file because this lost meshes in the game have physics.



file:

[http://www.mediafire.com/download/s4d85 ... acter.core](http://www.mediafire.com/download/s4d85qf6sy2l32t/assets_description.characters.hgh_smg_infantry_hgh_smg_infantry_character.core)

(the vertex buffer start in 0x4E0D and finish in 0x5B1FC)

the result of this file is this

 

this is the reference image

[http://m1.behance.net/rendition/modules ... 131b73.jpg](http://m1.behance.net/rendition/modules/13507721/disp/600d6870204fadd9640caccb8b131b73.jpg)

there is only one lost mesh in this file and there is only one havok data. these was my fundaments.

Maybe someone that know this data can tell me if this section are vertex or no , and how to figure out the mesh.

thanks
## Post #2
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-04-23T05:27:27+00:00
- Post Title: [HELP]Possible meshes with havok structure

I have this information from havok support

they seem to be packfiles that have been saved out on a 32 bit machine with big endian integer representation, I'd get Linux 32 bit.

You can read more about packfiles and all the other Havok file formats in the User Guide -> Common Havok Components -> Serialization -> File Formats.

As for what the files actually contain, it appears to be Havok shape data, therefore it will have geometry.

Packfiles are not a cross-platform file format so you won't be able to load them on a machine that doesn't have the exact same layout rules. Because they are very old packfiles, you'll also need to enable packfile versioning (which is deprecated - check the docs). For long-lasting asset files destined to be reused in a distant future and on different machines the recommendation is using tagfiles.

note: for now I can't download the havok sdk because the register page is down. someone can check this information please?
## Post #3
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-05-14T21:00:41+00:00
- Post Title: [HELP]Possible meshes with havok structure

How were you able to read the vertex data. Did the  strings in the header give you a hind on how the data was laid out? I am trying to make a custom havok file reader myself especially  for havok animation and havok behavior. Most of the files i cant even read with the existing  sdk.

The register page is back up.
