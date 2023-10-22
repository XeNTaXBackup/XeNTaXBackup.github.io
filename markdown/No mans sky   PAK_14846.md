## Post #1
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2016-08-12T22:12:36+00:00
- Post Title: No mans sky   PAK

First thanks for hosting this kind of forum for us all.
I wonder if you had time to look at the pak files the data for nms are stored in?
I would love to mod ship design, planet generation to if thats possible.
Thanks for your time.
## Post #2
- Username: emoose
- Rank: beginner
- Number of posts: 26
- Joined date: Fri Sep 11, 2015 4:06 am
- Post datetime: 2016-08-13T07:48:48+00:00
- Post Title: No mans sky   PAK

Seems to be a variant of the PSAR archive used in a lot of PlayStation games.

The quickbms script from here ([viewtopic.php?p=91717#p91717](http://forum.xentax.com/viewtopic.php?p=91717#p91717)) sorta manages to extract it, always seems to error but still manages to extract a lot of files.

Files themselves seem zlib compressed, offzip can decompress them, but I think the bms script is extracting too much data as offzip is finding streams from the files following the one being decompressed..

(edit: confirmed, bms script is extracting $decompressedSize bytes of the compressed data, instead of $compressedSize... probably just needs a small tweak to extract the proper compressed size and then decompress it

edit2: oh it's easy to fix, change the line near the bottom "log NAME OFFSET SIZE" to "Clog NAME OFFSET SIZE SIZE", this will decompress the files to their proper size

edit3: unfortunately it's not a proper fix, NMS files are compressed in 64kib chunks which this bms script doesn't account for, so it only extracts a max of 64kib 

I would fix it but I can't find anything in the file indicating the size of the compressed chunk, and there doesn't look like any way for BMS to give me the size of the compressed data used for Clog..

Was going to try decompressing from (offset : offset+fsize), then recompressing that data and using the size of the recompressed data as the chunk size so we can find the offset of the next chunk, but it's unlikely BMS would have the same compression level etc, giving us the wrong size )

Hopefully a proper NMS script/tool gets made soon
## Post #3
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2016-08-13T12:17:24+00:00
- Post Title: No mans sky   PAK

Thanks for the reply! I need to read your info carefully hehe.
## Post #4
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-08-13T13:46:49+00:00
- Post Title: No mans sky   PAK

The script you posted isn't suitable with the PSAR structure No Man's Sky used for packing their files.

Instead, check this out:
[http://aluigi.org/bms/brink.bms](http://aluigi.org/bms/brink.bms)
## Post #5
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2016-08-13T18:34:28+00:00
- Post Title: No mans sky   PAK

It worked !
I think i found the script files. But they are in a format called mbin.  Unreadable as one would guess haha.

Still thank you!
## Post #6
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-08-13T21:33:54+00:00
- Post Title: No mans sky   PAK

i made a batch file to unpack all the game files. Just place in bms dir and change the first path to the file directory and second to the output

quickbms -d -F "*.pak" "brink.bms" "F:\Even More Steam\steamapps\common\No Man's Sky\GAMEDATA\PCBANKS" "F:\Even More Steam\steamapps\common\No Man's Sky\GAMEDATA\PCBANKS\unpacked"

i made a batch file to unpack all the game files. Just place in bms dir and change the first path to the file directory and second to the output

quickbms -d -F "*.pak" "brink.bms" "PCBANKS DIR" "OUTPUT DIR"

seems a LOT of engine settings are in

NMSARC.553AF401.pak

good thing is the textures are open to edit. dds files
## Post #7
- Username: asasfdfsfs
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 12, 2014 5:02 am
- Post datetime: 2016-08-14T00:37:24+00:00
- Post Title: No mans sky   PAK

Help me pls
## Post #8
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2016-08-14T01:29:18+00:00
- Post Title: No mans sky   PAK

> Reply from iambosh
>
> i made a batch file to unpack all the game files. Just place in bms dir and change the first path to the file directory and second to the output

quickbms -d -F "*.pak" "brink.bms" "PCBANKS DIR" "OUTPUT DIR"

seems a LOT of engine settings are in

NMSARC.553AF401.pak

good thing is the textures are open to edit. dds files
Do you know how to read this format mbin ?
If so, can we repack modified files?
## Post #9
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-08-14T02:56:27+00:00
- Post Title: No mans sky   PAK

> Reply from danielkarloskar1
>
> iambosh wrote:i made a batch file to unpack all the game files. Just place in bms dir and change the first path to the file directory and second to the output

quickbms -d -F "*.pak" "brink.bms" "PCBANKS DIR" "OUTPUT DIR"

seems a LOT of engine settings are in

NMSARC.553AF401.pak

good thing is the textures are open to edit. dds files
Do you know how to read this format mbin ?
If so, can we repack modified files?

I don't no, hopefully it shouldnt be too hard.
## Post #10
- Username: emoose
- Rank: beginner
- Number of posts: 26
- Joined date: Fri Sep 11, 2015 4:06 am
- Post datetime: 2016-08-14T04:46:49+00:00
- Post Title: No mans sky   PAK

> Reply from AnonBaiter
>
> The script you posted isn't suitable with the PSAR structure No Man's Sky used for packing their files.

Instead, check this out:
http://aluigi.org/bms/brink.bms
Thanks for posting this, seems to work great.

Looks like shaders are inside NMSARC.EEAC04FA.pak, uncompiled, shouldn't be too hard to edit them if this script supports repacking. (if it doesn't, I think the PSARC tool from this page should support it: [http://nomansskymods.com/mods/psarc-decompile-tool/](http://nomansskymods.com/mods/psarc-decompile-tool/))

Looking forward to a chromatic aberration disable mod
## Post #11
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-08-14T10:45:59+00:00
- Post Title: No mans sky   PAK

> Reply from emoose
>
> AnonBaiter wrote:The script you posted isn't suitable with the PSAR structure No Man's Sky used for packing their files.

Instead, check this out:
http://aluigi.org/bms/brink.bms
Thanks for posting this, seems to work great.

Looks like shaders are inside NMSARC.EEAC04FA.pak, uncompiled, shouldn't be too hard to edit them if this script supports repacking. (if it doesn't, I think the PSARC tool from this page should support it: http://nomansskymods.com/mods/psarc-decompile-tool/)

Looking forward to a chromatic aberration disable mod

here is a cheat engine table that can disable aberration and the vignette effect

[https://t.co/YDp1mny2GL](https://t.co/YDp1mny2GL)
## Post #12
- Username: emoose
- Rank: beginner
- Number of posts: 26
- Joined date: Fri Sep 11, 2015 4:06 am
- Post datetime: 2016-08-14T11:53:15+00:00
- Post Title: No mans sky   PAK

Looks like some progress is already being made with the models: [https://www.youtube.com/watch?v=kDG3visCxlk](https://www.youtube.com/watch?v=kDG3visCxlk)
Models seem to use the generic MBIN format, so I guess you could say some progress is being made with MBIN files too 
Hope this gets an open-source release, I could see a lot of interest in people developing mod tools for this game.

> Reply from iambosh
>
> emoose wrote:AnonBaiter wrote:The script you posted isn't suitable with the PSAR structure No Man's Sky used for packing their files.

Instead, check this out:
http://aluigi.org/bms/brink.bms
Thanks for posting this, seems to work great.

Looks like shaders are inside NMSARC.EEAC04FA.pak, uncompiled, shouldn't be too hard to edit them if this script supports repacking. (if it doesn't, I think the PSARC tool from this page should support it: http://nomansskymods.com/mods/psarc-decompile-tool/)

Looking forward to a chromatic aberration disable mod 

here is a cheat engine table that can disable aberration and the vignette effect

https://t.co/YDp1mny2GL

Neat, thanks for the link, I'll have to give this a try later.
## Post #13
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2016-08-14T14:53:46+00:00
- Post Title: No mans sky   PAK

Its always good with progress =)
I saw someone has created a mod reddit sub, which is good to spread the word. 
For you who are working on nms things, thank in beforehand
## Post #14
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-08-14T15:27:02+00:00
- Post Title: No mans sky   PAK

Oh, and I hope someone takes a deep look into why the game itself isn't working for some computers. Although the game itself was designed for more powerful computers to begin with...
## Post #15
- Username: emoose
- Rank: beginner
- Number of posts: 26
- Joined date: Fri Sep 11, 2015 4:06 am
- Post datetime: 2016-08-14T17:17:24+00:00
- Post Title: No mans sky   PAK

Someone on reddit already posted modded shaders for removing chromatic abberation (+ some other ugly stuff) 

[https://www.reddit.com/r/NoMansSkyMods/ ... he/d6h7qf5](https://www.reddit.com/r/NoMansSkyMods/comments/4xo25d/any_way_to_remove_chromatic_aberration_and_the/d6h7qf5)

EDIT: Also, I've figured out a way to make the game load loose files without needing to repack them, should be useful for people working on mods: [https://www.reddit.com/r/NoMansSkyMods/ ... iles_when/](https://www.reddit.com/r/NoMansSkyMods/comments/4xpe1c/psa_theres_no_need_to_repack_pak_files_when/)
## Post #16
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2016-08-15T14:30:46+00:00
- Post Title: Re: No mans sky   PAK

Emoose, have you any luck finding the ship/spacecraft file?
In like a file that says the way they are put together. It seems like it are different parts being put in groups somehow.
Modular way perhaps.
## Post #17
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-08-16T03:25:39+00:00
- Post Title: Re: No mans sky   PAK

Any luck on the .mbin files? I see people are uploading edited files on nomansskymods.com
## Post #18
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2016-08-16T11:39:09+00:00
- Post Title: Re: No mans sky   PAK

I just read about your mbin tool emoose, congrats of doing that 
Could you attach it here?
Thanks for your time
## Post #19
- Username: redspike474
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 05, 2016 2:24 am
- Post datetime: 2016-08-16T16:57:40+00:00
- Post Title: Re: No mans sky   PAK

Any way to run the game with the files unpacked so that shader edits and such work?
## Post #20
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-08-16T17:39:46+00:00
- Post Title: Re: No mans sky   PAK

> Reply from danielkarloskar1
>
> I just read about your mbin tool emoose, congrats of doing that 
Could you attach it here?
Thanks for your time

yeah and it isnt compiled, any link for a compiled version?

update: nvm i actually compiled it myself
## Post #21
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2016-08-17T13:52:28+00:00
- Post Title: Re: No mans sky   PAK

Can you share the compiled exe?
have you found any discoveries in the files yet  ?
