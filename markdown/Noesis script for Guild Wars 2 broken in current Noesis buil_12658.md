## Post #1
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-03-03T11:50:08+00:00
- Post Title: Noesis script for Guild Wars 2 broken in current Noesis buil

Hey Guys.

So I've got the newest Noesis, I've got the Guild Wars 2 .dat extracted, I've got all the folders with .pf files in them.

However whenever I try to open one of them I get the following errors:


[http://puu.sh/gjBVx/7015e80743.png](http://puu.sh/gjBVx/7015e80743.png)

[http://puu.sh/gjBTx/bc05985a6a.png](http://puu.sh/gjBTx/bc05985a6a.png)

I'm guessing the way data is handled has changed a little bit.

Could anyone confirm that this works in any build from 2012 at all? And if so, perhaps be able to share a Noesis build from back then, Rich's website doesn't keep older versions it seems.

The script is from here: [https://code.google.com/p/noesis-plugin ... c=svn3&r=3](https://code.google.com/p/noesis-plugins-official/source/browse/trunk/demonsangel/Guild+Wars+2?spec=svn3&r=3)

The files are in the correct place, script written by DemonsAngel.
## Post #2
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2015-04-05T17:55:20+00:00
- Post Title: Noesis script for Guild Wars 2 broken in current Noesis buil

They most likely changed the model format after beta.
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-04-06T10:04:29+00:00
- Post Title: Noesis script for Guild Wars 2 broken in current Noesis buil

This was the suggestion from Mr Adults (which reminds me I need to share a file or 2 with him).

> it was probably written in a buffer-overrunning way and stopped working when I safe-guarded the index/vertex/etc. buffer inputs from Python, if I had to take a random guess.
## Post #4
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-04-06T14:16:43+00:00
- Post Title: Noesis script for Guild Wars 2 broken in current Noesis buil

That was just a blind guess, without having seen the script, the error, or the data. If they changed the actual data as demonsangel suggests, that's your problem.
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-04-06T15:42:45+00:00
- Post Title: Noesis script for Guild Wars 2 broken in current Noesis buil

> Reply from MrAdults
>
> That was just a blind guess, without having seen the script, the error, or the data. If they changed the actual data as demonsangel suggests, that's your problem.

Yeah its a guess, but hopefully its correct, I've PM'd you the code and some files to take a look at as you mentioned.

If its changed theren theres not much I can do about that I suppose.
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-04-06T18:31:29+00:00
- Post Title: Noesis script for Guild Wars 2 broken in current Noesis buil

Long time ago I wrote script for Guild Wars 2, I looked at Noesis script when I tried this format. Noesis script is half-done as far as I remember, there's a lot things left to cover in order to make it work. Mr.Adults will need to make it from scratch I guess, if he will not finish this game I'll try to find where's mine lol and will post it here if I'll find it
## Post #7
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-04-07T00:03:56+00:00
- Post Title: Noesis script for Guild Wars 2 broken in current Noesis buil

Uhh, I didn't write the Noesis script. And I'm not doing anything from scratch, I've no interest in supporting this game. You're at Demonsangel's mercy.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-07T05:43:25+00:00
- Post Title: Noesis script for Guild Wars 2 broken in current Noesis buil

> Reply from lionheartuk
>
> The script is from here: https://code.google.com/p/noesis-plugin ... c=svn3&r=3

The files are in the correct place, script written by DemonsAngel.with this change some pf can be loaded:
```
                rapi.rpgBindUV1BufferOfs(vertexBuffer, noesis.RPGEODATA_HALFFLOAT, Format.vertexSize, Format.uv16Mask)
                #if Format.uv16Count >=3: rapi.rpgBindUV2BufferOfs(vertexBuffer, noesis.RPGEODATA_HALFFLOAT, Format.vertexSize, Format.uv16Mask+8)
            print("matName: %s, vSize: %d, group: %d" %(material.name, Format.vertexSize, Format.group))
            if Format.group != -1:
                rapi.rpgBindBoneIndexBufferOfs(vertexBuffer, noesis.RPGEODATA_UBYTE, Format.vertexSize ,Format.group, 4)
            if Format.weights != -1:				
                rapi.rpgBindBoneWeightBufferOfs(vertexBuffer, noesis.RPGEODATA_UBYTE, Format.vertexSize, Format.weights, 4)
 
```



GW2-pf.JPG (33.18 KiB) Viewed 294 times


(doesn't work for skeleton and animation pf)
## Post #9
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2015-04-08T18:51:59+00:00
- Post Title: Noesis script for Guild Wars 2 broken in current Noesis buil

I haven't touched a model format in over a year and I don't think I still have the files for the format.

Edit: it looks like I was rewriting the script somewhere in 2013 but ragequit because the animation was some kind of stupid granny format.
## Post #10
- Username: LogicalEvil
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 16, 2014 1:37 pm
- Post datetime: 2015-05-25T21:17:27+00:00
- Post Title: Noesis script for Guild Wars 2 broken in current Noesis buil

Sorry to make a useless bump, but I was wondering if there was still any interest in the subject. GW2 has some awesome models, it would be a shame if interest in them were to die.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-28T08:22:06+00:00
- Post Title: Noesis script for Guild Wars 2 broken in current Noesis buil

from time to time I've a look at skeletons in different threads.

Here it's 00009978.pf skeleton file with this mesh contained:



GW2-09978-skel.JPG (145.11 KiB) Viewed 197 times


(Remember: it's a skeleton file, so the mesh is not too nice.  )

Once I got the skeleton displayed (if so) maybe I'll find another patch for the above mentioned Noesis python script (v 0.0.7 as of 24.11.12 by Demonsangel)
to make it work with this small pf. (But it's of very low priority for me.)

Had some troubles getting the zero-terminated bonenames 'til I realized they are expanded for DWORD alignment:
if ((cnt%4)!=0) { cnt /= 4 ; cnt++ ; cnt *= 4 ; }

edit: I checked for the skeleton (hierarchy built manually, may be errorness), have some odds with rotations.

Clavicles and Shoulders share the same position, same with Hips and Knees (don't understand it).

The py scripts points to a bonemap that reads like this:
6 14 11 12 9 10 2 4 19 20 25 22 32 28 31 27 24 23 21

I've added actionpoint:LeftHand/Righthand but the resulting skeleton doesn't "convince" me.

It could be helpful if someone sent me an old pf (skeleton) file which is loaded correctly by Demonsangle's script.
Otherwise I don't think that I'll waste more time on this.
