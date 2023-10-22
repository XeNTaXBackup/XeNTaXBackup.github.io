## Post #1
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-20T19:17:38+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Hi everybody !

Can someone help me to make theses 3d models importable in a 3d software (like 3ds, blender or anything...)
or a converter to .obj format please ?

Thank's in advance.

Here some sample (choose the weapon sample or item sample for quick test, since its a very small object):


EDIT:

OTOGI 2 folders: http://www.mediafire.com/?iyc334ek03xac
---------------------------------------------------------------
1) The Full Item Folder  [OK]
2) The Full Player  Folder  [OK](weapons are in the character folder)
3) The Full Hair Folder  [OK]
4) The Full Chr Folder  [OK](I think monsters must be in it, or in map folder ?)
5) The Full Map Folder n°1  [OK]
6) The Full Map Folder n°2  [OK]


OTOGI 1 folders: http://www.mediafire.com/?3g7c9at2negsa
---------------------------------------------------------------
1) The Full Item Folder         [OK]
2) The Full Player Folder       [OK](weapons are in the character folder)
4) The Full Chr Folder           [OK](I think monsters must be in it, or in map folder ?)
5) The Full Map Folder          [OK]




----------------------------------------------
I'm trying to learn how to reverse 3d model too, but I want to rip/convert/import a lot of model of various game: PGR2, Murakumo, OTOGI 1&2, XGRA, Wipeout HD, Quantum Redshift..... etc....

So a bit of help is required :p
----------------------------------------------

[](http://www.hostingpics.net/viewer.php?id=7393542610550344f7a4f709d0.jpg)[](http://www.hostingpics.net/viewer.php?id=1429220142615404860248jpg229x1287735176781166617.jpg)[](http://www.hostingpics.net/viewer.php?id=137847ME00003629292.jpg)[](http://www.hostingpics.net/viewer.php?id=622659otogi2immortalwarriors20040930083416949.jpg)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-20T22:17:10+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Haven't figured it out, but here is some progress.
I've labeled 3 unknown structs, two of them I have figured out the pattern, but one of them seems pretty random.

[https://www.dropbox.com/sh/7stlpd4qvkq3 ... gi2_mdl.py](https://www.dropbox.com/sh/7stlpd4qvkq3096/fxHCG0axg-/fmt_otogi2_mdl.py)

int = int32
If an offset is 0, just ignore it

```
   int filesize
   char[4] "MDL "
   short[2] unk
   int meshType?
   int ?
   int ?
   int count1
   int numIdx
   int numVerts1 # 60 byte vertex
   int numVerts2 # 64 byte vertex
   int numVerts3 # 72 byte vertex
   int count4
   int count3
   int numMat
   int numTex
   int unk1 Ofs
   int face Ofs
   int vert1 Ofs
   int vert2 Ofs
   int vert3 Ofs
   int vert4 Ofs
   int unk3 Ofs
   int matOfs
   int texOfs
  
   Unk1[count1] ??
   Unk2[??] ?? variable
   Unk3[count3] ??
   Material[numMat] mat structs
   Texture[numTex] tex Names
   Faces
   Vertex60
   Vertex64
   Vertex72
   Unk4
}

struct Unk1 {
    144 bytes
}

struct Unk2 {
    ?
}

struct Unk3 {
   32 bytes
}

struct Unk4 {
   432 bytes
}

struct Material {
    128 bytes
}

struct Texture {
   null-terminated string
}

struct Vertex60 {
   float[3] vx, vy, vz
   16 bytes
   float[2] tu, tv
   float[3] nx, ny, nz
   float[3] ?? 
}

struct Faces { # there are up to 4 index buffers, one for each vertex buffer
   short[numIdx] indices
}

struct Vertex64 {

}

struct Vertex72{

}

```
## Post #3
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-20T22:56:23+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> Which game is this? Or are they both the same format?

All the sample files come from OTOGI 2, I think this game have exactly the same format that OTOGI 1 have,
simply because the project OTOGI 2 has started immediately after the end of OTOGI 1 (even before is out for commercialization) .

#Source come from a Developer Diary in OXM (official xbox magazine).


For the game itself, OTOGI 1 & 2 are being developed by fromsoftware (Murakumo, Dark Soul, Armored Core etc....),
I suppose this game was developed by the same team who have worked in Murakumo.....

I searching now some info in the FIRST demo of this game, since  I remember that the first demo of the OTOGI 1 was very very different from the 2nd demo and the final game too.

Maybe, I will found more info in the format used or even some tools. (I have found some audio converter tools in the track folder of the demo game of PGR2{project gotham racing 2}, and even the name of their work directory xD)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-20T22:59:05+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Upload more samples. Maps aren't important.

Need weapons items, some more characters, and other types of models.
If there are buildings and stuff that would be cool too. Architecture is always nice to have.

The character models have multiple index buffers for some reason and their vertex structs are 72 bytes and I can't figure out how to parse it since there's only one file that is of that format.
## Post #5
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-20T22:59:58+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

WOW !!! EXCELLENT !!!!

Thank you so much !!! :p

For the random stuff its because I think I need to upload the entire character folder, because in the parent folder its seems to have some "config" data linked to the model.

I'm uploading right now, I will edit this post when it will be ready.
## Post #6
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-20T23:07:22+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Ok I have Uploaded:

OTOGI 2
--------------------------------
1) The Full Item Folder  [OK]
2) The Full Character Folder  [OK](weapons are in the character folder)
3) The Full Hair Folder  [OK]
3) The Full Chr Folder  [OK](I think monsters must ben it, or in map folder ?)

I'm ripping now the OTOGI 1 Disc on my xbox

---------------------------------
http://www.mediafire.com/?iyc334ek03xac
------------------------------------
Here the Tree folder of the game

ROOT FOLDER
--------------------------
[](http://www.hostingpics.net/viewer.php?id=982942rootfolder.jpg)

PLAYER FOLDER
--------------------------
[](http://www.hostingpics.net/viewer.php?id=437910playerfolder.jpg)
## Post #7
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-20T23:44:03+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

I have uploaded my HTML 3D viewer, (can easily make 3d model visible in any web browser supporting WEBGL).

I make some DOA sample on it, but my goal is to make a html xnalara/gmod like for web. :p

This is why I want to rip all object from my favorite games.

So Thanks a lot for your help finale00.

And if you accept, I will be able tomorrow to make a html page where all people can load anytime, anywhere, some of OTOGI 3d model :p (with credits of courses)
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T00:00:44+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

I just write the scripts. I don't really care what people do with them.
But if they go to jail for breaking their country's laws they better not complain that I'm responsible lol
## Post #9
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T00:07:05+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> I just write the scripts. I don't really care what people do with them.
>
> But if they go to jail for breaking their country's laws they better not complain that I'm responsible lol

Lol yes, I fully assume :p

I know that a lot of people doesn't have laws problems with XNaLara, so I think a simple 3Dweb poser model will not a be a " copyright crime ".
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T00:21:54+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

I think it really boils down to whether someone's going to take action or not.

I found a way to brute force the unk2 struct since it seems to be multiples of 16, but...it doesn't really work in general.
## Post #11
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T00:28:31+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> I think it really boils down to whether someone's going to take action or not.

Yes, I someone's take action against me (like Tecmo  ?) I will be obligated to take down, but if not........

> In any case, that unk2 struct I labeled is going to get in the way of pretty much every model until it's resolved.
>
> Would be nice to fill in some of those values in the header.

Yes, I finish to upload everything important and then I will get into it, you have done the hardest work (or all the work :p)
so it will be more easy now.


> I found a way to brute force the unk2 struct since it seems to be multiples of 16, but...it doesn't really work in general.
I'm working on. :p
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T01:36:46+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

dat files are just models and textures stored together with an offset table at the top.

```
int model_offset
int ofs into model?
int ofs into model?
int numTex
int[3] zeroes?

```


Each texture entry is 12 bytes long

```
int tex_offset
int ?

```


After that it's just null-terminated tex names, padded to 16 bytes

Then you just go through the file table and start parsing your models and loading the textures.
The textures are stored in sequence so if you don't know how to calculate the size of the DDS file (I don't) you just have to take the difference between the offset of the current texture and the next texture.
## Post #13
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T01:47:28+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Ok, so these .Dat files must be all monsters and Bosses.

I will try to help in this progress, even if really new in 3d model reversing, I have worked a lot on .xbe (xbox executable) hack and rip.....
:p


EDIT:

Yes you are right about "Unk2", I got the weapon worked with a 96 bytes.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T02:40:49+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Here's an unpacker for the map objects.
They're in the obj folder, extensions 000, 001, ...

The format is simple, but I can't seem to get it to work properly in quickbms.
The files are stored across multiple files (conveniently named as such), and there is a short in the file table that tells you which file it's in.

Anyways for now I just unpack the first file and leave the others for later.

```
# Script for QuickBMS

# doesn't seem to work as I thought it would
#open FDDE "000" 0
#open FDDE "001" 1

idstring "DIV\x00"
get unk long
get unk long
get filesize long # total of 000, 001, 002, ...
get FILES long
goto 64

for i = 0 < FILES
  get entry_num short
  get FILENUM short
  
  get OFFSET long
  get SIZE long
  get NAME_OFS long
  savepos CURR
  
  goto NAME_OFS
  get NAME string
  
  if FILENUM == 0
    goto OFFSET
    log NAME OFFSET SIZE
    goto CURR
  else
    break #we just need to read from the other file
  endif
  
next i

```


Possible to just write an importer to load up the entire file but...really makes no difference to me it's just more work.
## Post #15
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T02:52:25+00:00
- Post Title: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Thank you for all your work !

> Possible to just write an importer to load up the entire file but...really makes no difference to me it's just more work.

Well it's not a prob for me, I have spend 2 days for recompiling all maps from DOAX (the doax exporter export all objects, one by one....)

The map of OTOGI are very huge and beautiful, so if I need to import file by file, object by object or whatever, its not a prob :p

I will write here a table of all unk2 data for all objects in few minutes.
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T03:04:03+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

It probably isn't too useful to just see what they are. It's likely related to a couple of the values in the header.
I mean, I really don't see a pattern just by staring at a couple of those unk2's.

I think I figured out why there are multiple vertex values.

The header stores them like

```
int numVerts1 #60 byte vertices
int numVerts2 # 64 byte vertices
int numVerts3 # 72 byte vertices
int numVerts4 # 

```


It's likely to do with the fact that some meshes have weights while others don't or something, and the ones that don't have weights don't need to use a 72 byte vertex.

The indices are also stored that way. So if you have 3 separate vertex buffers for each vertex type, you'll have three index buffers.

But the index count in the header is the total number of indices; not really sure how to split it up even though they are stored sequentially.

So the two immediate issues so far are

1: unk2 struct
2: properly splitting up face buffer/ numIdx per mesh group
## Post #17
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T03:24:32+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> It probably isn't too useful to just see what they are. It's likely related to a couple of the values in the header.
>
> I mean, I really don't see a pattern just by staring at a couple of those unk2's.

Yes but by knowing them I can compare them.


```
--------------
Play0,weapon = 96,96,160,112

Play1,weapon

```


*List is updating*


W0
----------------
[](http://www.hostingpics.net/viewer.php?id=57294321w0.jpg)[](http://www.hostingpics.net/viewer.php?id=12252649w1.jpg)[](http://www.hostingpics.net/viewer.php?id=86943527w2.jpg)[](http://www.hostingpics.net/viewer.php?id=73661471w3.jpg)


EDIT:

> It's likely to do with the fact that some meshes have weights while others don't or something, and the ones that don't have weights don't need to use a 72 byte vertex.

I know that some weapons use a "cloth" that floating in the air when you move your character, I have uploaded some jpg what the complete form of the weapon.
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T03:37:44+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Ok there are offsets to all of the data sections in the header, so unk2 is not too important since we can just jump directly to materials and stuff LOL

There's no offset to unk2 section, so unk2 might be related to unk1.

Ignoring unk2, there still isn't an obvious way to split up the index buffer.
After that, figure out where the texNum is referenced in the material, then figure out how to assign the material to the faces.
## Post #19
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T03:43:01+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> Ok there are offsets to all of the data sections in the header, so unk2 is not too important since we can just jump directly to materials and stuff LOL
>
> 
>
> There's no offset to unk2 section, so unk2 might be related to unk1.
>
> 
>
> Ignoring unk2, there still isn't an obvious way to split up the index buffer

Well, I'm lost...........  

I will need to practice more, sometimes I find something, but its more lucky way......
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T03:47:12+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

I've updated the outline in my first post.
If you go to the index buffer and start scrolling down, you'll see that it starts from 0 and increases...but then it goes back to 0 again and then increases.

I want to know how to determine how many indices to read before it restarts.
Look at the hair or the player models.

Here is what I mean



It might be in unk2  

I've also figured out the rest of the offsets.
## Post #21
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T03:53:55+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Ok i'm looking it
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T04:23:22+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Otogi 1 is similar in that it has offsets to everything as well but it's a different format.
A lot of the structs are the same though.
## Post #23
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T04:34:21+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> Otogi 1 is similar in that it has offsets to everything as well but it's a different format.
>
> A lot of the structs are the same though.

Ok.

> how many indices to read before it restarts.

I don't understand exactly, do you want I count all octets before it restart ? 
(if yes, do you have some tips, because counting every octets its little boring lol)

Or how many restart ?
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T04:48:48+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Here's an otogi 1 item



> I don't understand exactly, do you want I count all octets before it restart ? 
>
> (if yes, do you have some tips, because counting every octets its little boring lol)
>
> 
>
> Or how many restart ?

If you look at the hex image, I've highlighted three 0's.
All of the indices from the highlighted 0 to the next is part of the same mesh.

The first group has a lot of indices. The second group has less indices than the first (much less). The next group is out of view but there isn't much there either.

I need to know how many of those there are in each group.
## Post #25
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T04:56:24+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Wow this the flame staff, if I remember :p



> The first group has a lot of indices. The second group has less indices than the first (much less). The next group is out of view but there isn't much there either.
>
> 
>
> I need to know how many of those there are in each group.

Ok, so by indices you mean Octets:

A9 00 AA 00 AA 00 AB 00 = 8 octet right ?

or you mean groups:

A9 00 AA 00 AA 00 AB 00 = 3 groups ?
## Post #26
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T04:57:40+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Each face is a triangle.
Each index is a short.
3 indices per triangle.

2 bytes per index
So 6 bytes per face.

You might need to search for index counts or face counts.

When I say face group, I just mean a set of n faces forming a single mesh.
## Post #27
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T05:25:12+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

hair\c011_hair.mdl

2 groups:
------------------
497 - indices (~165 Faces)
290 - indices (~96 Faces)

Does it right ?
## Post #28
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T05:35:29+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

NumIdx * 3 is always == num Triangles

I just noticed that the faces do not necessarily correspond to the vertex groups.

For example, I would expect

vert1 (60 bytes) => face 1
vert2 (64 bytes) => face 2
vert3 (72 bytes) => face 3

But one of the players I'm looking at has

vert1 => face 2
vert3 => face 1

So...I'm not really sure how it works.
It's most likely defined somewhere but I don't know where.
## Post #29
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T05:48:37+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> So...I'm not really sure how it works.
>
> It's most likely defined somewhere but I don't know where.
.xbe ?
## Post #30
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T05:50:36+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

It should be in the model.
## Post #31
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T05:56:25+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Are you sure about unk1 ??

since I have one model that require this settings:

```
        
        for i in range(count):
            
            self.inFile.seek(168, 1)
            
    def parse_unk2(self):
        
        self.inFile.seek(80, 1)
            
    def parse_unk3(self, count):
        
        for i in range(count):
            self.inFile.seek(32, 1)
```


For now:
----------------unk1,2,3
Play0,weapon0 = 144,96,32
Play0,weapon1 = 144,96,32
Play0,weapon2 = 144,160,32
Play0,weapon3 = 144,112,32

Play1,weapon0 = 144,64,32
Play1,weapon1 = 144,80,32
Play1,weapon2 = 168,80,32


I know it's maybe useless, but I think I need to index all of this, maybe we will find why some unk2 is so variable, shader ? animate object ? animate texture ? glossy texture ?
## Post #32
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T06:17:53+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> since I have one model that require this settings:

Which model is that?
## Post #33
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T06:21:02+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Play1,weapon2 = 168,80,32

player\p001\w002\w002r.mdl


EDIT: *list update*
----------------unk1,2,3

Play0,weapon0 = 144,96,32
Play0,weapon1 = 144,96,32
Play0,weapon2 = 144,160,32
Play0,weapon3 = 144,112,32

Play1,weapon0 = 144,64,32
Play1,weapon1 = 144,80,32
Play1,weapon2 = 168,80,32

Play2,weapon0 = 144,64,32
Play2,weapon1 = 144,64,32
Play2,weapon2 = 144,48,32
## Post #34
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T06:25:48+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

unk1 structs are still 144 bytes each.
The int at offset 60 gives you the start of unk1 section

The int at offset 24 gives you how many unk1 structs there are.

144 * 2 structs = 288, and then you get unk2 struct.
## Post #35
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T06:31:31+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> unk1 structs are still 144 bytes each.
>
> The int at offset 60 gives you the start of unk1 section
>
> 
>
> The int at offset 24 gives you how many unk1 structs there are.
>
> 
>
> 144 * 2 structs = 288, and then you get unk2 struct.

Yes but why we can't load this model without a 168 unk1 ?
I have tested a lot of multiple of 16, but it work's only with 168, and this is the only 1 model to do that for now.

```

Play0,weapon0 = 144,96,32
Play0,weapon1 = 144,96,32
Play0,weapon2 = 144,160,32
Play0,weapon3 = 144,112,32

Play1,weapon0 = 144,64,32
Play1,weapon1 = 144,80,32
Play1,weapon2 = 168,80,32

Play2,weapon0A = 144,64,32
Play2,weapon0B = 144,64,32
Play2,weapon0C = 144,48,32

Play2,weapon1A = 144,64,32
Play2,weapon1B = 144,64,32
Play2,weapon1C = 144,64,32

Play2,weapon2A = 144,64,32
Play2,weapon2B = 144,96,32
Play2,weapon2C = 144,96,32

```


With this list, I can say now that unk2 must have some material/animation info.
the weapons who have the lowest unk2 bytes, doesn't have any animation or glossy effect in the game.....
## Post #36
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T06:48:40+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Loads fine for me.
## Post #37
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T06:51:13+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

but what do you use :

unk1: 144
unk2: 80
unk3: 32 

this ?

EDIT: 
OK, I found why, I didn't updated my noesis with your last update (with unk2 pass)
## Post #38
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T18:52:42+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

unk2 might be related to materials, since there is no obvious way how you would assign 5 materials to one big mesh.
And that might be how it's partitioned.

I'm currently looking for models with different combinations of materials and textures in otogi 2

i115 - 3 mat, 3 tex, 16 + 96 byte unk2
i118 - 1 mat, 2 tex, 16 + 32 byte unk2
i124 - 2 mat, 2 tex, 16 + 64 byte unk2
i129 - 2 mat, 3 tex, 16 + 48 byte unk2
i500 - 1 mat, 2 tex, 16 + 32 byte unk2

Would need to look at what the actual numbers are and whether they relate to any of the values in the header.

I've separated unk2 into two parts. If you look at the second integer, you might notice that it's always the same as the 4th integer in the second line. For small files anyways like items.

It would be important to also keep in mind that there are 3 different vertex types, so the size may also depend on that.
## Post #39
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T19:05:05+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> I'm currently looking for models with different combinations of materials and textures in otogi 2
>
> 
>
> i115 - 3 mat, 3 tex, 16 + 96 byte unk2
>
> i118 - 1 mat, 2 tex, 16 + 32 byte unk2
>
> i124 - 2 mat, 2 tex, 16 + 64 byte unk2
>
> i129 - 2 mat, 3 tex, 16 + 48 byte unk2
>
> i500 - 1 mat, 2 tex, 16 + 32 byte unk2
>
> 
>
> Would need to look at what the actual numbers are and whether they relate to any of the values in the header.

Ok I will list some of the weapon folders too.
## Post #40
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T19:11:43+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Ok, unk2 is definitely two different parts.

If you look at p006.mdl, this is how unk2 starts



You see a bunch of shorts there, and then there's some odd 0x49's in between. There's obvious patterns in other files as well: some shorts, followed by some large number (an int), followed by more small shorts.

Now look at c015_hairA.mdl



I've highlighted the shorts.

If you go to the top of the file, you'll notice that the number of count1's is 7. So maybe these index into unk1 structs. Would be nice to know what they are.
## Post #41
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T19:22:43+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

```

player\p000\w000 = 1 mat, 1 tex, 16 + 96 byte unk2
player\p000\w001 = 2 mat, 1 tex, 16 + 96 byte unk2
player\p000\w002 = 2 mat, 2 tex, 16 + 160 byte unk2
player\p000\w003 = 2 mat, 2 tex, 16 + 112 byte unk2

player\p001\w000 = 1 mat, 1 tex, 16 + 64 byte unk2
player\p001\w001 = 3 mat, 1 tex, 16 + 80 byte unk2
player\p001\w002 = 2 mat, 1 tex, 16 + 80 byte unk2

player\p002\w000\w000l  = 1 mat, 3 tex, 16 + 64 byte unk2
player\p002\w000\w000r2 = 1 mat, 1 tex, 16 + 64 byte unk2
player\p002\w000\w000r  = 1 mat, 3 tex, 16 + 32 byte unk2

player\p002\w001\w001l  = 1 mat, 3 tex, 16 + 64 byte unk2
player\p002\w001\w001r2 = 1 mat, 2 tex, 16 + 64 byte unk2
player\p002\w001\w001r  = 1 mat, 2 tex, 16 + 64 byte unk2

player\p002\w001\w002l  = 1 mat, 3 tex, 16 + 64 byte unk2
player\p002\w001\w002r2 = 2 mat, 4 tex, 16 + 96 byte unk2
player\p002\w001\w002r  = 2 mat, 4 tex, 16 + 96 byte unk2


```


EDIT:
Where do you find how many materials are assigned to the model ?
For me I find the offset of the texture data, but I manually search for the material.....
[](http://www.hostingpics.net/viewer.php?id=875483Sanstitre2.jpg)
## Post #42
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T19:44:43+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

The material offset is right before the texture offset.
The matCount is right before the texCount

Just look at the outline. There's a couple unknowns that might be important.
## Post #43
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T20:00:39+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Ok I know where is that:

I will re-look quickly into weapons files, for confirm the material and texture data.


[](http://www.hostingpics.net/viewer.php?id=881986Sanstitre3.jpg)


EDIT:
Ok! here the correction *updating unk2 now*

```
----------------mat,tex,unk2

-------Raikoh----------P000-------------------

player\p000\w000 = 2 mat, 2 tex, 16 + 96 byte unk2
player\p000\w001 = 2 mat, 3 tex, 16 + 96 byte unk2
player\p000\w002 = 5 mat, 4 tex, 16 + 160 byte unk2
player\p000\w003 = 2 mat, 4 tex, 16 + 112 byte unk2

-------Kintoki---------P001-------------------

player\p001\w000 = 1 mat, 2 tex, 16 + 64 byte unk2
player\p001\w001 = 2 mat, 4 tex, 16 + 80 byte unk2
player\p001\w002 = 2 mat, 3 tex, 16 + 80 byte unk2

-------Tsuna-----------P002-------------------

player\p002\w000\w000l  = 1 mat, 3 tex, 16 + 64 byte unk2
player\p002\w000\w000r2 = 1 mat, 3 tex, 16 + 64 byte unk2
player\p002\w000\w000r  = 1 mat, 3 tex, 16 + 32 byte unk2

player\p002\w001\w001l  = 1 mat, 3 tex, 16 + 64 byte unk2
player\p002\w001\w001r2 = 1 mat, 2 tex, 16 + 64 byte unk2
player\p002\w001\w001r  = 1 mat, 2 tex, 16 + 64 byte unk2

player\p002\w002\w002l  = 1 mat, 3 tex, 16 + 64 byte unk2
player\p002\w002\w002r2 = 3 mat, 4 tex, 16 + 96 byte unk2
player\p002\w002\w002r  = 3 mat, 4 tex, 16 + 96 byte unk2

-------Sadamitsu-------P003-------------------

player\p003\w000 = 1 mat, 2 tex, 16 +  byte unk2
player\p003\w001 = 2 mat, 3 tex, 16 +  byte unk2
player\p003\w002 = 2 mat, 3 tex, 16 +  byte unk2

-------Suetake---------P004-------------------

player\p004\w000\w000l = 1 mat, 2 tex, 16 +  byte unk2
player\p004\w000\w000r = 1 mat, 2 tex, 16 +  byte unk2

player\p004\w001\w001l = 1 mat, 2 tex, 16 +  byte unk2
player\p004\w001\w001r = 1 mat, 2 tex, 16 +  byte unk2

player\p004\w002\w002l = 1 mat, 2 tex, 16 +  byte unk2
player\p004\w002\w002r = 2 mat, 3 tex, 16 +  byte unk2

-------Seimei----------P005-------------------

player\p005\w000\w000l = 0 mat, 0 tex, 16 +  byte unk2
player\p005\w000\w000r = 0 mat, 0 tex, 16 +  byte unk2

player\p005\w001\w001l = 0 mat, 0 tex, 16 +  byte unk2
player\p005\w001\w001r = 0 mat, 0 tex, 16 +  byte unk2

player\p005\w002\w002l = 0 mat, 0 tex, 16 +  byte unk2
player\p005\w002\w002r = 0 mat, 0 tex, 16 +  byte unk2


-------Raikoh(2)--------P006-------------------

player\p000\w000 = 2 mat, 2 tex, 16 + 96 byte unk2
player\p000\w001 = 2 mat, 3 tex, 16 + 96 byte unk2
player\p000\w002 = 5 mat, 4 tex, 16 + 160 byte unk2
player\p000\w003 = 2 mat, 4 tex, 16 + 112 byte unk2



```


there is a problem with SEIMEI (player005) her weapons doesn't store a lot of data, even MatCount and TexCount are not stored.
## Post #44
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T20:45:31+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Maybe that character doesn't have weapons.
## Post #45
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T20:53:09+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

No this character have weapons,

[](http://www.hostingpics.net/viewer.php?id=587698Sanstitre4.jpg)
## Post #46
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-21T20:57:13+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

The weapons might be stored with the model for some reason. Anyways the import is stuck until the faces are figured out.
## Post #47
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-21T21:47:24+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Ok I will make some files comparison, I will see if I found something.

EDIT: List updated
------------------------

```


*****************
**    ITEMS    **
*****************

i115 = 3 mat, 3 tex, 96 byte unk2
i118 = 1 mat, 2 tex, 32 byte unk2
i124 = 2 mat, 2 tex, 64 byte unk2
i129 = 2 mat, 3 tex, 48 byte unk2
i500 = 1 mat, 2 tex, 32 byte unk2


*****************
**   WEAPONS   **
*****************


-------Raikoh----------P000-------------------

player\p000\w000 = 2 mat, 2 tex, 96 byte unk2
player\p000\w001 = 2 mat, 3 tex, 96 byte unk2
player\p000\w002 = 5 mat, 4 tex, 160 byte unk2
player\p000\w003 = 2 mat, 4 tex, 112 byte unk2

-------Kintoki---------P001-------------------

player\p001\w000 = 1 mat, 2 tex, 64 byte unk2
player\p001\w001 = 2 mat, 4 tex, 80 byte unk2
player\p001\w002 = 2 mat, 3 tex, 80 byte unk2

-------Tsuna-----------P002-------------------

player\p002\w000\w000l  = 1 mat, 3 tex, 64 byte unk2
player\p002\w000\w000r2 = 1 mat, 3 tex, 64 byte unk2
player\p002\w000\w000r  = 1 mat, 3 tex, 32 byte unk2

player\p002\w001\w001l  = 1 mat, 3 tex, 64 byte unk2
player\p002\w001\w001r2 = 1 mat, 2 tex, 64 byte unk2
player\p002\w001\w001r  = 1 mat, 2 tex, 64 byte unk2

player\p002\w002\w002l  = 1 mat, 3 tex, 64 byte unk2
player\p002\w002\w002r2 = 3 mat, 4 tex, 96 byte unk2
player\p002\w002\w002r  = 3 mat, 4 tex, 96 byte unk2

-------Sadamitsu-------P003-------------------

player\p003\w000 = 1 mat, 2 tex, 48 byte unk2
player\p003\w001 = 2 mat, 3 tex, 112 byte unk2
player\p003\w002 = 2 mat, 3 tex, 112 byte unk2

-------Suetake---------P004-------------------

player\p004\w000\w000l = 1 mat, 2 tex, 48 byte unk2
player\p004\w000\w000r = 1 mat, 2 tex, 48 byte unk2

player\p004\w001\w001l = 1 mat, 2 tex, 48 byte unk2
player\p004\w001\w001r = 1 mat, 2 tex, 64 byte unk2

player\p004\w002\w002l = 1 mat, 2 tex, 16 byte unk2
player\p004\w002\w002r = 2 mat, 3 tex, 64 byte unk2

-------Seimei----------P005-------------------

player\p005\w000\w000l = 0 mat, 0 tex,  byte unk2
player\p005\w000\w000r = 0 mat, 0 tex,  byte unk2

player\p005\w001\w001l = 0 mat, 0 tex,  byte unk2
player\p005\w001\w001r = 0 mat, 0 tex,  byte unk2

player\p005\w002\w002l = 0 mat, 0 tex,  byte unk2
player\p005\w002\w002r = 0 mat, 0 tex,  byte unk2


-------Raikoh(2)--------P006-------------------

player\p000\w000 = 2 mat, 2 tex, 96 byte unk2
player\p000\w001 = 2 mat, 3 tex, 96 byte unk2
player\p000\w002 = 5 mat, 4 tex, 160 byte unk2
player\p000\w003 = 2 mat, 4 tex, 112 byte unk2


```


All unk2, textures and materials.
## Post #48
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-22T00:09:29+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

I have found where CountFace and CountVertex are.

I suggest to use this model, its the most short model (4 ko)

player\p004\w002\w002l = 1 mat, 2 tex, 16 byte unk2

player\p004\w002\w002l.mdl
## Post #49
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-22T00:45:59+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Where are they?
And how do I read them for larger files with multiple face and vertex groups? (where it matters)
## Post #50
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-08-22T00:59:13+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

For find them I have simply exported the 3d model to my 3d software, and looked how many vertices and faces the model have.

Then I have searched the total face and vertex in the model:

player\p004\w002\w002l = 1 mat, 2 tex, 16 byte unk2

player\p004\w002\w002l.mdl

VERTEX: 44  = 2C
FACES: 28    = 1C

[](http://www.hostingpics.net/viewer.php?id=738504Sanstitre2.jpg)

I have tested it with the others weapons, and it seems to be exact

About Large files, I have tested this on the Character model (Raikoh "player000") and yes I think they not show the "total vertices/face" of the entire model but each "total vertices/face" of different groups....

The fact is the Total Vertices is always more than the Total Faces, so we can separate them with this.
## Post #51
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-22T01:03:45+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

The format is incomplete. There are 3 different vertex types, and whenever there is more than one, you need to split up the faces appropriately.

The index count in the header is just the total number of indices.
## Post #52
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-12T13:38:58+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Hi
Any news about the faces ?

Because I'm completely lost about reversing these models....
## Post #53
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-12T14:26:02+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Haven't looked at it since then. Might look at again later.
## Post #54
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-12T14:41:56+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Ok !

Thank you.
## Post #55
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-07-15T09:19:47+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Any news/update ?
## Post #56
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2019-03-18T23:23:50+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Posting here a reply to say that I'm writing my own exporter/importer for this game ( already exported a models and re-imported in the game )

With Theme A


And Theme B


I have also fixed the triangle strip issue.

I will post here the script when fully completed.
## Post #57
- Username: TheJechtShot
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 05, 2019 9:48 am
- Post datetime: 2019-10-05T01:51:59+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

those two models are so good. love the theme too. really hope this comes along further! made an account just to follow this thread.
## Post #58
- Username: guiltytrace
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2020 11:18 am
- Post datetime: 2021-06-02T12:51:02+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Bumping. I've been talking to Zaykho over DM, but he/she has been too engrossed with other projects to find the time to polish the Otogi tools for public consumption. I've used the Otogi Noesis scripts written by Tsukihime to view weapon models and export them for use in Blender--that triangle strip issue is a real pain in the ass, but sometimes just deleting that vertex/face in Blender helps--and it's enough if all you want is weapon models and some field models, like power-ups.
## Post #59
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-02T15:11:07+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> Reply from zaykho ↑Tue Mar 19, 2019 7:23 am at Tue Mar 19, 2019 7:23 am
>
> I have also fixed the triangle strip issue.I'm not interested in those models but it could help others to tell what the problem was? 

> Reply from guiltytrace ↑Wed Jun 02, 2021 8:51 pm at Wed Jun 02, 2021 8:51 pm
>
> 
Bumping. I've been talking to Zaykho over DM, but he/she has been too engrossed with other projects to find the time to polish the Otogi tools for public consumption. I've used the Otogi Noesis scripts written by Tsukihime to view weapon models and export them for use in Blender--that triangle strip issue is a real pain in the ass,"Otogi tools", "Otogi Noesis scripts": is that the same or two different things?
## Post #60
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2021-06-02T16:47:29+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> Reply from shakotay2 ↑Wed Jun 02, 2021 11:11 pm at Wed Jun 02, 2021 11:11 pm
>
> 
I'm not interested in those models but it could help others to tell what the problem was?

There is a section that manage how the strip is handled. It break the mesh in multiple group with different strip, which often, reset before the end of the full strip order.

> Reply from shakotay2 ↑Wed Jun 02, 2021 11:11 pm at Wed Jun 02, 2021 11:11 pm
>
> 
"Otogi tools", "Otogi Noesis scripts": is that the same or two different things?

2 different things, "Otogi tools" is a set of tools that I made to view, export and import assets into the game (Otogi). 
[As seen here.](https://www.youtube.com/watch?v=roRavqj0YOI)

There is many many many games that I reversed that use the same set of tools that I made: Panzer Dragoon Orta, Murakumo, Otogi, Project Gotham Racing 2, Wipeout HD/Fury/Omega/VR, DOAX3 Fortune, Driveclub etc.....

And I don't want to release something that isn't fully completed (at least, not until Driveclub stream tool is finished).
## Post #61
- Username: Kohryu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 13, 2021 1:40 pm
- Post datetime: 2021-07-13T05:45:50+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Hello! Has there been any progress in the development of the "Otogi Tools" for public release? I am very interested in the models from the game, the weapons in particular, and this seems to be the only place/project with any real knowledge on the subject. So if the tools are working and avalible I would love to test them.
## Post #62
- Username: guiltytrace
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2020 11:18 am
- Post datetime: 2021-07-15T16:55:19+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> Reply from Kohryu ↑Tue Jul 13, 2021 1:45 pm at Tue Jul 13, 2021 1:45 pm
>
> 
Hello! Has there been any progress in the development of the "Otogi Tools" for public release? I am very interested in the models from the game, the weapons in particular, and this seems to be the only place/project with any real knowledge on the subject. So if the tools are working and avalible I would love to test them.

If you're particularly interested in weapon models, and want a glimpse into extraction and UV mapping, I recommend downloading Noesis and importing this script: [https://himeworks.com/redirect.php?type ... Otogi1_mdl](https://himeworks.com/redirect.php?type=noesis&name=Otogi1_mdl). Most of the weapons come out alright if backface culling is enabled, but as mentioned in previous posts, there are some random triangle strips in many of the models, so it's not a perfect solution. But if you get the model to display in Noesis, you can export it for use in Blender or 3DS to map the UVs and manipulate those errant strips.
## Post #63
- Username: Kohryu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 13, 2021 1:40 pm
- Post datetime: 2021-07-15T17:24:16+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> Reply from guiltytrace ↑Fri Jul 16, 2021 12:55 am at Fri Jul 16, 2021 12:55 am
>
> 
If you're particularly interested in weapon models, and want a glimpse into extraction and UV mapping, I recommend downloading Noesis and importing this script: https://himeworks.com/redirect.php?type ... Otogi1_mdl. Most of the weapons come out alright if backface culling is enabled, but as mentioned in previous posts, there are some random triangle strips in many of the models, so it's not a perfect solution. But if you get the model to display in Noesis, you can export it for use in Blender or 3DS to map the UVs and manipulate those errant strips.

Much appreciated, I have no 3D software experience however, so a simpler solution would be preferred, thus my hope for the Otogi tools. But thanks for the suggestion, I will give this method a try to see if I can manage it any.
## Post #64
- Username: NamelessKnight
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 30, 2021 10:42 pm
- Post datetime: 2021-07-19T15:10:01+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> Reply from guiltytrace ↑Fri Jul 16, 2021 12:55 am at Fri Jul 16, 2021 12:55 am
>
> 
Kohryu wrote: ↑Tue Jul 13, 2021 1:45 pm
Hello! Has there been any progress in the development of the "Otogi Tools" for public release? I am very interested in the models from the game, the weapons in particular, and this seems to be the only place/project with any real knowledge on the subject. So if the tools are working and avalible I would love to test them.


If you're particularly interested in weapon models, and want a glimpse into extraction and UV mapping, I recommend downloading Noesis and importing this script: https://himeworks.com/redirect.php?type ... Otogi1_mdl. Most of the weapons come out alright if backface culling is enabled, but as mentioned in previous posts, there are some random triangle strips in many of the models, so it's not a perfect solution. But if you get the model to display in Noesis, you can export it for use in Blender or 3DS to map the UVs and manipulate those errant strips.
Hello, friend. By any chance, can you tell me how it is possible to extract textures from map objects and enemies in Otogi 1/2? As I understand it textures are stored in data files, which have dds in the name. Thank you in advance for any help...
## Post #65
- Username: guiltytrace
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2020 11:18 am
- Post datetime: 2022-08-06T01:37:03+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

Oh man, I am sorry for the long, l-o-n-g delay. I hope you're still interested even a bit because the past year has been fruitful. To extract the dds images from the data files, specifically the ddsxxx_data.000 file, I use this little BMS script that searches for and pulls DDS images from a file as it finds the header. I initially needed it for MGR because IIRC those textures are similarly packed into one place and it works for Otogi, too.

> findloc OFFSET string "DDS" 0 "" 0
>
> math i = 0
>
> do
>
> 
>
>     goto OFFSET
>
>     get DUMMY long
>
>     findloc NEXT_OFFSET string "DDS" 0 ""
>
> 
>
>      if NEXT_OFFSET == ""
>
> 
>
>         get SIZE asize
>
>     else
>
>         math SIZE = NEXT_OFFSET
>
> 
>
>     endif
>
>     math SIZE -= OFFSET
>
>     log "" OFFSET SIZE
>
>     math i += 1
>
>     math OFFSET = NEXT_OFFSET
>
> 
>
> while NEXT_OFFSET != ""

I just ran that script on \map\m027 and it pulled 22 images, one of which is the skybox from the final battle. For the second step, instead of selecting an individual file, you can enter a * and the script will search and execute through the entire folder and any subfolders (which is helpful because there is another .000 in \map\m027\obj).

Edit: I just ran the script on the entire Otogi root folder and I would not recommend it. LOL It generated 1289 folders and there are images scattered everywhere, though it is the quickest method to get everything at once. Going folder by folder could be fun?

[https://drive.google.com/file/d/1OVd6NK ... sp=sharing](https://drive.google.com/file/d/1OVd6NKwuFm5TTg8YMzmXsRkMVa0P7NiD/view?usp=sharing)
## Post #66
- Username: Kohryu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 13, 2021 1:40 pm
- Post datetime: 2022-08-06T02:14:59+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> Reply from guiltytrace ↑Sat Aug 06, 2022 9:37 am at Sat Aug 06, 2022 9:37 am
>
> 
Oh man, I am sorry for the long, l-o-n-g delay. I hope you're still interested even a bit because the past year has been fruitful. To extract the dds images from the data files, specifically the ddsxxx_data.000 file, I use this little BMS script that searches for and pulls DDS images from a file as it finds the header. I initially needed it for MGR because IIRC those textures are similarly packed into one place and it works for Otogi, too.
findloc OFFSET string "DDS" 0 "" 0
math i = 0
do

    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET string "DDS" 0 ""

     if NEXT_OFFSET == ""

        get SIZE asize
    else
        math SIZE = NEXT_OFFSET

    endif
    math SIZE -= OFFSET
    log "" OFFSET SIZE
    math i += 1
    math OFFSET = NEXT_OFFSET

while NEXT_OFFSET != ""

I just ran that script on \map\m027 and it pulled 22 images, one of which is the skybox from the final battle. For the second step, instead of selecting an individual file, you can enter a * and the script will search and execute through the entire folder and any subfolders (which is helpful because there is another .000 in \map\m027\obj).

Edit: I just ran the script on the entire Otogi root folder and I would not recommend it. LOL It generated 1289 folders and there are images scattered everywhere, though it is the quickest method to get everything at once. Going folder by folder could be fun?

https://drive.google.com/file/d/1OVd6NK ... sp=sharing

Interesting. That's a Noesis script I'm guessing? I wouldn't mind skimming through some of the files next time I get the chance, particularly wondering if there is any cut content like weapons or such. That could be fun to include in the wiki, assuming there is anything like that.

Either way, keep up the good work.
## Post #67
- Username: guiltytrace
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2020 11:18 am
- Post datetime: 2022-08-18T16:13:24+00:00
- Post Title: Re: [XBOX] OTOGI 1 & 2 char, item, maps  ? (.dat & .mdl)

> Reply from Kohryu ↑Sat Aug 06, 2022 10:14 am at Sat Aug 06, 2022 10:14 am
>
> 

Interesting. That's a Noesis script I'm guessing?

No, it's a BMS script.
