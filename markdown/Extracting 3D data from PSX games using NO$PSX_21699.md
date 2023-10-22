## Post #1
- Username: Tomaszewski1994
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 04, 2019 2:03 am
- Post datetime: 2020-02-05T02:07:58+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

I am trying to extract 3D data from a PlayStation game, NASCAR Rumble, so far to no avail.

Any 3D ripping software, such as 3D Ripper DX or NinjaRipper would be useless as the PlayStation doesn't support Z-buffer, so all captures would be just flat graphics (although they are useful for extracting texture data, though they would be transparent DDS files). I also know that the vertex data (I am only concerned with vertex data for right now) for the models MUST be stored in the game's files somewhere, somehow.

So, I decided to use FlexHex on what I assume is the game's archive file, GLBLDATA.PSX, to see how the game's files are structured, and all I get is garbled text with what appears to be pointers to the actual game models, as opposed to a clean, human-readable file structure.

Referencing the post Analyzing and Reverse Engineering a Game Archive ([viewtopic.php?f=29&t=17891](https://forum.xentax.com/viewtopic.php?f=29&t=17891)), I assume that the file starts with file magic LRTC. When searching this set of characters, I found that subsequent appearances are preceded by what appears to be pointers to the car models (eg. Ccar.001.1_A).

However, when I tried to get OBJ data using Hex2Obj, with settings such as having a point cloud (again, I am only concerned with vertex data; I can fill the lines and triangles using Blender), I would only get a 2D plane of points.

For those who'd like to take a crack at it, here's a link to the game's files on my Google Drive: [https://drive.google.com/open?id=1SoU3U ... srXlLw7bUQ](https://drive.google.com/open?id=1SoU3UeYTakRhnXXgqi40q2srXlLw7bUQ). It includes everything, from the archive file to the executable and even subfolders containing movies and track data.

So, my next course of action is to use the No$PSX emulator, specifically the No$PSX VRAM Viewer.

What I've noticed is that whenever I highlight a quad or triangle, that above the texture viewer in the bottom-right corner, there are several lines of vertex data. I have attached a screenshot below:



NO$PSXscreenshot.jpg (254.75 KiB) Viewed 568 times



Most quads have twelve lines of Hex data, which I (possibly incorrectly, probably not) assumed were each a coordinate for a vertex on the quad.

After getting what I assumed was the vertex data for some triangles and quads, and loaded them onto Hex2Obj, what I got was nothing close to what the model was supposed to look like, even for a partial "capture".

What, exactly, does the hex data mean, and what can be done, if anything, to extract the 3D data from the game.

Thanks in advance.
## Post #2
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-02-05T19:43:55+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

Only for knowledge: there is something like this for PS2?
## Post #3
- Username: Tomaszewski1994
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 04, 2019 2:03 am
- Post datetime: 2020-02-06T00:59:26+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

Not that I'm aware of.
## Post #4
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-02-06T09:53:54+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

> Reply from Fiammanera628 ↑Thu Feb 06, 2020 3:43 am at Thu Feb 06, 2020 3:43 am
>
> 
Only for knowledge: there is something like this for PS2?

Well you have rdtechladys ps2 screenprint method:
1. Models: [https://youtu.be/oYuHGlm0xKs](https://youtu.be/oYuHGlm0xKs)
2. Textures: [https://youtu.be/iHlJ3qO4lys](https://youtu.be/iHlJ3qO4lys)
## Post #5
- Username: Tomaszewski1994
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 04, 2019 2:03 am
- Post datetime: 2020-02-17T00:03:13+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

> Reply from Henchman800 ↑Thu Feb 06, 2020 5:53 pm at Thu Feb 06, 2020 5:53 pm
>
> 
Fiammanera628 wrote: ↑Thu Feb 06, 2020 3:43 am
Only for knowledge: there is something like this for PS2?


Well you have rdtechladys ps2 screenprint method:
1. Models: https://youtu.be/oYuHGlm0xKs
2. Textures: https://youtu.be/iHlJ3qO4lys

This only works for PCSX2 0.9.8, and it only works about half the time. Also, the resulting rip is distorted. Only the latest version of PCSX2, 1.5.0, has support for PlayStation games.

Using Ninja Ripper on this emulator using this tutorial, [https://www.youtube.com/watch?v=svnWzkjuguY](https://www.youtube.com/watch?v=svnWzkjuguY), I got a flat mesh, surprisingly (but not), though I would be able to make out all the different faces that make it up.

Again, using model rippers would be out of the question.
## Post #6
- Username: psugorilla
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 24, 2020 11:38 pm
- Post datetime: 2020-05-24T15:58:27+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

Thomas,
I was wondering if you ever managed to complete the extraction? I am admittedly a complete noob at all of this but I too am trying to pull the 3d models from the game. Best I can tell, it appears that all the cars in the game of the same type use the same model. So the rookie cars are 1 model, the rookie trucks are a model etc. I didn't notice any difference in them based strictly on if the car was supposed to be a chevy or a ford. 
There's a whole lot more info in your post than I have found anywhere else online and I really thank you for that. 
I don't know if there is anything helpful I can offer but I was using PSXviewer on the ISO last night and the only models it could find were CROC models. 
314 of them I believe it was. But I haven't found any reference to those online. So now I am back at square one.
## Post #7
- Username: psugorilla
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 24, 2020 11:38 pm
- Post datetime: 2020-05-24T16:02:37+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

Would I be correct in assuming the .TRK files are the tracks? If so, then do you know what the .LSC files are?
## Post #8
- Username: Tomaszewski1994
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 04, 2019 2:03 am
- Post datetime: 2020-07-04T15:16:47+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

> Reply from psugorilla ↑Sun May 24, 2020 11:58 pm at Sun May 24, 2020 11:58 pm
>
> 
Thomas,
I was wondering if you ever managed to complete the extraction? I am admittedly a complete noob at all of this but I too am trying to pull the 3d models from the game. Best I can tell, it appears that all the cars in the game of the same type use the same model. So the rookie cars are 1 model, the rookie trucks are a model etc. I didn't notice any difference in them based strictly on if the car was supposed to be a chevy or a ford. 
There's a whole lot more info in your post than I have found anywhere else online and I really thank you for that. 
I don't know if there is anything helpful I can offer but I was using PSXviewer on the ISO last night and the only models it could find were CROC models. 
314 of them I believe it was. But I haven't found any reference to those online. So now I am back at square one.

Hello,

No, I haven't finished the conversion. As a matter of fact, I haven't been working on it, and I apologize for that; I have other projects I've been needing to finish, as well as my day-job and other personal things.

This, however, is one of the many things I've placed on the backburner, so I plan on getting back to it when I have finished my other projects.

I have noticed, too, that each of the Cup, Truck, and Legend vehicles are all the same model.

I appreciate your gratitude and interest; I have been no more successful than you on finding resources online, and the PlayStation does not use modern or even standard protocols for storing and accessing data.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-07-04T16:09:30+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

A little bit low poly, but a poly:  
.



GLBLDATA-PSX.png (24.2 KiB) Viewed 446 times

That's between "TADS" and "LND4".
## Post #10
- Username: psugorilla
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 24, 2020 11:38 pm
- Post datetime: 2021-04-02T15:07:36+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

So I got in touch with a couple of the game's developers and so far, this is the information I have received. I am not entirely sure I understand deciphering Chunks but this might be useful to some of you who do. 

The data on disk are very game specific and were produced using custom tools to process Soft Image (I don't think we had switched to Maya yet) exported files into game optimized data. 
So the only way to extract the data from the game would be to create some tools to extract the data back. Also, and forgive me if I doubt but it has been 20+ years, I think these tools ran on Mac on the MacOS 9...  I could certainly dig up some archive to find the runtime PS1 c code to get some indication on the format itself. 
Also if I properly recall, the TRK files are not just the track, they are actually "streamable files" where a large set of game data were embedded/sliced/"chunkified" in some IFF format, perhaps with built-in custom compression, so that would also need to be considered. If you open such TRK file in an hex editor, you'd see IFF chunk, meaning a 4 character code indicating the type of chunk, followed by the chunk size (including the chunk header), followed by the data whose type is specific to the chunk. Typically, the iff chunk header has these 5 fields (PSX1 being little endian, the data in the TRK files are in little endian fo// generic IFF header chunk

#defineIFF_CHUNK_COMMON \
int32 ChunkType; /* chunk type */ \ 
int32 ChunkSize; /* chunk size including header */ \ 
int32 time; /* position in stream time */ \ 
int32 channel; /* logical channel number */ \ 
int32 SubChunkType; /* data sub-type */

typedef struct StreamChunkS {
IFF_CHUNK_COMMON }
StreamChunk, *StreamChunkPtr;


Typically, you'd find CTRL, SHOC and FILL chunks but other types are possible since our stream could be used to embed audio, video or whatever, and even do this in an interleaved format (this was used extensively in other games). 
CTRL as the name implies is a control chunk mostly used to define sub section on a TRK file. FILL chunk are padding chunk so the TRK file can be read in fixed 24KB buffer size (easily streamed in the background). 
The SHOC chunks (this name comes from the Shockwave Game for 3DO then PSX for whose that game engine was first developed) are the game data specific that comes with 2 types of sub chunks: SHDR and SDAT. 
SHDR announces the game data type along with its size and additional optional stuff (like things allowing to conditionally load or skip for specific chunks). 

It is typically formated to match this: 

typedef struct Drive3DChunkHdrS {
IFF_CHUNK_COMMON
uint32 MemoryKind; 
uint32 AssocChkID; 
uint32 AssocChkRef; 
uint32 GlobalSize; 
uint32 HitActionOffset; 
uint32 FreeActionOffset; 
uint32 TargActionOffset; 
uint32 ConditionStrLength; 
uint32 LoadActionStrLength; 
} Drive3DChunkHdr, *Drive3DChunkHdrPtr;  

The SHDR (data header) chunk is then typically followed by 1 or more SDAT (actual data) chunks containing the sliced (and optionally compressed but if I recall not in Nascar Rumble) data. 
So the first step would be to write a little tool to extract all the game data from a TRK file. Then the game data itself (it could be track, cars or plenty of other things) would need to be interpreted according to its specific game format. 

The AssocChkID can be used to identify the track specific game data. 
It can be matched to: 
#define OPM_PATH MAKE_IFF_TYPE('C','p','t','h') 
#define CHUNK_PATH MAKE_IFF_TYPE('t','P','T','H') 
#define CHUNK_PATHeDGEaRRAY MAKE_IFF_TYPE('a','P','T','H') 
#define CHUNK_PATHoTHERaRRAY MAKE_IFF_TYPE('a','P','T','O') 
#define OPM_TRACK MAKE_IFF_TYPE('C','t','r','k') 
#define	kTrackColorChunkID MAKE_IFF_TYPE('T','C','O','L') 
#define	kTrackCurveChunkID MAKE_IFF_TYPE('T','C','R','V') 
#define	kTrackTexturesChunkID MAKE_IFF_TYPE('T','T','E','X') 
#define	kTrackSegmentChunkID MAKE_IFF_TYPE('T','S','E','G') 
#define	kTrackHorizonChunkID MAKE_IFF_TYPE('T','H','O','R') 
#define	kTrackInfoGridChunkID MAKE_IFF_TYPE('T','I','G','R') 
#define	kSunDefinitionChunkID MAKE_IFF_TYPE('T','S','U','N') 
#define	kTrackTexturesAnimChunkID MAKE_IFF_TYPE('T','T','X','A') 
#define OPM_3DCLASS MAKE_IFF_TYPE('C','o','b','j') // for 3D objects 

The MemoryKind was used to know where to rebuild the data being streamed in (main, temp, video, audio...)
## Post #11
- Username: psugorilla
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 24, 2020 11:38 pm
- Post datetime: 2021-04-04T22:24:58+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

As I mentioned, 'Cobj' was used for object subclasses so vehicles meshes should come as such data. Then you should find 'Cpag' game data type that are the texture pages. On the PSX, if my memory is not destroyed, textures were only compressed through the usage of palette so basically textures could be 8888, 556, 16 colors or 256 colors. Unfortunately, the format of the 'Cobj' or 'Cpag' might not be trivial.to reverse engineer.


Forgot to mention that .AV are indeed likely movie files and .LSC are the load screen files if I recall. So all the data you care about are in the .TRK file. BTW, the PSX did not have a floating point unit so all vertices, normals are stored in some fixed point format.
## Post #12
- Username: psugorilla
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 24, 2020 11:38 pm
- Post datetime: 2021-04-14T01:35:19+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

there are two files that may be of interest: GLBLDATA.PSX and  FE.TRK They are both in the same streamable IFF format. The first contains the global data (any data that might be shared against all tracks), the second contains the FrontEnd specific data. So it is very likely that the vehicle data are stored in GLBLDATA.PSX, no in the track specific .TRK files. I don't recall if we had made FrontEnd specific models for the vehicle (higher-res models and/or textures) to view in the car select menu but if we had, they would be in the FE.TRK.
## Post #13
- Username: lijkbezorger
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 08, 2021 2:26 pm
- Post datetime: 2023-10-12T10:15:29+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

> Reply from shakotay2 ↑Sun Jul 05, 2020 12:09 am at Sun Jul 05, 2020 12:09 am
>
> 
A little bit low poly, but a poly:  
.
GLBLDATA-PSX.pngThat's between "TADS" and "LND4".

By any chance could you please tell me what algorythm is used to parse 8 FVFsize hex data inside GLBDATA.PSX to get vertex representation in float ?    
I would like to automate parsing files by my own but I still can't get how something like this

```
64F9BEF31FF80000
```

become into such float values

```
v -6.609375 -12.257813 -7.878906
```

with same preset of params in hex2obj as in your screenshot

Thank you
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-12T11:26:18+00:00
- Post Title: Extracting 3D data from PSX games using NO$PSX

It's reading 16 bit values (shorts) then divide by 256.
