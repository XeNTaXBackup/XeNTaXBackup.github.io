## Post #1
- Username: master2s
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 14, 2023 9:20 pm
- Post datetime: 2023-09-22T13:39:26+00:00
- Post Title: RDR textures in wsf

I want help solving the problem of the wsf file, displaying dds images


Use MagicRDR_v1.3.4


[https://github.com/Foxxyyy/Magic-RDR/re ... tag/v1.3.4](https://github.com/Foxxyyy/Magic-RDR/releases/tag/v1.3.4)




Download 
flash.rpf
[https://mega.nz/file/VbRj0R4I#_N1KuZN08 ... R3PxRKBJqs](https://mega.nz/file/VbRj0R4I#_N1KuZN08PUe63hT5ffNQ9fMudOsee-hTR3PxRKBJqs)
## Post #2
- Username: N69
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 29, 2015 6:24 am
- Post datetime: 2023-10-09T17:50:26+00:00
- Post Title: RDR textures in wsf

Textures inside flash.rpf not in DDS, but using unity crunch .crn in modified form 
[https://github.com/Unity-Technologies/crunch/tree/unity](https://github.com/Unity-Technologies/crunch/tree/unity)
After converting textures back to DDS, you getting data in scattered and rotated form.

tex.crn - original texture, extracted from switch flash resource
tex.dds - converted (and broken)
networking.dds - how it should look (extracted from PS3 version)

PS. Its not a console specific swizzle, because files are identical between NSW and PS4. Its a modified by D11 file format.
[crunch.zip](https://xentaxbackup.github.io/file/24416_crunch.zip)
