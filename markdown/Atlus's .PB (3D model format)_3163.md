## Post #1
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2008-09-22T11:56:12+00:00
- Post Title: Atlus's .PB (3D model format)

The format is used in almost all of Atlus's PS2 games : Nocturne, DDS1&2, Devil Summoner. From Persona3 onwards, there's the .RMD format that doesn't look similar at all although they still use the .TMX format for the textures.

Ok, so first, the games listed above all have the IMG/DDT archive format which is basically an image header (the DDT) and the actual packed data (the IMG). I managed to figure out the DDT format and make up the directory structure but... when reading from the IMG there's these huge gaps between the files and from what I've seen they are irregular (different sizes for each file), and therefore I made up my reader to just ignore zero bytes and then begin the file when there's something different than zero. And the thing is that sometimes this isn't true, and the file doesn't get extracted well, and debugging is even harder considering the 7 000+ files.

On the Nocturne DVD, Atlus forgot an Windows executable that opens up .TMX files and so I've been able to figure out how the TMX header looks like although some parts are very dubious (like a byte with the value 19, that is present in most files, but in other files it's 0).

Now I'm focusing my attention on the .PB model format that contains model data, and it's like a file per model which means it has .TMX textures stacked in it (and possibly animations too). So far I partially figured out how the header looks like and I'm trying to get a hold of the actual polygons/normal/texcoords.

I'll make more posts once I discover more.

EDIT: The new release(v0.3) includes an inf file for configuration. I hope everyone gets what the variables are used for.

January 2012 EDIT : Improved conversion, Win32 GUI and full source code is now available to [download](http://www.mediafire.com/?1rbk7xu7a2ncqo3).
## Post #2
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2008-09-22T11:58:06+00:00
- Post Title: Atlus's .PB (3D model format)

Anyways, yesterday I worked a little bit more on .PB models and discovered that some files have wrong headers and direct the texture reading to other places than the real ones which is fuck weird because it screws up my processing. Next I discovered weird arrays of numbers right after the textures, like
1 0 -1 (72 bytes)
1 1 0 (72 bytes)
1 2 1 (72 bytes)
1 3 1 (72 bytes)
.......
1 89 88 (? bytes)
It's really weird because I know where they end, but don't know where the rest of the data begins (there's <=72 bytes, and any of them could start a new array of data). For the weird numbers, I think it's the skeletal bone tree(first number is ignored, second is child, and next it's parent) and right next to them there's 18 floats, which could mean a transformation matrix (since most values are near PI/2, 0 or 1), but some matrices sure look weird (like 1.2e-23) so I'm having some doubts.

EDIT:4 days later I found out that's the scene graph actually, and shows some kind of hierarchy, and in the 72 bytes between there's a position, some kind of rotation+scale and 2 file indexes to where the bounding box is and the start of the index array.
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-22T21:24:42+00:00
- Post Title: Atlus's .PB (3D model format)

This should have been put in the 3D models section but I think one of the mods can move it. As for the data given it may be that it is just an odd format that Atlus developed. Though I'll wait for some input from the other 3D people here.
## Post #4
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2008-09-25T21:30:00+00:00
- Post Title: Atlus's .PB (3D model format)

I finally got the meaning behind a weird number and managed to accurately extract all the files from a DDT\IMG archive. I updated the main post to include the exexcutable you can use.The pack includes an INF file for configuration. Enjoy.
## Post #5
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2008-09-29T21:18:01+00:00
- Post Title: Atlus's .PB (3D model format)

First look at the some vertex data extracted ! 

I worked on it some more and found out how to begin reading the index/vertex/normal/texcoord/color data but... there's still missing links like when to stop reading, what kind of data comes next (either one of texcoords/normals/colors) and what kind of render mode to use (triangles/triangle strips/fans/quads/etc).

Here's a look at "kage.PB" from Digital Devil Saga 1, hope you like it 
[Hackinator-PB.JPG](https://xentaxbackup.github.io/file/1666_Hackinator-PB.JPG)
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-30T18:49:52+00:00
- Post Title: Atlus's .PB (3D model format)

Heh! Well that is progress none the less to see something visual! But which is "kage" from DDS1?

Also, the program keeps saying the side-by-side configuration is incorrect.

I set the right drive path to the Digital Devil Saga DVD.

The error states as follows:

"The application has failed because its side-by-side configuration is incorrect. Please see the application event log for more detail."
## Post #7
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2008-10-02T09:52:25+00:00
- Post Title: Atlus's .PB (3D model format)

Ups! You'll need MSVCR90.DLL to run it . I usually compile my projects with dynamic linking because a few dependencies I have. If that doesn't work, check with the (www.)dependencywalker(.com) if you have any missing DLLs.
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-10-02T19:22:32+00:00
- Post Title: Atlus's .PB (3D model format)

> Error: The Side-by-Side configuration information for "c:\pcsx2_0.9.4\atlus v0.3\ATLUS HACKINATOR RELEASE.EXE" contains errors. The application has failed to start because its side-by-side configuration is incorrect. Please see the application event log for more detail (14001).
>
> Warning: At least one module has an unresolved import due to a missing export function in a delay-load dependent module.

Is what it is saying through that.
## Post #9
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2008-10-02T20:59:10+00:00
- Post Title: Atlus's .PB (3D model format)

Even after you put that DLL near it ?
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-10-02T22:15:04+00:00
- Post Title: Atlus's .PB (3D model format)

Yeah. O_o SHLWAPI.DLL and IEFRAME.DLL are in the red.

SHLWAPI
The function in red is #467

For IEFrame it is
#159, #141, #160, #165, #167, #142
## Post #11
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2008-10-02T22:59:10+00:00
- Post Title: Atlus's .PB (3D model format)

Hm... the thing is I had 2 builds, release and release with edit & continue, and they were named the same and I don't know which version I ended up distributing . This time I built the executable with static libs so it should work. First post was updated.
## Post #12
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-10-03T00:42:02+00:00
- Post Title: Atlus's .PB (3D model format)

Now it crashes... O_o

"Warning: At least one module has an unresolved import due to a missing export function in a delay-load dependent module." In Dependency Walker. What a weird thing it keeps doing...

IEFRAME:
#160, #159, #141

SHLWAPI:
#467

Well, much was resolved at least.
## Post #13
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2008-10-03T12:55:24+00:00
- Post Title: Atlus's .PB (3D model format)

Damn... 
I double checked and yeah, the past executable shouldn't exactly work because I did it in a hurry and forgot I had a variable that was overriding the current config so I can freely do my PB tests. Test it with the new one. If that doesn't work, hm... don't know what else to try. Are you running Vista by the way ?
## Post #14
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-10-03T19:48:53+00:00
- Post Title: Atlus's .PB (3D model format)

Yes, I use Vista. Is that the problem?
## Post #15
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2008-10-05T14:56:00+00:00
- Post Title: Atlus's .PB (3D model format)

No idea. I still use XP . If the problem persists (you haven't told me if it works or not with the new executable ?) I'll try to test it on Vista. I have it installed, but I never use it.

EDIT: I opened up Vista yesterday, and while the old executables aren't working, the new one at least starts. Haven't tried to extract an image though.
## Post #16
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-10-05T20:26:51+00:00
- Post Title: Re: Atlus's .PB (3D model format)

The new one is giving me trouble too. O_o
## Post #17
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2008-10-07T11:18:26+00:00
- Post Title: Re: Atlus's .PB (3D model format)

I was able to figure out parts of RMD data file based on the info given on .PB files

typedef struct  {
	UCHAR filetag[12];
	USHORT rmdtype;
} rmd_header;

typedef struct {
	UINT datatype;
	USHORT datasize;
	USHORT padding;
	UINT seperator; // "55 0 2 28"
} data_header;

typedef struct {
	UINT tex_width;
	UINT tex_height;
	UINT tex_bitdepth; //Not confirmed yet
	UCHAR data0[52]; //No clue yet most likely additional image formating intel
} tex_header;


//Weapon Model File Read Example 
//rmdheader
//dataheader ID 22 Size 9600 Data = Textures
//dataheader ID 1  Size 4    Data =  "0 1 0 6" bytes
//dataheader ID 21 Size 9560 Data = Tx2 Header + Tx2 Data
//dataheader ID 1  Size 8    Data = "PS2   " Label
//dataheader ID 2  Size 8    Data = "bat01 " Label
//dataheader ID 2  Size 4    Data = "  " Label
//dataheader ID 1  Size 9464 Data = Tx2 Data
//dataheader ID 1  Size 64   Data = Texture Info Data Width/Height/BitDepth/????
//dataheader ID 1  Size 9376 Data = Header/ImageData/Header/PaletteData
//dataheader ID 3  Size 16   Data = ?
//dataheader ID 272 Size 4   Data = 4032 ?
//dataheader ID 3  Size 0    Data = Nothing to Read

//dataheader ID 16 Size 3983 Data = 3D Data
//dataheader ID 1  Size 12   Data = "1 0 0 0 0 0 0 0 0 0 0 0" ?
//dataheader ID 14 Size 196  Data = ? 
//dataheader ID 1  Size 116  Data = ?  "Integers mixed with Floats" Matrix? 
//dataheader ID 3  Size 0    Data = Nothing to Read
//dataheader ID 3  Size 44   Data = ? 
//dataheader ID 286  Size 32   Data = ? 
//dataheader ID 26 Size 3675 Data = ? 
//dataheader ID 1  Size 4    Data = 1
//dataheader ID 15 Size 3647 Data = ? 
//dataheader ID 1  Size 2856 Data = Texture Coord/Index/BoundingBox/Vertices/Normals
//dataheader ID 8  Size 226  Data = ?
//dataheader ID 1  Size 8    Data = ?
//dataheader ID 7  Size 194  Data = ?
//dataheader ID 1  Size 28   Data = ?
//dataheader ID 6  Size 80   Data = ?
//dataheader ID 1  Size 4    Data = ?
//dataheader ID 2  Size 8    Data = "bat01 " Label
//dataheader ID 2  Size 4    Data = " " Label
//dataheader ID 3  Size 16   Data = ?
//dataheader ID 272 Size 4   Data = 4032 ? 
//dataheader ID 3  Size 50   Data = ?
//dataheader ID 287 Size 38  Data = "   name  02 - Default" String
//dataheader ID 3  Size 529  Data
//dataheader ID 1294 Size 472 Data = ? "Integers"
//dataheader ID 287 Size 33  Data = "FVF.UserData    " String
//dataheader ID 20 Size 40   Data = ?
//dataheader ID 1  Size 16   Data = ?
//dataheader ID 3  Size 0    Data = Nothing to Read
//dataheader ID 3  Size 0    Data = Nothing to Read
//dataheader ID 5  Size 64   Data = "Integers and Floats"
//dataheader ID 27 Size 88    Data = ?
//???????????
[WP000.rar](https://xentaxbackup.github.io/file/1680_WP000.rar)
## Post #18
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2008-10-09T02:07:29+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Well that was tricky I decoded about 70% of the format here is the result
of the RMD model posted earlier. So I guess the PB format evolved into the RMD format
[wrip.rar](https://xentaxbackup.github.io/file/1681_wrip.rar)
## Post #19
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2008-10-12T00:59:50+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Shit, I bookmarked the post, and I was continually checking the first page .

Anyways, sorry about the exe DarkFox, I have no idea why it's not working.
prototypesky good job man , can you post some updated data structs ?

I continued my work on the .PB reader but damn, I get these array flags which are pseudo-random and I thought there might be a pattern but It seems like I was wrong... Anyways, that RMD format seems much easier than the crappy .PB. By the way, do they store uncompressed images in the RMD or pallet based ones ? Because I don't know (as of yet) how to read that TMX format. Anyway, if it helps I will post some updated structure & reading code for the PB reader.
[PB_Reader.zip](https://xentaxbackup.github.io/file/1684_PB_Reader.zip)
## Post #20
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2008-10-12T03:44:10+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Well I am now able to view most RMD models now 

I am now trying to see if reverse engineering the animations are possible

Here are some of the additional discoveries I've made

//data types 22 = GROUP OF TX2 DATA
//           21 = TX2 DATA
//           20 = ??? DATA
//			 31 = ??? Count Value or Type
//          288 = ??? Count Value or Type
//            1 = SUB DATA  
//            2 = STRING DATA
//            3 = SUB DATA
//           16 = Marks the Start of 3D Data first 4byte = Int holding the number of models 16 marks bone data 26 marks vertex data 
//           26 = Marks the Start of 3D Data first 4byte = Int holding the number of meshes
//			 14 = ??? //the 1 Sub Data that follows this seems to be a mix of Ints and Floats 
                      //The first 4 bytes is the number of this data type and 286 Type that follow afterwards
					  //12 Float values followed by a Int Numbers increase but duplicate in some case then e.g 0 1 2 2 2 5 
//			286 = ??? //Starts of with the Int value 256 
                      //Then followed by an array of intergers seems to be in groups of three's but there are some inconsistancies
//           15 = MESH DATA
//			  8 = GROUP OF MATERIAL DATA
//            7 = MATERIAL VALUES //Ambient Diffuse etc
//            6 = MATERIAL DATA
//			272 = ??? // seems to have "192 15 0 0" 4032 // Probably a divider/padding
//          287 = Seems to be a desc for the Material
//         1294 = ???// An array of INT or SHORT DATA
//          278 = ??? //
//					42   bytes of Header Info
//					6192 bytes of INT or SHORT DATA  1548 3096
//					24768 bytes of FLOATS 6192
//					44 byte of FLOATS 11
//					Mix of Floats and ints with "17 1 0 0" and "120 37 1 38"

//       43 = ???//Animation Data Maybe
//       27 = ???//Animation Data Maybe
//       14 and 286 Might Also be related to some Animation System


There is an array Structure under data type 14 that looks the follow 
//Unknown Data[1]
//... 1.000000, 0.000000, 0.000000
//... 0.000000, 1.000000, 0.000000
//... 0.000000, 0.000000, 1.000000
//... 0.000000, 0.000000, 0.000000
//... 0
//... 3
//Unknown Data[2]
//... 1.000000, 0.000000, 0.000000
//... 0.000000, 0.000000, 1.000000
//... 0.000000, -1.000000, 0.000000
//... 0.000000, 107.609398, -3.500397
//... 1
//... 3
//Unknown Data[3]
//... 1.000000, 0.000000, 0.000000
//... 0.000000, 0.000000, 1.000000
//... 0.000000, -1.000000, 0.000000
//... 0.000000, 0.000000, 0.000000
//... 1
//... 3
//Unknown Data[4]
//... 0.000001, 1.000000, 0.000000
//... 0.000000, 0.000000, -1.000000
//... -1.000000, 0.000001, 0.000000
//... 0.000002, -1.496140, -95.843407
//... 3
//... 3
//Unknown Data[5]
//... 0.000000, 1.000000, 0.000001
//... -0.000001, 0.000001, -1.000000
//... -1.000000, 0.000000, 0.000001
//... -2.355187, -6.839119, -0.000000
//... 4
//... 3
//Unknown Data[6]
//... -0.112441, 0.000000, -0.993658
//... 0.000000, 1.000000, 0.000000
//... 0.993658, 0.000000, -0.112441
//... 1.580411, 1.352005, -0.181326
//... 4
//... 3
## Post #21
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2008-10-12T03:52:25+00:00
- Post Title: Re: Atlus's .PB (3D model format)

> Reply from cippyboy
>
> Shit, I bookmarked the post, and I was continually checking the first page .

Anyways, sorry about the exe DarkFox, I have no idea why it's not working.
prototypesky good job man , can you post some updated data structs ?

I continued my work on the .PB reader but damn, I get these array flags which are pseudo-random and I thought there might be a pattern but It seems like I was wrong... Anyways, that RMD format seems much easier than the crappy .PB. By the way, do they store uncompressed images in the RMD or pallet based ones ? Because I don't know (as of yet) how to read that TMX format. Anyway, if it helps I will post some updated structure & reading code for the PB reader.

I am yet to run into compressed Textures.
There propably isn't any since 4.7GB is alot of space and the largest textures I've see is 256x256 32bit
The Textures in the RMD are swizzled and the pallet indexes have the 4 and 5 bits reversed for 8bit textures.
Just unswizzle and swap the 4 and 5 bits of the pallete index values and you should be able to view the textures no problem
## Post #22
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2008-10-18T02:42:14+00:00
- Post Title: Re: Atlus's .PB (3D model format)

I found the bone data for the model that links the bones to the vertices and the respective weight values and the bones local matrix and an array that somewhat defines the parent child relationship of the bones. It's all stored in Data Header Id 278.

Unfortunately I can't pin point anything that resembles actually animation key frame data in the file
## Post #23
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2008-10-20T11:29:21+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Hey, just found out that if you have any problems with the exe, [this](http://www.microsoft.com/downloads/details.aspx?familyid=9B2DA534-3E03-4391-8A4D-074B9F2BC1BF&displaylang=en) might help. I made some more advancements but still couldn't get entire models out. I have an upside down, 70% mass free Raidou Kuzunoha by now; I'll make a pic when I get the time .
## Post #24
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2008-10-21T21:03:17+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Ok I found the actual animation data from a RMD file
the structure of it so far is
the first 4 bytes is a float value
the next 4 bytes is the number of animation key frames

Each key frame is 22 bytes in size
The first four bytes of each key frame is a float value
where the values range from 0.0f to 2.0f
then it is followed by 14 bytes of data which I haven't been able to confirm what each byte represents but they affect the bone matrix orientation for that frame and the last 4 bytes seems to be either 2 shorts or an interger value.

I've noticed that the first n key frame data structures where n = the total number of bones defined in the model, the last 4 byte values are the same and the first 4 byte float values are = to 0.0f
Then the next n value the first 4 byte float values now range from 0.0f to 2.0f and the 4 byte integer at the end of the 22 byte data structure value increments in multiples of 24 e.g (0, 24, 48, 72, 96 etc up until n*24 value after which the numbers don't don't ascend always the amount 24 but a multiple of 24 sometimes. I am guessing the last four bytes determines which bone matrix is altered and when on the animation time line they are altered.

Also after all the key frame data structures there are 6 float values.

Anyone wishes to try and make sense of this format?
[runani.rar](https://xentaxbackup.github.io/file/1694_runani.rar)
## Post #25
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-10-22T00:06:59+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Strangely the problem has become centralized with SHLWAPI.DLL and IEFRAME.DLL. The other problems however are gone.
## Post #26
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2008-10-23T22:59:16+00:00
- Post Title: Re: Atlus's .PB (3D model format)

> Reply from Darkfox
>
> Strangely the problem has become centralized with SHLWAPI.DLL and IEFRAME.DLL. The other problems however are gone.

If you got the VC9 redistributables and you still have problems it's kind of odd, did you try getting those DLLs off the internet ?
## Post #27
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-10-26T03:24:52+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Yes. Hm... some say this is normal with Vista, they say it should work anyways... huh...
## Post #28
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-08-01T11:23:18+00:00
- Post Title: Re: Atlus's .PB (3D model format)

The contents of this post was deleted because of possible forum rules violation.
## Post #29
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2012-01-06T02:45:42+00:00
- Post Title: Re: Atlus's .PB (3D model format)

3 years after I started this I came back to it in an attempt to finish it . The format proves to be quite tricky, probably the trickiest thing I've seen so far. Anyway, I'm working on it and will post some final code & the application soon.
[Munakata.png](https://xentaxbackup.github.io/file/4958_Munakata.png)
## Post #30
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2012-01-06T04:27:23+00:00
- Post Title: Re: Atlus's .PB (3D model format)

I-is that a Devil Summoner model I see!? IT IS! General Munakata, oh wow! 

A lot is missing of him but this is simply amazing! And glad to have you back!
## Post #31
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2012-01-14T04:33:03+00:00
- Post Title: Re: Atlus's .PB (3D model format)

I just released full source code for the new Win32 application I made to convert stuff to FBX, probably the single format that supports bones & stuff, absolutely needed for seeing actual models standing. Here's a [link](http://www.mediafire.com/?1rbk7xu7a2ncqo3), and this is how Munakata looks like as of now. Not perfect, but definetely looking better . If anyone wants to jump into the data hunt, they can do it now using the code.
[Munakata2.png](https://xentaxbackup.github.io/file/4985_Munakata2.png)
## Post #32
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2012-01-18T04:48:01+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Oh aye, definetly looking better, more parts are rendered now but still a bit light.  The switch to FBX was a great choice to preserve the structure of the model, will also make animation conversion easier to test out if that comes around.

All-in-all, well done! It is very appreciated on your contributions to cracking Megaten models.
## Post #33
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-12-05T15:16:10+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Ty for the info on the format even though your coding is very confusing to read to be honest so I ended up having to figure out a lot myself :p
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-05T16:27:07+00:00
- Post Title: Re: Atlus's .PB (3D model format)

> Reply from TGE
>
> [...] even though your coding is very confusing to read to be honest so I ended up having to figure out a lot myself :pwell, it's such comments/attitude which prevent me from releasing sources
## Post #35
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-12-05T17:43:50+00:00
- Post Title: Re: Atlus's .PB (3D model format)

> Reply from shakotay2
>
> TGE wrote:[...] even though your coding is very confusing to read to be honest so I ended up having to figure out a lot myself :pwell, it's such comments/attitude which prevent me from releasing sources
It's not an attitude, it's just very confusing for anyone but yourself to read sometimes.
If you add enough comments and explain what things are and what they do (which he didn't do for the most part) there should be no problem.
Not to mention I'm not that great at reading C++ source code.
## Post #36
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-12-08T23:14:09+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Now to figure out how the scene graph works...
## Post #37
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2014-12-27T23:50:10+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Long time but I'm impressed this has continued! Seems you've even got some models in animated states, or is that the default pose for Kodama's model?
## Post #38
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-12-30T18:54:43+00:00
- Post Title: Re: Atlus's .PB (3D model format)

> Reply from Darkfox
>
> Long time but I'm impressed this has continued! Seems you've even got some models in animated states, or is that the default pose for Kodama's model?

Seems like a leftover 'petrified' state model. It's a static model.
I'm really struggling to get the models to 'stand up' but as far as loading the meshes themselves goes, I can load nearly all models.
I've even added support for field models, so you'll be able to rip environments as well.


Of course, nothing will look correct till I get the scene graph to work in my MaxScript.. though I honestly have no clue how to implement it.
## Post #39
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-05-20T19:36:43+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Progress! I'm still working on this from time to time  (yes it's rigged)
## Post #40
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2015-05-21T12:11:50+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Really good! Can see all the little finger joints too are there and no oddities. I'm assuming from this you nearly got the entire structure down?
## Post #41
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-05-21T13:39:10+00:00
- Post Title: Re: Atlus's .PB (3D model format)

> Reply from Darkfox
>
> Really good! Can see all the little finger joints too are there and no oddities. I'm assuming from this you nearly got the entire structure down?
Nearly yeah, there's a few more mesh types I have to figure out for everything to work properly and there's a minor bug with invalid offsets but it's getting there :p
## Post #42
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2015-05-22T03:00:40+00:00
- Post Title: Re: Atlus's .PB (3D model format)

> Reply from TGE
>
> Nearly yeah, there's a few more mesh types I have to figure out for everything to work properly and there's a minor bug with invalid offsets but it's getting there :p

Oh yeah? What other mesh types? How much of the format is understood and in the process of understanding? I'm interested to hear.
## Post #43
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-05-23T13:12:32+00:00
- Post Title: Re: Atlus's .PB (3D model format)

> Reply from Darkfox
>
> TGE wrote:Nearly yeah, there's a few more mesh types I have to figure out for everything to work properly and there's a minor bug with invalid offsets but it's getting there :p

Oh yeah? What other mesh types? How much of the format is understood and in the process of understanding? I'm interested to hear.
The format uses types for certain mesh types eg:
0x1 for meshes with no bone assignments, 0x2 for meshes with weight assignment, 0x3 for (this is just as assumption) morpher meshes, 0x7 for.. bigger submeshes that use bone weights and 0x8 for bigger submeshes that don't use weights.
The format is horribly ps2-like with it's heavy use of vif code (ps2 gpu instructions, basically) shenanigans so in order to have a chance at parsing this correctly I wrote two functions to handle unpacking the data for me in max ([here's](http://pastebin.com/dM8yaNnP) the link to the function if you want to see it). 
The weighted meshes were quite confusing for me to figure out because I had an oversight in my code and they're stored in a weird way.
Basically how they're stored is they define the amount of bones assigned to the object along with the respective bone ids.
Then you loop through the vif 'batches' bone amount times to get the indivual vertex segments which are stored as Vector4s with element 1,2,3 being the 'relative vertex position' and element 4 being the weight and after you've looped through them you need to merge the individual vertex segments back into 1 segment by de-interleaving them based on their bone influences and transforming them by their bone transforms.
Something like 

```

```

I still haven't figured out how to get the normals out correctly for the 0x2 meshes though, as they store a normal vector for every segment and each segment only seems to shade one 'side' of the model so it's kinda weird.
It's kinda terrible to explain but it gets the job done.
As for the type 0x7 and 0x8 meshes, I don't really know too much about them yet. They just seem like 'less packed' versions of the 0x1 and 0x2 types.
The batch header and face indices are no longer packed but that's kinda it it seems.
The 0x3 meshes are kinda odd, I think they define an offset table in the beginning to all the different batches that make up the morpher meshes.
Luckily none of these types use special kind of face indices, so no weird ps2 triangle stripping.
## Post #44
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-05-30T14:57:47+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Okay so I got the rest of the types working for the most part.
I haven't figured out how to assign the textures automatically though, so that'll take me some time to figure out.
## Post #45
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-06-20T13:34:49+00:00
- Post Title: Re: Atlus's .PB (3D model format)

[http://puu.sh/ivZCy.png](http://puu.sh/ivZCy.png)
Morphers are now supported
## Post #46
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-06-27T07:37:20+00:00
- Post Title: Re: Atlus's .PB (3D model format)

TGE, nice progress on this, man. Looking forward to see the script
## Post #47
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-08-09T22:16:43+00:00
- Post Title: Re: Atlus's .PB (3D model format)

I released the script
[viewtopic.php?f=16&t=13159](http://forum.xentax.com/viewtopic.php?f=16&t=13159)
## Post #48
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2018-04-26T01:22:20+00:00
- Post Title: Re: Atlus's .PB (3D model format)

> Reply from prototypesky
>
> Ok I found the actual animation data from a RMD file
the structure of it so far is
the first 4 bytes is a float value
the next 4 bytes is the number of animation key frames

Each key frame is 22 bytes in size
The first four bytes of each key frame is a float value
where the values range from 0.0f to 2.0f
then it is followed by 14 bytes of data which I haven't been able to confirm what each byte represents but they affect the bone matrix orientation for that frame and the last 4 bytes seems to be either 2 shorts or an interger value.

I've noticed that the first n key frame data structures where n = the total number of bones defined in the model, the last 4 byte values are the same and the first 4 byte float values are = to 0.0f
Then the next n value the first 4 byte float values now range from 0.0f to 2.0f and the 4 byte integer at the end of the 22 byte data structure value increments in multiples of 24 e.g (0, 24, 48, 72, 96 etc up until n*24 value after which the numbers don't don't ascend always the amount 24 but a multiple of 24 sometimes. I am guessing the last four bytes determines which bone matrix is altered and when on the animation time line they are altered.

Also after all the key frame data structures there are 6 float values.

Anyone wishes to try and make sense of this format?

Ok solved it renderware had compressed floats

to uncompress
I = int(H & 0x8000) << 16
if H & 0x7fff:
	I |= int(int(H & 0x7800) << 12) + 0x38000000
	I |= int(H & 0x7ff) << 12

return I

to decompress the quaternion floats
then use the x,y,z offset vector and a x,y,z scale vector that follows the frame struct array that has to be applied to each decompressed position vectors for the proper value
[p4_anim.PNG](https://xentaxbackup.github.io/file/14284_p4_anim.PNG)
## Post #49
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2018-04-26T04:57:27+00:00
- Post Title: Re: Atlus's .PB (3D model format)

Have you tried dividing the frame data by 32767.0 or 65535.0?
## Post #50
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2018-04-26T17:32:06+00:00
- Post Title: Re: Atlus's .PB (3D model format)

> Reply from killercracker
>
> Have you tried dividing the frame data by 32767.0 or 65535.0?
yes it doesn't seem to be fixed point
the first four float should be an Quaternion identity of 0.0f, 0.0f, 0.0f, 1.0f
so the value 30720 should convert to 1.0f I believe

See previous post for solution.
