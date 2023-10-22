## Post #1
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2012-06-15T10:07:00+00:00
- Post Title: Model Parsing help needed

Hi I'm using Chroxx's notes (see below) to preview the model in Noesis, however I've been having some problems.

> Reply from chrrox
>
> here is the layout of the bsc files.
meshCount  - byte
unkCount    - byte
Null             -byte
then you read 12 bytes of data * the unkCount +1
so if the number is 1 you read 24 bytes if it is 2 you read 36 bytes
Then you end up at your mesh pieces
for each mesh piece you read
boneName - string
then skip from the start of the bone name 0x42 bytes
then read 2 longs
vertCount - Long
faceCount - long

then you read the mesh data
vert Structure 0x2C
00 - 0C Vertex positions as floats
0C - 18 normals as floats
18 - 1C Vertex Color as bytes
1C - 24 UV's as floats
24 - 2C Null and not used

then read the faces as normal triangle lists. unsigned shorts

that is it just repeat this for the mesh count and your done.

there should be a global skeleton file somewhere that the mesh pieces attach to.

In some models, the third byte (from the start of the file) is not 0. When it isn't then the first bone name does not follow the format that Chrrox/finale posted. If it has 1 then I have to skip the first bone Name and go to the second one, and if its 2 I have to skip the first two bone names and go to the third one. This allows me to read the models.
However, when the third byte is greater than 0 what does the data prior to the actual mesh data contain? Since if I were to write an exporter for this, I would need to know what each data is what. Funny thing is, when I set the third byte to 0 and removed the extra data (via hex editor) that appear before the actual mesh data, and the model loaded fine in game just how it loaded originally. I did not notice any difference between the original and the modified one.

Also, I've noticed the "unkCount" thing that Chrrox posted doesn't really validate on all models.
In fact, the second byte (the one you referred to as unkCount) is actually the number of textures it should load.
1 = .ba0
2 = .bb0 (including .ba0 will be loaded)
3 = .bc0 (.bb0, and .ba0 will be loaded)
4 = .bd0
and so forth

I could manage to figure out how the offset of the first boneName is located, so I am manually scanning for whether the name begins with Bo or bo and then break and -2 the seek to obtain the Bone name. It's quite reliable and works on all models I've tested on so far. I'm quite sure it's possible to calculate the first position, and rather would prefer this method. But I cannot seem to figure out how this is done.


I'm unsure on how to attach the current models to the skeleton file so I'll attach the models and the skeleton.

Here is the model files: [http://www.mediafire.com/?dpuup6j651g3d63](http://www.mediafire.com/?dpuup6j651g3d63)
And here's the skeleton: [http://www.mediafire.com/?dy9vyydbxq754sj](http://www.mediafire.com/?dy9vyydbxq754sj)

gr_010_arm/body are the files that does not have 0 in the third byte of the file [unsure of what the third byte does?].

gr_030_arm loads but does not appear correct. (needs to be mapped to the skeleton, have no clue on how to do)

It looks like this using the data provided by Chrrox/Finale:

When really it should look like this (ignore the shoulder part and shield):


I have also noted when a model is loaded the angel of the model is in a different angel, I am unable to get it to load in a correct angel like how finale000 did. Mind sharing how that was done?

Here's how it looks for me:
## Post #2
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2012-06-15T10:34:38+00:00
- Post Title: Model Parsing help needed

please can any one help me

if i offered money  do any one will help me
## Post #3
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-06-15T10:49:34+00:00
- Post Title: Model Parsing help needed

Why is it you need the models so bad you are willing to pay for it? You could try to learn to do it yourself.
There are tutorials for Noesis : for basic model importing : [viewtopic.php?f=29&t=7760](http://forum.xentax.com/viewtopic.php?f=29&t=7760)
Do some research about models and what they contain, read in these forums and look at examples. Finale00 has a lot of Noesis scripts that import models in this section, so does Chrrox.

And game resource sharing is a nono, moderators delete your posts if they contain links to resources, so if you want your post to stay you might want to edit out your link [viewtopic.php?p=73429#p73429](http://forum.xentax.com/viewtopic.php?p=73429#p73429).
## Post #4
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2012-06-15T10:52:28+00:00
- Post Title: Model Parsing help needed

cuz iam stupied in this stuff

i can modeling and desgining 

but i don't understand Scripts


but i'll try
## Post #5
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-06-15T10:56:08+00:00
- Post Title: Model Parsing help needed

It was the same for me and I still feel stupid when it comes to models, but I figured trying to do something myself and ask for help on that would gain me more then waiting for someone to take interest in my topic.
## Post #6
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2012-06-15T10:58:28+00:00
- Post Title: Model Parsing help needed

i don't want to be pro about this stuff

i just want to extract .Bsc files and inject them again


thats all
## Post #7
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2012-06-15T10:59:22+00:00
- Post Title: Model Parsing help needed

can u give me a link for the program that called "Noesis"
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-15T12:56:21+00:00
- Post Title: Model Parsing help needed

the textures are plain jpeg files just rename them to .jpg.
## Post #9
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2012-06-15T13:01:05+00:00
- Post Title: Model Parsing help needed

> Reply from chrrox
>
> the textures are plain jpeg files just rename them to .jpg.

ba0 . . etc  they textures i know

but the .bsc  for 3d model for the items

obj for the maps

i want to unpack them or use them in 3d prgorams

do you think i can find a programmer to create an unpacker/injector  for this  .Bsc  Obj Files

.Bsc,.obj  is a 3d models

thanks for replaying ^^
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-15T14:38:32+00:00
- Post Title: Model Parsing help needed

here is the layout of the bsc files.
meshCount  - byte
unkCount    - byte
Null             -byte
then you read 12 bytes of data * the unkCount +1
so if the number is 1 you read 24 bytes if it is 2 you read 36 bytes
Then you end up at your mesh pieces
for each mesh piece you read
boneName - string
then skip from the start of the bone name 0x42 bytes
then read 2 longs
vertCount - Long
faceCount - long

then you read the mesh data
vert Structure 0x2C
00 - 0C Vertex positions as floats
0C - 18 normals as floats
18 - 1C Vertex Color as bytes
1C - 24 UV's as floats
24 - 2C Null and not used

then read the faces as normal triangle lists. unsigned shorts

that is it just repeat this for the mesh count and your done.

there should be a global skeleton file somewhere that the mesh pieces attach to.
## Post #11
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2012-07-05T17:22:21+00:00
- Post Title: Model Parsing help needed

tried

it's hard to me

thats why i came to here
## Post #12
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2012-07-05T17:31:23+00:00
- Post Title: Model Parsing help needed

here example some one have the bsc model converter [ The only one ]
[http://www.youtube.com/watch?feature=pl ... jTXr9tEKSw](http://www.youtube.com/watch?feature=player_embedded&v=jjTXr9tEKSw)

thats what i mean
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-05T18:34:37+00:00
- Post Title: Model Parsing help needed

Chrrox just gave you the format outline. You just need to translate it to code.

I don't know what you mean by "don't want to be pro" it's not like you're going to be working for any gaming company. It's just a basic application of programming ability. And being a programmer doesn't make you a pro.

Anyways send me some models and I'll write a noesis plugin. Maybe.
## Post #14
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2012-07-05T18:58:02+00:00
- Post Title: Model Parsing help needed

> Reply from finale00
>
> Chrrox just gave you the format outline. You just need to translate it to code.

I don't know what you mean by "don't want to be pro" it's not like you're going to be working for any gaming company. It's just a basic application of programming ability. And being a programmer doesn't make you a pro.

Anyways send me some models and I'll write a noesis plugin. Maybe.

here

[http://www.mediafire.com/?60vbb9nhnk5ttth](http://www.mediafire.com/?60vbb9nhnk5ttth)

about "don't want to be pro"

i tried to do something in noesis program

but didn't work   

i can 3d modelling web hosting  , servers , designing . . .

but programing i leave it to the Professionals
## Post #15
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-05T19:15:42+00:00
- Post Title: Model Parsing help needed

Show us what you did in Noesis/Python.
Maybe it's just a few changes to what you already cooked up based on Chroxx's information.
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-05T21:06:53+00:00
- Post Title: Re: Bots / Models (.Bsc - .obj)

Didn't bother with the bone name

Outline is pretty much the same, except there's 24 bytes in the mesh struct after the vert and index counts.

```
   66 bytes
   int32 numVerts
   int32 numIdx
   24 bytes
   numVerts Vertex
   numIdx indices
}

```
## Post #17
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2012-10-27T04:34:15+00:00
- Post Title: Re: Bots / Models (.Bsc - .obj)

> Reply from finale00
>
> Didn't bother with the bone name

Outline is pretty much the same, except there's 24 bytes in the mesh struct after the vert and index counts.
Code: Select allStruct Mesh {
   66 bytes
   int32 numVerts
   int32 numIdx
   24 bytes
   numVerts Vertex
   numIdx indices
}

ommmg how did you do you that

i will do any thing anything for you 

just tell me how you did it

Free Kiss For You

nah  Millions Kisses

i will download  the program now and such of a noob

i don't won't to be pro  nah  i only want to get the modul of BSC Files
## Post #18
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2012-10-27T05:52:19+00:00
- Post Title: Re: Bots / Models (.Bsc - .obj)

here iam , , and i don't know what to do ^^

final00 you are the best . . every one is Creditz you in combat arms tuts for getting map moduls

you helped many people and i hope you help me in this too

sorry for being stupid 

if you busy just give me a some topic links and i'll read it to learn any thing about using Neosis
## Post #19
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-06-17T22:57:35+00:00
- Post Title: Re: Bots / Models (.Bsc - .obj)

can't any one help me
## Post #20
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-06-20T20:12:22+00:00
- Post Title: Re: Bots / Models (.Bsc - .obj)

what's the problem here ?
i do like the basic topbic


```

made-up format

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format 

modules!
def registerNoesisTypes():
   handle = noesis.register("Bots", ".bsc")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't 

leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = "GXXM0124"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 16:
      return 0
   if bs.readBytes(16).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   rapi.rpgClearBufferBinds()   
   return 1
```
## Post #21
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-20T22:44:49+00:00
- Post Title: Re: Bots / Models (.Bsc - .obj)

you set the id string to 8 bytes then you read 16 bytes to check the header.
## Post #22
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-06-27T01:40:07+00:00
- Post Title: Re: Bots / Models (.Bsc - .obj)

In some models, the third byte (from the start of the file) is not 0. When it isn't then the first bone name does not follow the format that Chrrox/finale posted. If it has 1 then I have to skip the first bone Name and go to the second one, and if its 2 I have to skip the first two bone names and go to the third one. This allows me to read the models.
However, when the third byte is greater than 0 what does the data prior to the actual mesh data contain? Since if I were to write an exporter for this, I would need to know what each data is what.  Funny thing is, when I set the third byte to 0 and removed the extra data (via hex editor) that appear before the actual mesh data, and the model loaded fine in game just how it loaded originally. I did not notice any difference between the original and the modified one.


Also, I've noticed the "unkCount" thing that Chrrox posted doesn't really validate on all models.
In fact, the second byte (the one you referred to as unkCount) is actually the number of textures it should load.
1 = .ba0
2 = .bb0 (including .ba0 will be loaded)
3 = .bc0 (.bb0, and .ba0 will be loaded)
4 = .bd0
and so forth

I could manage to figure out how the offset of the first boneName is located, so I am manually scanning for whether the name begins with Bo or bo and then break and -2 the seek to obtain the Bone name. It's quite reliable and works on all models I've tested on so far. I'm quite sure it's possible to calculate the first position, and rather would prefer this method. But I cannot seem to figure out how this is done.


I'm unsure on how to attach the current models to the skeleton file so I'll attach the models and the skeleton.

Here is the model files: [http://www.mediafire.com/?dpuup6j651g3d63](http://www.mediafire.com/?dpuup6j651g3d63)
And here's the skeleton: [http://www.mediafire.com/?dy9vyydbxq754sj](http://www.mediafire.com/?dy9vyydbxq754sj)

gr_010_arm/body are the files that does not have 0 in the third byte of the file [unsure of what the third byte does?].

gr_030_arm loads but does not appear correct. (needs to be mapped to the skeleton, have no clue on how to do)

It looks like this using the data provided by Chrrox/Finale:

When really it should look like this (ignore the shoulder part and shield):


I have also noted when a model is loaded the angel of the model is in a different angel, I am unable to get it to load in a correct angel like how finale000 did. Mind sharing how that was done?

Here's how it looks for me:
## Post #23
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-06-27T21:37:51+00:00
- Post Title: Re: Bots / Models (.Bsc - .obj)

Spent about 6 hours yesterday and 3 hours today looking up various examples on mapping bones, haven't found any that had been helpful so far.

Based on my research on the game:
1. The Bone names referenced in the bsc model files are references to the name defined in the xx_bone.bon file

The bone data is not located within the actual bsc files (All the examples I've seen has had the bone data stored inside the models and are parsing it from it directly, this game isn't like that).

I'm pretty sure I located the data for where the bones are located in the file in a hex editor by searching up the bone name. However, I am unable to calculate the offset for each bone name dynamically in the script. I have no idea how to parse the data I found in the hex editor and map it regardless of finding the correct offset.

Aside from that going based on this topic: [viewtopic.php?f=29&t=3739](http://forum.xentax.com/viewtopic.php?f=29&t=3739)
#6 shows how the matrixes are structured within that file
The floats are identically set up in the bone file (after locating the bone name) as seen in the following screenshot:

However, the problem is I am unsure on how to handle this data, and how to locate the number of matrixes are here. In chrrox's topic it shows the number of floats stored but I could not find such value in my file.
I searched for the bone after that and calculated the number of floats by dividing the selected data by 0x40 and got 0xB55, but I don't see where this count is located anywhere.

Any help would be appreciated, this is pretty much where I'm stuck at right now for almost 3 days.

The bone files + some models have already been uploaded links to it are in the previous post.
