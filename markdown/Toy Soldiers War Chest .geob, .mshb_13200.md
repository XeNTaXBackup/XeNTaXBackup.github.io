## Post #1
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2015-08-15T00:40:03+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

hey gang,

 I bought Toy Soldiers War Chest and it's Lendary Hero's DLC. I searched the forums and found past games format can be opened with a quickbms script. But that was for the older games format and not this one.

 the two formats I've found in the model folder of my steamapps common folder for toy soldiers are:
 .geob 
 .mshb 

 if I provide some file samples can you guys help me open them and extract the models? 

 Lastly I need to convert the texture files over since that's where it seems the main detail is. but the file are .pngb format. would doing something low tech as just renaming them as a ".png" make them work as an openable graphic file?

 thank you in advance for any help you may lend me.
## Post #2
- Username: JesseV92
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 09, 2015 6:21 am
- Post datetime: 2015-08-15T07:33:40+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

I would also like to know any progress that is made on reverse engineering the file types, so you're not alone.

The file types I saw are .nutb and .sigb and I haven't found anything on these file types across the Internet, so I have no idea how to open them.

Edit:

I found a .json file that lists what I assume are all the file types used by SigEngine to run TS:WC 

File name is "built-file-versions.json" located in ToySoldiersWarChest/Game/

```
{
"*.bikb":1,
"*.tgab":5,
"*.bmpb":1,
"*.sigb":6,
"*.geob":4,
"*.mshb":5,
"*.derb":22,
"*.tabb":11,
"*.mtlb":6,
"*.fxb":4,
"*.texb":2,
"*.anib":2,
"*.animapb":2,
"*.momapb":2,
"*.nutb":2,
"*.*":1,
"*.sacb":2,
"*.fntb":1,
"*.locb":1,
"*.sklb":1,
"*.xmlb":1,
"*.swfb":3,
"*.matb":5
}}

```


Edit:

The file formats for the videos are typed out as .bk2b, but if you rename them to .bk2 the RAD video tools can play them, so that's how you open the videos.

Edit: 

I tried doing the same to the .pngb and .tgab files but those didn't work so something else has to be done to those.
## Post #3
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2015-08-16T10:22:12+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

I am thankful to not be alone in wanting to look through these models. mine at first seemed to be .sigb files but when I looked at the directory again and looked in the individual units it came up as .geob and .mshb

 I'll post sample files for the forum here later on and hopefully that will help people crack them a little bit there has to be a solution here as the forums have taught me I am just not good enough to know how to crack these open at this present time.

 at any rate I thank you for this post as it's a starting point at the very least. I have the game on my gaming laptop or I'd do things now. 30 full bucks with the legendary heros dlc since I wanted all the characters I could get for this.

 back in a while with some of the files.
## Post #4
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-08-16T14:50:31+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

I want to see how this plays out as well, since they do have some sweet looking models =)

Anyways, I'll have a copy and I'll see what comes up

As previously stated, all files and with a B, like in XNA resource files, (fxb etc) so first thing is indeed I will try to get that be away from the extension and see what comes up.
Also, this might inply a binary representation, so maybe convert it to someting less binary ?

T.
## Post #5
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-08-16T17:23:01+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

So I took a simple file with the .geob extension and looked at it using 010 Editor and found the following:

files I investigated is cube.0.geob

which I was expecting a cube   

so at offset 302 in that file, you will find the nbr of Vertices => 24 in my case

3 floats for position of vertex, 3 float for I dono and FF FF FF FF to end with

then a set of 24 / 2 tris stocked as shorts

here is a quick max script to build that:

Uv's are under investigation

```
file = @"D:\Games\Toy Soldiers War Chest\Game\_tools\sigfx\cube.0.geob"

stream = fopen file "rb"

fseek stream 304 #seek_set

vertices = #()
uvws = #()
faces = #()


for i= 1 to 24 do
(
    x = readfloat stream
    y = readfloat stream
    z = readfloat stream

    u = readfloat stream
    v = readfloat stream

    unk1 = readfloat stream
    unk2 = readfloat stream

    append vertices [x,y,z]
    append uvws [u,v,1.0]

)

for i=1 to 24/2 do
(
    print i
    a = readshort stream
    b = readshort stream
    c = readshort stream

    append faces [a + 1, b + 1, c + 1]
)
theMesh = mesh name:"test" vertices:vertices faces:faces tverts:uvws
theMesh.WireColor = Color (random 0 128) (random 0 255) (random 0 128)

buildTVFaces theMesh false
for i = 1 to faces.count do
( setTVFace theMesh i faces[i] )

 update theMesh


fclose file

```
## Post #6
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-08-16T18:30:46+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

Found that the offset of the start of these vertices positions is found at position 96

So the amount of vertices is found on offset -2 ( position 94) and is stored as a Short ( UInt16)

The file helix.0.geob gives me this as a result:



T.
[helixexample.PNG](https://xentaxbackup.github.io/file/9543_helixexample.PNG)
## Post #7
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2015-08-18T16:44:01+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

> Reply from TaylorMouse
>
> So I took a simple file with the .geob extension and looked at it using 010 Editor and found the following:

files I investigated is cube.0.geob

which I was expecting a cube   

so at offset 302 in that file, you will find the nbr of Vertices => 24 in my case

3 floats for position of vertex, 3 float for I dono and FF FF FF FF to end with

then a set of 24 / 2 tris stocked as shorts

here is a quick max script to build that:

Uv's are under investigation
Code: Select all
file = @"D:\Games\Toy Soldiers War Chest\Game\_tools\sigfx\cube.0.geob"

stream = fopen file "rb"

fseek stream 304 #seek_set

vertices = #()
uvws = #()
faces = #()


for i= 1 to 24 do
(
    x = readfloat stream
    y = readfloat stream
    z = readfloat stream

    u = readfloat stream
    v = readfloat stream

    unk1 = readfloat stream
    unk2 = readfloat stream

    append vertices [x,y,z]
    append uvws [u,v,1.0]

)

for i=1 to 24/2 do
(
    print i
    a = readshort stream
    b = readshort stream
    c = readshort stream

    append faces [a + 1, b + 1, c + 1]
)
theMesh = mesh name:"test" vertices:vertices faces:faces tverts:uvws
theMesh.WireColor = Color (random 0 128) (random 0 255) (random 0 128)

buildTVFaces theMesh false
for i = 1 to faces.count do
( setTVFace theMesh i faces[i] )

 update theMesh


fclose file

 how do I add this script to 3d max and which version does it work with?  I read both your posts and this is amazing detective work and sorting I am honestly impressed.
## Post #8
- Username: JesseV92
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 09, 2015 6:21 am
- Post datetime: 2015-08-18T23:44:32+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

> Reply from TaylorMouse
>
> Words

I understand what some of those words mean individually, but I have no idea what they mean in this context.

I just want to get the GIJoe models, but Ninja Ripper is blocked by UPlay so I had to ask here.

I tried running the script and pointing it at another file and it gave an error:



I'm not a programmer so I have no idea what this error means.
## Post #9
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2015-08-19T20:43:38+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

> Reply from JesseV92
>
> TaylorMouse wrote:Words

I understand what some of those words mean individually, but I have no idea what they mean in this context.

I just want to get the GIJoe models, but Ninja Ripper is blocked by UPlay so I had to ask here.

I tried running the script and pointing it at another file and it gave an error:



I'm not a programmer so I have no idea what this error means.

 I figured that UPLAY would block any recording program. that's why I have been hoping for either a file extractor,a 3d max (or other program) importer or both.  I enjoy the game well enough but I hope to use the models as refs to remake them for things like GTA.   either way I am a patient man. I haven't grabbed my sample file for the board but so far I am happy with the pace of progress. 

 but what do I do with the script text in max how do I make it a script I can use? and what version of max is it designed for or it fairly universal?
## Post #10
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-08-19T22:56:53+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

I stopped looking at this for the moment, since I played the game a little at my brothers', I finally decided not to buy it cause when I got to level 2 or 3, I had to shoot down unicorns and flying barbies, not really my style.

Anyways, the animated models are actually not in the same patern as I thought, and while I did get a more complex model in max,I saw that nearly each model i had to change something to make that model work :/

T.
## Post #11
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2015-08-23T03:56:07+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

> Reply from TaylorMouse
>
> I stopped looking at this for the moment, since I played the game a little at my brothers', I finally decided not to buy it cause when I got to level 2 or 3, I had to shoot down unicorns and flying barbies, not really my style.

Anyways, the animated models are actually not in the same patern as I thought, and while I did get a more complex model in max,I saw that nearly each model i had to change something to make that model work :/

T.

 I'd be willing to continue the work if you might counsel me, if even in private on what to look for and how to figure out the changes for the models so I can do it myself.   I can get why you might not like the game as a whole and I respect that. but I do own the game and it's not just for the gameplay that I hope to use this game. at any rate I thank you for taking this as far as you felt you want to. I hope we can work so that I can continue the work myself and help others should this game come up again.
## Post #12
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2015-12-08T01:17:49+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

sorry to bump but I grabbed one characters model files and am posting them,as promised, in the hopes that maybe someone can figure out or make a plugin that can open this file in 3d studio max or some equivilent modeling program. thank you all for your time.

[http://www.mediafire.com/download/lebxa ... pack.0.zip](http://www.mediafire.com/download/lebxaq60eantog3/cobra_infantry_bat_pack.0.zip)
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-12-08T02:03:53+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

First submesh of cobra_infantry_bat.0.geob


h2o file for first submesh

```
Vb1
40 28
0x820 922
020100
0x0 255

```


the vertex and face blocks are lumped together, you must find the start and length of each submesh.
You can search for 00 00 01 00 02 to find the start of each face group, there should be 11 submeshes in that file
## Post #14
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2015-12-08T04:26:06+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

you've given me a great starting point. I grabbed a copy of h2o and will start on my own work with it using this. but I am also willing to post more of the models if others want to see what they can do with more then just the one model.

 at any rate I thank you so much for the help so far an will see what I can do now that I have this direction to take my reseach into.  you rock.
## Post #15
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2015-12-08T21:40:48+00:00
- Post Title: Toy Soldiers War Chest .geob, .mshb

I reuploaded the bat with it' textures then pulled out on of the vehicles with textures as well since part of this thread is figuring out how the texture files work and how to open then for study.

[http://www.mediafire.com/download/vya2k ... xtures.zip](http://www.mediafire.com/download/vya2ktnhp29x78b/cobra_infantry_bat__plus_textures.zip)

[http://www.mediafire.com/download/d0w5k ... xtures.zip](http://www.mediafire.com/download/d0w5kc319dp51v5/cobra_rattler_pose__with_textures.zip)

 also a good tutorial on hex editing would be appreciated. I started to poke around in h2o and relized,after reading it's tutorial,that i have no idea what I am doing right now.

 worse case..rules willing... I'd be willing to pay people to help translate these models for study and personal use.  but again if that's against the rules then I resend the last part.  thank you all so much for the help so far at least I know it's possible to access the models but you need a bit more technical knowledge then I currently possess.
## Post #16
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-12-09T02:41:50+00:00
- Post Title: Re: Toy Soldiers War Chest .geob, .mshb

TextureFinder reads the diffuse pngb textures that i tried as dxt1 with mipmaps and normalmap textures as dxt5 , they are just dds with a custom header.
It looks like the width and height are stored around 0x72 - 0x75 in the custom header.
You can look at the file sizes to get a hint to the image size too.
682kb - 1024x1024
170kb - 512x512



The main thing in the H2O tutorial that stuck with me after reading it the first time was this - 
"The face indices are very easy to find since parts of the indices block look like a scrambled alphabet."

using Hex2obj isn't so much about hex editing as it is about pattern recognition, 
which is why it is perfect for someone like me with no programming experience. 

If you find the pattern then you can see where it starts and you have your addresses.
The rest is just flipping switches until you see numbers or previews that make sense.
To find the vertex patterns in a hex editor i usually adjust the right side column width until the data starts to line up
vertically and you see bytes repeat up and down, this width in bytes would be your FVF size.


I still think the best game format to learn Hex2obj with is the ibuf and vbuf files from Disney Infinity.
Those 2 files contain the types of data you would normally look for in most singular model files.
the ibuf has your face indices and the vbuf has your vertex information like FVF and UV pos values.
There is usually never more than napkin math involved in the whole process.

SWTOR gr2 model files are another easy game format you could practice using Hex2obj with.
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-03-27T00:37:58+00:00
- Post Title: Re: Toy Soldiers War Chest .geob, .mshb

> Reply from octaviousrex
>
> I reuploaded the bat with it' textures then pulled out on of the vehicles with textures as well since part of this thread is figuring out how the texture files work and how to open then for study.

http://www.mediafire.com/download/vya2k ... xtures.zip

http://www.mediafire.com/download/d0w5k ... xtures.zip
I made a Noesis plugin to open those pngb textures you uploaded  


 fmt_TSWC_pngb.zip
(859 Bytes) Downloaded 54 times


it supports diffuse and normalmap textures, the specular textures are garbage so don't even bother with those.
## Post #18
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2016-04-13T01:29:56+00:00
- Post Title: Re: Toy Soldiers War Chest .geob, .mshb

> Reply from AceWell
>
> octaviousrex wrote:I reuploaded the bat with it' textures then pulled out on of the vehicles with textures as well since part of this thread is figuring out how the texture files work and how to open then for study.

http://www.mediafire.com/download/vya2k ... xtures.zip

http://www.mediafire.com/download/d0w5k ... xtures.zip
I made a Noesis plugin to open those pngb textures you uploaded  
fmt_TSWC_pngb.zip
it supports diffuse and normalmap textures, the specular textures are garbage so don't even bother with those.

 this is so awesome thank you so much for all the help I greatly appreciate it.
## Post #19
- Username: vertigoink
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 17, 2016 5:34 am
- Post datetime: 2016-07-19T22:05:37+00:00
- Post Title: Re: Toy Soldiers War Chest .geob, .mshb

I'd just really like the Dragon Walker and Blaster Hawk He-Man models to 3d print- I'd totally be willing to throw some donations at anyone who could oblige.
