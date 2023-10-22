## Post #1
- Username: plfx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 04, 2010 7:21 am
- Post datetime: 2010-08-04T00:01:47+00:00
- Post Title: Mortal Kombat Gold [.GEO]

I've been working on deciphering the file formats extracted from the disc image of this Dreamcast game. I figured out the texture format and will post it as a case study, but the model format has me stuck.

The files are all .GEO. Here's the .GEO file for Sub-Zero:
[http://drop.io/zr0gklg](http://drop.io/zr0gklg)
Also available there is the .IMG texture for that model and a BMP of the same texture.

I tried to wade through the 3D format identification tutorials out there, but I have done so little with 3D formats that I can't quite latch on to it.
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-08-04T17:04:15+00:00
- Post Title: Mortal Kombat Gold [.GEO]

This model format is pretty simple:
At offset 0h4, there is the end offset to the end of the model portion of the file.
At offset 0h8 there is a 4byteinteger of the number of submeshes:
Each submesh 32byte header then follows:
{01 00, 2byteInteger#TriStrips,4Byte"SectorOffset", the rest of each array is all 00's}
Then each tristrip will have a 32byte header, and then the data followed by the next trisrip and its header until the end of the 3d data:
{00 00 00 00, {Binary can be either 00, or 01} 00, 2ByteNumberofVertexes in Stri, The rest of each header is all 00's}
{4ByteFloatNormalMappings,4ByteFloatVertexes,4ByteFloatTexureUVCoords}
Notes:
1. "Sector" offsets are strange as they are not straight addresses to each submesh, maybe you have to add in a header for each one so they are off by the real start of each section by #headers*0h32? Why they end in "C" is a mystery as everything in this file begins at a multiple of 32
2. Tristrips are implicit so there is no face list, to render the face list just connect the vertexes in the order they are found in ie: (1stvertex,2nd vertex,3vertex=Face1) (2ndvertex,3rdvertex,4thvertex=face2)
3. the data after the 3d data doesnot appear to be 3d data maybe cd sector data

Here is a picture of the mesh(es) from the .geo file, there are about 12,000 vertexes, so some models overlap and are inside each other:

[http://ps23dformat.wikispaces.com/file/ ... zero.blend](http://ps23dformat.wikispaces.com/file/view/subzero.blend)
## Post #3
- Username: plfx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 04, 2010 7:21 am
- Post datetime: 2010-08-04T19:28:48+00:00
- Post Title: Mortal Kombat Gold [.GEO]

Extra nifty, thanks.
I kind of expected animations to be in these files, since I don't know of another place for them to be. It seems not so, though.
Also either in the header or in the info at the end there must be texture alignment info.

EDIT:
The more I look through the files the more I think the data at the end has to be animation data, though it seems too simple. Like I said though, I don't know much about model formats. Is it possible? Because all of the other files are completely explained.
## Post #4
- Username: plfx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 04, 2010 7:21 am
- Post datetime: 2010-08-12T21:15:28+00:00
- Post Title: Mortal Kombat Gold [.GEO]

Giving it a little bump to see if I can squeeze you guys for a little more information. Can anyone tell me whether its possible that these files include animations? There are segments of data at the end that don't seem to be geometry data.
## Post #5
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-08-12T23:04:52+00:00
- Post Title: Mortal Kombat Gold [.GEO]

> Reply from plfx
>
> Giving it a little bump to see if I can squeeze you guys for a little more information. Can anyone tell me whether its possible that these files include animations? There are segments of data at the end that don't seem to be geometry data.
The geo file you upload does not contain the animations, how ever that data in the geo file could be referencing data in other files. If you could give me a list of all the files and their respective sizes that could help me tell you which ones are animations. Also you should try deleting the same section of data in those files and then running the game with the modified files to see if there is any difference. If it freezes just try copying the first 16bytes in that section and pasting so they take up that whole section.
## Post #6
- Username: plfx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 04, 2010 7:21 am
- Post datetime: 2010-08-13T16:54:26+00:00
- Post Title: Mortal Kombat Gold [.GEO]

The dump contains only a few kinds of files.

1. System

The various files that contain the Dreamcast binaries and driver for the game, as well as a little bit of media.
1st_read.bin (6MB)
audio64.drv (20KB)
manatee.drv (33KB)
stream.mlt (288 bytes)

2. GEOmetry

The aforementioned GEO files. There are 149 of them, and their names identify them as character and stage geometry, as well as a few that are dedicated to things like menus. The alternate costumes for characters have their own GEO files. The largest of these is 840KB and holds the weapon geometry (for all weapons, it seems).

3. IMG textures

Uncompressed 16-bit XRGB top-to-bottom bitmaps. Concatenating an appropriate header makes them viewable as BMP files. There are 149 of these, one for each GEO file.

4. KAT audio

Uncompressed sound archives for various characters and contexts. All the game's sound effects other than stage music are stored in these. (The stage music was written as audio tracks on-disc.) Each character has an associated KAT file and there are others for generic and menu sounds. I haven't fully figured the format out, but I can cat these to /dev/dsp in Linux to hear the audio. Pretty sure it's 24-bit. These are all smaller than a megabyte, and the KATs for characters are each around 300KB.

5. SFD video

Various video files in a proprietary format. Converters exist for these.

Other than these, there are only two files. There is 0gdtex.pvr, which is an image in the standard PVR dreamcast texture format and displays the disc art for use in the system menu, and warning.da which is a graphic that I haven't bothered to pick apart. I'm pretty certain it just contains an antipiracy or rating warning or some such. These files are 128 and 863 kb, respectively.

I have not yet been able to put the game files back together into a playable game, since I do not have a working dreamcast emulator right now. I'll work on that, but mostly I've been trying to do this to export the characters into other games. (My original goal was just to see if I could get them into Quake or Source as player models.)

EDIT EDIT EDIT EDIT EDIT EDIT EDIT EDIT

Here's a verbose listing of all the files. I added it to the dropbox: [http://drop.io/zr0gklg](http://drop.io/zr0gklg). Ignore the directory structure; that's mine. On the disc all the files exist together in one directory.

SOME INFO ON THE FILES NAMES
The character files are given character prefixes, like SZ_ for Sub-Zero  and CY_ for Cyrax. Each character has several GEO and IMG file pairs. the standard costume for each character is simply named _GEO.(filext). So the standard costume for Reptile has the model RE_GEO.GEO and texture RE_GEO.IMG. First alternate costume is named _A_GEO (e.g. SZ_A_GEO) and second alternated (for characters for whom a second alternate exists) is _G_GEO. Each character also has a _M_GEO file, which is just an image containing a moves list for the character. *_M_GEO.GEO is always just a trivial mesh, probably just a rectangle, but the moves list is stored as an IMG and there is no IMG without a GEO. Many characters also have a *_FAT_G pair which contains art used only in fatalities.
## Post #7
- Username: tuxedo4x
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 20, 2019 10:57 pm
- Post datetime: 2019-06-20T15:51:50+00:00
- Post Title: Mortal Kombat Gold [.GEO]

> Reply from FurryFan ↑Thu Aug 05, 2010 1:04 am at Thu Aug 05, 2010 1:04 am
>
> 
This model format is pretty simple:
At offset 0h4, there is the end offset to the end of the model portion of the file.
At offset 0h8 there is a 4byteinteger of the number of submeshes:
Each submesh 32byte header then follows:
{01 00, 2byteInteger#TriStrips,4Byte"SectorOffset", the rest of each array is all 00's}
Then each tristrip will have a 32byte header, and then the data followed by the next trisrip and its header until the end of the 3d data:
{00 00 00 00, {Binary can be either 00, or 01} 00, 2ByteNumberofVertexes in Stri, The rest of each header is all 00's}
{4ByteFloatNormalMappings,4ByteFloatVertexes,4ByteFloatTexureUVCoords}
Notes:
1. "Sector" offsets are strange as they are not straight addresses to each submesh, maybe you have to add in a header for each one so they are off by the real start of each section by #headers*0h32? Why they end in "C" is a mystery as everything in this file begins at a multiple of 32
2. Tristrips are implicit so there is no face list, to render the face list just connect the vertexes in the order they are found in ie: (1stvertex,2nd vertex,3vertex=Face1) (2ndvertex,3rdvertex,4thvertex=face2)
3. the data after the 3d data doesnot appear to be 3d data maybe cd sector data

Here is a picture of the mesh(es) from the .geo file, there are about 12,000 vertexes, so some models overlap and are inside each other:

http://ps23dformat.wikispaces.com/file/ ... zero.blend

Hello FurryFan
I download models Mortal Kombat Gold here: [http://artist-3d.com/free_3d_models/dnm ... p?uid=1752](http://artist-3d.com/free_3d_models/dnm/model_disp.php?uid=1752) But seem to be it was modified both mesh and texture. Can you show a detail algorithm convert GEO to OBJ. 
This a file .geo was extracted from cdi file: [http://www.mediafire.com/file/m27totqhc ... o.rar/file](http://www.mediafire.com/file/m27totqhce6wokw/Geo.rar/file)
