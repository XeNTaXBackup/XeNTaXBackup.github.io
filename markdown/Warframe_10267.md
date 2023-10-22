## Post #1
- Username: just2good
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2011 3:04 am
- Post datetime: 2013-03-25T05:13:14+00:00
- Post Title: Warframe

I did a bunch of lurking and saw that quickbms had a script for Darkness II.

There is a game called Warframe made by the same company that developed Darkness II and uses the same engine as well.

I was wondering if anyone is able to unpack and repack some of its data files because I really want to make some edits to skill animations for a video project I am working on.
If anyone could help me I would greatly appreciate it!

The data folder for Warframe is filled with .cache and .tor just like Darkness II.

I uploaded an example of the game's .cache + .toc to mediafire.

[http://www.mediafire.com/?4rp1rfpelcac6u4](http://www.mediafire.com/?4rp1rfpelcac6u4)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-25T06:00:49+00:00
- Post Title: Warframe

[http://aluigi.altervista.org/papers/bms ... kness2.bms](http://aluigi.altervista.org/papers/bms/others/darkness2.bms)
## Post #3
- Username: just2good
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2011 3:04 am
- Post datetime: 2013-03-25T06:28:20+00:00
- Post Title: Warframe

> Reply from Ekey
>
> http://aluigi.altervista.org/papers/bms ... kness2.bms

I tried that and it doesn't work.


Here is the other thread explaining that.
[viewtopic.php?f=16&t=9813&hilit=warframe](http://forum.xentax.com/viewtopic.php?f=16&t=9813&hilit=warframe)

Looked inactive so I made a new one btw. (thread)
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-25T06:46:57+00:00
- Post Title: Warframe

Doesn't work what ? Unpacking files work fine.
## Post #5
- Username: just2good
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2011 3:04 am
- Post datetime: 2013-03-25T07:41:25+00:00
- Post Title: Warframe

> Reply from Ekey
>
> Doesn't work what ? Unpacking files work fine.

Then I stand corrected.

Only thing that makes me wonder is why I can't get it to work, I'm using GUI 2.0 btw.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-25T07:52:10+00:00
- Post Title: Warframe

you need to use the latest version of QuickBMS:
[http://quickbms.aluigi.org](http://quickbms.aluigi.org)

QuickBMS is NOT that GUI program you see in the Tutorials section!
They are two different things and only the version of QuickBMS matters when there are problems with extraction/reimporting.
## Post #7
- Username: just2good
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2011 3:04 am
- Post datetime: 2013-03-25T23:10:42+00:00
- Post Title: Warframe

> Reply from aluigi
>
> you need to use the latest version of QuickBMS:
http://quickbms.aluigi.org

QuickBMS is NOT that GUI program you see in the Tutorials section!
They are two different things and only the version of QuickBMS matters when there are problems with extraction/reimporting.

Awesome I got it to work. Thanks a bunch!
## Post #8
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2013-03-26T12:14:08+00:00
- Post Title: Warframe

I know I probably should open a new topic in the graphical format sections , but i think there are enough treads about this games. 

I'm quite interested to convert the hd textures from this games. each chara has 4 different resolution versions of the same textures form 256x256 to 2048x2048 for the body and a lower res for the head (max head tex resolution is 1024x512).

These are some samples of what the script extracts from the archieves. [http://www.mediafire.com/?o7zxxd8xweiiw14](http://www.mediafire.com/?o7zxxd8xweiiw14)

They should be headerless pngs textures, for the dds is easier to add headers but with pngs i have no ideas.
I would ask help to correctly convert these tex.
## Post #9
- Username: toogte
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 11, 2012 8:57 pm
- Post datetime: 2013-06-07T19:26:03+00:00
- Post Title: Warframe

I have just been tested and for me the pictures are all empty .. I've done something wrong or is that the [bms] file?
## Post #10
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2013-06-30T09:14:04+00:00
- Post Title: Warframe

> Reply from toogte
>
> I have just been tested and for me the pictures are all empty .. I've done something wrong or is that the [bms] file?

U probably did something wrong. The textures seem to have their correct size. The problem is how make them usable.
## Post #11
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2013-07-05T14:35:17+00:00
- Post Title: Warframe

I think we found out that it is extracting files like dds, fbx etc but they seem to be wrong. Something is strange with the extracted data
## Post #12
- Username: zhade
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon May 16, 2011 5:51 am
- Post datetime: 2013-08-01T19:14:07+00:00
- Post Title: Warframe

Any updates regarding the extracted files? .lua and .txt files also have been altered.
[text.zip](https://xentaxbackup.github.io/file/6538_text.zip)
## Post #13
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-09-12T20:23:44+00:00
- Post Title: Warframe

I'm going to take a shot at saying that Darkness 2's BMS isn't very useful here. From what it seems it's not using RLE3 for the decompression algorithm, as the Lua scripts I tried to unpack makes no sense (e.g. seeing the string "modu" repeated dozens of times before finally seeing "module"). I'll hazard a guess, and say it's likelier to be LZMA, considering that's the same compression used for some of the files that gets downloaded from the content server.

The BMS script isn't too great, since it only keeps the last folder name found, therefore you can't repack the data.
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-12T20:34:43+00:00
- Post Title: Warframe

> Reply from zhade
>
> Any updates regarding the extracted files? .lua and .txt files also have been altered.
What for? Script for unpack files work perfect. Lua scripts just compiled. And compiling is not reversible (only by byte code decompiling)
## Post #15
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-09-12T21:59:30+00:00
- Post Title: Warframe

> Reply from Ekey
>
> Script for unpack files work perfect.
In the attached .lua, notice the 0x03 at offset 0x2e. That 0x03 isn't supposed to be there (it's supposed to be the path to the original Lua source code, and normal Windows file paths don't typically contain an ETX character). Also, notice all the repeating patterns of "Pod" and 0x0080e00b? There are way too many of them to be reasonable.

I've made an observation about the cache files: those that start with 'H' are headers, and those that start with 'B' are the corresponding binary content. I'm not quite sure what 'F' is yet. When downloading a single file from the content server (uncheck "Bulk Download" from the launcher), the sample I had appeared to be a LZMA archive with all parts of the expected files. When extracted, the file has the same odd compressed form as in the cache (so I assume it's written into the cache directly). When written to disk, part of the file goes in an 'H' cache, part of it goes into a 'B' cache, and possibly another goes into the 'F' cache.
## Post #16
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2013-09-16T09:59:37+00:00
- Post Title: Re: Warframe

Extraction is fine but the files are strange.  The png's that are extracted dont have the typical header and fbx start with NXS.MESH

I am guessing its obfuscated in some way but I have no idea how to check 

Trid copying header from png but nothing
## Post #17
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-09-16T15:42:30+00:00
- Post Title: Re: Warframe

> Reply from pixellegolas
>
> Extraction is fine but the files are strange.  The png's that are extracted dont have the typical header and fbx start with NXS.MESH

I am guessing its obfuscated in some way but I have no idea how to check 

Trid copying header from png but nothing
Extraction is not fine. The script is using the wrong compression. Some of the .fbx files are PhysX cooked meshes.

Anyway, a preliminary analysis on the compression scheme.

The first four bytes in the compressed file are likely checksum bytes. Possible candidates include CRC, sum, and whatever random shift/xoring scheme people like these days.
Next byte is uncompressed bytes count.
The byte that follows contains the repeated data length. Currently it looks like the high four bits indicate the length of the repeated bytes. Will need to find more examples.
The next byte indicates the negative offset from the last uncompressed byte to find subsequent bytes to copy.
Summary: It's some sort of LZ compression.

Some revisions:

The first four bytes may not necessarily be checksums. It seems to contain a type byte, a length, and something else.
High 4 bits in length indicates copy data length, low 4 bits indicate plain data length. Maybe. How do you tell them apart?

Another update: Finally found the decompression code in the game EXE. I will try to reverse engineer it.
Yet another update: I think I've written the decompressor right, but a lot of the files are still failing, mostly running out of array space. Lua files are looking a lot nicer, though.
## Post #18
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-09-16T23:01:03+00:00
- Post Title: Re: Warframe

I think I got it. Each compressed file is made of many blocks, some LZ compressed and some not. The first four bytes indicate some info about the block. For the purposes of the compression format, everything is big endian. In each block, there are two numbers of type 'short', the first one the size of the compressed block, the second one the size of the uncompressed data. If the two numbers are equal, this block is not compressed. Default uncompressed block size is 16KB.

For the compression, it's some type of LZ. Code bytes (value indicated by 'cb' here) are used to instruct decompression, and the byte following the block info is the first code byte. If cb <= 0x1f, this represents a literal of size (cb + 1), and the literal bytes follow the code byte. If it's greater, this indicate a copying operation, where (((cb & 0x1f) << 8) | *(pcb + 1)), where *(pcb + 1) is the value that follows the code byte, is the lookback length less one, and (cb >> 5) is the copy length segment.  If that equals 7, read (pcb + 2) and add it on to the copy length segment. The total number of bytes to copy is that value plus 2. Rinse and repeat for the rest of the block.

Extractor has been posted [here](http://forum.xentax.com/viewtopic.php?f=32&t=10782).
## Post #19
- Username: antoineflemming
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 01, 2014 11:50 am
- Post datetime: 2014-06-08T06:24:49+00:00
- Post Title: Re: Warframe

I understand this is an old thread by now, but if no one has found a way to open these png files, is there a way to possibly merge these files (all files with each B, F, H texture folder) as a possible solution? Is that even a viable solution?
## Post #20
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2014-06-11T17:10:49+00:00
- Post Title: Re: Warframe

as stated in another thread you can use ninja ripper for now to extract textures from the game. Look it up  I could not get it working but might be a amd problem
## Post #21
- Username: antoineflemming
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 01, 2014 11:50 am
- Post datetime: 2014-07-01T00:18:58+00:00
- Post Title: Re: Warframe

> Reply from pixellegolas
>
> as stated in another thread you can use ninja ripper for now to extract textures from the game. Look it up  I could not get it working but might be a amd problem

Yeah. Was afraid of that. Was trying to see if I could extract the textures for files that aren't visible within the game, like the Tenno blaster or the Tenno jumpsuit. Thanks for the response though.
## Post #22
- Username: VoidsShadow
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 29, 2014 5:49 am
- Post datetime: 2014-08-28T21:56:44+00:00
- Post Title: Re: Warframe

I know this thread is a little old, but still...

Okay, I decided to just say f*** it and I selected the entire windows.cache folder for the input. If it was a bad idea, it's too late now. The process has been going at it for nearly 20 minutes now; it's working on the texture caches at the moment. I think all the raw files will really help with creating fanmade stuffs. And modding, now that I think about it.

Edit (a minute later): ooh, fonts! And more sound files.
## Post #23
- Username: xbeton0L
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Dec 16, 2011 10:40 pm
- Post datetime: 2014-09-22T06:19:33+00:00
- Post Title: Re: Warframe

> Reply from VoidsShadow
>
> The process has been going at it for nearly 20 minutes now; it's working on the texture caches at the moment. I think all the raw files will really help with creating fanmade stuffs. And modding, now that I think about it.

Edit (a minute later): ooh, fonts! And more sound files.

Have you been able to make sense of any of the sound or animation files? There's got to be a pattern to the way these files are obscured.
## Post #24
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-09-22T10:32:53+00:00
- Post Title: Re: Warframe

I think someone just used a .WAV extractor or something.
## Post #25
- Username: StrikerMan780
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 29, 2014 2:45 pm
- Post datetime: 2014-10-10T19:16:22+00:00
- Post Title: Re: Warframe

Did anyone ever figure out how to get the sounds into a working form? I need to get the firing sound to the Supra in Warframe. (Apologies if this is a massive bump)

The Warframe wikia wiki seems to have some of the sounds, but I think those just came from the fansite kit.

> Reply from GMMan
>
> I think someone just used a .WAV extractor or something.
Hopefully said person will post about what extractor/tool they used, if they managed it.
## Post #26
- Username: Osprey
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 12, 2014 11:39 am
- Post datetime: 2014-11-12T03:41:13+00:00
- Post Title: Re: Warframe

Hey all, sorry to revive the thread again,

New to the whole process of getting files out of thiese sort of things. 

I'm primarily trying to get these FBX files out, any advice on how to go about this? 

cheers .
## Post #27
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-11-13T18:50:48+00:00
- Post Title: Re: Warframe

Check [here](http://forum.xentax.com/viewtopic.php?f=32&t=10782) for the extractor. Just drag and drop the .toc or .cache file on to the program to extract. Most files are split into at least two pieces, one in the H cache and another in the B/F caches. The FBX files may or may not be in FBX format, but someone's made an importer for the non-FBX mesh format.
## Post #28
- Username: xbeton0L
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Dec 16, 2011 10:40 pm
- Post datetime: 2015-01-18T22:30:08+00:00
- Post Title: Re: Warframe

I suppose this is relevant to the overall conceptualization of Warframe's unpacked files. I'm trying to learn exactly how to combine (if that's even possible) the "h" and "b" files from .cache archives. Someone wrote a MaxScript not long ago which combined the "h" and "b" model data files inside 3ds Max. If it can be done inside 3dsMax, it shouldn't be too hard to implement as a stand-alone application. And maybe this functionality can be extended to non-3d model data files, such as sound and animation data files.

I'm new to this but I'd like to try and help research how this can be done if I can. I've come to this thread, and others based on Warframe, at least a dozen times looking for updates or insights. I guess if I have the time to waste looking for help, I might as well try learning how to help others and myself at the same time.
