## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-27T16:39:47+00:00
- Post Title: StarWars Battlefront unpacker / decoder

Modified "FrankElstner's" scripts to unpack StarWars Battlefront:

swbf_dump contains dumper script sw_dumper.py

fb3decoder contains audio conversion script fb3decoder.py

NOTE Don't forget to modify folder names in both scripts!

swbf_cas folder - the old simple extractor, just in case

p.s. old mesh tool is working, audio is extracted properly, updated texture tool included.
[swbf.rar](https://xentaxbackup.github.io/file/10239_swbf.rar)
## Post #2
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-11-27T22:15:40+00:00
- Post Title: StarWars Battlefront unpacker / decoder

Will you be updating your chunk and mesh tool,itexture tool and 3ds max script once you get the file names complete?
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-28T07:04:41+00:00
- Post Title: StarWars Battlefront unpacker / decoder

> Reply from JakeGreen
>
> your chunk and mesh tool,itexture tool and 3ds max script

These were done by somebody else. Ask them. I just see that nobody still made an extractor and did this quick solution. I can look into that though, if you explain what are you talking about.
## Post #4
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-11-28T07:59:48+00:00
- Post Title: StarWars Battlefront unpacker / decoder

> Reply from daemon1
>
> JakeGreen wrote:your chunk and mesh tool,itexture tool and 3ds max script

These were done by somebody else. Ask them. I just see that nobody still made an extractor and did this quick solution. I can look into that though, if you explain what are you talking about.

Ah i got your name and his mixed up oops lol anyways here is what i'm talking about 

[viewtopic.php?f=33&t=13145](http://forum.xentax.com/viewtopic.php?f=33&t=13145)

and here is a mesh and chunk tool that worked with the beta and most likely would with the main game if not i can edit it to possible work with it.

[https://dl.dropboxusercontent.com/u/881 ... 20tool.rar](https://dl.dropboxusercontent.com/u/88155050/SWBF%20Open%20Beta/Chunk%20and%20Mesh%20management%20tool.rar)
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-28T08:47:09+00:00
- Post Title: StarWars Battlefront unpacker / decoder

All these tools may be working already. At least nothing was changed in sound format, only .CAS structure itself.
## Post #6
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-11-28T18:58:11+00:00
- Post Title: StarWars Battlefront unpacker / decoder

> Reply from daemon1
>
> All these tools may be working already. At least nothing was changed in sound format, only .CAS structure itself.

Um a few people tried the itexture and 3ds max script and they both either don't work or give errors when you try to use them with the beta stuff.
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-28T19:02:57+00:00
- Post Title: StarWars Battlefront unpacker / decoder

> Reply from daemon1
>
> Here's the very first and quick solution.

Just use swbf_cas.exe on any .cas file and it will unpack it to 1000's of chunks without names. If some of them will be audio chunks, they'll have .EXA extension.

Then you can decode them with my decoder (latest version included).

Later I plan to check the new sb/toc format to have proper filenames.

Can you please share structure of cas files ? Im highly interested about this... Thx
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-28T20:02:42+00:00
- Post Title: StarWars Battlefront unpacker / decoder

> Reply from michalss
>
> Can you please share structure of cas files ? Im highly interested about this... Thx

Sure. The structure is relatively simple. The trick with frostbyte engine is in sb/toc files that are much more complex. But CAS files are basically all unnamed chunks packed together, and its structure is changing a bit from game to game. What exactly would you like to know?
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-29T20:29:56+00:00
- Post Title: StarWars Battlefront unpacker / decoder

Good news. The modified Frank's python script is working, and it unpacks all the sounds with proper names. I only need to check it a little more. I think tomorrow it will be ready.
## Post #10
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-11-29T20:33:27+00:00
- Post Title: StarWars Battlefront unpacker / decoder

> Reply from daemon1
>
> Good news. The modified Frank's python script is working, and it unpacks all the sounds with proper names. I only need to check it a little more. I think tomorrow it will be ready.

Will it extract .mesh files with proper names and textures like this t_hero_jedi_darthvader_body_c e6fbd4c48ccd094f 0b000000010000000000000000000000.unknownres 6bde20ba ?
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-29T20:38:04+00:00
- Post Title: StarWars Battlefront unpacker / decoder

It extracts files like 

meshp_chunk_generic_01_mesh d37b9d34210486c3 5003000000000000380000009000c000.mesh

t_metalchunk_01_s 7c6f454767c46a27 0b000000010000000000000000000000.unknownres 6bde20ba
## Post #12
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-29T20:53:56+00:00
- Post Title: StarWars Battlefront unpacker / decoder

> Reply from daemon1
>
> michalss wrote:Can you please share structure of cas files ? Im highly interested about this... Thx

Sure. The structure is relatively simple. The trick with frostbyte engine is in sb/toc files that are much more complex. But CAS files are basically all unnamed chunks packed together, and its structure is changing a bit from game to game. What exactly would you like to know?

I would like to understad the format and make repacker for F3 games... Im kind of person who makeing repacker for complicated games/engines  F3 is one of them...
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-30T15:10:31+00:00
- Post Title: StarWars Battlefront unpacker / decoder

> Reply from michalss
>
> I would like to understad the format and make repacker for F3 games... Im kind of person who makeing repacker for complicated games/engines  F3 is one of them...

Ok, but as I said, format changes from game to game, and you need to start from something. In addition to Frank's scripts there's DAI tools opensource project, so if you know Python or C#, it will be easier for you to start with these. Yet, DAI tools developers are still unable to unpack CAS chunks properly, although I told them how to do that.
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-30T16:51:38+00:00
- Post Title: StarWars Battlefront unpacker / decoder

The first version of python scripts are here in the title post.
## Post #15
- Username: nilentry
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 12, 2015 11:50 am
- Post datetime: 2015-11-30T19:50:05+00:00
- Post Title: StarWars Battlefront unpacker / decoder

I've followed the instructions and changed the file paths accordingly for the swbf_dump script, yet all I'm getting are empty folders in the dump directory. The console is simply spewing "chunk not found ...", and I've let it run for about thirty minutes now to see if maybe it was just missing some files.

It also prints the correct path to the file it would have created, such "C:\BattlefrontDump/bundles/ebx/characters/imperial/hero_jedi_darthvader/texture/t_hero_jedi_darthvader_glove_n.ebx", yet upon inspection, the file does not exist.
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-30T19:55:26+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

I assumed data chunks to be in these dirs:

\starwars\data\mp\cas.cat
\starwars\data\sp\cas.cat
\starwars\data\initial\cas.cat

Is that so? Also do you have a console or PC?
## Post #17
- Username: nilentry
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 12, 2015 11:50 am
- Post datetime: 2015-11-30T20:36:48+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from daemon1
>
> I assumed data chunks to be in these dirs:

\starwars\data\mp\cas.cat
\starwars\data\sp\cas.cat
\starwars\data\initial\cas.cat

Is that so? Also do you have a console or PC?

I am using a PC, Windows 8.1 64-bit.

The cat files are in these locations.
C:\Program Files (x86)\Origin Games\STAR WARS Battlefront\Data\Win32\installation\initialexperience\cas.cat
C:\Program Files (x86)\Origin Games\STAR WARS Battlefront\Data\Win32\installation\mp\cas.cat
C:\Program Files (x86)\Origin Games\STAR WARS Battlefront\Data\Win32\installation\sp\cas.cat
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-30T20:46:23+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

You have to find these lines

cat1Path       = r"mp\cas.cat" 
cat2Path       = r"sp\cas.cat" 
cat3Path       = r"initial\cas.cat" 

and change them to

cat1Path       = r"Win32\installation\mp\cas.cat" 
cat2Path       = r"Win32\installation\sp\cas.cat" 
cat3Path       = r"Win32\installation\initialexperience\cas.cat" 

Sorry, I don't have time to reupload the script now.
## Post #19
- Username: nilentry
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 12, 2015 11:50 am
- Post datetime: 2015-11-30T20:48:59+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from daemon1
>
> You have to find these lines

cat1Path       = r"mp\cas.cat" 
cat2Path       = r"sp\cas.cat" 
cat3Path       = r"initial\cas.cat" 

and change them to

cat1Path       = r"Win32\installation\mp\cas.cat" 
cat2Path       = r"Win32\installation\sp\cas.cat" 
cat3Path       = r"Win32\installation\initialexperience\cas.cat" 

Sorry, I don't have time to reupload the script now.

Thank you, that worked perfectly!
## Post #20
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-11-30T23:55:34+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

EDIT:Oops didn't see the page 2 LOL
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-05T18:25:09+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

Was anyone able to extract all sounds, and particularly, music? If yes, then I just update paths and update the script
## Post #22
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-12-06T15:16:20+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

Thank you for ubdate tool.
I unpack cas files. How I can restore body of data files (3d models) from *.mesh and chunks?
## Post #23
- Username: Loswut
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 28, 2015 10:55 am
- Post datetime: 2015-12-08T15:10:39+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

First of all, thanks for your efforts. Really appreciate it.

Sadly, it seems I'm making a mistake somewhere as it will not let me extract the files. I've replaced the bfDirectory targetDirectory and cat paths, but when I then try run the script it gives me a syntax error popup, saying invalid syntax. Specifically, it highlights this part in the script:

    #Deal with the chunks which are defined directly in the toc.
    #These chunks do NOT know their originalSize.
    #Available fields: id, offset, size
for entry in toc.chunks:
        targetPath=targetFolder+"/chunks/"+hexlify(entry.id)+".chunk"
if prepareDir(targetPath): continue
if toc.get("cas"):
try:
                catEntry=cat[entry.sha1]
if checkchunk(catEntry.path,catEntry.offset):
                    LZ77.decompressUnknownOriginalSize(catEntry.path,catEntry.offset,catEntry.size,targetPath)
except:
print "chunk not found", hexlify(entry.sha1)
else:
 if checkchunk(sbPath,entry.offset):
                LZ77.decompressUnknownOriginalSize(sbPath,entry.offset,entry.size,targetPath)

I probably made some silly error or forgot something totally obvious, but any help would be greatly appreciated
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-08T15:38:39+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

You need python 2.7.x
Somehow this script is not working with python3 and later
## Post #25
- Username: Loswut
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 28, 2015 10:55 am
- Post datetime: 2015-12-08T16:27:38+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

Thanks for the answer.
I'm afraid I've hit another bump though 

Traceback (most recent call last):
  File "C:\BattlefrontDump\swbf_dump\sw_dumper.py", line 45, in <module>
    LZ77 = cdll.LoadLibrary("LZ77")
  File "C:\Python27\lib\ctypes\__init__.py", line 443, in LoadLibrary
    return self._dlltype(name)
  File "C:\Python27\lib\ctypes\__init__.py", line 365, in __init__
    self._handle = _dlopen(self._name, mode)
WindowsError: [Error 193] %1 is not a valid Win32 application

Yeah, I'm pretty bad at this sort of thing :/
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-08T16:42:36+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

google says you prob need the 32-bit python
## Post #27
- Username: Loswut
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 28, 2015 10:55 am
- Post datetime: 2015-12-08T18:38:22+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

That did it! Extracting the files now, thank you so much for your help and patience
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-08T19:47:14+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from Loswut
>
> That did it! Extracting the files now, thank you so much for your help and patience

Let me know if sounds get converted
## Post #29
- Username: Loswut
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 28, 2015 10:55 am
- Post datetime: 2015-12-08T22:53:36+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

The extraction worked flawlessly as far as I can tell. 

When I use the Fb3decoder to conver the files I get this:

>>> 
XAS1 dll detected.
EASpeex dll detected.

Traceback (most recent call last):
  File "C:\BattlefrontDump\fb3decoder\fb3decoder.py", line 100, in <module>
    startupinfo.dwFlags |= subprocess.STARTF_USESHOWWINDOW
AttributeError: 'module' object has no attribute 'STARTF_USESHOWWINDOW'
>>>
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-09T15:34:32+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

It seems python is VERY sensitive to its version. Try installing exactly the version I have: 32bit 2.7.3
## Post #31
- Username: elementofprgress
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Dec 10, 2015 2:48 am
- Post datetime: 2015-12-09T19:19:36+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

I have a working dumper script that includes the new patched cas.cat format. I got something like 132k audio files with it. Can't remember if any chunks are cas dependent so if it makes a difference for not. For ebx and res  files it certainly does.

I'll post it once I clean it up a little. Right now it is kinda messy and super...not optimized because I was trying to break it down to figure out why the data I get is different then what is experienced in the game/patch notes.


As for the changes with textures. I have only taken a quick peak but it looks like the chunk files need some xor love and then will be good to go.
[https://gyazo.com/f24d71c98c46cf95e9ebca991b225030](https://gyazo.com/f24d71c98c46cf95e9ebca991b225030)
## Post #32
- Username: kkhaial
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 28, 2015 4:20 pm
- Post datetime: 2015-12-10T07:10:33+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

elementofprgress if you can get textures to work that would be awesome
## Post #33
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-10T20:18:59+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

I thought somebody already did the textures convertor. I'm not an expert, but nothing is xored here. Sample output:



And here's the version of "dainazinas" tool I made that at least unpacks most of the diffuse textures. Just need some time to find codes for normal maps. 

[http://www60.zippyshare.com/v/90AbbsOu/file.html](http://www60.zippyshare.com/v/90AbbsOu/file.html)
## Post #34
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-11T05:31:03+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from daemon1
>
> I thought somebody already did the textures convertor. I'm not an expert, but nothing is xored here. Sample output:

Awesome worked perfectly, even some of the normal maps worked like the ones that are blue.

Next all we need is for someone to edit his 3ds max script and we got everything working.

EDIT: I found a lot of Diffuse Textures not working still so what you wanna do is this.

Open up the non-working C or CS texture into your hex editor of choice and highlight the first 9 rows of hex, the last line should have a "c" (no quotes) in it and you wanna make sure you get the very last dot in the 9th line and hold it there.

Once you do that open up a texture in your hex editor that has a G in place of the C and copy all 9 lines to the last dot and go back to your main texture that isn't working and make sure you still have it all selected and hit paste and save an it should be good to go.\

Also from what i'm looking at this is BC7 without SRGB so if you wanna add back the SRGB find a diffuse texture that works and do the same above and it wont make the texture so bright. I used a MSR texture to do this so that's why it's only BC7.

Also lastly if you want the textures to work i found loading them into VS 2013 and save it as PNG then load it into a program like Xnview and just save it as DDS and it should be great.

Or you can take and on the 9th line change the 63 to 48 and it will be good to go.

Not working.


Working.
## Post #35
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-11T16:00:08+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from JakeGreen
>
> EDIT: I found a lot of Diffuse Textures not working still

This is because I only had a little time to find 3 most used compression types: bc1, bc3 & bc7. Also I understand that 62 should be used, not 63?

Anyway, I only have a very few textures unpacked from the files you sent me, so if you know which codes I need to use for which texture types (byte 12 in "unknownres" file), let me know and I will correct the tool.

I'm currently setting it to
63 (bc7) for 42
47 (bc1) for 36
4D (bc3) for 3C
and 63 for all other types.

Also I can remove the picture from it, so it will be small to upload here on xentax directly.
## Post #36
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-12-11T19:35:27+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from daemon1
>
> JakeGreen wrote:EDIT: I found a lot of Diffuse Textures not working still

This is because I only had a little time to find 3 most used compression types: bc1, bc3 & bc7. Also I understand that 62 should be used, not 63?

Anyway, I only have a very few textures unpacked from the files you sent me, so if you know which codes I need to use for which texture types (byte 12 in "unknownres" file), let me know and I will correct the tool.

I'm currently setting it to
63 (bc7) for 42
47 (bc1) for 36
4D (bc3) for 3C
and 63 for all other types.

Also I can remove the picture from it, so it will be small to upload here on xentax directly.

Yep those are all the ones i've found, kinda odd cause some of the textures that was BC7_SRGB in the alpha and beta are now BC1_SRGB.
## Post #37
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-12T08:25:08+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

Proceeding with types. The skyes are in BC6, 8192x2048
## Post #38
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-12T15:43:53+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

About the Frostbite restypes: they are just a hash of their real names, as expected, and

6bde20ba = "Texture",

5C4954A6 = "DxTexture",
2D47A5FF is not "gfx", but "SwfMovie",
49B156D4 is not "mesh", but "meshset", so on.
## Post #39
- Username: elementofprgress
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Dec 10, 2015 2:48 am
- Post datetime: 2015-12-12T18:04:37+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from daemon1
>
> About the Frostbite restypes: they are just a hash of their real names, as expected, and

6bde20ba = "Texture",

5C4954A6 = "DxTexture",
2D47A5FF is not "gfx", but "SwfMovie",
49B156D4 is not "mesh", but "meshset", so on.

A few months ago I got a resTypes list for BF4 from Frankelstner, who got it from Kiwidog or NoFate...I forget. anyways, you probably already have it all figured out but figure I'd post it so it is out there for everyone.
[http://pastebin.com/sQE1Rmh2](http://pastebin.com/sQE1Rmh2)

What I'm currently using for my SWBF 
[http://pastebin.com/hifAvG4f](http://pastebin.com/hifAvG4f)
If you have any updated resTypes or something is wrong, let me know. I've only barely looked into it.


> Reply from daemon1
>
> I thought somebody already did the textures converter. I'm not an expert, but nothing is xored here.
Awesome!, I remember when the beta came out things changed. I was never sure if it was some compression or xor or some sort or if they just jumped to dx10 textures....which I know absolutely zero about lol

I remember seeing dainazinas texture batch converter and it not working after the beta and failing miserably at tinkering with the source.
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-12T18:41:14+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from elementofprgress
>
> If you have any updated resTypes or something is wrong, let me know.

Sure:

    0xf04f0c81:".Dx11ShaderProgramDatabase",
    0x9C4FAA17:".HeightfieldDecal"
    0x957C32B1:".AtlasTexture",
    0xC6CD3286:".EnlightenStaticDatabase",
    0xA23E75DB:".TerrainLayerCombinations",
    0xE36F0D59:".HavokClothPhysicsData",
    0x6BDE20BA:".Texture",
    0x9D00966A:".UITtfFontFile",
    0xC611F34A:".MeshEmitterResource",

Here's all your unknown types, if you have something else unknown, let me know.
## Post #41
- Username: elementofprgress
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Dec 10, 2015 2:48 am
- Post datetime: 2015-12-12T21:11:55+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from daemon1
>
> elementofprgress wrote:If you have any updated resTypes or something is wrong, let me know.

Sure:

    0xf04f0c81:".Dx11ShaderProgramDatabase",
    0x9C4FAA17:".HeightfieldDecal"
    0x957C32B1:".AtlasTexture",
    0xC6CD3286:".EnlightenStaticDatabase",
    0xA23E75DB:".TerrainLayerCombinations",
    0xE36F0D59:".HavokClothPhysicsData",
    0x6BDE20BA:".Texture",
    0x9D00966A:".UITtfFontFile",
    0xC611F34A:".MeshEmitterResource",

Here's all your unknown types, if you have something else unknown, let me know.

Thank you, I just wanted to make sure that the resType list I use for the extraction scripts I write for symthic match with the resTypes your tools use. 

I'm hoping I'll be able to share the file extraction script I've been working on. I know I'm able to pull all the EBX files(as they were my main concern), but those are all cas entries. I'm putting it though its paces to see if there are any noncas res/chunks or if any changes are need to get at them. As well has scanning for any more unknown res types that exist.
## Post #42
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-13T10:06:01+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from elementofprgress
>
> I'm hoping I'll be able to share the file extraction script I've been working on.

What's the purpose of your script? How is it different from Frank's script that I posted here in this thread?
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-13T12:04:52+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

Texture conversion tool updated!

Included in the first post. Now it must convert all types including normals. It makes DDS in dx10 format, it can be viewed with PicoPixel viewer recommended by dainazinas. Even that tool is not working with height maps, and some other types, for those use something else. Only first side extracted for cubemaps, but I doubt anyone needs that.

Dumper script updated with res types. Textures will now have ".Texture" extension.
## Post #44
- Username: elementofprgress
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Dec 10, 2015 2:48 am
- Post datetime: 2015-12-13T14:55:40+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from daemon1
>
> elementofprgress wrote:I'm hoping I'll be able to share the file extraction script I've been working on.

What's the purpose of your script? How is it different from Frank's script that I posted here in this thread?

It is built off of Frankelstner's script. It is mostly small tweaks. Lots of cleaning. A lot of the main script isn't used/needed anymore. Though other areas are much messier to compensate. There are no flags labeling what is cas, noncas, a delta patch, etc anymore.

but the really big difference is that your script is only pulling files from the Data folder which is the patched folder(the base files). Which i'm sure you know from playing with the scripts and files but for the sake of anyone who doesn't the files in the Patch folder are the files the game mostly relies on. Though the patch folder is where things get tricky. A different format for the cat file. Yay delta patching and sha1 entries -.- The sb/tocs just throw everything at you with no way to identify whats a duplicate, what is gonna be patching something. You kinda just have to run it all though and see what sticks. Then the Update folder(which the patch folder used to be in) adds all the stuff from Jakku DLC but is also subject to patching from the patch files.


However, I haven't look into the chunks all that much(mainly because there are WAY to many) so I'm not sure how big of a difference getting patch files will make when it comes to audio and textures other then DLC stuff. How many audio files total have you been able to pull with just info from the data folder?
## Post #45
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-13T17:36:23+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from elementofprgress
>
> There are no flags labeling what is cas, noncas, a delta patch, etc anymore.

As far as I can see, there's no noncas chunks or resources in this game. Everything is in CAS files.

> Reply from elementofprgress
>
> How many audio files total have you been able to pull with just info from the data folder?

I don't have the game, so I don't know.

I have all small files (sb/toc, etc) and only the first cas_01.cas files from the whole set. But considering the size of chunks extracted from these, everything is extracted. The script goes through all sb/toc files, including the patch folder.

Also, by simple logic, since the whole patch folder is so small, it just can't hold any significant amount of chunk data (sounds or textures, or anything). The patch probably changes levels or some other game properties, but not the original audio/visual content.

At least thats how it was in other games that I had full size (Dragon age, Battlefield HL)
## Post #46
- Username: elementofprgress
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Dec 10, 2015 2:48 am
- Post datetime: 2015-12-13T20:02:11+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from daemon1
>
> elementofprgress wrote:There are no flags labeling what is cas, noncas, a delta patch, etc anymore.

As far as I can see, there's no noncas chunks or resources in this game. Everything is in CAS files.
BF4 had like....18 different possible kind of files, but pretty much all the files used like...6? or so and everything was nice and marked right in the toc, sb, bundles, and files themselves. 

> Reply from daemon1
>
> 
elementofprgress wrote:How many audio files total have you been able to pull with just info from the data folder?

I don't have the game, so I don't know.

I have all small files (sb/toc, etc) and only the first cas_01.cas files from the whole set. But considering the size of chunks extracted from these, everything is extracted. The script goes through all sb/toc files, including the patch folder.

Also, by simple logic, since the whole patch folder is so small, it just can't hold any significant amount of chunk data (sounds or textures, or anything). The patch probably changes levels or some other game properties, but not the original audio/visual content.

At least thats how it was in other games that I had full size (Dragon age, Battlefield HL)

AHHH I didn't know you didn't have the game/updated files. Things make more sense now. There are a few more cas/cat files now and a few weird things going on now. The release patch folder was so small I really didn't start catching on to what was going on in the patch folder and such until after when there was actually something there. 

Yeah, most of the game is in the base folders(~80k cat entries and like ~45k in the base, but even amount of sb/toc entries) but at the same time the patch folder if full of delta patches, where it only takes a handful of bytes to change a file. I was curious to see how much they messed with resource files via patching with out having to dump all the audio again. Last time I got something like 130k audio files and it took fooooorrrever.
## Post #47
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-13T20:41:14+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from elementofprgress
>
> I was curious to see how much they messed with resource files via patching with out having to dump all the audio again. Last time I got something like 130k audio files and it took fooooorrrever.

I can't imagine them changing some bytes in an AUDIO file. More like sound ebx, to turn the volume up/down a bit. Anyway, you can just comment the decoding routine and make a counter to do that.
## Post #48
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-17T17:58:19+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from elementofprgress
>
> 130k audio files

I also recommend using my XAS decoder, because Frank's dll makes 32-bit WAV files, and this is a big waste of space in case of 130k files.
## Post #49
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-29T16:03:48+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

Audio decoder updated. Because of minor error, very long audio chunks (music) were converted wrong.
## Post #50
- Username: ariarosmurf
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 14, 2016 7:51 pm
- Post datetime: 2016-02-14T11:56:30+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

Can someone please tell me where i can get the unpacker decoder, i wanna get all the voices from battlefront!
## Post #51
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-14T15:20:56+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from ariarosmurf
>
> Can someone please tell me where i can get the unpacker decoder, i wanna get all the voices from battlefront!

It's right here in this thread in the first post!
## Post #52
- Username: ariarosmurf
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 14, 2016 7:51 pm
- Post datetime: 2016-02-14T16:10:45+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

cant find it, please link me the download
## Post #53
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-14T17:38:28+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

[viewtopic.php?f=10&t=13584](http://forum.xentax.com/viewtopic.php?f=10&t=13584)
## Post #54
- Username: ariarosmurf
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 14, 2016 7:51 pm
- Post datetime: 2016-02-14T20:08:18+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

yeah but how do it work,  is it just SWBF.rar? what do i do help
## Post #55
- Username: ariarosmurf
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 14, 2016 7:51 pm
- Post datetime: 2016-02-14T20:23:23+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

please tell me what to do
## Post #56
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-15T15:42:41+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

If you never used python to unpack Frostbyte engine, I'm afraid this will be too hard. Try searching for tutorials for battlefield or other Frostbyte games.

Also you can use simple decoder, that's very easy, but in this case, files will have no proper names.
## Post #57
- Username: ariarosmurf
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 14, 2016 7:51 pm
- Post datetime: 2016-02-15T22:54:43+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

cant u give me a download llink for sounds
## Post #58
- Username: johnathon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 07, 2016 12:20 am
- Post datetime: 2016-04-14T08:05:40+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

Anyone else having memory issues with the script?
After running for about 5 hours, Python complains that it's out of RAM. I checked in task manager and it shows Python using 1.8GB of memory, which is just at the 2GB limit for 32bit processes.
Patching Python to be large address aware lets the script run for a lot longer. But eventually it fails in the same way when Python reaches 3.8GB memory usage.
Is the script leaking memory somewhere?
## Post #59
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-14T10:43:46+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

I don't have the full game, so I can't check it. I don't think the script can leak memory, but the LZ77.DLL, which is probably written in c++, can.

What's the result of unpack? How much of the data it dumps until crash?

I can suggest you unpacking 3 big parts separately: initial, mp & sp.
## Post #60
- Username: johnathon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 07, 2016 12:20 am
- Post datetime: 2016-04-16T11:06:51+00:00
- Post Title: Re: StarWars Battlefront unpacker / audio decoder

> Reply from daemon1
>
> I don't have the full game, so I can't check it. I don't think the script can leak memory, but the LZ77.DLL, which is probably written in c++, can.

What's the result of unpack? How much of the data it dumps until crash?

I can suggest you unpacking 3 big parts separately: initial, mp & sp.

It dumps around 13GB before failing.
Thanks for the suggestion, I'll give that a go. Presumably by commenting out the other cat path definitions?

I've also noticed that it doesn't seem to dump any ebx files from the expansion packs. It makes the xp0 and xp1 directories and subdirectories but they're all empty. I commented out the lines that dump the res and chunk files so that the script can complete (they use the most memory), but the folders are still empty. Any ideas?
## Post #61
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-16T11:37:56+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

> Reply from johnathon
>
> Presumably by commenting out the other cat path definitions?

Yes, and the same answer is for "XP" packs, the script only takes CAT files its told to. So by replacing the paths to those of expansion packs, you should be able to dump it too, though I'm not sure.

There's also a project by elementofprgress user here [viewtopic.php?f=10&t=13702](http://forum.xentax.com/viewtopic.php?f=10&t=13702) who tried to dump all data, including patches, you can check it too, while it had some problems with texture mips overwtiting main textures, it may be better in something.
## Post #62
- Username: johnathon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 07, 2016 12:20 am
- Post datetime: 2016-04-17T13:42:40+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

> Reply from daemon1
>
> johnathon wrote:Presumably by commenting out the other cat path definitions?

Yes, and the same answer is for "XP" packs, the script only takes CAT files its told to. So by replacing the paths to those of expansion packs, you should be able to dump it too, though I'm not sure.

Ah, of course. I didn't notice that the xp cats weren't included in the script.

So I ran the script again and kept an eye on the memory usage as it went. It worked as you'd expect for quite a while. Usage would go up by around 20MB while processing a chunk, and then decrease before moving onto the next chunk. However when it gets to a specific chunk (2550ad6e0c4d281384a6bf767bb7a959.chunk in Patches/chunk0.toc), it gets stuck and the memory usage keeps on growing until the process runs out of memory. So it looks like it isn't a memory leak, but instead a specific chunk is throwing it off. Surely the chunk can't be that big?

Update: I checked the chunk size in the cat and it says it's only 11132419 bytes...
## Post #63
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-17T14:05:48+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

Yes, must be something wrong with this chunk, but I can't check it, because I don't have this CAS file. So I can only suggest you skipping it for now. With a code like this maybe:

```
        if hexlify(entry.id)=="2550ad6e0c4d281384a6bf767bb7a959" : continue
```


p.s. maybe its some problem in decompression routine...
## Post #64
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-05-22T00:46:39+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

So i've been holding onto this for awhile and since the original devs have from what i can tell no use to ever finish it here you guys go.

This tool only works with the Alpha build of the game so remember that.

The tool was edited from the Dragon Age inquisition mod tool or DAI_Tool by danielmm8888,PistonMiner and me Corra_Ashu/JakeGreen edited a couple small things after they gave it to me, the tool can easily be decompiled as that is how they originally was able to edit this tool and get it working with SWBF.

The reason for the release of this now is cause SWBF is getting harder and harder to extract stuff from and for some reason the scripts posted here aren't getting out everything from the latest updates cause it errors very close to the end of finishing and this tool here if someone was to decompile it and edit it to work with the main game then we wouldn't have to extract 30 plus gigs or more to our hard drives when we want say a new hero,villain or weapon released to this game.

This tool also can support sound extraction but atm it's not working properly in the tool and i think it's an easy fix i just don't know enough on that end to fully fix it.

There are 2 versions of the the tool one that is called SRGB which is the textures as DICE made them pre-shaders and then No SRGB which is basically DICE's PBR baked into the texture to make it brighter, i suggest using the SRGB one as it's the original textures that DICE used pre-shaders and much nicer.

You are also going to need 2 tools which i find very useful, First tool would be Visual Studio 2013 to open the dds files extracted from the tool to convert them to PNG and then Xnview to convert them back to dds otherwise without xnview opening the png in photoshop merges the alpha layer in all the RGB channels.

You can find it here [https://www.visualstudio.com/en-us/d...studio-vs.aspx](https://www.visualstudio.com/en-us/d...studio-vs.aspx)

an Xnview here [http://www.xnview.com/en/](http://www.xnview.com/en/)

Finally here is the tool. 
[http://www.mediafire.com/download/ri5ui ... F_Tool.rar](http://www.mediafire.com/download/ri5uippk6oeh9bq/SWBF_Tool.rar)

Here is also a video on how the tool works

[https://www.youtube.com/watch?v=MA_O7lw ... e=youtu.be](https://www.youtube.com/watch?v=MA_O7lw9mz8&feature=youtu.be)

I really hope someone can edit this tool to work with the main game as it would be a huge help for everyone. Also something cool to note this tool works with Battlefield Hardline well last i check back in August it worked with it, the program errors close to the end of reading all the files but it still shows most of the base models from the game allowing for easy extraction.

Lastly this tool also can support the extraction of bones on the models but since the tool was never finished it doesn't work properly, maybe someone can fix that and make it so you can extract in FBX with bones.
## Post #65
- Username: stkopp
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 08, 2016 5:38 pm
- Post datetime: 2016-06-08T13:48:05+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

Well, textures from Batch_Itexture are broken
## Post #66
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-10T17:04:28+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

> Reply from stkopp
>
> Well, textures from Batch_Itexture are broken

I don't have the game, so if you want me to fix this, provide EBX & chunk files that don't work
## Post #67
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2016-07-25T00:28:17+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

Your Batch_Itexture_Converter is only working tool I found so far, which can convert textures from NFS Rivals .itexture files.
Especially normal maps.
But it's not fully compatible, it makes wrong (but fixable) headers and requires renaming .itexture to .texture for converting.

So, can I ask you for quick-fix version for NFS Rivals?

Only 2 changes is needed - read .itexture (again) and put correct dimensions to headers:



rivals.png (60.92 KiB) Viewed 203 times


I already fixed values on this pic, tool output is:

```
GUID = 8A1A0B99BDF3C8D8F177FA062BF01739    car_astonmartin_vanquish_2013_internal_e 7afe918e22c21d1b.Texture  1 x 256
GUID = BB3F8422F82B91F933DE6DEEB087A1F3    car_astonmartin_vanquish_2013_internal_material da9a0d3980b89b39.Texture  1 x 256
GUID = F4BC0488B115F95CC6341EF68D8764E1    car_astonmartin_vanquish_2013_internal_n 842d55a70b9698d3.Texture  1 x 2048
```
## Post #68
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2016-07-25T00:29:38+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

Sample .itexture files attached.
[itexture_samples.zip](https://xentaxbackup.github.io/file/11362_itexture_samples.zip)
## Post #69
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2016-07-25T00:47:23+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

Another little bug with "car_astonmartin_vanquish_2013_light_e 062006af8be60dfb.itexture" - compression type detected as 47, but correct is 4D.
Attached .chunk, just in case.

PS: Same thing with "car_astonmartin_vanquish_2013_light_material b1bac978a310c44d.itexture".
[light_e_chunk.zip](https://xentaxbackup.github.io/file/11363_light_e_chunk.zip)
## Post #70
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-07-25T06:19:59+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

Ok its not originally my tool, but I can make a version for NFS. They changed layout and compression codes. If one code changed, others may be different too.
## Post #71
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2016-07-25T10:49:09+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

> Reply from daemon1
>
> Ok its not originally my tool, but I can make a version for NFS. They changed layout and compression codes. If one code changed, others may be different too.
Would be really helpful, thanks!
Original author refuses to help in comments for his [tuto on youtube](https://www.youtube.com/watch?v=VdgwQpWCk84), and his [latest version of tool](https://dl.dropboxusercontent.com/u/88155050/StarWars%20BF/Batch_Itexture_Converter%28SWBF%29.rar) (for [SWBF 2015](http://forum.xentax.com/viewtopic.php?f=33&t=13145)), doesn't detect .itextures or .textures in NFS Rivals dump.
## Post #72
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-07-26T19:13:47+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

Can someone look at the Dumper script and see if they can edit it cause whenever i start python and start the script with what i have selected it always tells me Patched cat not found and here is what i have.

```
bf4Directory=r"D:\Program Files (x86)\Origin Games\STAR WARS Battlefront" 
targetDirectory = r"D:\Mod Files\SWBF\SWBF_Models" 


###The following paths do not require adjustments (unless the devs decided to rename their folders). Note that they are relative to bf4Directory.

#As files are not overwritten, the patched files need to be extracted first.
#The script will dump all tocs it can find in these two folders+subfolders:
tocRoot  = r"Patch\win32" #patched and xpack files FIRST
tocRoot2 = r"Data\win32"   #unpatched vanilla files SECOND

#Note: The "Update" tocRoot contains both patch (for vanilla AND xpack) and unpatched xpack files. The reason it still
#      works correctly is because it goes through the folders alphabetically, so the patch comes first.


#Feel free to comment out one or both cats if they don't exist (some Frostbite 2 games shipped without cats).
#Although in that case you could just as well use an invalid path, i.e. not change anything.
cat1Path       = r"Data\Win32\installation\SP\cas.cat" 
cat2Path       = r"Data\Win32\installation\MP\cas.cat" 
cat3Path       = r"Data\Win32\installation\initialexperience\cas.cat"
cat4Path       = r"Data\Win32\installation\extracontent_01\cas.cat"
cat5Path       = r"Patch\Win32\installation\SP\cas.cat"
cat6Path       = r"Patch\Win32\installation\MP\cas.cat"     
cat7Path       = r"Patch\Win32\installation\extracontent_01\cas.cat" 
cat8Path       = r"Patch\Win32\xp0\xp0\cas.cat"
cat9Path       = r"Patch\Win32\xp1\xp1\cas.cat"
cat10Path       = r"Patch\Win32\xp2\xp2\cas.cat"
#cat8Path       = r"Update\Xpack0\Data\Win32\xp0\xp0"
#cat9Path       = r"Patch\Win32\installation\sp\cas.cat" 
updateCatPath = r"Update"

```
## Post #73
- Username: sin10001
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 16, 2016 2:17 pm
- Post datetime: 2016-08-16T14:57:16+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

Hi!

First: I'm new to most of this, so apologies if I ask anything ignorant (and please direct me to places to learn for myself, if it's easier). 

Second: I want to get the head & body mesh etc for the characters in this game. I've run the first python script and gotten my dump folders ("Bundles, Chunks, EDX"), but am stuck after that. Any help would be much appreciated
## Post #74
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-08-26T00:44:32+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

Okay so the script on this page is messing up a lot now it's not finding the proper chunk files for basic textures that were once working like helmets for the stormtroopers and a lot of character msr and normal maps and making them really small file size (under 100kb) when they should be in the range of 2mb to 5mb.

Dice must of changed something in the files for the textures, is there anyway someone can take a look at the script and possible fix it,cause i did and i've tried to fix it and nothing i've done has worked.
## Post #75
- Username: badhorse
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 14, 2016 11:00 am
- Post datetime: 2016-08-27T14:59:04+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

> Reply from JakeGreen
>
> Okay so the script on this page is messing up a lot now it's not finding the proper chunk files for basic textures that were once working like helmets for the stormtroopers and a lot of character msr and normal maps and making them really small file size (under 100kb) when they should be in the range of 2mb to 5mb.

Dice must of changed something in the files for the textures, is there anyway someone can take a look at the script and possible fix it,cause i did and i've tried to fix it and nothing i've done has worked.

I'm having the same problem. I'm not sure if it's putting the wrong mip data in the chunk file, or if the correct data is getting pulled, but the hex identity in the texture file is wrong and pointing to the wrong chunk file. I guess it's possible that the correct image data is in a different chunk, but I'm not sure how to figure out which one it might be. As it is now, the DDS header end up with the wrong image size data, and had to be hex edited manually to even open up the incorrect smaller mip. 

Unfortunately I can't see the pattern as far as which images get pulled correctly, and which ones are undersized, with incorrect erroneous header data.
## Post #76
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-08-29T05:16:56+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

> Reply from badhorse
>
> JakeGreen wrote:Okay so the script on this page is messing up a lot now it's not finding the proper chunk files for basic textures that were once working like helmets for the stormtroopers and a lot of character msr and normal maps and making them really small file size (under 100kb) when they should be in the range of 2mb to 5mb.

Dice must of changed something in the files for the textures, is there anyway someone can take a look at the script and possible fix it,cause i did and i've tried to fix it and nothing i've done has worked.

I'm having the same problem. I'm not sure if it's putting the wrong mip data in the chunk file, or if the correct data is getting pulled, but the hex identity in the texture file is wrong and pointing to the wrong chunk file. I guess it's possible that the correct image data is in a different chunk, but I'm not sure how to figure out which one it might be. As it is now, the DDS header end up with the wrong image size data, and had to be hex edited manually to even open up the incorrect smaller mip. 

Unfortunately I can't see the pattern as far as which images get pulled correctly, and which ones are undersized, with incorrect erroneous header data.

From what i seen is if you try to extract the patch files and the data files together along with the DLC it doesn't even care about getting the DLC other then some of their folder names but for some reason textures inside the patch files are different like they've been updated and the format changed a bit or something so the texture converter doesn't work.

I went and copied the data folder out of the game and extracted everything properly via that but there are weapons and updated files in the patch files that aren't extracting and working when they do extract, i really hope someone can fix this.
## Post #77
- Username: Icetric
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 09, 2017 6:19 pm
- Post datetime: 2017-02-15T12:56:15+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

> Reply from daemon1
>
> Modified "FrankElstner's" scripts to unpack StarWars Battlefront:

swbf_dump contains dumper script sw_dumper.py

fb3decoder contains audio conversion script fb3decoder.py

NOTE Don't forget to modify folder names in both scripts!

swbf_cas folder - the old simple extractor, just in case

p.s. old mesh tool is working, audio is extracted properly, updated texture tool included.

Hello, I now be badly in need of LZ77. DLL source code, but do you have? Can you give me a? Thank you very much! My email is [849392294@qq.com](mailto:849392294@qq.com)
## Post #78
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-15T15:11:41+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

> Reply from Icetric
>
> Hello, I now be badly in need of LZ77. DLL source code, but do you have? Can you give me a? Thank you very much! My email is 849392294@qq.com

This is NOT LZ77. This is standard LZ4. You can find source everywhere.
## Post #79
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-04T18:15:33+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

I managed to get this script to work a while back, this was before reinstalling windows, now I try again but it gives me an error:

```
  File "C:\Users\Darren\Downloads\Models\SWBF\tools\swbf_dump\sw_dumper.py", line 52, in <module>
    LZ77 = cdll.LoadLibrary("LZ77")
  File "C:\PYTHON27\LIB\ctypes\__init__.py", line 443, in LoadLibrary
    return self._dlltype(name)
  File "C:\PYTHON27\LIB\ctypes\__init__.py", line 365, in __init__
    self._handle = _dlopen(self._name, mode)
WindowsError: [Error 126] The specified module could not be found
```


Would anyone know how to solve this? I placed the .dll in the main Python folder, placed it in the dll folder, both don't make it work. Thanks.
## Post #80
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-04T18:34:41+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

must be 32/64 bit problem
## Post #81
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-04T20:00:05+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

I tested both 32 and 64, 64 gives me "is not a valid Win32 application" error and 32 version gives me this error.
## Post #82
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-04T21:05:49+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

This is not my DLL but I can suppose that something it needs is missing, like msvcp110.dll or msvcr110.dll
## Post #83
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-03-04T21:20:04+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

I downloaded the needed programs to get those dlls but it doesn't seem to work either unfortunately :/ I didn't do anything special the last time it worked before I reinstalled windows, so I have no idea why it doesn't work now.
## Post #84
- Username: Icetric
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 09, 2017 6:19 pm
- Post datetime: 2017-07-15T02:19:57+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

Hello, I downloaded the batch_Itexture_Converter some problems, you can send me some newer no problem source? Thank you very much!
## Post #85
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2017-11-18T01:42:47+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

hi all i unpack all audio files in to wav will game pickup the wav files as they are or do have repack them make them work as played game for sum hour it missing wow factor hoping it blow mind with in game audio but it don't so hope if files unpack i edit them give game bit kick, i have very large hifi 7.1 system it just not what i thinking game sound like so will play wav.
## Post #86
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2017-11-18T03:18:43+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

so when use the swbf_cas.exe after give me .exa on end wav files how batch 1995 files as don't want drag one at time too xas_decode.exe i could just chance the .exa to .wav but they not unpack don't work. is faster way do it. i try drag all them in to program no luck get all do same time. ok so unpack all sound files i work out way do all at same time save trying do 1 a time right click got open program with set it to xas_decode.exe then when go folder u see all exa file high light all them then press enter it do all same time when unpack them half 1 ch and 2 ch, as well 4 ch can't under stand why did audio so low sample rate 48khz i recoded them to 96khz sound lot better and i try 192khz see if still work in game taking me good day of work unpack them, just big thanks to you guys great job making program we stuffed without u guys.
## Post #87
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2017-11-29T04:08:47+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

hi all i unpack all files and made folder all sound file and program unpack game files so here link to folder.
[https://mega.nz/#!ti4kgCLb!DOJOpQ5Cph7c ... MSBolMphFk](https://mega.nz/#!ti4kgCLb!DOJOpQ5Cph7cbnAiCwW1bpdsHXLd4X1JDMSBolMphFk)
here as well all sound files in mp3 as well it could upload wav one as hit 146gb's so made in mp3 192khz so it only 3.34gb's they put right folders for game u unpack them to game if like as found it plays mp3 audio it took me days do all them hope u all do mods on sounds or use them other thing enjoy. I have start work on each sound file fix up low sounds and add effects to them add echo to light-saber give whoosh sound better as miss in my game i done video of sound mod just find place upload them. here link to mp3 in folder.

[https://mega.nz/#!Az5RXCqB!zrsftyfR24L3 ... e4IbntS7wg](https://mega.nz/#!Az5RXCqB!zrsftyfR24L3cX_Ezpfopu_08I4h23yJ5e4IbntS7wg)
## Post #88
- Username: vaultboye
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 02, 2017 10:12 pm
- Post datetime: 2017-12-02T14:15:31+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

Does anyone have a batch version for xas_decode ? Putting multiple .exa files on it will cause it to crash, and there are literally too many files to drag and drop one by one. (noob btw)
## Post #89
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-12-02T14:26:37+00:00
- Post Title: Re: StarWars Battlefront unpacker / decoder

you better use python script to convert all sounds with proper names automatically

anyway you dont need "batch" xas_decode, just make batch file (.bat) and run it
