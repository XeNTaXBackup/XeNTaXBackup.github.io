## Post #1
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-08-30T19:07:01+00:00
- Post Title: [Request] Sleeping Dogs Model Files

Hello all!

I am one of the few people interested in modding the game Sleeping Dogs. I have already figured out sounds, but I need assistance with the rest. 
All of the game's art assets are packed into .big files. The models for this game are in the format .perm.bin, with accompanying .temp.bin files.

[A few fellows made a .big extractor a while back](http://forum.xentax.com/viewtopic.php?t=9481), but they all promptly abandoned the project for reasons unknown. They also managed to [open textures from the .temp.bin files](http://forum.xentax.com/viewtopic.php?f=18&t=10233), but as far as I know nobody has tried to decompile the actual models. There is also a [supposed .bin decompressor](http://forum.xentax.com/viewtopic.php?p=83162#p83162) from the same guys but it doesn't seem to work completely.

I would like to ask if anyone here has any info on or could make an extractor for the actual models. It would really help the community and breath new life into the game.

[Here's some sample files](http://www.mediafire.com/download/sjhlb5umoym5l9s/SleepingDogsFileSample.zip).
## Post #2
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-04T06:10:12+00:00
- Post Title: [Request] Sleeping Dogs Model Files

Aha, apparently I was incorrect. 

.perm.bin





Are in fact model model files, but 

_TS0.perm.bin



Contain the textures.



Unfortunately though that's the extent of my knowledge. Is anyone here capable of assisting?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-04T16:14:00+00:00
- Post Title: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Is anyone here capable of assisting?hmm, "capable"? Don't know this word.  
[](http://www.pic-upload.de/view-20622569/ElectroWeapon001_TS001.temp.jpg.html)
At the bottom the normal map?
## Post #4
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-04T17:13:36+00:00
- Post Title: [Request] Sleeping Dogs Model Files

Seems so, but how exactly did you get it? I tried that program with those settings, but for some reason it's not opening properly for me. 
Which file did you open? Did you run it through the decompressor first?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-04T18:03:47+00:00
- Post Title: [Request] Sleeping Dogs Model Files

I just open ElectroWeapon001_TS001.temp.bin from your Props_new samples folder in TextureFinder. No decompression. (I think texture files are not compressed because it does not make much sense to compress a DXT1 compressed file again - but that's just a guess).

(The name "SDDecompressor" appears in the image because I copied the samples into that folder. Sry for misleading you.)
## Post #6
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-04T18:58:19+00:00
- Post Title: [Request] Sleeping Dogs Model Files

Woah, [you're right](http://puu.sh/4j2w6.jpg)! First there's the specular, then the diffuse, then the normal, just like the _TS0.perm.bin says. Although for the specular and diffuse you need to have "a" checked, and to get the normal you need to switch it to DXT5.
This is awesome! At least we finally have some progress. While it would be nice to have a batch texture extractor it's not really necessary if we have this.

However, even if textures are now possible it's only half the battle. The most important part is the model itself. 

Do you know someone who's good at model extraction?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-04T19:16:56+00:00
- Post Title: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Do you know someone who's good at model extraction?There are about 2 or 3 handful of guys in this forums who are. Don't know them personally - just have a look around. Not difficult to find them.

I myself had a try and what I can say so far: it's as difficult as it has been with the mafia2 models. It's easy to get vertices and faces but in blender it's a whole mess. Two possible reasons: the vertices might have to be sorted in another way or they have to be calculated in another way than I did. I tried half floats and the mafia2 formulas. At no avail.

The faceindices look quite "normal" although some uncommon beginning:
f 175 176 177 
f 178 179 180 
f 546 547 548 
f 555 556 557 
f 811 812 813 
f 3 4 1 
f 1 2 3 
f 39 3 2 
f 38 41 39 
f 2 40 39 

[](http://www.pic-upload.de/view-20624641/Klienod_01.jpg.html)
(Since I don't owe this game I don't think I will bother any more.)
## Post #8
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-04T19:19:42+00:00
- Post Title: [Request] Sleeping Dogs Model Files

Hm... well thanks for the help anyways. 

I've tried asking in various places but it seems like nobody cares about this game anymore. It's a shame really. It has some pretty amazing models.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-04T19:35:24+00:00
- Post Title: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> It's a shame really. It has some pretty amazing models.They were ripping models at [http://forums.sleepingdogs.net](http://forums.sleepingdogs.net) afaik. Maybe you could present some (or at least a link to them) to arise some/more interest here? (Although it might be politically incorrect I dare to say: some nice babe's pic could sometimes cause miracles...  )
## Post #10
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-04T19:39:31+00:00
- Post Title: [Request] Sleeping Dogs Model Files

That was me. I used Ninja Ripper for those, and [you saw how it turned out](http://puu.sh/3UFPR).

All the models have giant holes in them, no t-poses, and all UV maps are utterly destroyed. I have [here](http://facepunch.com/showthread.php?t=1283567) two models where the UV was redone from scratch, but that's it.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-04T19:54:11+00:00
- Post Title: [Request] Sleeping Dogs Model Files

If I had a very simple model, let's say a cube, a chest, a bench or a table I could give it another try. (But they should not have any decorations/ornaments. Because that would increase the verts count.)
## Post #12
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-04T20:05:54+00:00
- Post Title: [Request] Sleeping Dogs Model Files

[Here's a book](http://puu.sh/4j6bi.zip). That should be pretty low-poly.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-04T20:48:48+00:00
- Post Title: [Request] Sleeping Dogs Model Files

Thx. This is a book (should be): [](http://www.pic-upload.de/view-20625599/book.jpg.html)

But that was simple because the vertices are common.

So another model won't help I guess because I had a former try on Klienod01_CopLight.perm.bin which is a very small model, too. What I got you can see some posts above.

Maybe you can tell me what a Klienod CopLight is or what it should look like. Is it the signal light on a police car?

edit: yes. it is: [](http://www.pic-upload.de/view-20625804/CopLight.jpg.html)

Do you have a model that's as small as a CopLight but not of glass? Maybe the modelling of this glass structure made the vertices complicate (just a wild guess).
## Post #14
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-04T21:02:26+00:00
- Post Title: [Request] Sleeping Dogs Model Files

The Klienod is the [base vehicle](http://puu.sh/4j8UL.png), the CopLights are the [sirens and a computer next to the steering wheel](http://puu.sh/4j8VT.png). (this model was ripped with Ninja Ripper, and as you can see it has some... [defects](http://puu.sh/4j98m.png))

EDIT: Here's one that's a bit bigger, a [briefcase](http://puu.sh/4j92F.zip).
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-04T21:11:44+00:00
- Post Title: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> EDIT: Here's one that's a bit bigger, a briefcase.Perfect! Thx again. Seems to contain half floats.
But I'm a little bit tired now - will try it tomorrow. Good night.
## Post #16
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-04T21:22:15+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from shakotay2
>
> Perfect! Thx again. Seems to contain half floats.
But I'm a little bit tired now - will try it tomorrow. Good night.
I just noticed that since the briefcase can be used as a weapon it seems to have two models inside the file: a normal and a broken version. I have no idea how that will affect the process, so here's a [different one](http://puu.sh/4j9IK.zip) just in case. Still relatively small.

Take all the time you need, there's no hurry.
## Post #17
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-05T06:22:18+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Files automaticly decompressing while unpacking if they compressed. About textures [here](http://forum.xentax.com/viewtopic.php?f=18&t=10233)
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-05T09:02:39+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Ekey: thx for the link!

> Reply from SergeantJoe
>
> I just noticed that since the briefcase can be used as a weapon it seems to have two models inside the file: a normal and a broken version. I have no idea how that will affect the process, [...]I made some progress on the briefcase: [](http://www.pic-upload.de/view-20628356/briefcase_SM2_.jpg.html)

Now I must get rid of the superfluous strange rectangle and some other vertices.
The broken version does only consist of the grip, does it?

(The PoliceBadge again having 3 floats vertices, the tex two half floats and 6 bytes to skip - didn't bother creating the obj but there should be no problems.)
## Post #19
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-05T15:49:37+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

I already posted that link, but whatever. 

> Reply from shakotay2
>
> The broken version does only consist of the grip, does it?
I believe so. To me the stretching looks like some sort of error, but still, amazing work!

Does this mean that larger models like vehicles or characters are now possible, or am I being too hasty?


Say, Ekey, is there any chance you happen to know anything about these? You were the one that made the .big extractor and decompressor in the first place, why did you suddenly quit?
## Post #20
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-05T16:28:45+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Say, Ekey, is there any chance you happen to know anything about these? You were the one that made the .big extractor and decompressor in the first place, why did you suddenly quit?

Unpacker works perfectly and can decompress compressed content. My job is done
## Post #21
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-05T17:23:32+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Wait, hold on. I've heard multiple people use the term decompress when talking about this game, but they all seem to be referring to different things. Are you talking about .bix/.big->.bin or just the .bin files?

Because when I hear decompress I think of .bin->.obj, but I understand that's rather ignorant of me.
## Post #22
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-05T19:46:35+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Because when I hear decompress I think of .bin->.obj, but I understand that's rather ignorant of me.
BIGUnpacker does not convert files to other format, only decompress. Do not confuse [Conversion method](http://en.wikipedia.org/wiki/Data_conversion) with [De/Compression method](http://en.wikipedia.org/wiki/Data_compression)
## Post #23
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-05T19:48:39+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Ah, okay. I see what you mean. Thanks for the clarification.

So, the files are all decompressed, now we need a way to covert them into a useable format.
Just out of curiosity, what method did you use to get that book and briefcase shakotay?
## Post #24
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-05T19:56:36+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> So, the files are all decompressed, now we need a way to covert them into a useable format.
Exactly
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-05T20:15:12+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Does this mean that larger models like vehicles or characters are now possible, or am I being too hasty?Should be. Atm it's a numerical problem of finding the rules to exclude the unwanted vertices: [](http://www.pic-upload.de/view-20634607/improving_briefcase.jpg.html)
And finally: [](http://www.pic-upload.de/view-20634954/leftSideOpen.jpg.html)

But the left side is open now. wtf.
This is bursting my imagination. And I had to do some steps manually for one simple model. Difficult to do that automatically.

With characters there's another problem: Jackie seems to be quartered, half right back, half right front.

> what method did you use to get that book and briefcase shakotay?It's always the same method: fiddeling the verts and faces together.  

Here [viewtopic.php?f=16&t=10720](http://forum.xentax.com/viewtopic.php?f=16&t=10720) you'll find a crash course about DragonBall online meshes - just to get an imagination.
## Post #26
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-05T20:41:28+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Hmm, interesting. 

I took a look at what Ninja Ripper spat out and it seems that Wei and Jackie are extremely high-poly compared to the other characters. Maybe a [generic civilian](http://puu.sh/4jVeZ.zip) would easier?
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-06T07:23:35+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Thx again, but it doesn't seem to be a problem with the poly count - the char models are just buried in a "mesh coffin". And it's the same with vehicles: [](http://www.pic-upload.de/view-20637315/270DX01.jpg.html)

I tried an exclusion depending on the vector length of vertices but guess I'll have to wait for another brainwave.
Though I could create an UV extractor. For simple models the UVs seem to correct; for others (see in above pic) setting of some points to 0.0 0.0 might be required but that would be easier than recreating the complete UV map.

edit: here I deleted all submesh_1 faces with vertices greater than ~2900 [](http://www.pic-upload.de/view-20637486/lowerPartOffaces.jpg.html)

UV map Jackie (maybe uncomplete): [](http://www.pic-upload.de/view-20637738/UVmap_Jackie.jpg.html)

(If ripping the models and fixing the missing parts were acceptable we would be done here.)

edit: well, combining the above mentioned face data with the ripped model data would need some recalculation, I guess. This being a task I haven't ever done so far.

A simpler solution would be to merge the ripped model into the extracted one in a 3D program. Then move/rotate it until it's fitting to the buried one and deleting this one (only vertices, preserving faces). Didn't try such thing so far, too. But should work. More or less...


edit2: I tried to exclude vertices with the same vector gradient. At no avail.
And then I realized: the parallel vectors I tried to eliminate just appear because of an position offset between the model "quarters". I'm such a dumbo...  
[](http://www.pic-upload.de/view-20638030/offsetBetweenQuarters.jpg.html)
Maybe the vectors building a quarter are grouped in the data? After I will have found them adding an offset would be a lesser task...
## Post #28
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-06T16:45:45+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Words cannot express how amazed I am right now. After half a year of nothingness seeing so much progress all at once is astounding.

Really glad to hear that UVs are at least more or less possible. Although it won't really help with characters this will make vehicles very easy.
And yeah, that UV is [not complete](http://puu.sh/4kxpN.jpg), but as long as it has the most difficult parts (IE the hands and face), I suppose it doesn't matter.

> Reply from shakotay2
>
> I realized: the parallel vectors I tried to eliminate just appear because of an position offset between the model "quarters".
Wait, so if this is the current state of the model, wouldn't it be possible to simply move the pieces together manually? It looks like all the vertices are there, just stretched out.
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-06T17:08:52+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> wouldn't it be possible to simply move the pieces together manually?Yes, that means "setting the offset to 0". And I'd prefer doing this programatically rather than manually.

There are a few issues to solve but maybe I can upload a tiny extractor at the end of the next week.
"Tiny" means you'll have to input a threshold for the cutting of the faces for example.
## Post #30
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-06T17:25:40+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Whatever you say man. Believe me, I really appreciate it, a lot.

And just fyi, I'll be away for a week starting tomorrow, but just in case you need any more samples this guy uploaded the necessary .big/.bix files [here](http://facepunch.com/showthread.php?t=1283567&p=41507294&viewfull=1#post41507294), you can extract those with Ekey's program.

[There's also a free demo of the game on Steam.](http://store.steampowered.com/app/202170/)
## Post #31
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-10T21:19:41+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

These damned offsets being rather simple at the end:
[](http://www.pic-upload.de/view-20682412/Jackie_arm.jpg.html)

[](http://www.pic-upload.de/view-20682532/Jackie_ok.jpg.html)

Exclusion of errorness texture faces might be left to the user by defining a "range":
[](http://www.pic-upload.de/view-20692141/Jackie_textured.jpg.html)
## Post #32
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-09-12T20:44:23+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Can you write down some pseudo code on how the file format is constructed?

Thnx

T.
## Post #33
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-13T09:57:43+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Sure - but let me first finish the extractor. 

edit: some vehicles are going to be o.k.:
[](http://www.pic-upload.de/view-20722000/270DX01_.jpg.html)

Some others are not:
[](http://www.pic-upload.de/view-20722072/sampan01.jpg.html)
## Post #34
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-15T01:35:00+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Back! 
The hair is a separate mesh, maybe that's why. At least the body UVs are intact.

Model itself looks amazing! Is it really just a pure luck hit or miss with the vehicles though?

EDIT: Yeah, I'm pretty sure the hair uses a separate texture. At least Wei's does.
## Post #35
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-15T22:10:14+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from shakotay2
>
> SleepDogsExtractor.zip

This is a mesh extractor for SleepingDogs' *.perm.bin files.
YES! Although most of the details are a bit over my head I'm sure I can figure it out.

Thank you so much, this will make a lot of people very happy, I guarantee it.
## Post #36
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-15T22:21:58+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Thank you so much, this will make a lot of people very happy, I guarantee it.I hope so.  
But with the vehicles there's some weird error I didn't figure out so far.
FireEngine
[](http://www.pic-upload.de/view-20737718/FireEngine.jpg.html)
and bisai01:[](http://www.pic-upload.de/view-20737753/Bisai01_SM2_add_faces.jpg.html) having additional faces I can't understand.

Again I have to look for a small model with this error to understand what's going on.
## Post #37
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-15T22:25:51+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Well, I hope you can get that sorted out. The wheels are missing because they're stored in a different .perm.bin file.

And by the way, your program seems to be creating .obj files all right, but they're completely empty. Or am I just doing something wrong?
## Post #38
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-15T22:36:01+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> And by the way, your program seems to be creating .obj files with nothing in them.Talking about the t12-button? Another thing to be figured out - so far only for sampan01 something useful (fender, steering wheel) is being created. 

(Maybe I should lock this button to avoid the tool losing reputation?  )

"Completely" empty? Could you give a model example/params used/buttons pressed?
## Post #39
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-15T22:50:12+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

I didn't change anything, I just loaded the very first .perm.bin from Characters_New and it gave me [this](http://puu.sh/4smub.png).

It must be my computer again, other people are saying it works fine.
## Post #40
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-16T01:39:05+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Say, did Ekey ever release [this](http://img4.imageshack.us/img4/570/55366567.png)?

The folks at FP are trying to get textures, and that would be very useful for those of us that aren't programmers.
## Post #41
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-16T06:52:51+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Say, did Ekey ever release this?

The folks at FP are trying to get textures, and that would be very useful for those of us that aren't programmers.
Nope, because project frozen.
## Post #42
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-16T16:43:24+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Well that's a disappointment. Oh well, we do have the program that Shako showed us, that will have to do.
## Post #43
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-17T18:25:52+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Say, will you continue working on this? I know that you're doing this out of good will and on your own time, but I really want to get as much done as possible. 
Who knows when another person with programming experience will take notice of this game?

EDIT: And by the way, I've tried running the program on Windows 8, and even on Windows 7 and XP virtual machines, it still produces 0 kb files no matter what. Does it require any special libraries or anything?
## Post #44
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-17T22:08:45+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Say, will you continue working on this?Yes - problem is that I'm a little bit stuck atm at the additional faces on the vehicles.
I cut the bisai01 LOD2 model down to 100 vertices and still don't have a clue how to identify the additional (=wrong) faces or where they come from:

```
v 6.361328 0.000000 -4.155273
v 6.177734 0.000000 -1.404297
v 6.088867 1.877930 -1.422852
v 5.879883 0.000000 0.977539
v 5.754883 1.966797 0.796875
v 1.517578 2.772461 2.229492
v 0.987305 2.664063 2.094727
v 1.130859 2.707031 1.947266
v 1.571289 2.806641 2.050781
v 6.141602 1.756836 -4.341797
v 6.174805 0.000000 -4.402344
v 5.955078 1.994141 -4.198242
v 6.066406 2.080078 -3.763672
v 4.241211 2.645508 -3.007813
v 4.245117 2.559570 -3.715820
v 2.382813 2.946289 3.082031
v 2.059570 2.898438 2.561523
v 2.201172 2.910156 2.389648
v 2.568359 2.918945 2.875977
v 2.568359 2.432617 2.875977
v 3.443359 2.511719 2.934570
v 3.443359 2.789063 2.934570
v 2.568359 2.918945 2.875977
v 2.570313 2.467773 -2.183594
v 2.570313 3.027344 -2.183594
v 4.104492 2.703125 -2.451172
v 4.153320 2.199219 -2.454102
v 1.384766 2.666992 -1.487305
v 2.509766 2.879883 -2.161133
v 1.384766 2.290039 -1.487305
v 1.384766 2.290039 -1.487305
v 1.142578 2.352539 2.112305
v 1.130859 2.707031 1.947266
v 1.384766 2.666992 -1.487305
v 1.142578 2.352539 2.112305
v 2.042969 2.410156 2.294922
v 1.571289 2.806641 2.050781
v 1.130859 2.707031 1.947266
v 2.042969 2.410156 2.294922
v 2.568359 2.918945 2.875977
v 2.201172 2.910156 2.389648
v 1.571289 2.806641 2.050781
v 2.201172 2.910156 2.389648
v 4.155273 2.541016 -2.454102
v 4.104492 2.703125 -2.451172
v 4.153320 2.684570 -2.454102
v 4.104492 2.703125 -2.451172
v 4.155273 2.541016 -2.454102
v 4.153320 2.199219 -2.454102
v 3.801758 2.524414 2.854492
v 3.746094 2.724609 2.813477
v 3.443359 2.789063 2.934570
v 3.801758 2.524414 2.854492
v 3.794922 2.710938 2.786133
v 4.153320 2.684570 -2.454102
v 5.969727 2.090820 -2.452148
v 5.969727 2.090820 -2.452148
v 5.969727 1.947266 -2.452148
v 4.155273 2.541016 -2.454102
v 3.944336 2.461914 3.298828
v 3.838867 1.272461 3.881836
v 3.666016 1.291992 4.085938
v 3.695313 2.422852 3.656250
v 3.826172 0.000000 4.045898
v 3.658203 0.000000 4.255859
v 6.088867 1.877930 -1.422852
v 5.856445 2.108398 -0.418945
v 6.017578 2.063477 -2.452148
v 6.271484 1.791016 -4.091797
v 6.141602 1.756836 -4.341797
v 5.559570 2.189453 0.689453
v 5.856445 2.108398 -0.418945
v 6.088867 1.877930 -1.422852
v 5.754883 1.966797 0.796875
v 5.559570 2.189453 0.689453
v 3.002930 2.546875 4.297852
v 3.180664 2.365234 4.265625
v 2.975586 2.361328 4.433594
v 2.623047 2.918945 3.191406
v 2.564453 2.896484 3.817383
v 2.381836 2.940430 3.778320
v 2.564453 2.896484 3.817383
v 2.623047 2.918945 3.191406
v 2.604492 2.821289 3.827148
v 3.937500 2.654297 2.874023
v 5.005859 2.362305 1.496094
v 3.944336 2.461914 3.298828
v 3.700195 2.509766 3.592773
v 3.717773 2.710938 3.133789
v 3.695313 2.422852 3.656250
v 3.443359 2.789063 2.934570
v 3.746094 2.724609 2.813477
v 3.717773 2.710938 3.133789
v 2.623047 2.918945 3.191406
v 2.568359 2.918945 2.875977
v 3.700195 2.509766 3.592773
v 2.604492 2.821289 3.827148
v 3.575195 2.422852 3.811523
v 3.695313 2.422852 3.656250

vt 0.652344 0.701416
vt 0.655518 0.616455
vt 0.525146 0.616455
vt 0.525879 0.705566
vt 0.412109 0.616455
vt 0.420898 0.709717
vt 0.434082 0.934082
vt 0.440430 0.958160
vt 0.446777 0.951599
vt 0.442383 0.931641
vt 0.664307 0.699707
vt 0.667236 0.616455
vt 0.726807 0.735352
vt 0.706299 0.729980
vt 0.670410 0.816528
vt 0.704102 0.816284
vt 0.395996 0.894714
vt 0.419434 0.909424
vt 0.427246 0.902954
vt 0.405273 0.886292
vt 0.405273 0.886292
vt 0.402832 0.846558
vt 0.402832 0.846558
vt 0.405273 0.886292
vt 0.631348 0.895691
vt 0.631348 0.895691
vt 0.644043 0.822998
vt 0.644287 0.820679
vt 0.598389 0.951843
vt 0.630371 0.898560
vt 0.598389 0.951843
vt 0.598389 0.951843
vt 0.427734 0.963348
vt 0.435547 0.963867
vt 0.598389 0.951843
vt 0.439453 0.951080
vt 0.431152 0.910156
vt 0.442383 0.931641
vt 0.446777 0.951599
vt 0.431152 0.910156
vt 0.405273 0.886292
vt 0.427246 0.902954
vt 0.442383 0.931641
vt 0.427246 0.902954
vt 0.644287 0.820679
vt 0.644043 0.822998
vt 0.644287 0.820679
vt 0.644043 0.822998
vt 0.644287 0.820679
vt 0.644287 0.820679
vt 0.406250 0.830200
vt 0.408203 0.832764
vt 0.402832 0.846558
vt 0.406250 0.830200
vt 0.409180 0.830566
vt 0.644287 0.820679
vt 0.644043 0.734619
vt 0.644043 0.734619
vt 0.644043 0.734619
vt 0.644287 0.820679
vt 0.395508 0.732422
vt 0.390625 0.676025
vt 0.382324 0.677002
vt 0.383789 0.730713
vt 0.389648 0.615723
vt 0.381836 0.615723
vt 0.595215 0.729004
vt 0.547852 0.739990
vt 0.644043 0.732422
vt 0.721680 0.720215
vt 0.733643 0.726563
vt 0.495117 0.754028
vt 0.547852 0.739990
vt 0.595215 0.729004
vt 0.490234 0.744873
vt 0.495117 0.754028
vt 0.341797 0.866577
vt 0.343262 0.858521
vt 0.335449 0.867798
vt 0.391113 0.883789
vt 0.363281 0.886475
vt 0.364746 0.894775
vt 0.363281 0.886475
vt 0.391113 0.883789
vt 0.362793 0.884644
vt 0.419922 0.806152
vt 0.457031 0.780273
vt 0.399902 0.805786
vt 0.385742 0.817383
vt 0.407715 0.816528
vt 0.382813 0.817627
vt 0.402832 0.846558
vt 0.408203 0.832764
vt 0.393555 0.834106
vt 0.391113 0.883789
vt 0.405273 0.886292
vt 0.373047 0.834839
vt 0.362793 0.884644
vt 0.363281 0.840576
vt 0.370605 0.835083

#  1321 faces
f 83/83 84/84 85/85
f 86/86 87/87 88/88
f 98/98 99/99 100/100
# f 107/107 108/108 109/109
# f 118/118 119/119 120/120
# f 123/123 124/124 125/125
f 1/1 2/2 3/3
f 3/3 4/4 1/1
f 6/6 9/9 10/10
f 10/10 7/7 6/6
f 5/5 6/6 7/7
f 7/7 8/8 5/5
f 5/5 8/8 19/19
f 19/19 20/20 5/5
f 20/20 19/19 41/41
f 11/11 12/12 13/13
f 13/13 14/14 11/11
f 17/17 18/18 15/15
f 15/15 16/16 17/17
f 39/39 17/17 16/16
f 16/16 38/38 39/39
f 29/29 38/38 25/25
f 29/29 39/39 38/38
f 25/25 26/26 27/27
f 29/29 40/40 39/39
f 29/29 25/25 28/28
f 27/27 28/28 25/25
f 40/40 29/29 42/42
f 42/42 43/43 40/40
f 21/21 22/22 23/23
f 23/23 24/24 21/21
f 30/30 31/31 32/32
f 32/32 33/33 30/30
f 34/34 35/35 36/36
f 36/36 35/35 37/37
f 46/46 47/47 44/44
f 44/44 45/45 46/46
f 62/62 46/46 45/45
f 51/51 62/62 45/45
f 45/45 48/48 51/51
f 50/50 51/51 48/48
f 48/48 49/49 50/50
f 49/49 53/53 52/52
f 52/52 50/50 49/49
f 54/54 55/55 56/56
f 56/56 57/57 54/54
f 60/60 61/61 58/58
f 58/58 59/59 60/60
f 60/60 59/59 80/80
f 80/80 81/81 60/60
f 81/81 80/80 82/82
f 82/82 90/90 89/89
f 81/81 82/82 71/71
f 89/89 71/71 82/82
f 81/81 71/71 68/68
f 71/71 69/69 68/68
f 67/67 68/68 69/69
f 69/69 70/70 67/67
f 63/63 64/64 65/65
f 65/65 66/66 63/63
f 72/72 73/73 74/74
f 74/74 75/75 72/72
f 76/76 77/77 78/78
f 77/77 79/79 78/78
f 93/93 94/94 91/91
f 91/91 92/92 93/93
f 92/92 96/96 97/97
# f 92/92 97/97 101/101
f 92/92 95/95 93/93

f 45/45 46/46 47/47
f 58/58 59/59 60/60
f 72/72 73/73 74/74

f 41/41 42/42 37/37
f 36/36 37/37 38/38
f 38/38 39/39 36/36
f 43/43 40/40 44/44
f 40/40 21/21 24/24
f 21/21 22/22 23/23
f 23/23 24/24 21/21
f 23/23 22/22 54/54
f 48/48 49/49 50/50
f 49/49 56/56 57/57

f 7/7 8/8 9/9
f 9/9 10/10 7/7
f 18/18 7/7 10/10
f 10/10 19/19 18/18
f 17/17 18/18 19/19
f 19/19 20/20 17/17
f 80/80 17/17 20/20
f 82/82 17/17 80/80
f 80/80 81/81 82/82
# f 196/196 82/82 81/81
# f 81/81 195/195 196/196
f 15/15 16/16 13/13
f 13/13 14/14 15/15
f 13/13 71/71 70/70
f 70/70 14/14 13/13
f 69/69 14/14 70/70
f 67/67 68/68 69/69
f 70/70 67/67 69/69
f 67/67 75/75 76/76
f 75/75 87/87 76/76
f 86/86 87/87 75/75
f 90/90 86/86 88/88
f 75/75 88/88 86/86
f 88/88 89/89 90/90
f 89/89 88/88 91/91
f 27/27 28/28 25/25
f 25/25 26/26 27/27
f 25/25 31/31 29/29
f 30/30 26/26 25/25
f 29/29 30/30 25/25
f 32/32 33/33 34/34
f 34/34 35/35 32/32
f 51/51 52/52 53/53
f 52/52 51/51 55/55
f 63/63 64/64 61/61
f 61/61 62/62 63/63
f 66/66 63/63 62/62
f 62/62 65/65 66/66
# f 157/157 66/66 65/65
# f 156/156 157/157 154/154
# f 65/65 154/154 157/157
# f 154/154 155/155 156/156
f 77/77 78/78 79/79
# f 98/98 77/77 199/199
f 99/99 78/78 77/77
f 99/99 97/97 100/100
f 77/77 97/97 99/99
f 77/77 98/98 94/94
f 94/94 97/97 77/77
f 98/98 95/95 92/92
f 92/92 94/94 98/98
f 92/92 95/95 96/96
f 92/92 93/93 94/94
f 83/83 84/84 85/85

f 3/3 4/4 1/1
f 6/6 4/4 3/3
f 3/3 5/5 6/6
# f 103/103 5/5 3/3
f 2/2 1/1 11/11
# f 3/3 101/101 103/103
f 1/1 2/2 3/3
f 11/11 12/12 2/2

f 1/1 2/2 3/3
f 3/3 4/4 1/1
f 5/5 6/6 7/7
f 7/7 8/8 5/5
f 9/9 10/10 11/11
f 9/9 11/11 14/14
f 11/11 12/12 14/14
f 12/12 13/13 14/14
f 15/15 16/16 17/17
f 15/15 17/17 20/20
f 17/17 18/18 20/20
f 18/18 19/19 20/20
f 21/21 22/22 23/23
f 23/23 24/24 21/21
f 25/25 26/26 27/27
f 27/27 28/28 25/25
f 29/29 30/30 31/31
f 29/29 32/32 33/33
f 33/33 30/30 29/29
f 34/34 35/35 36/36
f 38/38 36/36 35/35
f 35/35 37/37 38/38
f 39/39 40/40 41/41
f 41/41 42/42 39/39
f 45/45 39/39 43/43
f 43/43 44/44 45/45
f 46/46 47/47 48/48
f 48/48 49/49 46/46
f 48/48 55/55 49/49
f 50/50 51/51 52/52
f 54/54 52/52 51/51
f 51/51 53/53 54/54
f 60/60 61/61 62/62
f 60/60 58/58 59/59
f 60/60 62/62 58/58
f 59/59 58/58 57/57
f 58/58 62/62 63/63
f 56/56 57/57 58/58
f 63/63 56/56 58/58
f 68/68 69/69 70/70
f 68/68 67/67 65/65
f 68/68 65/65 69/69
f 67/67 66/66 65/65
f 71/71 69/69 65/65
f 64/64 65/65 66/66
f 65/65 64/64 71/71
f 72/72 73/73 74/74
f 74/74 79/79 72/72
f 79/79 74/74 78/78
f 78/78 77/77 79/79
f 77/77 78/78 75/75
f 75/75 76/76 77/77
f 80/80 81/81 82/82
f 81/81 80/80 87/87
f 87/87 84/84 81/81
f 84/84 87/87 85/85
f 83/83 84/84 85/85
f 85/85 86/86 83/83
# face index min/max: 1 / 100

```

> EDIT: And by the way, I've tried running the program on Windows 8, and even on Windows 7 and XP virtual machines, it still produces 0 kb files no matter what. Does it require any special libraries or anything?On every model? Or some models? Then could you please give me a model name? (But keep in mind I only can check the models from your 9.87 MB samples zip.)

If it's on every model then I'd like to know if anyone else having this problem.

And 'no' it doesn't require any special library.
## Post #45
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-17T23:03:14+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from shakotay2
>
> On every model? Or some models?
I've tried dozens of different models from both folders, they all end up the same. I'm pretty sure it's just me though, everyone else I've talked to seems to be able to do it just fine. Strange. 
Oh well, I already got someone that I can send bins to and they can convert them for me.

The Bisai is the smallest four-wheeled vehicle in the game, I'm not sure what else to say.
## Post #46
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-17T23:21:50+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

What I could think of is a data error in your downloaded zip.
When you do a RMB click on the SleepDogsExtractor.exe in the zip then properties you should get this checksum:
[](http://www.pic-upload.de/view-20756788/CRC32_SleepDogsExtractor.jpg.html)
## Post #47
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-18T00:06:48+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

[No dice](http://puu.sh/4tYy2.png). This is really bizarre. 

Oh well, don't worry about it. This isn't the first time my computer has mysteriously broken a program for no reason.
## Post #48
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-18T06:33:10+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> [...]my computer has mysteriously broken a program for no reason.Hehehe, with computer errors there is always a reason. You might try chkdsk /f/r c:
for your c drive (or another letter for the drive your running the exe on).
## Post #49
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-19T03:02:55+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Process completed successfully, yet it still gives me a blank file. 

Oh well, it must be just a Windows 8 thing. Like I said, don't worry about it. I already got someone who can convert the files for me.

EDIT: I don't really know where to put this but I thought I should mention it anyway:

If you open Global.big/Data/Scripts and open one of the .skoo files with Notead, you can find some pretty interesting snippets. [(example)](http://puu.sh/4uUEO.png)

Those seem to be comments from the game code! So theoretically if someone had a copy of the SkookumScript IDE and a .big repacker they could pretty much have full control over nearly all game scenarios. (but not core gameplay I think)
While it's not as good as the alternatives, this still could possibly open up a whole world of modding capabilities. But currently there's no way to mod anything unless we get a .big repacker, but I'm being overly optimistic here.

Anyway, sorry for rambling. Good luck with those faces.
## Post #50
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-20T05:29:17+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

I just got it to work! 

Turns out I was opening the model, but I never pressed the "go" button. I feel really stupid now.

EDIT: [And it works perfectly](http://puu.sh/4w5y7.png). Thank you so much once again.
## Post #51
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-21T18:24:52+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from shakotay2
>
> Well, with the faces of the vehicles it's a little bit complicated.
For bisai01.perm.bin for example I found 193, 1321 and 4529 faces (LOD1,2,3?).
But if you display 3 models there are weird faces for example in LOD2 model.

With the help from Mariusz Szkaradek I understood that the 3 submeshes have to be devided up.

In fact there seem to be 8 submeshes.
SM 0 having 193 faces
no 1 to 3  have 99, 535+579+50 and 46+12 faces (1321 in sum)
The 4529 faces split up on submeshes 4..7

So the riddle is solved thanks Mariusz.

edit: hmm, I've made a comparison between the faces in the submeshes 1 to 3 and the ones of the errorness LOD2 SM.
They are identical!
So my error seems to be in the relation to the vertices list. Sure it's a rather simple one but I have to stick to RL again...
So, are vehicles now supported or am I being hasty again?

Also, if you have the time could you take a look at [these](http://puu.sh/4wKks.zip) bins? They all give me a "no mesh found error", even though they do in fact contain a model.
## Post #52
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-21T21:49:15+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> So, are vehicles now supported or am I being hasty again?Will take some time.

> Also, if you have the time could you take a look at [...]these bins? They all give me a "no mesh found error", even though they do in fact contain a model.Some don't contain the full "Buffer" string. further analysis is required.
## Post #53
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-09-21T22:26:22+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Alright, take your time. Meanwhile I'll get to work converting these 100+ character models.
## Post #54
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-10-29T03:18:46+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Once again, big thanks to Shako for the mesh support.

However, now we need the model skeleton. [We are really close to creating the very first mod for this game](http://forums.sleepingdogs.net/viewtopic.php?f=11&t=4760), and if one day it will be possible to make a .perm.bin repacker then bones will be very important.

Is there anyone here who's good at extracting bones? Howfie said he would look at it a month ago but I haven't really heard anything since then.
## Post #55
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-10-29T05:32:55+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

i can get em, will take a little more time (my time is a little limited the last month... as u can see i dont even have time to play the game lmao).
## Post #56
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-10-29T06:10:09+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Wait, really? I kind of assumed you lost interest since you haven't really responded to any of my PMs.

If you can still get the bones that'd be truly amazing. Sorry for jumping to conclusions.
## Post #57
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-10-29T07:30:30+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

no i havent lost interest hehehe, its just my gf doesnt share my love of extracting models so if i get caught on my laptop working on those asian prostitutes hahaha....

btw shakotay, is mariusz going to help you do the bones? if you dont mind sharing ur code i can help you get the bones and weights. but i know mariusz is helping you so no biggie if he wants to help you finish it as well.
## Post #58
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-29T08:27:38+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from howfie
>
> btw shakotay, is mariusz going to help you do the bones? if you dont mind sharing ur code i can help you get the bones and weights. but i know mariusz is helping you so no biggie if he wants to help you finish it as well.Mariusz send me his SleepingDogs blend file (including python code) when I was stuck wtih vehicles.

I was wondering why he didn't release it on Xentax himself and I promissed him to respect this.
So I don't know why he didn't, I ask him whether he is active in any forum but there was no response.

So maybe someone (SergantJoe?) is kindly going to ask him for some support.

My focus is not on SleepingDogs (because of my limited bandwith I even don't want download the steam demo).

I append the starting part of my first code which was capable of extracting characters. The format is a little bit confusing so is my code. So it won't help you either I guess

It was just searching for "xBuf" in the model data to determine the startaddresses of indexBuffers and VertexBuffers.

If you have a look at Jackie.perm.bin: there are two index- and two vertexBuffers. But they don't seem to contain bones info.

There's some kind of bones list from 0x0C10 to 0x1E0F (Bip01 Head, ..., Bip01 R Toe0) but it's not very helpful to me. There's no "parenting data" but maybe one could build the skeleton just from the sequential hierarchy.
Maybe more bones info to be contained in the animation files. 
But Cop.bin for example does not contain any "xBuf" string so my code will not be useful for this kind of files.

The python code mainly did a 4 bytes pattern search for the different data buffers. But if I recall correctly it couldn't handle bones data.

```
/*				das ist der erste SleepingDogs extractor code für char model; ziemliche probs mit vehicles
					offs = 1 ; l= 0 ; lastFaceNo= 0 ; cnt= 0 ; VBl_cnt=0 ;
						do {		// ja, super! Der algo versagt, wenn er auf einer Fundstelle startet! Weil offs2 dann =0
							bGetMesh= false ;			//lastFaceNo= 0 ; // for debug only
							nValue[0]= 0x78; nValue[1]= 0x42; nValue[2]= 0x75; nValue[3]= 0x66; // "xBuf"
							if ((*(pFBuf+offs)&255)==nValue[0]) offs-- ;	// gegen Algoversagen
							offs2 = FindStringInBuf_contDECO(offs, dwFileSize, nValue, 4) ;
							if (offs2!=0)	{
								offs += offs2 ; 
								if ((*(pFBuf+offs-4)&255)==0x49) {		// 'I'
									l++ ; VBl_cnt=0 ;
									offs3 = offs-6 ;	cnt= 0 ;	// zurück auf Submesh name
									while (*(pFBuf+offs3)!=0) {offs3-- ; cnt++ ;}
									offs3 += 5 ; cnt -= 4 ; fprintf( stream, "g submesh_%d\n# ", l) ;
									if (cnt>255) chMB("Submeshname too long!") ;
									else for (k=0;k<cnt;k++) fprintf( stream, "%c", *(pFBuf+offs3+k)) ;
									dwStartI= offs + 47 - cnt ;		// addr of faceIndices cnt
									fprintf( stream, "\n") ;
								}
								else if ((*(pFBuf+offs-5)&255)==0x56) {		// 'V'
									VBl_cnt++ ;
									if (cnt==0) {						// wenn vorher kein "I" gefunden
										// if start with VertexBlock
										offs3 = offs-7 ;				// zurück auf Submesh name Ende
										while (*(pFBuf+offs3)!=0) {offs3-- ; cnt++ ;}	// Anfang suchen
										offs3 += 6 ; cnt -= 5 ; fprintf( stream, "g submesh_%d\n# ", l) ;
										if (cnt>255) chMB("Submeshname too long!") ;
										else for (k=0;k<cnt;k++) fprintf( stream, "%c", *(pFBuf+offs3+k)) ;
										fprintf( stream, "\n") ;
										cnt++ ;				// magic, ask Dr. Ferguson
										// end if
									}
									offs3 = offs + 46 - cnt ;				// same SubMeshname expected!!
									type = *(pFBuf+offs3-4) ;				// zurück auf type; skip type 8
									if (!bType12) bType12 = (type==12) ;
									if (!bSearchType12) {
										if (type==16) dwStartV= offs3 ;
									}
									else
										if (bType12 && (bType12First)) { dwStartV= offs3 ; bType12First= false ; }	// 									
									if (type==4) {					// skip 2, whatever it is
										dwStartVt= offs3 ; 
										bType12First= true ;			// für nächstes Submesh
										if (l<999) dwSM_WEverCnt[l]= offs ; else offs2= 0 ;		// for loop break
										if (bSearchType12&&(!bType12))
											chMB("no Vertexblock type 12 contained!") ;
										else bGetMesh= true ;		// Ausgabe des Sub-Meshes
									}
									fprintf( stream, "# Vertexblock %d: type %d after 0x%x (count: %d)\n", VBl_cnt, type, offs3, (*(pFBuf+offs3) &255)+(*(pFBuf+offs3+1) &255)*256) ;
								}
								if (bGetMesh) FindStringInBuf_SleepingDogs(dwStartV, dwStartVt, dwStartI, dwFileSize, nValue, 4, lastFaceNo, bSearchType12, xFac, yFac, zFac) ;
								//fprintf( stream, "# 0x%x\n", offs) ;
								offs += 100 ;		// 
								//fprintf( stream, "\n\n") ;
							}
						} while (offs2!=0) ;
					if (l==0) { chMB("no mesh found! Try other button.") ; return true ;}
					//lastSM = l ; cnt= 0 ;  
					return true ;
*/

```
## Post #59
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-10-29T20:30:40+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Problem is, I don't know this Mariusz fellow. Where can I find him?

Also, Cop.bin probably doesn't have any vertices since it's an animation file:

> Cop_Arrest_Counter_Cuff_GIV 
>
> hkClassEnumItem
>
> hkaAnimationBinding
>
> hkaSplineCompressedAnimation
>
> hkaDefaultAnimatedReferenceFrame
## Post #60
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-29T23:43:09+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Problem is, I don't know this Mariusz fellow. Where can I find him?Marisuz is szkaradek123,  one of my heroes in this forum. Last post to be found here:
[viewtopic.php?f=16&t=7259&p=84226#p84226](http://forum.xentax.com/viewtopic.php?f=16&t=7259&p=84226#p84226)

(Really don't know why he has 49 thanks only. Should be 4900 or so.   He solved the very difficult model formats.)
## Post #61
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-10-29T23:44:34+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from shakotay2
>
> Marisuz is szkaradek123,  one of my heroes in this forum. Last post to be found here:
viewtopic.php?f=16&t=7259&p=84226#p84226
Ah, ok. Thanks, I'll try asking him.
## Post #62
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-10-30T09:54:03+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

he only has 49 because most of his scripts were written pre-thanks system. btw u dont need to search for exBuf, the chunk code for a buffer as you know is 0x7A971479, and 0x40 bytes into the data is a uint16, if 0, its a vertex buffer. if 1, index. if 2, it is an attribute buffer.
## Post #63
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-11-04T22:11:30+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Well, I talked to him, he said that he was having trouble with the bones. But, he did give me his [Blender import script](http://puu.sh/58UFP.zip) that supports materials.

Also, he brought up an interesting point. This game uses the Havok physics engine. Don't know if that makes any difference whatsoever but just fyi.

Here's the [models](http://puu.sh/57eff.zip) and [animations](http://puu.sh/57Q9U.zip) for reference.
## Post #64
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-04T23:44:11+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> This game uses the Havok physics engine. Don't know if that makes any difference whatsoever but just fyi.Definitely should.

CharacterRigs.bin contains a hkx header at 0xB0. After copying the data from 0xB0 to 0x39FF
into a new hkx and loading it into Havok Standalone tools sadly nothing is shown.
(Here u can see how it should look like: [viewtopic.php?f=16&t=10922&p=89781#p89781](http://forum.xentax.com/viewtopic.php?f=16&t=10922&p=89781#p89781))

There are 63 other headers in this bin file.
edit: seems there are 64/2 = 32 different skeletons contained. 
But nearly look the same, only bone names/count differ.
(Wei Head also being a whole skeleton, not a head as assumed.)

If we could import one of the hkx an xml could be exported.
## Post #65
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-05T09:22:03+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

and now here it is: Amanda's skeleton:
[](http://www.pic-upload.de/view-21240772/SleepingDogs_Amanda_skel.jpg.html)

(Just copied parent indices, bone names and reference pose matrices into an existing xml (to ease my efforts)
so don't know if everything's correct.)

Next step would be to convert the xml to some more useful format like FBX for example.

I dragged the xml onto Autodesk's FBX converter but it denied to take the file. 
(yes, I know, it wasn't designed for such a task) 

This is the advantage of (3D format) standards: having so many of them... 

edit: the 2nd skeleton in CharacterRigs.bin having 127 bones. For a reason I don't know only 64 are displayed:
[](http://www.pic-upload.de/view-21241319/2ndWeird.jpg.html)

There seems to be an error with the parenting of the bones, too.

With the error corrected the funny tail got lost. Still no clue about the missing bones.
[](http://www.pic-upload.de/view-21241398/2ndSkel.jpg.html)
## Post #66
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-11-05T16:41:38+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Aw man, that is great! But, I don't quite understand how that works. All the game skeletons are in one file? 

(and the tail is probably from the [Yaoguai](http://puu.sh/59yBB.jpg))
## Post #67
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-05T17:25:00+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> All the game skeletons are in one file?That's just a supposition for characters.

Search for "_HD" in characterRigs.bin and you'll find 84 names. Since they are doubled there might be 42 skeletons contained (see above where I calculated it to 32).
## Post #68
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-11-11T04:07:51+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Since bones are on hiatus, I got another crazy idea: what about the game world?

Hong Kong is split into nearly two thousand chunks, all of which are also stored in .perm.bin files. However they're not the same format as the models. 

[Here's a small sample.](http://puu.sh/5eTSD.zip)
## Post #69
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-11T09:48:08+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> I got another crazy idea: what about the game world?Well then, don't know why this should be?  
[](http://www.pic-upload.de/view-21301293/NP_ChopShopLOD.jpg.html)

But yes: the uvs crazy again (as always with SleepingDogs)  .
## Post #70
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-11-11T10:00:04+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Oooh, lovely. 

Bah, those blasted UVs. Just out of curiosity, what makes them so extraordinarily difficult? No 3D ripping tool can process them.


And just to be thorough, here's [a larger chunk](http://puu.sh/5f5HY.zip). Also, I think these bins contain both the model and textures at the same time.
## Post #71
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-11T10:48:16+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Oooh, lovely. 

Bah, those blasted UVs. Just out of curiosity, what makes them so extraordinarily difficult? No 3D ripping tool can process them.In this case they look like this:
...
vt 0.921875 0.874939 
vt 0.921875 0.188965 
vt 0.851135 0.874023 
vt 0.851135 0.843018 
vt 0.844360 0.845276 
vt 0.844360 0.874023 
vt 0.862976 0.830383 
vt 0.862976 0.804810 
vt 0.856445 0.804810 
vt 0.856445 0.830383 
vt 0.874878 0.816162 
...
As you can see: too less variation Doesn't really matter whether you treat them as WORDs or half floats.
(There was a game where uv y simply had to be divided by 2 and everything was fine.)

It's not that worse; you'll just have to get the idea...
[](http://www.pic-upload.de/view-21301653/NP_ChopShop_UV.jpg.html)

edit: hmm, three nice coffins?
[](http://www.pic-upload.de/view-21301752/coffin_uv.jpg.html)
## Post #72
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-11-11T19:13:51+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Hmm. And I was right, they do contain textures as well. Luckily Howfie's texture program can still process them.

You may be on to something with those coffins, the [texture is vaguely L-shaped](http://puu.sh/5fqIe.dds).
## Post #73
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-11T20:14:12+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

This texture contains squares for outside walls and a pavement, doesn't it?
Won't fit for the square stones ("coffins"). Got it from the coffin bins?

[](http://www.pic-upload.de/view-21307396/Cell_1394__NewYearLOD_temp_bin.jpg.html)
## Post #74
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-11-11T21:32:27+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Hm, I'm not quite sure. I can't even find this section in-game.
## Post #75
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-11-23T00:54:35+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Any news on the bones/weighting? I've attempted multiple times to re-rig everything from scratch, but that hasn't gone too well, and whenever I ask elsewhere I get utterly ignored.

Also, [here's something interesting](http://puu.sh/5qoM7.bin). It's just a regular .perm.bin model file, but it contains over a hundred submeshes! Shako's program opened the first few successfully, but started borking after the first twenty.

That folder is just filled with interesting stuff. TrueCrowd.bin contains a huge list of models, [wst_files.bin](http://puu.sh/5qp4t.bin) seems to deal with the bone weighting.
## Post #76
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-23T11:53:37+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Any news on the bones/weighting?
 As you know from Mariusz' py script he's building a weightslist. But I don't know why there are four values (last two always 0.0) per vertex:

6838 0x54760L
1.0 0.0 0.0 0.0
6839 0x54768L
1.0 0.0 0.0 0.0
6840 0x54770L
1.0 0.0 0.0 0.0
6841 0x54778L
0.83137254902 0.16862745098 0.0 0.0
6842 0x54780L
0.972549019608 0.0274509803922 0.0 0.0
6843 0x54788L
1.0 0.0 0.0 0.0
6844 0x54790L
0.564705882353 0.435294117647 0.0 0.0
6845 0x54798L
0.741176470588 0.258823529412 0.0 0.0
6846 0x547a0L
0.572549019608 0.427450980392 0.0 0.0
6847 0x547a8L
0.733333333333 0.266666666667 0.0 0.0
6848 0x547b0L
0.623529411765 0.376470588235 0.0 0.0
6849 0x547b8L
0.83137254902 0.16862745098 0.0 0.0
6850 0x547c0L
1.0 0.0 0.0 0.0
6851 0x547c8L
1.0 0.0 0.0 0.0
6852 0x547d0L
0.980392156863 0.0196078431373 0.0 0.0
6853 0x547d8L
0.980392156863 0.0196078431373 0.0 0.0
6854 0x547e0L
0.611764705882 0.388235294118 0.0 0.0
6855 0x547e8L
0.839215686275 0.160784313725 0.0 0.0
6856 0x547f0L
0.729411764706 0.270588235294 0.0 0.0
6857 0x547f8L
0.866666666667 0.133333333333 0.0 0.0
6858 0x54800L
0.725490196078 0.274509803922 0.0 0.0
6859 0x54808L
1.0 0.0 0.0 0.0
6860 0x54810L

Maybe you simply try out the first one?

(You used a custom skeleton, did you? How did you calculate the weights? Or did you take the ones of an other game's model?)

> It's just a regular .perm.bin model file, but it contains over a hundred submeshes!
didn't expect more than 20, yep. These are the two biggest, uvs completely missing:
[](http://s14.directupload.net/file/d/3450/yiq5xzsc_jpg.htm)
## Post #77
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-11-23T19:48:36+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from shakotay2
>
> Maybe you simply try out the first one?
How exactly? I don't know ANYTHING about programming, at least not yet. The only thing I know how to do is use the Weight Paint tool in Blender. And even then, [I suck at it](http://puu.sh/5c2iX.jpg). 

> Reply from shakotay2
>
> didn't expect more than 20, yep. These are the two biggest, uvs completely missing:
That looks like the skybox! Don't know what that giant sphere is though.
## Post #78
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-23T22:18:12+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

you didn't answer my question concerning the skeleton. And I don't have an idea whether you started with a weight of 1.0 on all of the vertices for example.

ok, anyway, we have the amanda skeleton as an xml and some wild guesses about the weighting.

I didn't find a simple way to import the xml into 3dsmax.
Before it comes to skinning you'll need a properly rigged character.

Atm I don't see any easy solution for the skinning of Sleeping Dogs models.
## Post #79
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-11-23T22:57:09+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from shakotay2
>
> you didn't answer my question concerning the skeleton. And I don't have an idea whether you started with a weight of 1.0 on all of the vertices for example.
Oh, yeah, I'm using a Source Engine skeleton. And I think that may be my problem, I'm not really adjusting any of the values. I need to learn how to do that.
## Post #80
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-24T06:37:19+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

It's about 5 years ago I read a fantastic 3dsmax (3dsmax 2009 ?) tutorial about copying the skinning from one model to a similar one.

Sadly I don't find it any more on my drives nor I had a google hit
because I'm not even sure whether they used the Skin Utility.

What I remember is that the models have to be very similar. Nearly same vertex count for example.
Also there were three (mercenary?) models in the viewport.
## Post #81
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-11-24T07:40:07+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Hmm, I don't know if that's going to help me much. SD models t-pose is different than most games, and I'm too incompetent to move the vertices into the correct positions. 

I've even tried bribing people to do the rigging, but it seems that truly nobody cares about models from this game except for you and me.
## Post #82
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-24T21:44:32+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> [...], and I'm too incompetent to move the vertices into the correct positions.I'm pretty sure you could learn it with little efforts.  

For me I'm circulating through 4 .. 5 projects of mine (just releaxing in a forum like this one) 
and have little time to focus on rigging/skinning. Thinking if you want to do it in a decent manner
you'll have to spend at least 4 weeks to learn the basics only.

BUT I found this 6 year old project on my hard disk:
[http://www.mit.edu/~ibaran/autorig/index.html](http://www.mit.edu/~ibaran/autorig/index.html)
[http://www.mit.edu/~ibaran/autorig/pinocchio.html](http://www.mit.edu/~ibaran/autorig/pinocchio.html)
Maybe it has improved meanwhile.

So far I tested the rigging only:
[](http://www.pic-upload.de/view-21433757/autorigged.jpg.html)
Maybe more to come...

edit: ah, well, this is what Ilya Baran wrote:

> Using your own motion data
>
> The short answer is that unfortunately, with DemoUI, you can't. The package comes with several sequences that DemoUI can read, but my skeleton is hard-coded in the code and the format is non-standard. If you would like to animate meshes rigged by Pinocchio with your own motions, you have to write your own front end. If you don't care about skeleton embedding, but only skinning weights, Blender's "Bone Heat" and the PM_heatWeight plugin for Maya are implementations of my algorithm

edit2: well, the walking is a little bit curious (the walking data is for another mesh I think):
[](http://www.pic-upload.de/view-21434788/walking.jpg.html)
(Think I will weld Jackie and give it another try...)

edit 3: oops, even with a welding threshold of 0.05 Jackie's getting crunchy fingers. Too bad.
Also DemoUI needs "a single connected component". I used the main submesh only so don't know what this means exactly. 

All I know that in Mesh::integrityCheck() edges.twin is -1 (0xFFFFFFFF)

Seems you'll have to "prepare" your mesh before it can be autoweighted.

edit4: when comparing Jackie's fingers to the ones of the test sample things are becoming clearer...
## Post #83
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-11-30T02:56:45+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Since bones were a bust, what about the buildings?

I really hate to keep bothering you, but it's best to get as much done as possible right now. Once you're finished there's nobody else to work on this.
## Post #84
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-30T06:17:08+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Since bones were a bust, what about the buildings?The uvs, forgot them?
Did you try Mariusz' script on the buildings?
(I'm working on dozens of models but some guys seem to expect me remembering every aspect of them
even after 3 weeks.  So sorry, case that suggestion is a "known fail".)
## Post #85
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-11-30T07:10:14+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from shakotay2
>
> Did you try Mariusz' script on the buildings?
Oh yeah, I completely forgot about that. 

Well, it works, but all the UVs are broken. You're right, the UVs are the most problematic part of this game. Even Direct X ripping programs can't figure them out.


Also, I just noticed something: that script supports weighting. Could I theoretically attach those weight groups to a custom skeleton?

EDIT: [Yeah, look at that!](http://puu.sh/5xxYV.jpg) If someone could figure out how to convert that xml we could get full bones and weighting!

But like I said, I know that you're doing this out of good will and on your own free time, so I don't want to press you. [In the meantime I can use my custom skeleton.](http://puu.sh/5xzJ2.jpg) It'll take a lot of shuffling and renaming, but it's possible!
## Post #86
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-30T12:35:01+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Also, I just noticed something: that script supports weighting.Did I miss something? (You didn't read my first post of Nov. 23th, did you?)
## Post #87
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-11-30T18:35:25+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

I did, but at the time I thought you were referring to something else. I'm really angry at myself now, I should've made that connection sooner.

This is almost as bad as the time I thought the extractor wasn't working when I just wan't pressing the Go button. Ugh.
## Post #88
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-12-01T02:54:38+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

So I tacked the weights onto the skeleton, [and the end result isn't half bad](http://puu.sh/5yxWs.jpg). 

So, I suppose that's it then. We can take out HD textures, and models with rigging.
Of course we still need the original skeleton for vehicles and faces, but other than that and the building UVs there's really not much else. Well, there's also animations, but that's a bit extreme.
## Post #89
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-01T09:11:18+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> So I tacked the weights onto the skeleton, and the end result isn't half bad.Very fine!  

How about sharing the result as a small tutorial: "How to apply weights on a sleeping dogs character model"?

Then I could try to assign the original skeleton.
## Post #90
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-12-01T09:36:52+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Well, I'm using a custom skeleton, so I had to rename all the vertex groups for it to work.

Theoretically if you had the original skeleton you can just assign it to the model via the Armature modifier and the vertex groups will be automatically applied.
## Post #91
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-01T09:55:02+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

yes... I know...
But how did you proceed? Did you import the skeleton to blender?
Which format does it have?

I'm just stuck here:
[](http://www.pic-upload.de/view-21493369/SleepingDogs_Jackie.jpg.html)

And I don't think that I will waste my time fiddeling out every single step that you did.
## Post #92
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-12-01T10:06:24+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

I imported the custom skeleton into Blender, assigned it to the model with the Armature modifier, [then renamed all those vertex groups to the skeleton's bone names](http://puu.sh/5yE3l.png), and it automatically attached the weights to the new bones.

[The skeleton I'm using is in Source Engine .SMD format.](http://puu.sh/5yEa7.smd) There are Blender plugins available for it.


You can use any skeleton you want, just make sure the vertex group names match the bone names. However, unless we have the original Sleeping Dogs skeleton there's always going to be errors with the weighting.
## Post #93
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-01T15:53:29+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> [...]and it automatically attached the weights to the new bones.Does the imported skeleton have the same bone count? Means are there bones to add or to delete?

edit3: there are 69 bones only in the SMD.

What about the parenting? I see there are 5 fingers for a hand with "2 sub fingers" for both the SMD skeleton and Mariusz' vertex groups for Sleeping Dogs Jackie.

edit3:
9 "ValveBiped.Bip01_R_UpperArm" 8
10 "ValveBiped.Bip01_R_Forearm" 9
So the R_ForeArm is a child of R_UpperArm.
Is this the original skeleton or did you change something?
It's a little bit of work to apply the missing 58 bones for Jackie and do the parenting.

There are 4 "Spines". Guess you renamed Spine4 of SMD to Spine3 of Jackie?

> The skeleton I'm using is in Source Engine .SMD format. There are Blender plugins available for it.Thx. I was always fiddeling around with .x, fbx and so on. Didn't expect this being so easy just using SMD format.

Guess if you shared this info earlier we would have solved the SleepingDogs skeleton problem 3 months ago.  

> However, unless we have the original Sleeping Dogs skeleton there's always going to be errors with the weighting.So well, I don't know if it's as easy to solve like I boasted one sentence before but should work.

But I've lots of work atm so may last some days...

What about the position of the bones? (see lower part of SMD file)
Did you adjust them? You could use the positions from the amanda xml, I guess.
(Hmm, did I upload the xml?  
[Amanda_skeleton.zip](http://www.uploadmb.com/dw.php?id=1385897148)
Ok, I will look for Jackie's or Wei's...)

edit: well, what is what?
(0.061026 -0.020621 0.000000 ) (0.707106 0.000001 0.707107 0.000001 ) (1.000000 1.000000 1.000000 )
For Amanda first brackets should be position, 2nd one the rotation.
For the SMD I'll  have to look into the format specs.
0 0.254867 -0.828583 38.566917 1.570796 -0.000000 0.000000
Guess bold values are pos x,y,z and then rotation following, because 1.57... is PI/2.

edit2: huuaah, forget about Amanda! Jackie having 127 bones!

edit6: seems the last(?) problem to solve was how to transform the hkx bone rotation values into SMD ones.
And a quarternion to euler angles conversion was required.
So here is the final(?) result (Jackie):

```
nodes
0 "ValveBiped.Bip01" -1
1 "ValveBiped.Bip01_Pelvis" 0
2 "ValveBiped.Direction" 1
3 "ValveBiped.Sync01" 2
4 "ValveBiped.Balance" 1
5 "ValveBiped.Bip01_Spine" 4
6 "ValveBiped.Bip01_Spine1" 5
7 "ValveBiped.Bip01_Spine2" 6
8 "ValveBiped.Bip01_Spine3" 7
9 "ValveBiped.Bip01_Neck" 8
10 "ValveBiped.Bip01_Head" 9
11 "ValveBiped.Bip01_L_Thigh" 1
12 "ValveBiped.Bip01_R_Thigh" 1
13 "ValveBiped.Bip01_L_Calf" 11
14 "ValveBiped.Bip01_R_Calf" 12
15 "ValveBiped.Bip01_L_Foot" 13
16 "ValveBiped.Bip01_R_Foot" 14
17 "ValveBiped.Bip01_L_Toe0" 15
18 "ValveBiped.Bip01_R_Toe0" 16
19 "ValveBiped.Bip01_L_Clavicle" 9
20 "ValveBiped.Bip01_R_Clavicle" 9
21 "ValveBiped.Bip01_L_UpperArm" 19
22 "ValveBiped.Bip01_R_UpperArm" 20
23 "ValveBiped.Bip01_L_Forearm" 21
24 "ValveBiped.Bip01_R_Forearm" 22
25 "ValveBiped.Bip01_L_Hand" 23
26 "ValveBiped.Bip01_R_Hand" 24
27 "ValveBiped.Bip01_L_Finger0" 25
28 "ValveBiped.Bip01_R_Finger0" 26
29 "ValveBiped.Bip01_L_Finger01" 27
30 "ValveBiped.Bip01_R_Finger01" 28
31 "ValveBiped.Bip01_L_Finger02" 29
32 "ValveBiped.Bip01_R_Finger02" 30
33 "ValveBiped.Bip01_L_Finger1" 25
34 "ValveBiped.Bip01_R_Finger1" 26
35 "ValveBiped.Bip01_L_Finger11" 33
36 "ValveBiped.Bip01_R_Finger11" 34
37 "ValveBiped.Bip01_L_Finger12" 35
38 "ValveBiped.Bip01_R_Finger12" 36
39 "ValveBiped.Bip01_L_Finger2" 25
40 "ValveBiped.Bip01_R_Finger2" 26
41 "ValveBiped.Bip01_L_Finger21" 39
42 "ValveBiped.Bip01_R_Finger21" 40
43 "ValveBiped.Bip01_L_Finger22" 41
44 "ValveBiped.Bip01_R_Finger22" 42
45 "ValveBiped.Bip01_L_Finger3" 25
46 "ValveBiped.Bip01_R_Finger3" 26
47 "ValveBiped.Bip01_L_Finger31" 45
48 "ValveBiped.Bip01_R_Finger31" 46
49 "ValveBiped.Bip01_L_Finger32" 47
50 "ValveBiped.Bip01_R_Finger32" 48
51 "ValveBiped.Bip01_L_Finger4" 25
52 "ValveBiped.Bip01_R_Finger4" 26
53 "ValveBiped.Bip01_L_Finger41" 51
54 "ValveBiped.Bip01_R_Finger41" 52
55 "ValveBiped.Bip01_L_Finger42" 53
56 "ValveBiped.Bip01_R_Finger42" 54
57 "ValveBiped.Bip01_L_ForeTwist" 21
58 "ValveBiped.Bip01_R_ForeTwist" 22
59 "ValveBiped.Bip01_LUpArmTwist" 19
60 "ValveBiped.Bip01_RUpArmTwist" 20
61 "ValveBiped.Bip01_L_Prop" 25
62 "ValveBiped.Bip01_R_Prop" 26
63 "ValveBiped.face_l_cheek" 10
64 "ValveBiped.face_r_cheek" 10
65 "ValveBiped.face_r_ear" 10
66 "ValveBiped.face_l_ear" 10
67 "ValveBiped.face_l_eye" 10
68 "ValveBiped.face_l_lowerEyeLid" 10
69 "ValveBiped.face_l_upperEyeLid" 10
70 "ValveBiped.face_r_eye" 10
71 "ValveBiped.face_r_upperEyeLid" 10
72 "ValveBiped.face_r_lowerEyeLid" 10
73 "ValveBiped.face_eyeBrows_sdk" 10
74 "ValveBiped.face_jaw" 10
75 "ValveBiped.face_chin" 74
76 "ValveBiped.face_tongue_1" 74
77 "ValveBiped.face_tongue_2" 76
78 "ValveBiped.face_tongue_3" 77
79 "ValveBiped.face_underChin" 74
80 "ValveBiped.face_r_nasalLabialFold" 10
81 "ValveBiped.face_l_nasalLabialFold" 10
82 "ValveBiped.face_l_temple" 10
83 "ValveBiped.face_r_temple" 10
84 "ValveBiped.face_noseMain" 10
85 "ValveBiped.face_l_nostril" 84
86 "ValveBiped.face_r_nostril" 84
87 "ValveBiped.face_skull" 10
88 "ValveBiped.face_l_brow_A" 10
89 "ValveBiped.face_l_brow_B" 10
90 "ValveBiped.face_l_brow_C" 10
91 "ValveBiped.face_r_brow_C" 10
92 "ValveBiped.face_r_brow_B" 10
93 "ValveBiped.face_r_brow_A" 10
94 "ValveBiped.face_l_innerCheek" 10
95 "ValveBiped.face_l_UpperCheek" 10
96 "ValveBiped.face_r_innerCheek" 10
97 "ValveBiped.face_r_UpperCheek" 10
98 "ValveBiped.face_r_lowerLip_atJaw" 10
99 "ValveBiped.face_r_lowerLip_b" 98
100 "ValveBiped.face_r_lowerLip_f" 98
101 "ValveBiped.face_l_lowerLip_atJaw" 10
102 "ValveBiped.face_l_lowerLip_f" 101
103 "ValveBiped.face_l_lowerLip_b" 101
104 "ValveBiped.face_lowerLip_atJaw" 10
105 "ValveBiped.face_lowerLip_f" 104
106 "ValveBiped.face_lowerLip_b" 104
107 "ValveBiped.face_r_lipCorner_atMouth" 10
108 "ValveBiped.face_r_lipCorner_t" 107
109 "ValveBiped.face_r_lipCorner_b" 107
110 "ValveBiped.face_l_lipCorner_atMouth" 10
111 "ValveBiped.face_l_lipCorner_t" 110
112 "ValveBiped.face_l_lipCorner_b" 110
113 "ValveBiped.face_upperLip" 10
114 "ValveBiped.face_upperLip_b" 113
115 "ValveBiped.face_upperLip_f" 113
116 "ValveBiped.face_l_upperLip" 10
117 "ValveBiped.face_l_upperLip_f" 116
118 "ValveBiped.face_l_upperLip_b" 116
119 "ValveBiped.face_r_upperLip" 10
120 "ValveBiped.face_r_upperLip_f" 119
121 "ValveBiped.face_r_upperLip_b" 119
122 "ValveBiped.face_adamsApple" 9
123 "ValveBiped.l_upperarm_twist" 0
124 "ValveBiped.r_upperarm_twist" 0
125 "ValveBiped.l_shoulder_joint" 0
126 "ValveBiped.r_shoulder_joint" 0
end
skeleton
time 0
0 0.000000 -0.000000 0.962432 0.000000 0.000000 -1.570795
1 0.000000 0.000000 0.000000 -0.021273 -1.570796 -1.549522
2 -0.962432 0.000000 -0.000001 1.115935 -1.570451 2.025658
3 0.000000 0.000000 -0.000000 0.000000 -0.000000 0.000000
4 0.058822 -0.019876 0.000000 1.115934 -1.569761 2.025658
5 -0.000000 -0.000000 0.000000 -1.570903 -1.570796 -1.570691
6 0.116583 -0.000093 0.000000 -0.000000 -0.000000 0.000000
7 0.116583 -0.000093 0.000000 -0.000000 -0.000000 0.000000
8 0.116583 -0.000093 0.000000 -0.000000 -0.000000 0.000000
9 0.123849 -0.018681 -0.000000 -0.000000 -0.000001 0.182813
10 0.074050 0.006895 0.000000 -0.000000 0.000000 -0.130540
11 -0.000000 0.000000 0.086709 -3.141027 -0.054466 -3.061052
12 0.000000 -0.000000 -0.086709 3.141030 0.054469 -3.061052
13 0.433544 0.000000 -0.000000 -0.000000 -0.000000 -0.000977
14 0.433544 0.000000 -0.000000 -0.000000 0.000000 -0.000977
15 0.431013 -0.000000 0.000000 -0.228499 -0.054245 0.081667
16 0.431012 0.000000 -0.000000 0.228499 0.054245 0.081667
17 0.095216 0.128370 -0.001270 0.000000 0.000000 1.570796
18 0.095216 0.128370 0.001270 -0.000000 -0.000000 1.570796
19 -0.037603 0.016762 0.036248 -0.944282 -1.403160 -2.387640
20 -0.037604 0.016762 -0.036248 0.944258 1.403164 -2.387663
21 0.158107 0.000000 0.000000 -0.036490 0.659105 -0.304214
22 0.158106 0.000000 -0.000000 0.036490 -0.659105 -0.304214
23 0.260127 0.000000 0.000000 -0.000000 0.000000 -0.148916
24 0.260127 -0.000000 -0.000000 0.000000 -0.000000 -0.148916
25 0.248671 0.000000 0.000000 -1.880375 -0.019397 0.169870
26 0.248671 -0.000000 -0.000000 1.880375 0.019397 0.169870
27 0.023226 0.003893 -0.032915 1.160342 0.687200 0.420147
28 0.023227 0.003893 0.032915 -1.160342 -0.687200 0.420147
29 0.039321 -0.000000 0.000000 -0.000000 0.000000 0.211794
30 0.039320 0.000000 0.000000 0.000000 -0.000000 0.211794
31 0.032834 0.000000 -0.000000 0.000000 -0.000000 0.016612
32 0.032834 -0.000000 -0.000000 -0.000000 0.000000 0.016612
33 0.100190 -0.000452 -0.034206 -0.000819 0.235556 -0.000191
34 0.100190 -0.000452 0.034206 0.000819 -0.235556 -0.000191
35 0.032939 0.000000 0.000000 -0.000000 -0.000000 0.085070
36 0.032939 -0.000000 -0.000000 0.000000 0.000000 0.085070
37 0.023828 0.000000 0.000000 0.000000 0.000000 0.092737
38 0.023828 -0.000000 0.000000 -0.000000 -0.000000 0.092737
39 0.104151 0.000470 -0.009029 -0.153563 0.054423 0.031572
40 0.104151 0.000470 0.009029 0.153563 -0.054423 0.031571
41 0.037698 -0.000000 -0.000000 -0.000000 -0.000000 0.026297
42 0.037698 -0.000000 0.000000 0.000000 0.000000 0.026297
43 0.027258 0.000000 0.000000 0.000000 -0.000000 0.043986
44 0.027257 0.000000 0.000000 0.000000 -0.000000 0.043985
45 0.098267 0.005354 0.016013 -0.231834 -0.118925 0.053755
46 0.098267 0.005354 -0.016013 0.231834 0.118925 0.053755
47 0.037458 0.000000 0.000000 -0.000000 -0.000000 0.048243
48 0.037458 0.000000 0.000000 0.000000 -0.000000 0.048243
49 0.026390 0.000000 0.000000 0.000000 -0.000000 -0.007270
50 0.026390 0.000000 0.000000 -0.000000 0.000000 -0.007270
51 0.089976 0.012264 0.036594 -0.216471 -0.261607 0.166656
52 0.089976 0.012264 -0.036594 0.216471 0.261607 0.166656
53 0.028257 -0.000000 0.000000 0.000000 0.000000 0.001410
54 0.028257 0.000000 -0.000000 -0.000000 -0.000000 0.001410
55 0.019769 -0.000000 0.000000 0.000000 0.000000 0.077613
56 0.019769 0.000000 -0.000000 0.000000 0.000000 0.077613
57 0.260127 -0.000000 0.000000 -0.156722 0.000000 -0.148916
58 0.260127 -0.000000 -0.000000 0.156722 -0.000000 -0.148916
59 0.158107 0.000000 -0.000000 0.055100 0.659105 -0.304214
60 0.158107 0.000000 -0.000000 -0.055100 -0.659105 -0.304214
61 -0.000000 0.000000 0.000000 -0.000000 -0.000000 -0.000000
62 -0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
63 0.043256 0.076297 0.042071 3.083818 -1.570796 0.004705
64 0.043257 0.076297 -0.042071 3.083818 -1.570796 0.004705
65 0.075768 0.002102 -0.075136 3.083818 -1.570796 0.004705
66 0.075768 0.002102 0.075136 3.083818 -1.570796 0.004705
67 0.103697 0.085590 0.030956 3.083818 -1.570796 0.004705
68 0.103696 0.085587 0.030960 3.083818 -1.570796 0.004705
69 0.103696 0.085587 0.030960 3.083818 -1.570796 0.004705
70 0.103697 0.085590 -0.030955 3.083818 -1.570796 0.004705
71 0.103696 0.085587 -0.030960 3.083818 -1.570796 0.004705
72 0.103696 0.085587 -0.030960 3.083818 -1.570796 0.004705
73 0.117689 0.099976 0.000000 3.083818 -1.570796 0.004705
74 0.067118 0.010384 -0.000000 3.083818 -1.570796 0.004705
75 0.000000 -0.079952 -0.068376 0.000000 -0.000000 -0.000000
76 0.000000 -0.039515 -0.040343 0.000000 -0.000000 -0.000000
77 0.000000 -0.020805 0.003950 0.000000 -0.000000 -0.000000
78 0.000000 -0.018515 -0.001700 0.000000 -0.000000 -0.000000
79 0.000000 -0.043359 -0.071235 0.000000 -0.000000 -0.000000
80 0.057453 0.092377 -0.029416 3.083818 -1.570796 0.004705
81 0.057453 0.092377 0.029416 3.083818 -1.570796 0.004705
82 0.121217 0.059080 0.065005 3.083818 -1.570796 0.004705
83 0.121218 0.059081 -0.065005 3.083818 -1.570796 0.004705
84 0.083968 0.109099 0.000000 3.083818 -1.570796 0.004705
85 0.014419 0.001987 -0.018189 0.000000 -0.000000 -0.000000
86 -0.014419 0.001987 -0.018189 0.000000 -0.000000 -0.000000
87 0.138003 0.026381 0.000001 3.083818 -1.570796 0.004705
88 0.116575 0.101291 0.014520 3.083818 -1.570796 0.004705
89 0.122027 0.098424 0.031072 3.083818 -1.570796 0.004705
90 0.119112 0.085987 0.047123 3.083818 -1.570796 0.004705
91 0.119113 0.085987 -0.047123 3.083818 -1.570796 0.004705
92 0.122027 0.098424 -0.031071 3.083818 -1.570796 0.004705
93 0.116575 0.101291 -0.014520 3.083818 -1.570796 0.004705
94 0.085796 0.099080 0.017472 3.083818 -1.570796 0.004705
95 0.082143 0.080503 0.052733 3.083818 -1.570796 0.004705
96 0.085796 0.099080 -0.017472 3.083818 -1.570796 0.004705
97 0.082143 0.080503 -0.052733 3.083818 -1.570796 0.004705
98 0.027610 0.106103 -0.013884 3.083818 -1.570796 0.004705
99 0.001653 0.003437 0.005604 0.000000 -0.000000 -0.000000
100 0.000031 -0.000774 0.005604 0.000000 -0.000000 -0.000000
101 0.027610 0.106103 0.013884 3.083818 -1.570796 0.004705
102 -0.000031 -0.000774 0.005604 0.000000 -0.000000 -0.000000
103 -0.001653 0.003437 0.005604 0.000000 -0.000000 -0.000000
104 0.025830 0.107732 0.000000 3.083818 -1.570796 0.004705
105 -0.000000 -0.002433 0.004772 0.000000 -0.000000 -0.000000
106 -0.000000 0.003120 0.006052 0.000000 -0.000000 -0.000000
107 0.034726 0.098279 -0.025200 3.083818 -1.570796 0.004705
108 0.002679 0.000014 0.003726 0.000000 -0.000000 -0.000000
109 0.003004 0.000626 -0.003602 0.000000 -0.000000 -0.000000
110 0.034726 0.098279 0.025200 3.083818 -1.570796 0.004705
111 -0.002679 0.000014 0.003726 0.000000 -0.000000 -0.000000
112 -0.003004 0.000627 -0.003602 0.000000 -0.000000 -0.000000
113 0.047898 0.111297 -0.000000 3.083818 -1.570796 0.004705
114 0.000000 0.006970 -0.008527 0.000000 -0.000000 -0.000000
115 0.000000 -0.000842 -0.008527 0.000000 -0.000000 -0.000000
116 0.045863 0.107459 0.013013 3.083818 -1.570796 0.004705
117 0.001010 -0.000675 -0.006109 0.000000 -0.000000 -0.000000
118 -0.001449 0.004165 -0.006109 0.000000 -0.000000 -0.000000
119 0.045863 0.107459 -0.013013 3.083818 -1.570796 0.004705
120 -0.001010 -0.000675 -0.006109 0.000000 -0.000000 -0.000000
121 0.001449 0.004165 -0.006109 0.000000 -0.000000 -0.000000
122 0.052228 0.051975 0.000000 2.959754 -1.570796 -0.001771
123 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
124 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
125 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
126 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
end
```
## Post #94
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-12-01T19:03:40+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from shakotay2
>
> Does the imported skeleton have the same bone count? Means are there bones to add or to delete?
No, it doesn't. That's what I was saying, unless you have the original skeleton there's going to be some missing/misplaced bones, like those 50 face bones. Only thing I changed was the position of the arm and fingers so they fit the mesh.


Well, I don't really see any issues with parenting, but [it's still rather borked](http://puu.sh/5z24o.png). Still, that's pretty awesome you got the all the bones already.

And by the way, you can find complete documentation on the .SMD format [here](https://developer.valvesoftware.com/wiki/Studiomdl_Data).
## Post #95
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-01T21:19:09+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Well, I don't really see any issues with parenting, but it's still rather borked.Which version it is? Yours or the SMD I posted?

> And by the way, you can find complete documentation on the .SMD format here.Thx, I used it already for the building of the said SMD.

Which importer do you use? This one?
Based on a nonworking script copyright (c) 2005 Michael Fuller                    |
# | [http://www.3D2Toy.com](http://www.3D2Toy.com)                                   |
# | [SlashAndBurn@3D2Toy.com](mailto:SlashAndBurn@3D2Toy.com)                                 |
# | June 30, 2005                                           |
# | Revised to Blender 2.42 standards and made functional by Eric Finley (Hellequin), 2007

Because even my last SMD version with euler angles doesn't look as good as yours.
## Post #96
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-12-01T21:24:08+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

That one certainly is better, but it's still skewed. 

Also, that's another problem. I use Blender 2.66 with [BlenderSourceTools](http://steamreview.org/BlenderSourceTools/), so there might be some compatibility issues there.
## Post #97
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-02T07:48:51+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> That one certainly is better, but it's still skewed.I released a new version (see 4 posts above).
Unbelieveable - finally I managed a hkx to SMD conversion. 



JackieSkeleton.JPG (18.28 KiB) Viewed 175 times
## Post #98
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-12-02T08:07:44+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Well, that was quick, not mention simply amazing. You truly are a talented fellow.   


Wait, hold on, I'm confused. How does this system work? Is there one master skeleton for all models and each .perm.bin assigns the weights to it, or does each model have it's own skeleton?

Reason I ask is that Jackie has a lot of extra face bones that the generic thugs don't have.
## Post #99
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-02T08:33:29+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Well, that was quick, not mention simply amazing. You truly are a talented fellow.Well, after your tip with the SMD it was just a simple conversion. (Talented people would understand the QuarternionToEuler formula in depth.  )


> How does this system work? Is there one master skeleton for all models and each .perm.bin assigns the weights to it, or does each model have it's own skeleton?
>
> 
>
> Reason I ask is that Jackie has a lot of extra face bones that the generic thugs don't have.You will have to find out this for yourself, I fear. Have a look at CharacterRigs.bin and tell me which chars skeletons you need.
(Where "Wei head" is a complete char afair.)

Amanda.smd

```
nodes
0 "ValveBiped.Bip01" -1
1 "ValveBiped.Bip01_Pelvis" 0
2 "ValveBiped.Direction" 1
3 "ValveBiped.Sync01" 2
4 "ValveBiped.Balance" 1
5 "ValveBiped.Bip01_Spine" 4
6 "ValveBiped.Bip01_Spine1" 5
7 "ValveBiped.Bip01_Spine2" 6
8 "ValveBiped.Bip01_Spine3" 7
9 "ValveBiped.Bip01_Neck" 8
10 "ValveBiped.Bip01_Head" 9
11 "ValveBiped.Bip01_L_Thigh" 1
12 "ValveBiped.Bip01_R_Thigh" 1
13 "ValveBiped.Bip01_L_Calf" 11
14 "ValveBiped.Bip01_R_Calf" 12
15 "ValveBiped.Bip01_L_Foot" 13
16 "ValveBiped.Bip01_R_Foot" 14
17 "ValveBiped.Bip01_L_Toe0" 15
18 "ValveBiped.Bip01_R_Toe0" 16
19 "ValveBiped.Bip01_L_Clavicle" 9
20 "ValveBiped.Bip01_R_Clavicle" 9
21 "ValveBiped.Bip01_L_UpperArm" 19
22 "ValveBiped.Bip01_R_UpperArm" 20
23 "ValveBiped.Bip01_L_Forearm" 21
24 "ValveBiped.Bip01_R_Forearm" 22
25 "ValveBiped.Bip01_L_Hand" 23
26 "ValveBiped.Bip01_R_Hand" 24
27 "ValveBiped.Bip01_L_Finger0" 25
28 "ValveBiped.Bip01_R_Finger0" 26
29 "ValveBiped.Bip01_L_Finger01" 27
30 "ValveBiped.Bip01_R_Finger01" 28
31 "ValveBiped.Bip01_L_Finger02" 29
32 "ValveBiped.Bip01_R_Finger02" 30
33 "ValveBiped.Bip01_L_Finger1" 25
34 "ValveBiped.Bip01_R_Finger1" 26
35 "ValveBiped.Bip01_L_Finger11" 33
36 "ValveBiped.Bip01_R_Finger11" 34
37 "ValveBiped.Bip01_L_Finger12" 35
38 "ValveBiped.Bip01_R_Finger12" 36
39 "ValveBiped.Bip01_L_Finger2" 25
40 "ValveBiped.Bip01_R_Finger2" 26
41 "ValveBiped.Bip01_L_Finger21" 39
42 "ValveBiped.Bip01_R_Finger21" 40
43 "ValveBiped.Bip01_L_Finger22" 41
44 "ValveBiped.Bip01_R_Finger22" 42
45 "ValveBiped.Bip01_L_Finger3" 25
46 "ValveBiped.Bip01_R_Finger3" 26
47 "ValveBiped.Bip01_L_Finger31" 45
48 "ValveBiped.Bip01_R_Finger31" 46
49 "ValveBiped.Bip01_L_Finger32" 47
50 "ValveBiped.Bip01_R_Finger32" 48
51 "ValveBiped.Bip01_L_Finger4" 25
52 "ValveBiped.Bip01_R_Finger4" 26
53 "ValveBiped.Bip01_L_Finger41" 51
54 "ValveBiped.Bip01_R_Finger41" 52
55 "ValveBiped.Bip01_L_Finger42" 53
56 "ValveBiped.Bip01_R_Finger42" 54
57 "ValveBiped.Bip01_L_ForeTwist" 21
58 "ValveBiped.Bip01_R_ForeTwist" 22
59 "ValveBiped.Bip01 LUpArmTwist" 19
60 "ValveBiped.Bip01 RUpArmTwist" 20
61 "ValveBiped.Bip01_L_Prop" 25
62 "ValveBiped.Bip01_R_Prop" 26
63 "ValveBiped.face_ingame_jaw" 10
64 "ValveBiped.face_ingame_r_upper_lip" 10
65 "ValveBiped.face_ingame_r_lip" 10
66 "ValveBiped.face_ingame_l_lip" 10
67 "ValveBiped.face_ingame_l_upper_lip" 10
68 "ValveBiped.face_ingame_l_upper_eyelid" 10
69 "ValveBiped.face_ingame_l_outer_eyebrow" 10
70 "ValveBiped.face_ingame_l_inner_eyebrow" 10
71 "ValveBiped.face_ingame_r_outer_eyebrow" 10
72 "ValveBiped.face_ingame_r_inner_eyebrow" 10
73 "ValveBiped.face_ingame_r_upper_eyelid" 10
74 "ValveBiped.face_ingame_r_eye" 10
75 "ValveBiped.face_ingame_l_eye" 10
76 "ValveBiped.face_ingame_r_lower_lip" 63
77 "ValveBiped.face_ingame_l_lower_lip" 63
78 "ValveBiped.CameraSync01" 0
79 "ValveBiped.Bip01_L_Hand_Effector" 0
80 "ValveBiped.Bip01_R_Hand_Effector" 0
81 "ValveBiped.l_upperarm_twist" 0
82 "ValveBiped.r_upperarm_twist" 0
83 "ValveBiped.l_shoulder_joint" 0
84 "ValveBiped.r_shoulder_joint" 0
end
skeleton
time 0
0 0.000000 -0.000000 0.998452 0.000000 -0.000000 -1.570795
1 0.000000 0.000000 0.000000 -0.021273 -1.570796 -1.549522
2 -0.998452 0.000000 -0.000001 1.115935 -1.570451 2.025658
3 0.000000 0.000000 -0.000000 0.000000 -0.000000 0.000000
4 0.061026 -0.020621 0.000000 1.166445 -1.569951 1.975148
5 0.000000 0.000000 0.000000 -1.571009 -1.570796 -1.570585
6 0.120951 -0.000096 0.000000 -0.000000 -0.000000 -0.000000
7 0.120951 -0.000096 0.000000 -0.000000 -0.000000 -0.000000
8 0.120951 -0.000096 0.000000 -0.000000 -0.000000 -0.000000
9 0.128489 -0.019381 -0.000000 -0.000000 -0.000001 0.182813
10 0.077599 0.006855 0.000000 -0.000000 0.000000 -0.130540
11 -0.000000 0.000000 0.089957 -3.141027 -0.054466 -3.061052
12 0.000000 -0.000000 -0.089957 3.141030 0.054469 -3.061052
13 0.449787 0.000000 -0.000000 0.000000 0.000000 -0.000977
14 0.449787 0.000000 -0.000000 -0.000000 -0.000000 -0.000977
15 0.447161 0.000000 -0.000000 -0.228499 -0.054245 0.081667
16 0.447161 0.000000 -0.000000 0.228499 0.054246 0.081667
17 0.098783 0.133179 -0.001318 0.000000 -0.000000 1.570796
18 0.098783 0.133180 0.001318 0.000000 -0.000000 1.570796
19 -0.039012 0.017390 0.037606 -0.944282 -1.403160 -2.387639
20 -0.039012 0.017390 -0.037606 0.944258 1.403165 -2.387663
21 0.164030 0.000000 0.000000 -0.036490 0.659105 -0.304214
22 0.164030 0.000000 0.000000 0.036490 -0.659105 -0.304214
23 0.269872 0.000000 0.000000 -0.000000 -0.000000 -0.148916
24 0.269872 0.000000 0.000000 0.000000 -0.000000 -0.148916
25 0.257988 0.000000 0.000000 -1.880375 -0.019397 0.169870
26 0.257988 0.000000 -0.000000 1.880375 0.019397 0.169870
27 0.024097 0.004039 -0.034148 1.160342 0.687200 0.420147
28 0.024097 0.004039 0.034148 -1.160342 -0.687200 0.420147
29 0.040793 0.000000 0.000000 -0.000000 -0.000000 0.211794
30 0.040794 -0.000000 0.000000 0.000000 -0.000000 0.211794
31 0.034064 -0.000000 0.000000 0.000000 -0.000000 0.016612
32 0.034064 0.000000 -0.000000 -0.000000 0.000000 0.016612
33 0.103943 -0.000469 -0.035487 -0.000819 0.235556 -0.000191
34 0.103943 -0.000468 0.035487 0.000819 -0.235556 -0.000191
35 0.034173 0.000000 -0.000000 -0.000000 -0.000000 0.085069
36 0.034173 0.000000 -0.000000 0.000000 -0.000000 0.085069
37 0.024721 0.000000 0.000000 0.000000 0.000000 0.092737
38 0.024721 -0.000000 -0.000000 -0.000000 -0.000000 0.092737
39 0.108053 0.000488 -0.009367 -0.153563 0.054423 0.031571
40 0.108054 0.000488 0.009367 0.153563 -0.054423 0.031572
41 0.039110 -0.000000 0.000000 -0.000000 -0.000000 0.026296
42 0.039110 0.000000 0.000000 0.000000 -0.000000 0.026296
43 0.028279 -0.000000 0.000000 0.000000 0.000000 0.043986
44 0.028279 0.000000 0.000000 0.000000 -0.000000 0.043986
45 0.101948 0.005554 0.016613 -0.231834 -0.118925 0.053755
46 0.101949 0.005554 -0.016613 0.231834 0.118925 0.053755
47 0.038861 0.000000 -0.000000 -0.000000 0.000000 0.048242
48 0.038861 0.000000 0.000000 -0.000000 0.000000 0.048242
49 0.027379 0.000000 0.000000 0.000000 -0.000000 -0.007270
50 0.027379 0.000000 0.000000 0.000000 -0.000000 -0.007270
51 0.093347 0.012724 0.037965 -0.216471 -0.261607 0.166656
52 0.093347 0.012723 -0.037965 0.216471 0.261607 0.166656
53 0.029316 0.000000 0.000000 -0.000000 -0.000000 0.001411
54 0.029315 0.000000 0.000000 -0.000000 0.000000 0.001411
55 0.020510 -0.000000 -0.000000 0.000000 0.000000 0.077614
56 0.020510 0.000000 0.000000 -0.000000 0.000000 0.077614
57 0.269872 0.000000 0.000000 -0.156721 0.000000 -0.148916
58 0.269873 -0.000000 0.000000 0.156722 -0.000000 -0.148916
59 0.164030 0.000000 0.000000 0.055100 0.659105 -0.304214
60 0.164030 0.000000 0.000000 -0.055100 -0.659105 -0.304214
61 0.000000 -0.000000 0.000000 -0.000000 0.000000 -0.000000
62 0.000000 0.000000 0.000000 -0.000000 0.000000 0.000000
63 0.056289 0.038189 0.000000 3.141592 -0.000001 2.315846
64 0.042051 0.130099 -0.010145 3.004401 -1.569761 1.654919
65 0.034547 0.119311 -0.029236 3.004401 -1.569761 1.654919
66 0.034855 0.119413 0.029000 3.004401 -1.569761 1.654919
67 0.042487 0.130076 0.010000 3.004401 -1.569761 1.654919
68 0.110077 0.119171 0.031871 -0.533632 -1.570796 -1.090232
69 0.125814 0.117931 0.045000 -0.533632 -1.570796 -1.090232
70 0.125325 0.125936 0.013712 -0.533632 -1.570796 -1.090232
71 0.125812 0.117901 -0.044606 -0.659283 -1.570796 -0.964581
72 0.125419 0.126140 -0.014382 -0.533632 -1.570796 -1.090232
73 0.110070 0.119172 -0.029652 -0.533632 -1.570796 -1.090232
74 0.104714 0.096337 -0.030181 -3.141341 -1.569177 1.517475
75 0.104716 0.096389 0.030080 -0.015546 -1.570024 -1.608319
76 0.083468 0.041496 0.009548 0.849986 1.570796 -3.064284
77 0.083603 0.041024 -0.010000 1.738467 1.570451 -2.175804
78 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
79 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
80 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
81 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
82 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
83 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
84 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
end
```
## Post #100
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-12-02T08:41:55+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

[Beautiful!](http://puu.sh/5zGF5.jpg) The vertex groups match the skeleton perfectly.


> Reply from shakotay2
>
> You will have to find out this for yourself, I fear. Have a look at CharacterRigs.bin and tell me which chars skeletons you need.
(Where "Wei head" is a complete char afair.)
Ahh, okay. CharacterRigs contains all the skeletons, so it's just a matter of pulling out the data into an xml, then converting it to smd?
I'll poke around and see what I can find.

EDIT: Oh jeez, every main character has their own skeleton. How about 'PrimaryBasicMale' to start?

Also, can you please leave the bone names intact? That way they will match the original weight group names. I can rename them myself as necessary.
## Post #101
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-02T09:26:28+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Ahh, okay. CharacterRigs contains all the skeletons, so it's just a matter of pulling out the data into an xml, then converting it to smd?With some manual editing required, yes.

> Also, can you please leave the bone names intact? That way they will match the original weight group names. I can rename them myself as necessary.Yep. Wasn't sure about the needs of the SMD importer. So I left "ValveBiped." (You can simply replace it by an empty string in a text editor.)

PrimaryBasicMale

```
nodes
0 "ValveBiped.Bip01" -1
1 "ValveBiped.Bip01 Pelvis" 0
2 "ValveBiped.Direction" 1
3 "ValveBiped.Sync01" 2
4 "ValveBiped.Balance" 1
5 "ValveBiped.Bip01 Spine" 4
6 "ValveBiped.Bip01 Spine1" 5
7 "ValveBiped.Bip01 Spine2" 6
8 "ValveBiped.Bip01 Spine3" 7
9 "ValveBiped.Bip01 Neck" 8
10 "ValveBiped.Bip01 Head" 9
11 "ValveBiped.Bip01 L Thigh" 1
12 "ValveBiped.Bip01 R Thigh" 1
13 "ValveBiped.Bip01 L Calf" 11
14 "ValveBiped.Bip01 R Calf" 12
15 "ValveBiped.Bip01 L Foot" 13
16 "ValveBiped.Bip01 R Foot" 14
17 "ValveBiped.Bip01 L Toe0" 15
18 "ValveBiped.Bip01 R Toe0" 16
19 "ValveBiped.Bip01 L Clavicle" 9
20 "ValveBiped.Bip01 R Clavicle" 9
21 "ValveBiped.Bip01 L UpperArm" 19
22 "ValveBiped.Bip01 R UpperArm" 20
23 "ValveBiped.Bip01 L Forearm" 21
24 "ValveBiped.Bip01 R Forearm" 22
25 "ValveBiped.Bip01 L Hand" 23
26 "ValveBiped.Bip01 R Hand" 24
27 "ValveBiped.Bip01 L Finger0" 25
28 "ValveBiped.Bip01 R Finger0" 26
29 "ValveBiped.Bip01 L Finger01" 27
30 "ValveBiped.Bip01 R Finger01" 28
31 "ValveBiped.Bip01 L Finger02" 29
32 "ValveBiped.Bip01 R Finger02" 30
33 "ValveBiped.Bip01 L Finger1" 25
34 "ValveBiped.Bip01 R Finger1" 26
35 "ValveBiped.Bip01 L Finger11" 33
36 "ValveBiped.Bip01 R Finger11" 34
37 "ValveBiped.Bip01 L Finger12" 35
38 "ValveBiped.Bip01 R Finger12" 36
39 "ValveBiped.Bip01 L Finger2" 25
40 "ValveBiped.Bip01 R Finger2" 26
41 "ValveBiped.Bip01 L Finger21" 39
42 "ValveBiped.Bip01 R Finger21" 40
43 "ValveBiped.Bip01 L Finger22" 41
44 "ValveBiped.Bip01 R Finger22" 42
45 "ValveBiped.Bip01 L Finger3" 25
46 "ValveBiped.Bip01 R Finger3" 26
47 "ValveBiped.Bip01 L Finger31" 45
48 "ValveBiped.Bip01 R Finger31" 46
49 "ValveBiped.Bip01 L Finger32" 47
50 "ValveBiped.Bip01 R Finger32" 48
51 "ValveBiped.Bip01 L Finger4" 25
52 "ValveBiped.Bip01 R Finger4" 26
53 "ValveBiped.Bip01 L Finger41" 51
54 "ValveBiped.Bip01 R Finger41" 52
55 "ValveBiped.Bip01 L Finger42" 53
56 "ValveBiped.Bip01 R Finger42" 54
57 "ValveBiped.Bip01 L ForeTwist" 21
58 "ValveBiped.Bip01 R ForeTwist" 22
59 "ValveBiped.Bip01 LUpArmTwist" 19
60 "ValveBiped.Bip01 RUpArmTwist" 20
61 "ValveBiped.Bip01 L Prop" 25
62 "ValveBiped.Bip01 R Prop" 26
63 "ValveBiped.face_ingame_jaw" 10
64 "ValveBiped.face_ingame_r_upper_lip" 10
65 "ValveBiped.face_ingame_r_lip" 10
66 "ValveBiped.face_ingame_l_lip" 10
67 "ValveBiped.face_ingame_l_upper_lip" 10
68 "ValveBiped.face_ingame_l_upper_eyelid" 10
69 "ValveBiped.face_ingame_l_outer_eyebrow" 10
70 "ValveBiped.face_ingame_l_inner_eyebrow" 10
71 "ValveBiped.face_ingame_r_outer_eyebrow" 10
72 "ValveBiped.face_ingame_r_inner_eyebrow" 10
73 "ValveBiped.face_ingame_r_upper_eyelid" 10
74 "ValveBiped.face_ingame_r_eye" 10
75 "ValveBiped.face_ingame_l_eye" 10
76 "ValveBiped.face_ingame_r_lower_lip" 63
77 "ValveBiped.face_ingame_l_lower_lip" 63
78 "ValveBiped.CameraSync01" 2
79 "ValveBiped.Bip01 L Hand Effector" 25
80 "ValveBiped.Bip01 R Hand Effector" 26
81 "ValveBiped.l_upperarm_twist" 0
82 "ValveBiped.r_upperarm_twist" 0
83 "ValveBiped.l_shoulder_joint" 0
84 "ValveBiped.r_shoulder_joint" 0
end
skeleton
time 0
0 0.000000 -0.000000 1.000106 0.000000 -0.000000 -1.570795
1 0.000000 0.000000 0.000000 -0.021273 -1.570796 -1.549522
2 -1.000106 0.000158 -0.000001 0.000000 -1.570451 0.000000
3 0.000000 0.000000 0.000000 -0.000000 -0.000000 0.000000
4 0.061128 -0.020655 0.000000 -2.063639 -1.569761 -1.077949
5 -0.000000 0.000000 -0.000000 -1.572714 -1.570796 -1.568883
6 0.121151 -0.000097 0.000000 -0.000000 -0.000000 0.000000
7 0.121151 -0.000096 0.000000 -0.000000 -0.000000 0.000000
8 0.121151 -0.000096 0.000000 -0.000000 -0.000000 0.000000
9 0.128702 -0.019413 -0.000000 -0.000000 -0.000001 0.182813
10 0.077535 0.006895 0.000000 -0.000000 0.000000 -0.130540
11 -0.000000 0.000000 0.090107 -3.141027 -0.054466 -3.061052
12 0.000000 -0.000000 -0.090107 3.141030 0.054469 -3.061052
13 0.450533 0.000000 0.000000 0.000000 0.000000 -0.000977
14 0.450533 -0.000000 0.000000 -0.000000 0.000000 -0.000977
15 0.447902 0.000000 -0.000000 -0.228499 -0.054245 0.081667
16 0.447902 0.000000 0.000000 0.228499 0.054246 0.081667
17 0.098947 0.133400 -0.001520 0.000000 0.000000 1.570796
18 0.098947 0.133400 0.001520 0.000000 -0.000000 1.570796
19 -0.039077 0.017418 0.037668 -0.944282 -1.403160 -2.387640
20 -0.039077 0.017419 -0.037668 0.944258 1.403164 -2.387663
21 0.164302 0.000000 -0.000000 -0.036490 0.659105 -0.304214
22 0.164302 -0.000000 0.000000 0.036490 -0.659105 -0.304214
23 0.270320 0.000000 0.000000 -0.000000 -0.000000 -0.148916
24 0.270320 0.000000 -0.000000 0.000000 -0.000000 -0.148916
25 0.258416 -0.000000 0.000000 -1.880375 -0.019397 0.169870
26 0.258415 0.000000 0.000000 1.880375 0.019397 0.169870
27 0.024137 0.004046 -0.034205 1.160342 0.687200 0.420147
28 0.024137 0.004046 0.034205 -1.160342 -0.687200 0.420147
29 0.040861 0.000000 0.000000 -0.000000 0.000000 0.211794
30 0.040861 0.000000 0.000000 -0.000000 0.000000 0.211794
31 0.034121 -0.000000 0.000000 0.000000 0.000000 0.016612
32 0.034120 -0.000000 -0.000000 0.000000 0.000000 0.016612
33 0.104115 -0.000469 -0.035546 -0.000819 0.235556 -0.000191
34 0.104115 -0.000469 0.035546 0.000819 -0.235556 -0.000191
35 0.034230 -0.000000 -0.000000 0.000000 0.000000 0.085069
36 0.034230 0.000000 -0.000000 0.000000 -0.000000 0.085069
37 0.024762 0.000000 0.000000 -0.000000 0.000000 0.092737
38 0.024762 0.000000 0.000000 -0.000000 0.000000 0.092737
39 0.108233 0.000489 -0.009383 -0.153563 0.054423 0.031571
40 0.108232 0.000489 0.009383 0.153563 -0.054423 0.031572
41 0.039175 0.000000 -0.000000 -0.000000 0.000000 0.026296
42 0.039175 0.000000 0.000000 -0.000000 -0.000000 0.026296
43 0.028326 -0.000000 0.000000 -0.000000 -0.000000 0.043986
44 0.028326 -0.000000 -0.000000 0.000000 -0.000000 0.043986
45 0.102118 0.005564 0.016640 -0.231834 -0.118925 0.053755
46 0.102117 0.005563 -0.016640 0.231834 0.118925 0.053755
47 0.038925 0.000000 0.000000 -0.000000 0.000000 0.048242
48 0.038925 0.000000 0.000000 -0.000000 0.000000 0.048242
49 0.027424 0.000000 -0.000000 0.000000 -0.000000 -0.007270
50 0.027424 -0.000000 -0.000000 0.000000 0.000000 -0.007270
51 0.093502 0.012745 0.038028 -0.216471 -0.261607 0.166656
52 0.093502 0.012744 -0.038028 0.216471 0.261607 0.166656
53 0.029364 -0.000000 -0.000000 0.000000 -0.000000 0.001411
54 0.029364 -0.000000 0.000000 -0.000000 0.000000 0.001411
55 0.020544 0.000000 0.000000 -0.000000 0.000000 0.077614
56 0.020544 0.000000 0.000000 -0.000000 -0.000000 0.077614
57 0.270320 0.000000 -0.000000 -0.156722 0.000000 -0.148916
58 0.270320 0.000000 0.000000 0.156722 -0.000000 -0.148916
59 0.164302 0.000000 -0.000000 0.055100 0.659105 -0.304214
60 0.164302 0.000000 0.000000 -0.055100 -0.659105 -0.304214
61 0.000000 0.000000 0.000000 0.000000 0.000000 -0.000000
62 0.000000 -0.000000 0.000000 0.000000 0.000000 0.000000
63 0.066071 0.031861 -0.000000 3.141592 -0.000001 2.315846
64 0.039590 0.117704 -0.012443 3.004401 -1.569761 1.654919
65 0.032684 0.104028 -0.024607 3.004401 -1.569761 1.654919
66 0.032644 0.104149 0.025000 3.004401 -1.569761 1.654919
67 0.040026 0.117681 0.012000 3.004401 -1.569761 1.654919
68 0.108869 0.103460 0.030330 -0.523877 -1.570796 -1.099988
69 0.122648 0.106010 0.042000 -0.523877 -1.570796 -1.099988
70 0.115113 0.112081 0.013713 -0.523877 -1.570796 -1.099988
71 0.122648 0.106010 -0.042181 -0.659283 -1.570796 -0.964581
72 0.115208 0.112286 -0.014382 -0.523877 -1.570796 -1.099988
73 0.108869 0.103460 -0.030454 -0.523877 -1.570796 -1.099988
74 0.105064 0.088901 -0.029925 -3.141383 -1.569214 1.517517
75 0.105067 0.088954 0.028735 -0.004316 -1.570024 -1.619549
76 0.087429 0.028968 0.011846 0.677796 1.570451 3.046711
77 0.087384 0.028923 -0.012000 1.712157 1.570451 -2.202114
78 0.000000 -0.000158 1.062333 -0.017080 -0.000001 -0.000000
79 0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
80 0.000000 0.000000 0.000000 -0.000001 0.000000 0.000000
81 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
82 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
83 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
84 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
end
```
 (Very similar to Amanda.)
I'm off now for the rest of the day...
## Post #102
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-12-02T09:29:18+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Well, the female models have different arm positions than male models.

Anyhow, that'll work. Thanks!
## Post #103
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-12-03T04:05:42+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Hm, there seem to be multiple weighting errors with the police models. However, that's an issue with the Blender script, and in any case I'm sure I can fix the weights manually.


Anyway, right now the important ones are the thugs. 
There are four types of enemies in this game: Brawler, Grappler, Quick, and Striker. The Brawler and Quick skeletons are plainly labeled in CharacterRigs, but the other two seem to be elsewhere. 

There's also the possibility they share skeletons. After all, their reference meshes aren't that different. Could you please get the Brawler and Quick ones? Once I figure this out there shouldn't be any more skeletons necessary.
## Post #104
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-03T08:56:13+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Brawler:

```
nodes
0 "Bip01" -1
1 "Bip01 Pelvis" 0
2 "Direction" 1
3 "Sync01" 2
4 "Balance" 1
5 "Bip01 Spine" 4
6 "Bip01 Spine1" 5
7 "Bip01 Spine2" 6
8 "Bip01 Spine3" 7
9 "Bip01 Neck" 8
10 "Bip01 Head" 9
11 "Bip01 L Thigh" 1
12 "Bip01 R Thigh" 1
13 "Bip01 L Calf" 11
14 "Bip01 R Calf" 12
15 "Bip01 L Foot" 13
16 "Bip01 R Foot" 14
17 "Bip01 L Toe0" 15
18 "Bip01 R Toe0" 16
19 "Bip01 L Clavicle" 9
20 "Bip01 R Clavicle" 9
21 "Bip01 L UpperArm" 19
22 "Bip01 R UpperArm" 20
23 "Bip01 L Forearm" 21
24 "Bip01 R Forearm" 22
25 "Bip01 L Hand" 23
26 "Bip01 R Hand" 24
27 "Bip01 L Finger0" 25
28 "Bip01 R Finger0" 26
29 "Bip01 L Finger01" 27
30 "Bip01 R Finger01" 28
31 "Bip01 L Finger02" 29
32 "Bip01 R Finger02" 30
33 "Bip01 L Finger1" 25
34 "Bip01 R Finger1" 26
35 "Bip01 L Finger11" 33
36 "Bip01 R Finger11" 34
37 "Bip01 L Finger12" 35
38 "Bip01 R Finger12" 36
39 "Bip01 L Finger2" 25
40 "Bip01 R Finger2" 26
41 "Bip01 L Finger21" 39
42 "Bip01 R Finger21" 40
43 "Bip01 L Finger22" 41
44 "Bip01 R Finger22" 42
45 "Bip01 L Finger3" 25
46 "Bip01 R Finger3" 26
47 "Bip01 L Finger31" 45
48 "Bip01 R Finger31" 46
49 "Bip01 L Finger32" 47
50 "Bip01 R Finger32" 48
51 "Bip01 L Finger4" 25
52 "Bip01 R Finger4" 26
53 "Bip01 L Finger41" 51
54 "Bip01 R Finger41" 52
55 "Bip01 L Finger42" 53
56 "Bip01 R Finger42" 54
57 "Bip01 L ForeTwist" 21
58 "Bip01 R ForeTwist" 22
59 "Bip01 LUpArmTwist" 19
60 "Bip01 RUpArmTwist" 20
61 "Bip01 L Prop" 25
62 "Bip01 R Prop" 26
63 "face_ingame_jaw" 10
64 "face_ingame_r_upper_lip" 10
65 "face_ingame_r_lip" 10
66 "face_ingame_l_lip" 10
67 "face_ingame_l_upper_lip" 10
68 "face_ingame_l_upper_eyelid" 10
69 "face_ingame_l_outer_eyebrow" 10
70 "face_ingame_l_inner_eyebrow" 10
71 "face_ingame_r_outer_eyebrow" 10
72 "face_ingame_r_inner_eyebrow" 10
73 "face_ingame_r_upper_eyelid" 10
74 "face_ingame_r_eye" 10
75 "face_ingame_l_eye" 10
76 "face_ingame_r_lower_lip" 63
77 "face_ingame_l_lower_lip" 63
78 "CameraSync01" 0
79 "Bip01 L Hand Effector" 0
80 "Bip01 R Hand Effector" 0
81 "l_upperarm_twist" 0
82 "r_upperarm_twist" 0
83 "l_shoulder_joint" 0
84 "r_shoulder_joint" 0
end
skeleton
time 0
0 0.000000 -0.000000 0.998452 0.000000 -0.000000 -1.570795
1 0.000000 0.000000 0.000000 -0.021273 -1.570796 -1.549522
2 -0.998452 0.000000 -0.000001 1.115935 -1.570451 2.025658
3 0.000000 0.000000 -0.000000 0.000000 -0.000000 0.000000
4 0.061026 -0.020621 0.000000 1.115934 -1.569761 2.025658
5 0.000000 -0.000000 0.000000 -1.570903 -1.570796 -1.570691
6 0.120951 -0.000096 0.000000 -0.000000 -0.000000 0.000000
7 0.120951 -0.000096 0.000000 -0.000000 -0.000000 0.000000
8 0.120951 -0.000096 0.000000 -0.000000 -0.000000 0.000000
9 0.128489 -0.019381 -0.000000 -0.000000 -0.000001 0.182813
10 0.077382 0.006895 0.000000 -0.000000 0.000000 -0.130540
11 -0.000000 0.000000 0.089957 -3.141027 -0.054466 -3.061052
12 0.000000 -0.000000 -0.089957 3.141030 0.054469 -3.061052
13 0.449787 0.000000 0.000000 0.000000 0.000000 -0.000977
14 0.449787 0.000000 0.000000 -0.000000 -0.000000 -0.000977
15 0.447161 0.000000 -0.000000 -0.228499 -0.054245 0.081667
16 0.447161 0.000000 -0.000000 0.228499 0.054246 0.081667
17 0.098783 0.133179 -0.001318 0.000000 -0.000000 1.570796
18 0.098783 0.133180 0.001318 0.000000 -0.000000 1.570796
19 -0.039012 0.017390 0.037606 -0.944282 -1.403160 -2.387639
20 -0.039012 0.017390 -0.037606 0.944258 1.403165 -2.387663
21 0.164030 0.000000 0.000000 -0.036490 0.659105 -0.304214
22 0.164030 0.000000 -0.000000 0.036490 -0.659105 -0.304214
23 0.269872 0.000000 0.000000 -0.000000 0.000000 -0.148916
24 0.269873 0.000000 0.000000 0.000000 -0.000000 -0.148916
25 0.257988 0.000000 0.000000 -1.880375 -0.019397 0.169870
26 0.257988 0.000000 -0.000000 1.880375 0.019397 0.169870
27 0.024097 0.004039 -0.034148 1.160342 0.687200 0.420147
28 0.024097 0.004039 0.034148 -1.160342 -0.687200 0.420147
29 0.040794 0.000000 0.000000 -0.000000 -0.000000 0.211794
30 0.040794 -0.000000 0.000000 0.000000 -0.000000 0.211794
31 0.034064 -0.000000 0.000000 0.000000 -0.000000 0.016612
32 0.034064 0.000000 -0.000000 -0.000000 0.000000 0.016612
33 0.103943 -0.000469 -0.035487 -0.000819 0.235556 -0.000191
34 0.103943 -0.000468 0.035487 0.000819 -0.235556 -0.000191
35 0.034173 0.000000 -0.000000 -0.000000 -0.000000 0.085069
36 0.034173 0.000000 0.000000 0.000000 0.000000 0.085069
37 0.024721 0.000000 0.000000 0.000000 0.000000 0.092737
38 0.024721 -0.000000 -0.000000 -0.000000 -0.000000 0.092737
39 0.108053 0.000488 -0.009367 -0.153563 0.054423 0.031571
40 0.108054 0.000488 0.009367 0.153563 -0.054423 0.031572
41 0.039110 -0.000000 -0.000000 -0.000000 -0.000000 0.026296
42 0.039110 0.000000 0.000000 0.000000 -0.000000 0.026296
43 0.028279 -0.000000 0.000000 0.000000 0.000000 0.043986
44 0.028279 0.000000 0.000000 0.000000 -0.000000 0.043986
45 0.101948 0.005554 0.016613 -0.231834 -0.118925 0.053755
46 0.101949 0.005554 -0.016613 0.231834 0.118925 0.053755
47 0.038861 0.000000 -0.000000 -0.000000 0.000000 0.048242
48 0.038861 0.000000 -0.000000 -0.000000 0.000000 0.048242
49 0.027379 0.000000 0.000000 -0.000000 -0.000000 -0.007270
50 0.027379 0.000000 0.000000 0.000000 -0.000000 -0.007270
51 0.093347 0.012724 0.037965 -0.216471 -0.261607 0.166656
52 0.093347 0.012723 -0.037965 0.216471 0.261607 0.166656
53 0.029316 0.000000 -0.000000 -0.000000 -0.000000 0.001411
54 0.029316 -0.000000 0.000000 -0.000000 0.000000 0.001411
55 0.020510 -0.000000 -0.000000 0.000000 0.000000 0.077614
56 0.020510 0.000000 0.000000 -0.000000 -0.000000 0.077614
57 0.269872 0.000000 0.000000 -0.156721 0.000000 -0.148916
58 0.269872 0.000000 0.000000 0.156722 -0.000000 -0.148916
59 0.164030 0.000000 0.000000 0.055100 0.659105 -0.304214
60 0.164030 0.000000 0.000000 -0.055100 -0.659105 -0.304214
61 -0.000000 -0.000000 -0.000000 -0.000000 0.000000 -0.000000
62 0.000000 0.000000 0.000000 -0.000000 0.000000 0.000000
63 0.047304 0.043625 0.000000 3.141592 -0.000001 2.315846
64 0.036751 0.111929 -0.009477 3.004401 -1.569761 1.654919
65 0.032480 0.102163 -0.023402 3.004401 -1.569761 1.654919
66 0.032482 0.102158 0.023256 3.004401 -1.569761 1.654919
67 0.036752 0.111929 0.008951 3.004401 -1.569761 1.654919
68 0.105850 0.102149 0.031216 -0.523877 -1.570796 -1.099988
69 0.127614 0.087155 0.044827 -0.523877 -1.570796 -1.099988
70 0.126146 0.105804 0.013712 -0.523877 -1.570796 -1.099988
71 0.127614 0.087155 -0.045484 -0.659283 -1.570796 -0.964581
72 0.126240 0.106008 -0.014382 -0.523877 -1.570796 -1.099988
73 0.105850 0.102149 -0.027988 -0.523877 -1.570796 -1.099988
74 0.099929 0.081067 -0.028751 -3.141590 -1.483529 1.517725
75 0.099929 0.081067 0.028556 -0.000002 -1.483529 -1.623863
76 0.062223 0.033175 0.010326 0.849986 1.570796 -3.064284
77 0.062217 0.033175 -0.010183 1.712157 1.570451 -2.202114
78 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
79 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
80 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
81 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
82 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
83 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
84 0.000000 0.000000 0.000000 0.000000 -0.000000 0.000000
end
```

Quick:

```
nodes
0 "Bip01" -1
1 "Bip01 Pelvis" 0
2 "Direction" 1
3 "Sync01" 2
4 "Balance" 1
5 "Bip01 Spine" 4
6 "Bip01 Spine1" 5
7 "Bip01 Spine2" 6
8 "Bip01 Spine3" 7
9 "Bip01 Neck" 8
10 "Bip01 Head" 9
11 "Bip01 L Thigh" 1
12 "Bip01 R Thigh" 1
13 "Bip01 L Calf" 11
14 "Bip01 R Calf" 12
15 "Bip01 L Foot" 13
16 "Bip01 R Foot" 14
17 "Bip01 L Toe0" 15
18 "Bip01 R Toe0" 16
19 "Bip01 L Clavicle" 9
20 "Bip01 R Clavicle" 9
21 "Bip01 L UpperArm" 19
22 "Bip01 R UpperArm" 20
23 "Bip01 L Forearm" 21
24 "Bip01 R Forearm" 22
25 "Bip01 L Hand" 23
26 "Bip01 R Hand" 24
27 "Bip01 L Finger0" 25
28 "Bip01 R Finger0" 26
29 "Bip01 L Finger01" 27
30 "Bip01 R Finger01" 28
31 "Bip01 L Finger02" 29
32 "Bip01 R Finger02" 30
33 "Bip01 L Finger1" 25
34 "Bip01 R Finger1" 26
35 "Bip01 L Finger11" 33
36 "Bip01 R Finger11" 34
37 "Bip01 L Finger12" 35
38 "Bip01 R Finger12" 36
39 "Bip01 L Finger2" 25
40 "Bip01 R Finger2" 26
41 "Bip01 L Finger21" 39
42 "Bip01 R Finger21" 40
43 "Bip01 L Finger22" 41
44 "Bip01 R Finger22" 42
45 "Bip01 L Finger3" 25
46 "Bip01 R Finger3" 26
47 "Bip01 L Finger31" 45
48 "Bip01 R Finger31" 46
49 "Bip01 L Finger32" 47
50 "Bip01 R Finger32" 48
51 "Bip01 L Finger4" 25
52 "Bip01 R Finger4" 26
53 "Bip01 L Finger41" 51
54 "Bip01 R Finger41" 52
55 "Bip01 L Finger42" 53
56 "Bip01 R Finger42" 54
57 "Bip01 L ForeTwist" 21
58 "Bip01 R ForeTwist" 22
59 "Bip01 LUpArmTwist" 19
60 "Bip01 RUpArmTwist" 20
61 "Bip01 L Prop" 25
62 "Bip01 R Prop" 26
63 "face_ingame_jaw" 10
64 "face_ingame_r_upper_lip" 10
65 "face_ingame_r_lip" 10
66 "face_ingame_l_lip" 10
67 "face_ingame_l_upper_lip" 10
68 "face_ingame_l_upper_eyelid" 10
69 "face_ingame_l_outer_eyebrow" 10
70 "face_ingame_l_inner_eyebrow" 10
71 "face_ingame_r_outer_eyebrow" 10
72 "face_ingame_r_inner_eyebrow" 10
73 "face_ingame_r_upper_eyelid" 10
74 "face_ingame_r_eye" 10
75 "face_ingame_l_eye" 10
76 "face_ingame_r_lower_lip" 63
77 "face_ingame_l_lower_lip" 63
78 "CameraSync01" 0
79 "Bip01 L Hand Effector" 0
80 "Bip01 R Hand Effector" 0
81 "l_upperarm_twist" 0
82 "r_upperarm_twist" 0
83 "l_shoulder_joint" 0
84 "r_shoulder_joint" 0
end
skeleton
time 0
0 0.000000 -0.000000 0.998452 0.000000 -0.000000 -1.570795
1 0.000000 0.000000 0.000000 -0.021273 -1.570796 -1.549522
2 -0.998452 0.000000 -0.000001 1.115935 -1.570451 2.025658
3 0.000000 0.000000 -0.000000 0.000000 -0.000000 0.000000
4 0.061026 -0.020621 0.000000 1.115934 -1.569761 2.025658
5 0.000000 -0.000000 0.000000 -1.570903 -1.570796 -1.570691
6 0.120951 -0.000096 0.000000 -0.000000 -0.000000 0.000000
7 0.120951 -0.000096 0.000000 -0.000000 -0.000000 0.000000
8 0.120951 -0.000096 0.000000 -0.000000 -0.000000 0.000000
9 0.128489 -0.019381 -0.000000 -0.000000 -0.000001 0.182813
10 0.077383 0.006895 0.000000 -0.000000 0.000000 -0.130540
11 -0.000000 0.000000 0.089957 -3.141027 -0.054466 -3.061052
12 0.000000 -0.000000 -0.089957 3.141030 0.054469 -3.061052
13 0.449787 0.000000 -0.000000 0.000000 0.000000 -0.000977
14 0.449787 0.000000 -0.000000 -0.000000 -0.000000 -0.000977
15 0.447161 0.000000 -0.000000 -0.228499 -0.054245 0.081667
16 0.447161 0.000000 -0.000000 0.228499 0.054246 0.081667
17 0.098783 0.133179 -0.001318 0.000000 -0.000000 1.570796
18 0.098783 0.133180 0.001318 0.000000 -0.000000 1.570796
19 -0.039012 0.017390 0.037606 -0.944282 -1.403160 -2.387640
20 -0.039012 0.017390 -0.037606 0.944258 1.403164 -2.387663
21 0.164030 -0.000000 0.000000 -0.036490 0.659105 -0.304214
22 0.164030 0.000000 0.000000 0.036490 -0.659105 -0.304214
23 0.269872 0.000000 -0.000000 -0.000000 0.000000 -0.148916
24 0.269872 0.000000 0.000000 0.000000 -0.000000 -0.148916
25 0.257988 0.000000 0.000000 -1.880375 -0.019397 0.169870
26 0.257988 0.000000 -0.000000 1.880375 0.019397 0.169870
27 0.024097 0.004039 -0.034148 1.160342 0.687200 0.420147
28 0.024097 0.004039 0.034148 -1.160342 -0.687200 0.420147
29 0.040794 0.000000 0.000000 -0.000000 0.000000 0.211794
30 0.040793 0.000000 -0.000000 0.000000 -0.000000 0.211794
31 0.034064 -0.000000 -0.000000 0.000000 -0.000000 0.016612
32 0.034064 -0.000000 -0.000000 -0.000000 -0.000000 0.016612
33 0.103943 -0.000469 -0.035487 -0.000819 0.235556 -0.000191
34 0.103943 -0.000468 0.035487 0.000819 -0.235556 -0.000191
35 0.034173 -0.000000 0.000000 -0.000000 -0.000000 0.085070
36 0.034173 0.000000 -0.000000 0.000000 -0.000000 0.085070
37 0.024721 -0.000000 0.000000 -0.000000 -0.000000 0.092737
38 0.024721 0.000000 0.000000 -0.000000 -0.000000 0.092737
39 0.108053 0.000488 -0.009367 -0.153563 0.054423 0.031571
40 0.108054 0.000488 0.009367 0.153563 -0.054423 0.031572
41 0.039110 -0.000000 -0.000000 0.000000 0.000000 0.026297
42 0.039110 0.000000 0.000000 0.000000 -0.000000 0.026297
43 0.028279 0.000000 0.000000 0.000000 -0.000000 0.043986
44 0.028279 0.000000 0.000000 -0.000000 0.000000 0.043985
45 0.101948 0.005554 0.016613 -0.231834 -0.118925 0.053755
46 0.101949 0.005554 -0.016613 0.231834 0.118925 0.053755
47 0.038861 0.000000 -0.000000 -0.000000 0.000000 0.048243
48 0.038861 0.000000 -0.000000 -0.000000 0.000000 0.048243
49 0.027379 0.000000 -0.000000 -0.000000 -0.000000 -0.007270
50 0.027379 -0.000000 0.000000 0.000000 0.000000 -0.007270
51 0.093347 0.012723 0.037965 -0.216471 -0.261607 0.166656
52 0.093347 0.012723 -0.037965 0.216471 0.261607 0.166656
53 0.029315 -0.000000 -0.000000 -0.000000 0.000000 0.001410
54 0.029315 0.000000 0.000000 0.000000 0.000000 0.001410
55 0.020509 0.000000 0.000000 0.000000 0.000000 0.077613
56 0.020510 0.000000 -0.000000 0.000000 -0.000000 0.077613
57 0.269872 -0.000000 0.000000 -0.156722 0.000000 -0.148916
58 0.269872 -0.000000 0.000000 0.156722 -0.000000 -0.148916
59 0.164030 -0.000000 0.000000 0.055100 0.659105 -0.304214
60 0.164030 -0.000000 0.000000 -0.055100 -0.659105 -0.304214
61 0.000000 0.000000 -0.000000 -0.000000 0.000000 -0.000000
62 0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
63 0.037457 0.082022 0.047731 3.100353 -1.570796 -0.011830
64 0.037457 0.082022 -0.047730 3.100353 -1.570796 -0.011830
65 0.074343 0.005422 -0.075198 3.100353 -1.570796 -0.011830
66 0.074343 0.005422 0.075198 3.100353 -1.570796 -0.011830
67 0.103712 0.080418 0.030487 3.100353 -1.570796 -0.011830
68 0.103712 0.080418 0.030487 3.100353 -1.570796 -0.011830
69 0.103712 0.080418 0.030487 3.100353 -1.570796 -0.011830
70 0.103712 0.080418 -0.030486 3.100353 -1.570796 -0.011830
71 0.103712 0.080418 -0.030486 3.100353 -1.570796 -0.011830
72 0.103712 0.080418 -0.030486 3.100353 -1.570796 -0.011830
73 0.122795 0.098470 0.000001 3.100353 -1.570796 -0.011830
74 0.050665 0.032370 0.000000 3.100353 -1.570796 -0.011830
75 0.000000 -0.077522 -0.048596 -0.000000 -0.000000 0.000000
76 0.000000 -0.018994 -0.022559 -0.000000 -0.000000 0.000000
77 -0.000000 -0.016413 0.001120 0.000000 0.000000 0.000000
78 0.000000 -0.018308 -0.002002 0.000000 0.000000 0.000000
79 0.000000 -0.047978 -0.062829 -0.000000 -0.000000 0.000000
80 0.052900 0.104554 -0.026496 3.100353 -1.570796 -0.011830
81 0.052900 0.104554 0.026497 3.100353 -1.570796 -0.011830
82 0.106481 0.061957 0.063238 3.100353 -1.570796 -0.011830
83 0.106481 0.061957 -0.063238 3.100353 -1.570796 -0.011830
84 0.080949 0.108221 0.000000 3.100353 -1.570796 -0.011830
end
```
## Post #105
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-12-05T04:28:46+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Whew, after nearly six hours of messing about I finally managed to adjust the skeleton to fit the mesh and the ValveBiped. I can just use this one for now on, no more skeletons necessary. 


Say, now that hkx to smd is now possible, are [animations](http://puu.sh/5CB6g.zip) still that big of a stretch? I don't want to be greedy, but if we had those we wouldn't even need to spend all this time and effort to line up the bones, we could just replace them with ones tailored specifically for the original skeleton. 

Plus this game has the best melee animations I've ever seen, they'd be an excellent asset for movie-making and such.
## Post #106
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-05T08:23:09+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Whew, after nearly six hours of messing about I finally managed to adjust the skeleton to fit the meshwhich mesh? And why was the adjustment required?

> are animations still that big of a stretch?Don't know.
Again someone had to spend his time and nerves...

> I don't want to be greedy, butYep, that's what you are.  

> we could just replace them with ones tailored specifically for the original skeleton.hmm, "tailored"?
That means you'll need to edit them. That's another fun...

> Plus this game has the best melee animations I've ever seen,sounds like an advertising slogan - but maybe.
## Post #107
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-12-05T08:33:11+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from shakotay2
>
> sounds like an advertising slogan - but maybe.
No, it's just my personal opinion. They are pretty cool though.

> Reply from shakotay2
>
> Yep, that's what you are.
Sigh, I suppose you're right. Heck, back in July I was still using Ninja Ripper and remaking all the UVs from scratch. And look where we are now. 

But like I said, I want to get as much as possible right now, since after you're done, that's it. There is nobody else who has the experience or even the slightest interest to work on stuff from this game.


Look, I appreciate all the time and hard work you've put into this for absolutely no reward, I truly do. I understand you're probably sick of this whole thing already, but could you please do me this one last favor? 
At least take a look, if it's too difficult or time consuming you can just drop the entire thing.
## Post #108
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-05T08:51:32+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Again my prevoius unanswered question:
"which mesh? And why was the adjustment required?"

> Reply from SergeantJoe
>
> , but could you please do me this one last favor?The thing is that animations are not on my focus atm. This may change in 3 or 4 months.
I'm messing around with several projects and only when I'm bored with them I use my spare time to "relax" on things where my knowledge is poor as for example with "skeletons".
## Post #109
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2013-12-05T09:24:53+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Well, alright.

> Reply from shakotay2
>
> "which mesh? And why was the adjustment required?"
Oh, I was referring to the [models I showed you earlier](http://puu.sh/5yxWs). Basically what I'm doing is making these models compatible with the Source Engine so they can be used with games and programs like Garry's Mod and Source Filmmaker. 

However, for the former the model needs a specific set of animations. That's what I was saying, it would be better to have the SD animations, because they're intended for SD skeletons. Valve animations are intended for Valve skeletons, and I have to significantly alter the SD skeletons to make them fit on Valve animations. 
(plus, like I said, SD contains a huge amount of smooth melee animations which would be perfect for a variety of purposes)

But in any case, I have to stick with forcing Valve animations onto SD skeletons for now. The entire thing looks terrible by the time I'm done, but at least it works.



I suppose that's it then. If you decide to take this up one day that would be more than great, but it's up to you. (or if someone else comes along, but I highly doubt that)
## Post #110
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-05T12:11:38+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

As I wrote, I won't dig deep into havok animation format (especially when it's compressed) but if we had a havok animation (of any game) that is playable in the Havok standalone tool I surely would have a look at it.

For example here [http://forums.bethsoft.com/topic/129382 ... converter/](http://forums.bethsoft.com/topic/1293826-rel-havok-animation-converter/) is described how to convert Havok animation from the Skyrim-compatible binary format to the Havok XML format.

Or you could export any animation in 3dsmax into hkx:
[http://forums.elementalgame.com/398524](http://forums.elementalgame.com/398524)

Hah, that's great. You load the mesh, add the skeleton and the animation (into the havok StanadaloneTool)  and then it goes.
[](http://www.pic-upload.de/view-21579994/Havok_anim.jpg.html)
I really love it when things are as easy as this.
(But coders all around the world tend to keep things fxcking complicated for a reason I never will understand....  )
(To be honest: I'd like to purge when seeing nif formats specification for example...I really hate it.)


edit: well, as I thought: the girl has an UncompressedAnimation while Thug.bin seems to contain a compressed one. Also the bone names are missing in here.
## Post #111
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-03T18:23:51+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

I'm interested in the source to this HKX to SMD converter tool. I don't see it posted in the thread. Anyone know where it's available?
## Post #112
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-12-03T22:02:52+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

There is no tool, he did everything by hand if I remember correctly.

Also, wow, It's been almost a year and a half already. Bless shako, if it weren't for him we wouldn't have anything to this day.
## Post #113
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-12-04T02:25:21+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> There is no tool, he did everything by hand if I remember correctly.

Also, wow, It's been almost a year and a half already. Bless shako, if it weren't for him we wouldn't have anything to this day.

Gotcha, thanks.
## Post #114
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-10-22T15:18:08+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Here's tools to split CharacterRigs.bin and PropRigs.bin into .hkx and then convert them into .smd
made by daemon today.
[skeleton_bin_converter_tool.zip](https://xentaxbackup.github.io/file/13484_skeleton_bin_converter_tool.zip)
## Post #115
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2017-10-22T16:29:25+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from Tosyk
>
> Here's tools to split CharacterRigs.bin and PropRigs.bin into .hkx and then convert them into .smd
made by daemon today.

I can't help but feel so lucky to be alive in the age of daemon1 and his marvelous mind for 3D model exporter tools!
## Post #116
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2017-10-29T23:32:08+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

It's great to see someone still interested in this game even after all these years!

Tried it out, works perfectly. Thank you very much to you and daemon!
## Post #117
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2017-11-10T20:05:00+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Can someone re-upload Ekey's DE unpacker ? The link is old and got expired!
## Post #118
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2017-11-10T21:52:23+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

[Right here.](http://www.mediafire.com/file/lx2au8hxf4rchpf/SDDEUnpacker_0.0.2_r3.7z)
## Post #119
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2017-11-11T21:18:43+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from SergeantJoe
>
> Right here.

Thank you so much Joe! now what do I do after extracting these archives ?
## Post #120
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2017-11-13T00:59:37+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Well you can extract the character models and textures and use them for whatever you want, but sadly that's pretty much it. You can't modify the game at all:

> Reply from SergeantJoe
>
> When you unpack a .BIG file, you'll end up with "../SleepingDogsDefinitiveEdition/*NameOfBig*/Data/". If you move the Data folder into the main game folder and remove the BIG file, the game will load the unpacked files directly. 

There are some issues with this though. The unpacker doesn't assign filenames to everything, so when the games tries to load the unnamed files it crashes.
Meaning if you try to unpack and Run Characters.big, where all the important stuff is located, it won't work. Only way to get around that is to somehow convince ekey to update the unpacker, which I doubt will happen without a small donation of a million dollars.
## Post #121
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2018-10-13T20:58:12+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

Sorry for digging up a dormant thread but has there been any latest news about an easier way of getting the game models?
## Post #122
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2018-10-22T02:00:25+00:00
- Post Title: Re: [Request] Sleeping Dogs Model Files

> Reply from artworkplay
>
> Sorry for digging up a dormant thread but has there been any latest news about an easier way of getting the game models?

Absolutely nobody has cared about this game for past 5 years, what makes you think that all of a sudden there would be new work on it??

Hell even I've given up over three years ago. Nobody on the internet knows this game exists, much less someone who knows about file formats.
