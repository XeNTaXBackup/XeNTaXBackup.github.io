## Post #1
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-05-22T23:08:54+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

Figured I'd bring this up since I am researching formats found in this framework/engine for Dragon's Dogma out of pure curiosity. Older posts have covered the archive format.

Depending on the game, various versions of the archive format are present, but they all follow the same basic format:

```
  uint32 magic // '\0ARC'
  uint16 version //(or flags?)
  uint16 fileCount
```


Observed versions: 4, 7, 8, 17

for each fileCount:

```
  char[64] name
  uint32 typeHash
  uint32 compressedSize
  uint32 flags
  uint32 offset
```


flags in each entry contains two values -- an unknown flags value, and the uncompressedSize. The position of flags depends on the game (older games have it stored in the upper 3 bits, newer games have it stored in the lower 3 bits). Unfortunately you can't handle this through the header's version value, since for example, Lost Planet 2 (PC) has a version of 8, but the unknown flags are in the upper 3 bits, but newer games such as Dragon's Dogma (on PS3), have version 8, but the flags are in the lower 3 bits.

Thus, the values, if the flags are in the lower 3 bits:

```
unknownFlags = (flags & 0x00000007) >> 0;
```


Or, if they are in the upper 3 bits:

```
unknownFlags = (flags & 0xE0000000) >> 29;
```


unknownFlags has been observed as always being 2 (b010) in Resident Evil 5 and Dragon's Dogma.

If compressedSize is equal to uncompressedSize, the data is not compressed.

Compression in the archives depends on game and platform as well, Resident Evil 5 (PC) uses zlib, Dragon's Dogma (Xenon) uses XCompress, Dragon's Dogma (PS3) uses zlib (but with non-default settings).

The main reason I'm opening this thread isn't about any of the above though, it's about the typeHash value.

typeHash value is a [crc32 hash of a string](http://svn.gib.me/public/mt/trunk/Gibbed.MT.FileFormats/StringHelpers.cs), masked by 0x7FFFFFFF (dropping the uppermost bit).

You can find complete (barring guessed file extensions) type lists for Dragon's Dogma and Resident Evil 5 on my MT repository:
[Dragon's Dogma](http://svn.gib.me/public/mt/trunk/bin/projects/Dragon%27s%20Dogma/archive_file_types.cfg), [Resident Evil 5](http://svn.gib.me/public/mt/trunk/bin/projects/Resident%20Evil%205/archive_file_types.cfg)

I can't help you with other games, but the type lists for those games should give you some idea of what to look for.

My repository can be found at: [http://svn.gib.me/public/mt/](http://svn.gib.me/public/mt/)

There are no binaries or a Pack tool (yet, if ever).
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-22T23:30:51+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

Thanks Ricky useful
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-22T23:32:16+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

the re5 demo on pc will throw errors on files it can't find and it will list the extension of the file its looking for. Just edit the arc file so the file name is different and it throws an error cant find file XXX.
might help with the finding of unknown extensions.
## Post #4
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-05-27T20:43:46+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from chrrox
>
> the re5 demo on pc will throw errors on files it can't find and it will list the extension of the file its looking for. Just edit the arc file so the file name is different and it throws an error cant find file XXX.
might help with the finding of unknown extensions.Thanks for this hint, I've figured out how to identify actual extensions in Dragon's Dogma.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-27T22:13:45+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

what was the trick to it.
## Post #6
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-05-27T22:41:27+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from chrrox
>
> what was the trick to it.The resource classes all specify the extension it uses, I just hadn't noticed.
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-05-28T07:33:57+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Rick
>
> chrrox wrote:what was the trick to it.The resource classes all specify the extension it uses, I just hadn't noticed.

hi Rick,

Does it also support RE5 X360?
## Post #8
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-05-28T08:22:42+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

Rick: So, I believe you figured out the archive file types same as you did filenames in Dragon Age 2, right? By hooking up game executable and dumping them?
## Post #9
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-05-29T03:47:45+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from michalss
>
> hi Rick,

Does it also support RE5 X360?No idea. Try the code and see if it works. I don't own RE5 on 360.

Edit: I haven't corrected the RE5 resource types list yet though.
Edit2: And you will need to set up a new project for Resident Evil 5 (Xenon) in the bin\projects directory to specify settings correctly.
Edit3: Specified & corrected all extensions for Resident Evil 5 resource types, revision 5.
## Post #10
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-05-29T03:48:06+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from mnn
>
> Rick: So, I believe you figured out the archive file types same as you did filenames in Dragon Age 2, right? By hooking up game executable and dumping them?Something like that, yes. Each game has its own specific resource types though.
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-05-29T12:31:54+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Rick
>
> michalss wrote:hi Rick,

Does it also support RE5 X360?No idea. Try the code and see if it works. I don't own RE5 on 360.

Edit: I haven't corrected the RE5 resource types list yet though.
Edit2: And you will need to set up a new project for Resident Evil 5 (Xenon) in the bin\projects directory to specify settings correctly.
Edit3: Specified & corrected all extensions for Resident Evil 5 resource types, revision 5.

Thx Rick. Can you please provide me right xml file with config?

I will send files to your PM.

Thx
## Post #12
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2012-06-01T13:03:50+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from michalss
>
> Rick wrote:michalss wrote:hi Rick,

Does it also support RE5 X360?No idea. Try the code and see if it works. I don't own RE5 on 360.

Edit: I haven't corrected the RE5 resource types list yet though.
Edit2: And you will need to set up a new project for Resident Evil 5 (Xenon) in the bin\projects directory to specify settings correctly.
Edit3: Specified & corrected all extensions for Resident Evil 5 resource types, revision 5.

Thx Rick. Can you please provide me right xml file with config?

I will send files to your PM.

Thx

using the xenon (xbox360) project setting of dragon's dogma unpacks re5 from x360 just fine for me.


use it in cmd as [path to gibbed.mt.unpack.exe] -p="Dragon's Dogma (Xenon)" [input] [ouput directory]
I had to move the trunk/bin/projects folder to trunk/gibbed.mt.unpack/bin/release/projects to make this work.
## Post #13
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-06-01T14:47:48+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

that is great any chane for repack RICK pls ?
## Post #14
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-01T21:53:35+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

I've been working on a repacker for this. So far it's working well although I need to make some changes before I can release it. There's a few things I can point out about the format when it comes to repacking:

- Dragon's Dogma is very nitpicky about the order of the files in the archives. If they're in a different order, it'll crash as it unpacks that arc. I'm not sure if it would be possible to figure out what the order is. Right now I've set up a system where the program saves a text file with the file order when extracting, and that text file can be used when repacking. RE5 doesn't seem to care about the order of files at all.

- The engine is okay with all files in an archive being uncompressed. One could be very lazy in this regard and add no support for zlib and xmem if you want only want a repacker with no extraction support.
## Post #15
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-03T19:21:48+00:00
- Post Title: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

Here's my extract/repack tool: [http://www.tzarsectus.com/tools/ARCtool.rar](http://www.tzarsectus.com/tools/ARCtool.rar)

I haven't added any proper documentation yet. Thanks to rick and aluigi for all the information on the format. Tool is compatible with xbox versions of RE5, RE6 demo and Dragon's Dogma. It might be compatible with more xbox MT Framework games. I haven't added support for PC or PS3 arc formats (yet).

Here's some quick examples how to use it...

Dragon's Dogma extract:
arctool -x -txt -dd npc375.arc

Dragon's Dogma repack:
arctool -c -txt -dd npc375

Resident Evil 6 demo extract:
arctool -x s0502.arc

Resident Evil 6 demo repack:
arctool -c -alwayscomp s0502

Resident Evil 5 extract:
arctool -x -re5 s400.arc

Resident Evil 5 repack:
arctool -c -re5 s400

Edit: Updated the tool, same download link. RE6 seems to require every file to be compressed so I added an option for always compressing files.
## Post #16
- Username: OneTwo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2011 7:01 pm
- Post datetime: 2012-07-04T04:50:56+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> Here's my extract/repack tool: http://www.tzarsectus.com/tools/ARCtool.rar
I haven't added support for PC or PS3 arc formats (yet).

Resident Evil 5 extract:
arctool -x -re5 s400.arc

Resident Evil 5 repack:
arctool -c -re5 s400
Waiting for support PC release
## Post #17
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-04T09:07:14+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from OneTwo
>
> Sectus wrote:Here's my extract/repack tool: http://www.tzarsectus.com/tools/ARCtool.rar
I haven't added support for PC or PS3 arc formats (yet).

Resident Evil 5 extract:
arctool -x -re5 s400.arc

Resident Evil 5 repack:
arctool -c -re5 s400

Waiting for support PC release
[http://z6.invisionfree.com/Resident_Evi ... opic=10046](http://z6.invisionfree.com/Resident_Evil_4_PC/index.php?showtopic=10046) - You can use this tool for extracting and repacking RE5 arc files on PC.

I'll probably add support for PC MT Framework games later for my tool.
## Post #18
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-07-04T10:12:30+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> Here's my extract/repack tool: http://www.tzarsectus.com/tools/ARCtool.rar

I haven't added any proper documentation yet. Thanks to rick and aluigi for all the information on the format. Tool is compatible with xbox versions of RE5, RE6 demo and Dragon's Dogma. It might be compatible with more xbox MT Framework games. I haven't added support for PC or PS3 arc formats (yet).

Here's some quick examples how to use it...

Dragon's Dogma extract:
arctool -x -txt -dd npc375.arc

Dragon's Dogma repack:
arctool -c -txt -dd npc375

Resident Evil 6 demo extract:
arctool -x s0502.arc

Resident Evil 6 demo repack:
arctool -c -alwayscomp s0502

Resident Evil 5 extract:
arctool -x -re5 s400.arc

Resident Evil 5 repack:
arctool -c -re5 s400

Edit: Updated the tool, same download link. RE6 seems to require every file to be compressed so I added an option for always compressing files.

Good work gonna try X360 Dragon's Dogma  Thx
## Post #19
- Username: OneTwo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2011 7:01 pm
- Post datetime: 2012-07-04T10:32:16+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> 
http://z6.invisionfree.com/Resident_Evi ... opic=10046 - You can use this tool for extracting and repacking RE5 arc files on PC.

I'll probably add support for PC MT Framework games later for my tool.
Yes, I am familiar with this program, but yours I like more  because it has the support of the console commands. Therefore very much hope that you will get and carry out full-fledged support of PC-Release.
sorry for the translate.yandex.ru
## Post #20
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-04T10:49:24+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

I'll definitely add PC support at some point, but it'll take some work as I need to add support for zlib compression and right now I'm busy with another project. Thanks for liking the program.
## Post #21
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-07-04T12:03:29+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> I'll definitely add PC support at some point, but it'll take some work as I need to add support for zlib compression and right now I'm busy with another project. Thanks for liking the program.

Dont worry about PC . Console rulezzzz  joke
## Post #22
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-04T16:00:54+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from michalss
>
> Sectus wrote:I'll definitely add PC support at some point, but it'll take some work as I need to add support for zlib compression and right now I'm busy with another project. Thanks for liking the program.
Dont worry about PC . Console rulezzzz  joke
I do not think so. For console is much more difficult to write unpacker, than PC. For PC you can debugging, for console nope
## Post #23
- Username: Nexus Elite
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 16, 2011 1:36 am
- Post datetime: 2012-07-05T06:05:13+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> I'll definitely add PC support at some point, but it'll take some work as I need to add support for zlib compression and right now I'm busy with another project. Thanks for liking the program.

Is there any chance you could get LP2 files to extract as well?
## Post #24
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-05T07:31:19+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Nexus Elite
>
> Sectus wrote:I'll definitely add PC support at some point, but it'll take some work as I need to add support for zlib compression and right now I'm busy with another project. Thanks for liking the program.

Is there any chance you could get LP2 files to extract as well?
PC or xbox version of LP2? It might already work with xbox version of the game.
## Post #25
- Username: Nexus Elite
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 16, 2011 1:36 am
- Post datetime: 2012-07-05T21:25:08+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> Nexus Elite wrote:Sectus wrote:I'll definitely add PC support at some point, but it'll take some work as I need to add support for zlib compression and right now I'm busy with another project. Thanks for liking the program.

Is there any chance you could get LP2 files to extract as well?
PC or xbox version of LP2? It might already work with xbox version of the game.

Which ever works fine. Since the current arc extractor, doesn't seem to extract it properly, i think. 

And when viewing the dds or the model files, it's broken.
## Post #26
- Username: marlborox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 09, 2011 10:03 am
- Post datetime: 2012-07-13T12:11:44+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

Great tool, although i tried extracting s0305 & repacking it compressed & got the following error.



The only thing that springs to mind is it reads the last character wrong because the directory+filename is longer than expected, but thought you should know, am looking forward to this 

i know one of them is the wrong cmd for repacking, i was just checking to see if it happened doing that too
## Post #27
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-13T14:18:16+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from marlborox
>
> Great tool, although i tried extracting s0305 & repacking it compressed & got the following error.



The only thing that springs to mind is it reads the last character wrong because the directory+filename is longer than expected, but thought you should know, am looking forward to this 

i know one of them is the wrong cmd for repacking, i was just checking to see if it happened doing that too
Oh yeah, I did fix that but I forgot to upload the newest version.

It should work fine with this version: [http://www.tzarsectus.com/tools/ARCtool.rar](http://www.tzarsectus.com/tools/ARCtool.rar)
## Post #28
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-07-13T20:58:29+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

Hi Sectus,
Do u know please where are the texts please ?Or anyone ??

EDIT :
I Found them in millions of files  - This is gonna be really pain to translate

Thx
## Post #29
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-19T15:55:23+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

New version of my tool: [http://www.tzarsectus.com/tools/ARCtool.rar](http://www.tzarsectus.com/tools/ARCtool.rar)

Use "-tex" to automatically convert TEX to TGA files. Use "-texRE5" or "-texRE6" to choose TEX format. This doesn't work with all TEX files though. And there's still no PC support.
## Post #30
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-07-20T15:12:45+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> New version of my tool: http://www.tzarsectus.com/tools/ARCtool.rar

Use "-tex" to automatically convert TEX to TGA files. Use "-texRE5" or "-texRE6" to choose TEX format. This doesn't work with all TEX files though. And there's still no PC support.

That is perfect thx
## Post #31
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-07-21T11:42:18+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> New version of my tool: http://www.tzarsectus.com/tools/ARCtool.rar

Use "-tex" to automatically convert TEX to TGA files. Use "-texRE5" or "-texRE6" to choose TEX format. This doesn't work with all TEX files though. And there's still no PC support.

HI can u also add DD please. Does repack function works as well pls? Reason why u it does not work on all TEX files is that some of them are double compressed. Dont ask me why, coz i dont know.
## Post #32
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-21T12:35:46+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

I can't remember if I tested it much, but extracting DD textures should work if you use "-texRE6"

I haven't added a feature for converting TGA files back to TEX but I'm planning to.
## Post #33
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-07-21T14:32:07+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> I can't remember if I tested it much, but extracting DD textures should work if you use "-texRE6"

I haven't added a feature for converting TGA files back to TEX but I'm planning to.

Does not work on DD, if i use texRE6 nothing happen, if i use -tex application crashing.. Also wanna as you if u can use DDS format instead of TGA
## Post #34
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-21T15:01:31+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

My original plan was to use DDS as I thought the TEX format on xbox was pretty much DDS with a few minor changes, but from what I understand the format isn't compatible with normal DDS files. I saw a way to easily convert it to TGA so I think I'm just gonna keep to that. TGA works better as an intermediate format anyway.

I'll look into Dragon's Dogma. I thought that would be supported.

Edit: Can you give me an exact example how it crashed (which archive you used and the command line arguments used)? I tried to extract textures from a couple of achives, and it worked for me.
## Post #35
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-07-21T15:49:02+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> My original plan was to use DDS as I thought the TEX format on xbox was pretty much DDS with a few minor changes, but from what I understand the format isn't compatible with normal DDS files. I saw a way to easily convert it to TGA so I think I'm just gonna keep to that. TGA works better as an intermediate format anyway.

I'll look into Dragon's Dogma. I thought that would be supported.

Edit: Can you give me an exact example how it crashed (which archive you used and the command line arguments used)? I tried to extract textures from a couple of achives, and it worked for me.

I was trying it on font files - ddfont_jpn_00_ID_HQ.tex in file bbs_rpg.arc. Cmd - arctool -x -texRE6 -dd -txt  bbs_rpg.arc
## Post #36
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-21T18:12:26+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from michalss
>
> Sectus wrote:My original plan was to use DDS as I thought the TEX format on xbox was pretty much DDS with a few minor changes, but from what I understand the format isn't compatible with normal DDS files. I saw a way to easily convert it to TGA so I think I'm just gonna keep to that. TGA works better as an intermediate format anyway.

I'll look into Dragon's Dogma. I thought that would be supported.

Edit: Can you give me an exact example how it crashed (which archive you used and the command line arguments used)? I tried to extract textures from a couple of achives, and it worked for me.

I was trying it on font files - ddfont_jpn_00_ID_HQ.tex in file bbs_rpg.arc. Cmd - arctool -x -texRE6 -dd -txt  bbs_rpg.arc
[http://www.tzarsectus.com/tools/ARCtool.rar](http://www.tzarsectus.com/tools/ARCtool.rar) - Uploaded new version, it shouldn't crash on that archive anymore. The reason for the crash is it tried to convert a TEX file of an unknown variant. I'll have to do some research one of these days to understand the various TEX files the tool doesn't support right now.
## Post #37
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-24T18:45:55+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

New version: [http://www.tzarsectus.com/tools/ARCtool.rar](http://www.tzarsectus.com/tools/ARCtool.rar)

This one supports converting TGA files back to TEX. However, it does not work with all TEX types (it should safely ignore the ones it doesn't support), and there is some lossiness to the image data when converting back and forth. The TGA files must be the same resolution as the original ones.

Here's a quick example of it working. Mercedes' cape made invisible by adding a completely black alpha channel: [http://h10.abload.de/img/2012-07-24_20-25-39wxq8b.jpg](http://h10.abload.de/img/2012-07-24_20-25-39wxq8b.jpg)

It is still rather experimental, so if anyone encounters any crashes, let me know.
## Post #38
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-07-24T18:50:16+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> New version: http://www.tzarsectus.com/tools/ARCtool.rar

This one supports converting TGA files back to TEX. However, it does not work with all TEX types (it should safely ignore the ones it doesn't support), and there is some lossiness to the image data when converting back and forth. The TGA files must be the same resolution as the original ones.

Here's a quick example of it working. Mercedes' cape made invisible by adding a completely black alpha channel: http://h10.abload.de/img/2012-07-24_20-25-39wxq8b.jpg

It is still rather experimental, so if anyone encounters any crashes, let me know.

Greate gonna test it
## Post #39
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2012-07-25T16:16:58+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

Great tool Sectus.
But I came up with a big question if possible would like a solution.
When trying to extract the MsgResource.arc by CMD displays the message saying it can not open the file as shown in print.


But if you drag and drop the file on top of BAT it can usually perform the extraction, as shown in print.


```

Wrote C:\Users\tc2963\etc\message\mes_system_s.msg

Wrote C:\Users\tc2963\etc\message\mes_stage5_s.msg

Wrote C:\Users\tc2963\etc\message\mes_stage1_s.msg

Wrote C:\Users\tc2963\etc\message\mes_item_s.msg

Wrote C:\Users\tc2963\etc\message\mes_event_s.msg

Wrote C:\Users\tc2963\etc\message\mes_file_s.msg

Wrote C:\Users\tc2963\etc\message\mes_stage3_s.msg

Wrote C:\Users\tc2963\etc\message\mes_stage2_s.msg

Process complete.

Extracted 8 files. 8 were compressed and 0 uncompressed.

```


Why with the command line it can not extract the file, and another thing to try reinserting the MSG has shown the error print.


One could add the tool to extract the extension MSG texts of the game?
## Post #40
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-25T16:50:13+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from carnage
>
> Great tool Sectus.
But I came up with a big question if possible would like a solution.
When trying to extract the MsgResource.arc by CMD displays the message saying it can not open the file as shown in print.


But if you drag and drop the file on top of BAT it can usually perform the extraction, as shown in print.

Why with the command line it can not extract the file, and another thing to try reinserting the MSG has shown the error print.


One could add the tool to extract the extension MSG texts of the game?
I think typos are the cause of both errors. The archive is called "MsgResource_s.arc". In the first picture you forgot the "_s" part and in the last picture you misspelled "Resource" and forgot "_s". Also, when repacking, you shouldn't add the ".arc" part. It should be the name of the directory it creates the archive from. In this case, it would be "MsgResource_s"

By the way, when writing in command prompt, you can press the tab key to auto complete file and directory names.

For instance, if you type:

```
arctool -c -re5 msg
```

And then press tab, it'll automatically complete msg for you (you can press tab multiple times to cycle through files and directories:

```
arctool -c -re5 MsgResource_s
```
## Post #41
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-26T10:55:06+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

can you show an example of using the hash to verify the correct file extension.
I can see the unknown extensions in the xex file for re6 but I can not figure out how to use the hash function to verify what one goes where. Thanks.
## Post #42
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-26T14:07:32+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

[http://www.tzarsectus.com/tools/ARCtool.rar](http://www.tzarsectus.com/tools/ARCtool.rar) - New version of the tool.

Used "-gmd" to automatically convert gmd files to text. However, it doesn't work with all of them (and right now it only works with Dragon's Dogma files). There's 2 types of GMD files. Those which only has text (they are converted properly), and those which have 3 arrays of data: some kind of values, variable names and then the text.

I'm trying to determine how the value array works. There's one value in the header which is probably related which I can't figure out how it works. There's num values and num lines (which corresponds with the amount of text and variable names), but there's "unknown4" which I don't know. Once I figure this out, I'll add support for converting the txt files back to gmd.
## Post #43
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-07-26T15:12:20+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> http://www.tzarsectus.com/tools/ARCtool.rar - New version of the tool.

Used "-gmd" to automatically convert gmd files to text. However, it doesn't work with all of them (and right now it only works with Dragon's Dogma files). There's 2 types of GMD files. Those which only has text (they are converted properly), and those which have 3 arrays of data: some kind of values, variable names and then the text.

I'm trying to determine how the value array works. There's one value in the header which is probably related which I can't figure out how it works. There's num values and num lines (which corresponds with the amount of text and variable names), but there's "unknown4" which I don't know. Once I figure this out, I'll add support for converting the txt files back to gmd.

That is imazing mate  - does it also do repack of gmd files. I already have a tool for both gmd types  But geat work anyway....

EDIT: I would 100% need something for RE6. BTW RE5 is done already
## Post #44
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2012-07-26T15:58:37+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> 
I think typos are the cause of both errors. The archive is called "MsgResource_s.arc". In the first picture you forgot the "_s" part and in the last picture you misspelled "Resource" and forgot "_s". Also, when repacking, you shouldn't add the ".arc" part. It should be the name of the directory it creates the archive from. In this case, it would be "MsgResource_s"

I'm sorry it was my lack of attention, I swear it went unnoticed. 
Sectus I have the source code of a dump of MSG but it only works in the PC version. 
If you want to find interesting or if I can provide the script for you to add to your tool, so others can make the translation of games in your language.
## Post #45
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-26T17:25:20+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from carnage
>
> Sectus wrote:
I think typos are the cause of both errors. The archive is called "MsgResource_s.arc". In the first picture you forgot the "_s" part and in the last picture you misspelled "Resource" and forgot "_s". Also, when repacking, you shouldn't add the ".arc" part. It should be the name of the directory it creates the archive from. In this case, it would be "MsgResource_s"


I'm sorry it was my lack of attention, I swear it went unnoticed. 
Sectus I have the source code of a dump of MSG but it only works in the PC version. 
If you want to find interesting or if I can provide the script for you to add to your tool, so others can make the translation of games in your language.
You can feel free to send it, although I'm not sure if I'll add support for it.
## Post #46
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-07-26T21:24:16+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> I'm trying to determine how the value array works. There's one value in the header which is probably related which I can't figure out how it works. There's num values and num lines (which corresponds with the amount of text and variable names), but there's "unknown4" which I don't know. Once I figure this out, I'll add support for converting the txt files back to gmd.Ah, I haven't commit a bunch of stuff. Here's my GuiMessageFile code:

[https://gist.github.com/f9f41fbc91ab7942cfc8](https://gist.github.com/f9f41fbc91ab7942cfc8)

This is specifically for Dragon's Dogma GMD files, I don't know if it differs for other games.
## Post #47
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-26T22:03:31+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Rick
>
> Sectus wrote:I'm trying to determine how the value array works. There's one value in the header which is probably related which I can't figure out how it works. There's num values and num lines (which corresponds with the amount of text and variable names), but there's "unknown4" which I don't know. Once I figure this out, I'll add support for converting the txt files back to gmd.Ah, I haven't commit a bunch of stuff. Here's my GuiMessageFile code:

https://gist.github.com/f9f41fbc91ab7942cfc8

This is specifically for Dragon's Dogma GMD files, I don't know if it differs for other games.
Thanks for the link. I did figure out how it works, but another example how it's written is always useful.

I've looked into the files for RE6 GMD files and they are different. They also look a bit weird with gigantic chunks of FF data, I guess that's data blanked out just for the demo.
## Post #48
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2012-07-27T14:00:18+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> 
You can feel free to send it, although I'm not sure if I'll add support for it.

The following code was released by the Game Vicio group (GV).
Is in C# and works only for the PC version.
The following information on how to use the program.

> Resident Evil 5 MSG2 Editor 1.02
>
> 
>
> This is a brazilian tool, so the language is portuguese of Brazil.
>
> 
>
> Just drag and drop a RE5 .MSG2 file in the tool, and a .txt will be genarated.
>
> To repack, drag and drop the .txt in the tool, and will b generated a new .MSG2 like this:
>
> 'mes_event_e.MSG2.gv'
>
> 
>
> Rename to: 'mes_event_e.MSG2' and test in the game.
>
> 
>
> Note: .net framework required to run this tool
>
> 
>
> Don't ask me about bugs crashes or something, because I'm not the owner of this tool.
>
> 
>
> Enjoy

The comments are in PT-BR, if necessary if I translate into English.
## Post #49
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-07-27T19:36:35+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from carnage
>
> Sectus wrote:
You can feel free to send it, although I'm not sure if I'll add support for it.

The following code was released by the Game Vicio group (GV).
Is in C# and works only for the PC version.
The following information on how to use the program.

Resident Evil 5 MSG2 Editor 1.02

This is a brazilian tool, so the language is portuguese of Brazil.

Just drag and drop a RE5 .MSG2 file in the tool, and a .txt will be genarated.
To repack, drag and drop the .txt in the tool, and will b generated a new .MSG2 like this:
'mes_event_e.MSG2.gv'

Rename to: 'mes_event_e.MSG2' and test in the game.

Note: .net framework required to run this tool

Don't ask me about bugs crashes or something, because I'm not the owner of this tool.

Enjoy

The comments are in PT-BR, if necessary if I translate into English.

This does not work with special chars. I got also X360 version of this tool  But pretty usless
## Post #50
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2012-07-27T21:19:50+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from michalss
>
> 

This does not work with special chars. I got also X360 version of this tool  But pretty usless

I also think that, does it have any way to edit the XBOX version?

What I'm doing is taking the PC version of MSG in my case is already translated and rocking the ARC through the Sectus tool, or use the files packed with the PC version and the XBOX ARC compression.
In my view it is likely that work has not tested it, but if it works, it is likely that other files can get the PC version as TEXT, IMAGES, etc. and pack with the ARC of the XBOX.
## Post #51
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-07-27T21:34:59+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from carnage
>
> I also think that, does it have any way to edit the XBOX version?

What I'm doing is taking the PC version of MSG in my case is already translated and rocking the ARC through the Sectus tool, or use the files packed with the PC version and the XBOX ARC compression.
In my view it is likely that work has not tested it, but if it works, it is likely that other files can get the PC version as TEXT, IMAGES, etc. and pack with the ARC of the XBOX.
The formats are too different for that to work. Many formats are quite simply not the same (like textures, models and a few other formats) and all of them are reverse endian, which is the main problem.

Whenever I add PC support to my tool, I'll try to update my GMD and TEX converters to work between platforms but we'll see. There's some formats I'd really wish to figure out, like the XFS format, since it controls so many different gameplay systems but I've had little luck with that.
## Post #52
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-07-28T02:15:40+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

SFX are serialized game objects, I can read some of the data but it's not completely correct.
## Post #53
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-07-28T10:47:02+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

I know how the XFS fmt works partially. I can also read some of the strings but it's not all of them.
## Post #54
- Username: jackyjy
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jul 23, 2012 5:16 pm
- Post datetime: 2012-08-05T06:39:30+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from michalss
>
> Sectus wrote:My original plan was to use DDS as I thought the TEX format on xbox was pretty much DDS with a few minor changes, but from what I understand the format isn't compatible with normal DDS files. I saw a way to easily convert it to TGA so I think I'm just gonna keep to that. TGA works better as an intermediate format anyway.

I'll look into Dragon's Dogma. I thought that would be supported.

Edit: Can you give me an exact example how it crashed (which archive you used and the command line arguments used)? I tried to extract textures from a couple of achives, and it worked for me.

I was trying it on font files - ddfont_jpn_00_ID_HQ.tex in file bbs_rpg.arc. Cmd - arctool -x -texRE6 -dd -txt  bbs_rpg.arc

Me too,I was found a file ddfont_jpn.gfd. I dont know what is it. And how can I creat my own TEX format Font?
## Post #55
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2012-08-06T21:22:20+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from Sectus
>
> 
The formats are too different for that to work. Many formats are quite simply not the same (like textures, models and a few other formats) and all of them are reverse endian, which is the main problem.

Whenever I add PC support to my tool, I'll try to update my GMD and TEX converters to work between platforms but we'll see. There's some formats I'd really wish to figure out, like the XFS format, since it controls so many different gameplay systems but I've had little luck with that.

I took the test, but as we knew gave error.
The game starts normally, but when some text that appears the error "fatal crash intercepted"
I tried to change the header, but when the game starts speaking it is necessary to clean the cd.
The way is to edit the MSG2 Editor tool to work with files or XBOX 360 would be better to create a new tool?
## Post #56
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2012-08-29T22:10:00+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

With the help of a friend (Ray) has created an extraction tool based on PHP's MSG2 Editor.
The Dump is working properly and he can make the extraction of 3 files PC, XBOX360 and PS3, follows the first 10 lines of script version PC and XBOX, the test was not done with the PS3 version because I have but apparently works correctly.

The encode already been created and tested, it encodes correctly but not efetuei the test PC and XBOX game in 3660, but it is likely that work properly.
Soon I'll post screens from both versions.

```
19795,18226,0,64,1,29576,0,2048,2304,1152,18,36,0,0,1056,256,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0
(dummy)
Mano-a-mano{0,11268}
Faca{0,11268}
M92F (PST){0,11268}
VZ61 (MTR){0,11268}
Ithaca M37 (MTR){0,11268}
S75 (RIF){0,11268}
Granada de mão{0,11268}
Granada incendiária{0,11268}
Granada Flash{0,11268}
SIG 556 (MTR){0,11268}
Bomba de proximidade{0,11268}
S&W M29 (MAG){0,11268}
Lança granadas{0,11268}

```


```
0,0,8,0,0,9,0,5,18,0,36,0,0,0,0,0,32,4,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0
(dummy)
Corpo-a-corpo{0,1068}
Faca{0,1068}
M92F (PST){0,1068}
VZ61 (MET){0,1068}
Ithaca M37 (ESC){0,1068}
S75 (RIF){0,1068}
Granada de mão{0,1068}
Granada incendiária{0,1068}
Granada de luz{0,1068}
SIG 556 (MET){0,1068}
Bomba de proximidade{0,1068}
S&W M29 (MAG){0,1068}
Lança-granadas{0,1068}

```


Both are already translated into Portuguese PT-BR.
## Post #57
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-08-30T04:04:51+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

can u please post the tool for X360?
## Post #58
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2012-08-30T13:11:38+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from michalss
>
> can u please post the tool for X360?

Yes of course, but I have to perform the test on encode if everything is ok put the source code.
I intend to spend a GUI tool for VBA.
## Post #59
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-03-19T14:26:53+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

Sorry for necroposting but...
ArctTools 0.9.26 incorrect extract some normal maps from DragonsDogma (Xbox).
If use "-texRE6" - created only txt file, without tga;
if use only "-tex" - maps incorrect;
Sample:
[http://www.sendspace.com/file/0lkf02](http://www.sendspace.com/file/0lkf02)
## Post #60
- Username: nameless32
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 17, 2010 2:51 am
- Post datetime: 2014-03-19T21:05:32+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

> Reply from erik945
>
> Sorry for necroposting but...
ArctTools 0.9.26 incorrect extract some normal maps from DragonsDogma (Xbox).
If use "-texRE6" - created only txt file, without tga;
if use only "-tex" - maps incorrect;
Sample:
http://www.sendspace.com/file/0lkf02

hei arctool have support to Dragon´s Dogma Dark Arisen PS3 ?
and DMC4 PS3 ??

i can´t find the information in readme.txt

sorry for my bad english
## Post #61
- Username: Portagas
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 17, 2014 11:03 pm
- Post datetime: 2014-08-02T11:42:31+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

Ps3...
## Post #62
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2014-08-06T04:33:38+00:00
- Post Title: Re: Capcom's MT Framework (DR, RE5, DMC4, LP, MvC, DD, etc)

hello i just wanted to know if you have any plans on adding dead rising 1 ?
