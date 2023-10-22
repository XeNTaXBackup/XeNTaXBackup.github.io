## Post #1
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2021-11-14T20:19:35+00:00
- Post Title: RESET Model Extraction Help

Hi Guys,

[SKIP IF YOU DON'T WANT TO READ, THIS IS JUST CONTEXT]
In a bit of a pickle currently, for a bit of context, I'm trying to extract the 3D models from an indie game that seems to sadly never have come to fruition. That game being called Reset - [https://www.youtube.com/watch?v=iHRu0jw7b2U](https://www.youtube.com/watch?v=iHRu0jw7b2U). They released a Steam Greenlight demo after being officially greenlit back in 2015, however shortly after that they deleted the build and there was no link to the original greenlight build. As a matter of fact after that to my knowledge, there was never another build released to the public about the game, and now the game has been sadly put on hold indefinitely - [http://reset-game.net/](http://reset-game.net/) - I've managed after weeks of searching, found a media fire link of the build that someone uploaded buried in the comments of the steam page (the comment was also deleted shortly after, but thankfully someone saved a snapshot via internet Wayback machine) and the media fire link is still active - [http://www.mediafire.com/file/ebx4y2ixa ... 4.exe/file](http://www.mediafire.com/file/ebx4y2ixaeopnxp/Reset_Greenlight_Demo_0.4.exe/file) - I've also made copies of the build and have it myself. So after finding that, and since the game doesn't seem to be coming to fruition after years of silence now I figured oh well, let's extract the data from the game itself as I did already and find out what kind of secrets are buried in it, and also having some fun with the content itself like fanart or whatnot 

So quick history out of the way, game data was stored in .dat files and I wrote an extractor for it. Managing to snag the DDS texture files (stored both as actual DDS, but also found them within a large collection of files but under a different extension or .bin for some reason), audio files stored via .bnk files, and have extracted them successfully, all shader files as well (can also decompile those shaders successfully), but the last step of the journey here is extracting the mesh files which I've been struggling to do so. So now leads to the main problem I've been having. For a bit of context yes I do have a lot of experience with game modding and writing tools, programming, reading hex files, and all of that jazz for various formats but I've kept mesh files out of my loop specifically because they are very complex. That's not to say I don't know what meshes are, I'm familiar with them on a basic level. I have experience with graphics programming, and I know what vertices, UVs, normals, and faces are but not the nitty-gritty technical details like how it's stored in memory or binary form, how it's laid out, or such like that. EDIT: Yes before some of you link it, I have in fact known and have read (and still reading) the information and the "tutorial" that is here - [viewtopic.php?t=17890](https://forum.xentax.com/viewtopic.php?t=17890) - however, I wouldn't be asking here for help if I'm struggling with reading this unknown format specifically.

[SKIP TO HERE TO READ MY PROBLEM] 
I've found the mesh files I was looking for (along with a few other simple ones for comparison) but the biggest issue is that these files appear to be headerless? which is a nightmare (There is some sort of header, but it's not a header I've seen common with mesh formats). There is no clear indication in the header as to what these kinds of file nor what kind of structure they hold, or the data that is in the header itself. (Exaggerating a bit, but its difficult nonetheless) I've been using 3D Model Researcher - [http://mr.game-viewer.org/](http://mr.game-viewer.org/) - to dig through an attempt to figure out the different aspects of a mesh file but struggle to get a good result out of it.

Through digging around and some other research I know the following clues.
1. Input files for meshes were in fact FBX files. That likely doesn't mean much but this is (or was) a very small indie studio and it doesn't make much sense to me if they spent their time building their own proprietary mesh format. My guess is that they share some resemblance with an FBX mesh file given that once again, the original mesh files were FBX. There are also numerous references in the executable of FBX and the Autodesk FBX SDK.
2. There are no explicit animation files upon extracting all of the assets (And yes I have double-checked and in fact, my extractor does in fact get everything stored in those .dat files). The animations themselves seem to be embedded in the FBX files (normal for FBX meshes, they have that ability) which gives me all the more reason to believe this format must be an FBX or share a similar structure to it.
3. This game was built and designed only for windows PC's to my knowledge, so the format is little-endian. Not big-endian
4. This game was designed and built on DirectX, I know that isn't much of a surprise nor much help but any clues help.
5. The first 4 bytes of the file appear to be an uint32 that holds the value 16 and that is consistent across the mesh files that I've been observing. This is likely either an indicator to the header length, or an indicator of the file type used by the engine.
6. The second set of 4 bytes after the first uint32 seems to increase in value with complex meshes. What I mean is that compared to simple meshes like test spheres and other simple meshes the value is 1, but for a complex mesh like the main robotic (geo suit is the name) mesh is 5 or 6 which leads me to believe this could be the number of mesh groups? or just objects that are in the file.
7. The third set of 4 bytes after the second uint32 appears to be a single float32 value. This is usually 1 across multiple files but specifically on large mesh files like terrain they are around 200 so this must be some kind of scale factor.
8. The fourth set of 4 bytes after that seem to be zero across all files. Not sure what it is but it could just potentially be byte padding.
9. Any strings serialized in the file are Wide strings. They are 16 bit (2 bytes) "characters", not like the traditional 8 bit (1 byte) "characters". They are also prefixed by a uint32.
10. The bytes from the offset (in decimal) 12 - 27 appear to always be zero or empty across the mesh files I have.
11. The uint32 starting at offset (in decimal) 28 in the file appears to also be a float value, the values also seem to also be similar to scale? No clue here.

Here is a zip of the mesh files from the game. (No malware I promise) (FIRST SET OF MODELS)
[https://www.mediafire.com/file/0q7sid41 ... s.zip/file](https://www.mediafire.com/file/0q7sid412013wcj/reset-mesh-files.zip/file)

EDIT: Here is another set of sample files from the game.
[https://www.mediafire.com/file/ykcdnuy7 ... t.zip/file](https://www.mediafire.com/file/ykcdnuy7iu46y0h/new-set.zip/file) (SECOND SET OF MODELS)

EDIT 2: Here is again another set of sample files from the game.
[https://www.mediafire.com/file/90o2m0kl ... 3.zip/file](https://www.mediafire.com/file/90o2m0klirw1ecj/new-set3.zip/file) (THIRD SET OF MODELS)

EDIT 3: For clarification, on the models specifically I'm looking to keep the following from the models of the game (some of it is obvious of course) is just the vertices, faces, normals, and UVs. If you can manage to figure out the rig then that is a bonus but I can rig it myself if it's impossible to snatch the rig. If you can also detail how in the model file(s) you were looking at where the data lies, how its ordered, and how big it is, and etc I can write a converter program to spit out an .obj and run that with the rest of the models in the game. I also have all of the game textures extracted. 

If you want you can also get in touch with me via discord. Discord ID - 249746780621766658 (David M#5343) But please, any help would be appreciated. If more information is needed I'll do my best to provide it.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-14T23:19:43+00:00
- Post Title: RESET Model Extraction Help

Big "wall of text", so I didn't read anything (except the link to the samples , sry ) and don't know how far you got.
Just a test, not sure, whether it's correct (maybe face culling required or different FVFsize, dunno):
.



puzzle_cyl.png (34.55 KiB) Viewed 275 times
## Post #3
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2021-11-15T01:21:18+00:00
- Post Title: RESET Model Extraction Help

Yep that is about as close as I have gotten although you managed the face indices, I managed only the vertices though I see you're probably missing some? Probably just the face incidies being incorrect. If you have any more info or such let me know, and also if anyone else wants to give this a stab too.

Also, please at least read lol the "important" section since I stuffed some info on there that I think would help with going through the format you or anyway have prior knowledge.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-15T07:46:18+00:00
- Post Title: RESET Model Extraction Help

> Reply from frostbone25 ↑Mon Nov 15, 2021 9:21 am at Mon Nov 15, 2021 9:21 am
>
> 
Also, please at least read lol the "important" section since I stuffed some info on there that I think would help with going through the format you or anyway have prior knowledge.Well, really, no.   Why show a "format as text description"  , not as a picture?

As an example see first picture here:

> Reply from Bigchillghost ↑Sat Oct 30, 2021 2:06 pm at Sat Oct 30, 2021 2:06 pm
>
> 
or here:

> Reply from shakotay2 ↑Fri Jun 18, 2021 7:44 pm at Fri Jun 18, 2021 7:44 pm
>
> 

btw: sorry, when appearing to be annoying, but I've too much text to read in RL atm, suffering from "brain overflow" 

well, there must be some trick with the face indices, trying strips I got an error, these are my nearest hits so far (ugly):
.



car_flight_.png (108.26 KiB) Viewed 236 times
## Post #5
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2021-11-15T19:42:31+00:00
- Post Title: RESET Model Extraction Help

Sorry, didn't know you read too much text IRL 

But yeah you're getting some decent results, again those face indices are trouble. I wish I could help but you seem to be getting better results than I've been able to manage and much faster, though I'm trying! I'll post my efforts here when manage to get something decent. I think it's worth mentioning also that getting the UV maps after the main vertices, normals, and faces would be nice. Bonus points ideally if somehow we can figure out the rig and animation that is in the model as well but I doubt it.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-16T09:13:34+00:00
- Post Title: RESET Model Extraction Help

It might help if you uploaded another .bin sample, sized > 270 kB, but smaller than 1 MB, if possible.
## Post #7
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2021-11-16T18:18:23+00:00
- Post Title: RESET Model Extraction Help

> Reply from shakotay2 ↑Tue Nov 16, 2021 5:13 pm at Tue Nov 16, 2021 5:13 pm
>
> 
It might help if you uploaded another .bin sample, sized > 270 kB, but smaller than 1 MB, if possible.
[https://www.mediafire.com/file/ykcdnuy7 ... t.zip/file](https://www.mediafire.com/file/ykcdnuy7iu46y0h/new-set.zip/file)
Here's another set of samples, there aren't that many test files (but a lot of main mesh files of course) so I couldn't really find much of anything that small. It's a bit difficult to track most down since all file names are hashed and the only way to find the correct name is to go through an .asset file and get the corresponding hash, and likely that is also the name of the mesh file.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-16T20:43:12+00:00
- Post Title: RESET Model Extraction Help

Thanks!   Nice point cloud of a howling wolf, btw. But, the face indices don't make sense to me, again. Especially the doubles - I don't see an easy rule how to skip them:
.



FIs_wolf_statue.png (50.77 KiB) Viewed 192 times



(There's also those a+1, a, a+1 sequences with a= 0x2BE, or 0x557 or other.)
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-17T10:02:36+00:00
- Post Title: RESET Model Extraction Help

Just arrays of per-polygon vertices and face normals.



geo_suit_05.png (104.43 KiB) Viewed 178 times



There's also an edge vertices block followed. No sign of UVs unfortunately.
## Post #10
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2021-11-18T18:54:19+00:00
- Post Title: RESET Model Extraction Help

Hmmm, interesting that the model is in that pose given that a screenshot of the model in that exact pose was posted in 2015 - [http://reset-game.net/?attachment_id=726](http://reset-game.net/?attachment_id=726) - I figured it would be either in an A or T pose. I suppose I'll start digging for the other variants of the GeoSuit model.

Nice to see how far you got, I'll send a 3rd set of mesh files of complex and large meshes and see if you can work your magic on those. Those obviously should contain some more data, possibly UVs if for whatever reason it doesn't have them (it should, would be surprised if there are models stored here with no UVs or if the UVs are stored elsewhere but that seems very unlikely. Stupid geuss but who knows.)
## Post #11
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2021-11-18T19:58:25+00:00
- Post Title: RESET Model Extraction Help

Welp, turns out the most complex and bigget mesh files in the game just happened to be the main GeoSuit model itself. The rest are simpler and are landscape or cityscape-oriented. Suppose I spoiled you guys with the biggest files from the game lol but oh well, I did try to find the next biggest and complex ones, closest to that were some vegetation models. I threw in some more simple models as well just so there is a wider variety - [https://www.mediafire.com/file/90o2m0kl ... 3.zip/file](https://www.mediafire.com/file/90o2m0klirw1ecj/new-set3.zip/file)

Meanwhile, I'm gonna try taking another stab now at getting a model from the file seeing that you guys are starting to get something more. If you have some details also on some of the files where data lies, etc, and the sort of basic structure you got figured out on it also that would be helpful.
## Post #12
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-19T15:17:04+00:00
- Post Title: RESET Model Extraction Help

> Reply from frostbone25 ↑Fri Nov 19, 2021 2:54 am at Fri Nov 19, 2021 2:54 am
>
> 
I figured it would be either in an A or T pose.
Coz it's just a static model. Meshes from geo_suit_animated.bin:



geo_suit_animated.png (191.26 KiB) Viewed 119 times



> Reply from frostbone25 ↑Fri Nov 19, 2021 2:54 am at Fri Nov 19, 2021 2:54 am
>
> 
Those obviously should contain some more data, possibly UVs if for whatever reason it doesn't have them
Nope, still no sign of UVs and every file I've checked share the same vertex layout. You might check the textures to confirm whether they have actual UVs or were using just view projections.
## Post #13
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2021-11-19T16:23:26+00:00
- Post Title: RESET Model Extraction Help

Damn, I suppose I'll try digging around for the UVs potentially being stored in a different .bin file. That just seems very odd to me, now I gotta write another app that basically unhashes all of the bin file names so I can see what I actually have... Oh well, that is modding after all. Anyways also I noticed you seem to be using Mesh Reaper, mind sharing some of the settings you're using from it whenever you can?

I've also checked the textures and they indeed seem to be having a UV-like layout rather than a projection like you described. I'll post a sample here later, and also I'll do some additional searching with the bin files and organize it to find out if in fact they are stored separately, and I'll double-check the DDS also in case there was additional data slapped onto it either at the top or bottom of the file (Didn't seem like it when I initially did extract them but doesn't hurt to double-check). If I find anything that might help I'll be sure to update you lads on it.
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-20T06:33:55+00:00
- Post Title: RESET Model Extraction Help

> Reply from frostbone25 ↑Sat Nov 20, 2021 12:23 am at Sat Nov 20, 2021 12:23 am
>
> Anyways also I noticed you seem to be using Mesh Reaper, mind sharing some of the settings you're using from it whenever you can?
AXE is not up to the task for handling such format elegantly, coz there's face normal inserted after every 3 vertex positions. Though you can use the Parameter Set workaround to piece together the triangles one at a time, but that's only useful for validation. So I just dumped the positions into a whole block and duplicated each face normal by 3 times as another, then used the normal workflow in AXE to construct the model as shown in that post.

Here's the overall layout for the format:

```
long    meshCount
for i = 0 < meshCount
{
    byte    skip[0x40]
    long    faceCount
    for j = 0 < faceCount
    {
        for k = 0 < 3
            float    position[3]
        float    faceNormal[3]
    }
    long    edgeCount
    for j = 0 < edgeCount
    {
        for k = 0 < 2
            float    position[3]
        for k = 0 < 2
            long    faceID // IDs of the faces the edge belongs to, -1 for placeholder
    }
    float    skip
}

```


And here's a simple Obj convertor for the format. Double click the exe to see the usage.


 ResetBin2Obj.zip
(5.36 KiB) Downloaded 15 times
## Post #15
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2021-11-20T07:23:57+00:00
- Post Title: RESET Model Extraction Help

Oh wow, thanks dude, I was just going to write the converter myself based on what you guys could figure but you went the extra mile writing a simple app! I'll definitely use it as a base when I write my personal one, thanks again.

I'm still also currently still writing the de-hasher app, when it's done of course once again I'll provide info here about it if I finally find out clues as to where those UVs lie (or if they really don't exist).
## Post #16
- Username: frostbone25
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 24, 2020 11:49 pm
- Post datetime: 2021-11-23T17:44:47+00:00
- Post Title: Re: RESET Model Extraction Help

Big wall of text warning, but just an update.

I didn't finish the hash converter app but after really intensive research I discovered basically that the current files that exist within the game, that being these .asset and .asset.user files which are human-readable, don't contain all of the corresponding hashes of the hashed files that exist within the game. To give a bit of context these .asset.user files are sorta like prefabs or materials, they seem multi-purpose in a way but most of these are meshes or materials, and a .asset.user file contains the hashes to the corresponding input files that the .asset uses (the .asset also shows in the "input" fields the original file name for the file). For reference also the hashing algorithm they use is SHA-1.

However, given that there are over 22814 hashed files in the game. Sadly there are only like a 1000 of these files that can be de-hashed through going through those .asset.user files. There aren't enough of those .asset.user files with their usually numerous instances of hashes that could cover 22814 files. I didn't want to stop there and tried to identify the majority of what these files were and after discovering that I sorta narrowed down about what half of the files actually are, but half are still unidentifiable. 

This is a console output of the quick app I wrote to identify what was in the file (the rest of the files were unidentifiable, and some did have a clear header but I couldn't even track down what these could possibly be)

782 / 22814 - DDS Files
25 / 22814 - "  xD" files
310 / 22814 - Mesh Files
14577 / 22814 - PhysX NXS Files
789 / 14577 - PhysX Mesh Files
13788 / 14577 - PhysX Convex Mesh Files
14577 / 14577  - PhysX Total Files Found (Found all PhysX NXS files)
15694 / 22814 - Total Files Found

So about 68% of the files could be identified. DDS are obviously texture files. "  xD" files I'm not sure but they did share that 4 byte ASCII across the headers. 310 Mesh files I identified thanks to your code @Bigchillghost . A majority of the files I found were PhysX related, which makes sense as PhysX was utilized heavily in this game, so lots of traditional PhysX collision mesh files. The rest like I said have unidentifiable headers and contents and given also that they are hashed, and have no extension other than .bin that makes it really difficult to even figure out what the rest could be. Extracting the strings from the exe itself also doesn't help too much sadly. I would share a lot more here but this is now getting a bit off-topic of the 3D model extraction help. 

Again lol the goal here was to basically find if the UV's were stored separately for whatever reason but there won't be a way for me to identify them, unfortunately. With also the intensive research I confirmed the fact that they did have UV sets when building the 3D content in this blog post - [http://reset-game.net/?p=169](http://reset-game.net/?p=169) - They had 2 UV sets as a matter of fact. The first set was the main base material and often this was just a tiling texture and the second set was a dirt/moss mask for the object. Given their "limited" resources as an indie studio they did in fact go the mostly procedural route but they still had to paint per object textures, that being the dirt/moss masks. While also making the base material UVs tileable and seamless. There are also of course some textures that are related to the main GeoSuit model that are in fact layed out in some kind of UV configuration, just to note that they didn't fully commit to that full procedural texturing route for some of their "specialized" models.

So yeah, sadly I think the road stops there. I did de-hash 98% of all of the mesh files to their corresponding name by hand (there were only just 310) and extracted the majority of the 310 mesh files with a quick batch script using your app. I've zipped up and uploaded these models here - [https://www.mediafire.com/file/w1dlgqjf ... j.zip/file](https://www.mediafire.com/file/w1dlgqjf9ilvh9y/obj.zip/file) - But yep, like I said the road sorta ends there, you helped achieve the goal I had of just needing to extract the meshes as I already extracted the music/sound, textures, and shaders from the game.
