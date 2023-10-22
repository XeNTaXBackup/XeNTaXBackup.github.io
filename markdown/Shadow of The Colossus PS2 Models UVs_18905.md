## Post #1
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2018-10-08T03:21:12+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

So I managed to extract the shadow of the colossus nmo models from my own PS2 disk using a bms script, but unfortunately the models did not keep their UV maps. 
Is there a tool somewhere that will let me extract from the NICO dat with the model's UV maps intact? I know the Dormin viewer lets you see the colossi (and other models) with their skeletons and textures applied, but I don't think it lets you extract them?
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-10-08T04:00:45+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

got any model (with the textures ofc) samples and the script?

i could lean myself out the window and assume you may just have to scale the uvs. the ps2 models i got to extract (using those weirdo 3ds bms scripts) used integer uv coordinates not floating point. they are just damn large. i think they scale around 4096. so you should scale by 1/4096 to get them into the 0 to 1 floating point range.
## Post #3
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2018-10-14T02:29:27+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

> Reply from episoder
>
> got any model (with the textures ofc) samples and the script?

i could lean myself out the window and assume you may just have to scale the uvs. the ps2 models i got to extract (using those weirdo 3ds bms scripts) used integer uv coordinates not floating point. they are just damn large. i think they scale around 4096. so you should scale by 1/4096 to get them into the 0 to 1 floating point range.

Hi there! I'm so sorry I haven't gotten back to you sooner! This week has been really hectic for me. 
Anywho, I selected the mesh and went into blender's UV window to investigate, but there wasn't even anything there for me to select. I'm not sure if its just so large that I cant see a thing (I even zoomed all the way out to look) or if there really is just nothing there. I even tried doing a select all and it didn't pick anything up.



I've attached Avion's model down below with his textures along with the bms scripts. Unfortunately, the wiki I got the scripts from just went down at the end of September, so I can't link you too the source. I should also probably add that my knowledge of Python is minimal. A lot of this just looks like gibberish to me. I'm just learning...heh...
Oh! And the textures weren't extracted by the scripts. Those I got from another source.
[sotc avion.7z](https://xentaxbackup.github.io/file/15025_sotc avion.7z)
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-14T06:21:00+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

i think getting models from PS4 remake may be much easier
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-14T06:31:36+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

> Reply from Snapdragons
>
> I've attached Avion's model down below with his texturesWhat you uploaded is the already converted .3ds file without uvs, afaiks.
What we need is the original model, i.e. eeMemory.bin, or something else, the file where you extracted the .3ds from.

Also you provided two bms scripts; which one did you use? (nico.bms seems to be an earlier version.)

btw:

> Reply from Snapdragons
>
> Unfortunately, the wiki I got the scripts from just went down at the end of September, so I can't link you too the source. I should also probably add that my knowledge of Python is minimal. A lot of this just looks like gibberish to me.It's not a python script, it's bms scripts for quickbms. (Using nonsense names for variables like "spyrodragon", "rubyfox" or "snake" makes the scripts hard to read, yes.  )
## Post #6
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2018-10-14T09:13:06+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

> Reply from shakotay2
>
> Snapdragons wrote:I've attached Avion's model down below with his texturesWhat you uploaded is the already converted .3ds file without uvs, afaiks.
What we need is the original model, i.e. eeMemory.bin, or something else, the file where you extracted the .3ds from.

Also you provided two bms scripts; which one did you use? (nico.bms seems to be an earlier version.)

btw:
Snapdragons wrote:Unfortunately, the wiki I got the scripts from just went down at the end of September, so I can't link you too the source. I should also probably add that my knowledge of Python is minimal. A lot of this just looks like gibberish to me.It's not a python script, it's bms scripts for quickbms. (Using nonsense names for variables like "spyrodragon", "rubyfox" or "snake" makes the scripts hard to read, yes.  )

Aha, my "ultra-noob" hat becomes me, doesn't it? ( I suppose this is what happens when a sound engineer tries to 3D model, hm? bwhaha!)

I extracted the models from the NICO.dat copied off of my own PS2 disk. I don't quite think XeNTaX can allow such an upload?
As for which script I used, I believe it was the "nmobmsupdated" I simply downloaded both since the wiki was going down and I wasn't sure if it was going to be useful at any point.
And to address your last statement, now you see why I need help? Haha! I had never used bms (or any major scrips) before this, so my terminology is...quite off.  (But I am slowly trying to learn).
## Post #7
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2018-10-14T09:20:14+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

> Reply from daemon1
>
> i think getting models from PS4 remake may be much easier

You are probably quite correct, but since my PS2 and PS3 copies of sotc are all I currently have, I figured there wasn't much harm in trying. Cause clearly my PS4 file-hunting skills are uhhh...
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-14T12:23:48+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

> Reply from Snapdragons
>
> I extracted the models from the NICO.dat copied off of my own PS2 disk. I don't quite think XeNTaX can allow such an upload?We only need a small part of that Nico.dat. Last time I handled PS2 uvs I had a 32 MB eeMemory.bin file as input for a bms script.

Guess that Nico.dat is much bigger? Did you use it to be loaded by your bms scripts or do you have smaller fragments of that dat? Otherwise the first 32 MB of the Nico.dat should be sufficient to look for the uvs.

You could create it by using a hexeditor, load the .dat, select the bytes from offset 0 to 0x2000000 then "save selected" (or something like that, save as binary data).
## Post #9
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-10-14T12:32:27+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

well. yes, the model is already xtracted. nothing we can do with that data. you coulda just uploaded the bird_A.nmo and textures. that's how it rolls here.

and while i'm getting a rom and further search for file extractors (that may not exist anymore) you could check out [this link](https://forum.unity.com/threads/released-shadow-of-the-colossus-viewer-texture-and-models-exporter-xd.261522/) and see if that sotc viewer can help you get what you want, easily. i really don't feel like rewriting another of those scripts (if i'd ever meet this guy i gotta punch him for writing this cryptic and incomplete mess that nobody could finish easy. what a stupid dummy).
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-14T13:11:51+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

> Reply from episoder
>
> (if i'd ever meet this guy i gotta punch him for writing this cryptic and incomplete mess that nobody could finish easy. what a stupid dummy).yeah, punching people who create solutions.
If that isn't stupid?  
The author is a funny guy, indeed, guess, a very young one, when  he wrote the scripts, but there's no reason to insult him.

The real problem is the cryptic 3D format of PS2.
## Post #11
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-10-14T21:42:03+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

> Reply from shakotay2
>
> episoder wrote:(if i'd ever meet this guy i gotta punch him for writing this cryptic and incomplete mess that nobody could finish easy. what a stupid dummy).yeah, punching people who create solutions.
If that isn't stupid?  
The author is a funny guy, indeed, guess, a very young one, when  he wrote the scripts, but there's no reason to insult him.

The real problem is the cryptic 3D format of PS2.

didn't get the 'joke'? i gotta use more smilies again?  to not be read like seriously 'offending'? ugh man, i hate this negative reception sometimes. you didn't feel well that you read it wrong? still the same. the code he wrote is aweful to work with second hand.

and yeh the data is not really cryptic but packed af. the VU and VIF are lil weird processors to feed. they can take random data streams/buffers and rearrange arbitrary into the output stream (GSpackets) buffers, where a normal shader gpu is streamlined with fixed input slots. me decoding this face index array on the cavia files was like writing a VU program to output the streamlined polygon data to feed the GS. nuts. 

edit: well. i need some sleep. this is making my head hurt. if you wanna take a look at a bird. @shakotay i dunno if it's the same tho. there are alot of birds in the dat file and i don't wanna try to extract all of the 16000+ models (as far as the signature search goes). i gotta figure out the structures first, not doing binary search. i had to get another hexeditor tho and it's not helping it's lacking a bunch of keyshort features.  gotta like xvi.
[bird_A.rar](https://xentaxbackup.github.io/file/15029_bird_A.rar)
## Post #12
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2018-10-17T04:30:23+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

> Reply from episoder
>
> well. yes, the model is already xtracted. nothing we can do with that data. you coulda just uploaded the bird_A.nmo and textures. that's how it rolls here.

and while i'm getting a rom and further search for file extractors (that may not exist anymore) you could check out this link and see if that sotc viewer can help you get what you want, easily. i really don't feel like rewriting another of those scripts (if i'd ever meet this guy i gotta punch him for writing this cryptic and incomplete mess that nobody could finish easy. what a stupid dummy).

Ah! I didn't quite know how to extract the nmo file itself. I see you two suggesting hex editors, and I'm still trying to learn about those...   
And I've seen that tool you linked! But my computer's anti-virus keeps catching and deleting it. I know its likely safe, but I was wondering if you had any input on it.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-17T05:55:48+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

this is what I get using a little bit patched .nmo /script:



SotC-prob.png (10.21 KiB) Viewed 228 times


First three lines of header seem to be ok but output doesn't make too much sense to me:

offset   filesize   filename
--------------------------------------
name obj_bird_A.nmo.1.3ds
  00000000 112        obj_bird_A.nmoa.1.3ds

- 1 files found in 0 seconds
  coverage file 0   202%   830565     409735     . offset 0000000f
  coverage file -2  100%   36         36         . offset 00000024
  coverage file -4  100%   8          8          . offset 00000008
  coverage file -7  100%   410009     409732     . offset 000000d2
  coverage file -8  100%   112        112        . offset 00000060
  coverage file -11 100%   3          3          . offset 00000003
  coverage file -12 100%   4          4          . offset 00000004
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-17T09:49:22+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

pointcloud with a missing wing?



birds_1.png (2.84 KiB) Viewed 221 times
## Post #15
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-10-17T15:19:47+00:00
- Post Title: Shadow of The Colossus PS2 Models: UVs

well. the dat container is really bad to read. no clear start and clear pointers. you see the script uses binary search to find the signatures. it does not hit the NMO directly either. neither extracts files as files. means i had to wing that file with the bird_A string and using some signature to signature logic, not the correct way either. that would be pointer to start and filesize, which is can't assemble right now.

anyway, now that i look at the file it may be an animation file. it uses a different 'data command' even. 0x6C not 0x68. shit.

if you don't mind downloading a rom for 700 megs, you get the 2.4 gig dat file with all of it. i won't reup it.

i'm gettin somewhere in this rabbit hole. i still dunno what is a 'folder' or 'subfolder' and what should be considered a 'file'. xff definitions seem like wrappers for files, cause this NTO2 texture is a direct payload in that particular xff structure. xff2 should be considered a folder? huh. i dunno. when i get there, i'll mosdef have to dump all the textures into a single nto folder as it seems. may be easy to code a custom importer to load from a single texture path. 

i need a break tho. chill with my tv *cough* stream. lol
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-21T08:31:08+00:00
- Post Title: Re: Shadow of The Colossus PS2 Models: UVs

from the JimmyNeutron thread I got the idea to get more vertices for the bird:



bird_a-autoFIs.png (24.11 KiB) Viewed 119 times


(autocreated face indices are not nice, though)
## Post #17
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2018-10-25T04:10:05+00:00
- Post Title: Re: Shadow of The Colossus PS2 Models: UVs

> Reply from shakotay2
>
> from the JimmyNeutron thread I got the idea to get more vertices for the bird:
bird_a-autoFIs.png
(autocreated face indices are not nice, though)

Is there any way to apply textures to it? That looks like one of the eagles
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-25T21:21:00+00:00
- Post Title: Re: Shadow of The Colossus PS2 Models: UVs

> Reply from Snapdragons
>
> Is there any way to apply textures to it? That looks like one of the eaglesFirst step  is to get a correct mesh. I need more understanding for that.

Getting better, but had to erase superfluous faces; some still being present:



bird_a-nmo.png (28.33 KiB) Viewed 87 times
