## Post #1
- Username: Alek Sander
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 04, 2010 8:37 pm
- Post datetime: 2010-11-13T16:48:52+00:00
- Post Title: Viking Battle for Asgard models

Hi all! I'm new here and so on and etc... 
I know the game isn't that popular, but I want to get the models from it + some understanding about 3d file format. It's more like a challenge for me (my first).

So, the models are packed in CHR_MDLS.PAK file, for which I've made a BSM script.

I've got 4 types of files:
BNS - bone structure?
COL - collision? the file has something in it only for the player model though.
DNH - have no idea, but it isn't present for all the models
SKIN - model itself, I guess...

Here is my understanding of SKIN files so far (please, don't laugh )

```
long	number of segm?
word	number of segm?
word	??? same for all
long	??? same for all

long	segm
long	number of connections between vertexes?
long	number of vertexes
long	??? not same for all

long	??? same for all
long	number of bytes per description block?
long	dummy?
long	(sometimes) 1/3 of the 8th byte in each point description block
```

So, a vertex is described by 18 bytes. And here I'm lost. There is no correct float value for a coordinate - it's either too big (like +38) or too small (-20). Maybe they are using half-precision here... Plus I don't know (understand) if there are normals and uv-coords, weights and other 3d data...
Here I need help!
[THE_PLAYER.rar](https://xentaxbackup.github.io/file/3599_THE_PLAYER.rar)
## Post #2
- Username: Alek Sander
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 04, 2010 8:37 pm
- Post datetime: 2010-11-14T05:54:50+00:00
- Post Title: Viking Battle for Asgard models

A little update:
A vertex is described by 24 bytes, not by 18. (it's 0x18=24)
At the end of file i think there are indices, but they are a bit strange.
## Post #3
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-11-16T15:23:21+00:00
- Post Title: Viking Battle for Asgard models

What's about the converted files ?
[skin_to_obj.zip](https://xentaxbackup.github.io/file/3611_skin_to_obj.zip)
## Post #4
- Username: Alek Sander
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 04, 2010 8:37 pm
- Post datetime: 2010-11-16T17:45:01+00:00
- Post Title: Viking Battle for Asgard models

> Reply from Karpati
>
> What's about the converted files ?What do you mean?
I see you've made nice progress! But I wanted somebody to help me by actually explaining those moment I don't understand. 
Thanks for converted files! I've already understood the formation of faces. Trying to see the vertexes...
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-11-16T18:47:24+00:00
- Post Title: Viking Battle for Asgard models

Do you have the texture files for your sample files ?

Can you send me some other sample files to [kz_3d@tvn.hu](mailto:kz_3d@tvn.hu) ?
(I don't have this game and I would like to test my loader module with other files.)
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-11-16T18:50:36+00:00
- Post Title: Viking Battle for Asgard models

> Reply from Alek Sander
>
> A little update:
A vertex is described by 24 bytes, not by 18. (it's 0x18=24)

The vertex coords are 2 byte integers.
## Post #7
- Username: Alek Sander
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 04, 2010 8:37 pm
- Post datetime: 2010-11-17T16:53:30+00:00
- Post Title: Viking Battle for Asgard models

> Reply from Karpati
>
> Do you have the texture files for your sample files ?

Can you send me some other sample files to kz_3d@tvn.hu ?
(I don't have this game and I would like to test my loader module with other files.)
Sending all the models I extracted from the game (9 Mb)... But I didn't find any textures, like at all! I'll get the image of the game tomorrow and will look harder.

The player model that you've converted doesn't look like the player, you know. It should look like a man. Maybe there is some clue on dimensions inside the model file?
And where did you take the .mtl description?
## Post #8
- Username: Alek Sander
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 04, 2010 8:37 pm
- Post datetime: 2010-11-17T17:43:12+00:00
- Post Title: Viking Battle for Asgard models

> Reply from Karpati
>
> The vertex coords are 2 byte integers.
In your converted models you add 1000 to the X coord for each vertex. Maybe that is the reason model of the player doesn't look right?
And what about vt (vertex textures)? How do you calculate them?
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-11-17T18:08:43+00:00
- Post Title: Viking Battle for Asgard models

> Sending all the models I extracted from the game (9 Mb)... But I didn't find any textures, like at all! I'll get the image of the game tomorrow and will look harder.
>
> 
>
> The player model that you've converted doesn't look like the player, you know. It should look like a man. Maybe there is some clue on dimensions inside the model file?

Thank you for your sample files I received it successfully.

The vertex size=24 works on the other models like swords, shields (geom is OK; UV is OK), but does not work on the player model (geom is not OK; UV is OK).

I don't understand why ?
## Post #10
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-11-17T20:34:17+00:00
- Post Title: Viking Battle for Asgard models

> In your converted models you add 1000 to the X coord for each vertex. Maybe that is the reason model of the player doesn't look right?
>
> And what about vt (vertex textures)? How do you calculate them?

You have right, I used that temporally to separate the different submodels.

How to get the UV-s (vertex size=24):

X,Y,Z: 2 bytes Integer
skip the next 7*2 bytes
U=2 bytes Word/8192
V=2 bytes Word/8192
skip the remaining bytes
## Post #11
- Username: Alek Sander
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 04, 2010 8:37 pm
- Post datetime: 2010-11-17T22:42:32+00:00
- Post Title: Viking Battle for Asgard models

Look at the player model, the 3rd and 4th submodel (segm part). The vertex size here is not 24, but 44.
Why to divide UV by 8192? Where did you get that number? (Sorry for these lame questions )
## Post #12
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-11-18T05:58:41+00:00
- Post Title: Viking Battle for Asgard models

> Reply from Alek Sander
>
> Look at the player model, the 3rd and 4th submodel (segm part). The vertex size here is not 24, but 44.

I know that...

> Reply from Alek Sander
>
> Why to divide UV by 8192? Where did you get that number?

It stores the 'float' UV on the non float type (word/word ---> float). I checked out the UV datas by my Unwrap UV function and I 'dreamed' this value.
