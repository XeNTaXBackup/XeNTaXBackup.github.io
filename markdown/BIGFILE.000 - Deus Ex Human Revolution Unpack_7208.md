## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-21T09:40:22+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi all,

I was wonder if someone allready try to upcaked the bigfiles from new Deus EX ? Here is the example of BIGFILE, can anyone have a look pls ?

DL:

```
http://dl.dropbox.com/u/38234344/BIGFILE.000_new
```


```
http://dl.dropbox.com/u/38234344/BIGFILE.004
```


Regards
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-22T11:40:34+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

anyone please ?
## Post #3
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-22T12:00:05+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

Please upload bigfile.000 - not the whole file, just a few megabytes. Because bigfile.000 contains header along with all file information.
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-22T12:41:29+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> Please upload bigfile.000 - not the whole file, just a few megabytes. Because bigfile.000 contains header along with all file information.

OK i will do so but it is 1.5 GB size
## Post #5
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-22T12:44:05+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

Upload only a few megabytes - I don't need whole file!

Use some hex editor to cut off unnecessary data.
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-22T12:53:09+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> Upload only a few megabytes - I don't need whole file!

Use some hex editor to cut off unnecessary data.

OK give me 5 mins
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-22T12:57:38+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

file is getting uplaoded from server cut it to 400 MB. Please check download link in 15 mints. Thx for help
## Post #8
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-22T15:03:20+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

This file is from PS3 or X360 version?
## Post #9
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2011-08-22T15:46:23+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

Header is xenon-w.
Seen as the Xbox 360.
## Post #10
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-22T16:16:03+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from oveja
>
> Header is xenon-w.
Seen as the Xbox 360.

It is from X360
## Post #11
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-22T16:23:09+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

Problem with this file format, that files, which are located in other archives (bigfile.001, bigfile.002, etc.) need to have a shift of around 400kB from original file's offset in bigfile.000 header. (So if file A has offset X in bigfile.000 header, and is located in bigfile.001, the actual offset in bigfile.001 is X - (filesize_of_bigfile.000) - shift)

I'll take a look if the offset is same as in leaked PC beta.
## Post #12
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-22T16:26:45+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

Offset is simple,

max file blocks = file alignment / 2048

offset / max file blocks = file #
(offset % max file blocks) * 2048 = actual offset

For PS3, file alignment is 0x7FF00000.
For X360, file alignment is 0x62300000.

header:
- dword fileAlignment
- char basePath[64]
- dword count
- dword nameHashes[count]
- file files[count]

file:
- dword size
- dword offset
- dword locale
- dword unknown
## Post #13
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-22T16:56:10+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

Rick: All great - but that's info for Tomb Raider: Underworld (unfortunately, no longer applicable for Deus Ex Human Revolution).
## Post #14
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-22T16:57:06+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> Rick: All great - but that's info for Tomb Raider: Underworld (unfortunately, no longer applicable for Deus Ex Human Revolution).This came from my research on DX3 PS3 & X360 data samples. I will be probably have some code up for unpacking / packing after Steam decrypts my PC copy at midnight.
## Post #15
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-22T17:06:14+00:00
- Post Title: BIGFILE.000 - Deus Ex Human Revolution Unpack

I don't want to argue - I haven't examined this format, myself.

However the fact is that I never get correct offsets using your information/code.
## Post #16
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-22T17:08:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> I don't want to argue - I haven't examined this format, myself.Not trying to argue - just clarifying that my research came directly from DX3 and not any other game.

> Reply from mnn
>
> However the fact is that I never get correct offsets using your information/code.Can you give me an example that's giving you a wrong offset? Maybe block sizes aren't 2048 bytes on X360?
## Post #17
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-22T17:25:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

OK, it works! My bad! 

Just an idea - that unknown in file could be simple padding to 16 bytes (because it's always 0x0).
## Post #18
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-22T17:39:27+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> Just an idea - that unknown in file could be simple padding to 16 bytes (because it's always 0x0).Likely, alternatively it could be a flags value.
## Post #19
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-22T19:52:03+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Friends, someone will be able to create a tool for unpaker and repaker?

I'm thinking of translating the game for PS3.

Hug.
## Post #20
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-08-22T22:03:07+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Tomb Raider games use the same format, try this tool:

[http://www.tombraiderforums.com/showthread.php?t=181335](http://www.tombraiderforums.com/showthread.php?t=181335)

I know it'll unpack, not sure about repacking. It'll work with 360,PS3,PC,PSP.

That's saying that the formats are identical...
## Post #21
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-22T23:46:02+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Doesn't unpack for me for the console versions.

Doesn't even open it.
## Post #22
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-23T00:52:39+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

DX3 has a slightly different header so that tool would need to be updated.
## Post #23
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-23T02:07:20+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

He gave up on the program before he could add support.
## Post #24
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-23T02:33:09+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

he will be able to update us?

Or if it is an open project would be possible someone can help.
## Post #25
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-23T03:01:50+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I Doubt it, So ricks are only hope.
## Post #26
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-23T16:13:24+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Rick any news pls ?
## Post #27
- Username: Pey
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Mar 26, 2011 6:14 pm
- Post datetime: 2011-08-23T16:23:08+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #28
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-23T19:58:15+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hope you'll be able to unpack it, cause, as i heard it's the only way to get English sound, with other-language subs.
## Post #29
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-23T21:28:14+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

[http://svn.gib.me/public/deusex3/](http://svn.gib.me/public/deusex3/)

Pack code is untested.
## Post #30
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2011-08-23T22:20:32+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> http://svn.gib.me/public/deusex3/

Pack code is untested.

Thank you very much , appreciate your hard work 

but excuse me , How to unpack the game files !

I tried to use Quickbms , but it didn't work :S

in other mean how to use the codes you made ? is any other tool
## Post #31
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-08-24T00:29:41+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from killerpepo
>
> Rick wrote:http://svn.gib.me/public/deusex3/

Pack code is untested.

Thank you very much , appreciate your hard work 

but excuse me , How to unpack the game files !

I tried to use Quickbms , but it didn't work :S

in other mean how to use the codes you made ? is any other tool

Rick provided the source code for a visual c# solution, just open with visual C# express and build solution! why do people always complain about this method? its better than providing a closed source executable.
## Post #32
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-24T00:48:19+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> http://svn.gib.me/public/deusex3/

Pack code is untested.

Thank you Rick.

anyone can build for me?
## Post #33
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-24T02:30:08+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Here it is compiled.
\[http://www.mediafire.com/?ssx5ieo83u7dqs7](http://www.mediafire.com/?ssx5ieo83u7dqs7)
## Post #34
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-24T04:21:45+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi Rick getting Exeption any idea 

```

Unhandled Exception: System.OverflowException: Arithmetic operation resulted in
an overflow.
   at Gibbed.DeusEx3.FileFormats.BigFile.Deserialize(Stream input) in C:\My Stuf
f\deusex3\trunk\Gibbed.DeusEx3.FileFormats\BigFile.cs:line 96
   at Gibbed.DeusEx3.Unpack.Program.Main(String[] args) in C:\My Stuff\deusex3\t
runk\Gibbed.DeusEx3.Unpack\Program.cs:line 111
```


EDIT it works but only for PC please update the tool for X360.
## Post #35
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-24T04:33:56+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> deusex3: rick * r10 Gibbed.DeusEx3.FileFormats/BigFile.cs: Oops. Typo'd a check that breaks Xbox 360 support.
## Post #36
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-24T11:09:53+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Ps3 in the file that contains the texts is the file CACHE.001.

Rick, you will be able to support this file?
## Post #37
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-24T11:15:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from timartinelli
>
> Ps3 in the file that contains the texts is the file CACHE.001.

Rick, you will be able to support this file?

Yes this is what i'm trying to do! Rick i hope going to do X360 support and that is what i do care about, PS3 will be the same format.
## Post #38
- Username: Skymmer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 25, 2010 8:50 am
- Post datetime: 2011-08-24T14:08:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Rick, thanks for providing the code.
I tried to unpack the bigfile.000 from PC version and got the files in output folder. The size of files in output folder is 7 849 723 953 bytes. The size of all parts of bigfile is 7 864 535 040 bytes, so I suppose everything went fine during unpacking.
But seems that packing is little bit buggy. On output I have only

```
bigfile.001	1 423 130 908
bigfile.002	3 306 279

```

While the original is

```
bigfile.001	2 146 390 016
bigfile.002	2 145 282 048
bigfile.003	1 524 129 792

```


A better results on patch0.000 file.

```
Recreated    28 748 620

```

There are a couple of different bytes between files and original has some extra NULs at the end.
## Post #39
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-24T14:33:20+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Yes I'm still working on Pack, . Pack is a less priority for me since I am working on the *.drm format.
## Post #40
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-24T15:07:10+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Pack should hopefully work better now...

> deusex3: rick * r11 Gibbed.DeusEx3.Pack/ (Gibbed.DeusEx3.Pack.csproj Program.cs): Improved packing logic.
## Post #41
- Username: BlackeneD
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 25, 2011 12:08 am
- Post datetime: 2011-08-24T16:12:06+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Guys, please tell me how to pack. Unpacking done, but how to pack? Code for the bat file ?
## Post #42
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-24T17:28:39+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

It is possible to change the language of the subs, right?
## Post #43
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-24T17:32:36+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> Pack should hopefully work better now...
deusex3: rick * r11 Gibbed.DeusEx3.Pack/ (Gibbed.DeusEx3.Pack.csproj Program.cs): Improved packing logic.

Rick pls are you planning to do X360 support ? Thank you
## Post #44
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-24T17:43:50+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from michalss
>
> Rick wrote:Pack should hopefully work better now...
deusex3: rick * r11 Gibbed.DeusEx3.Pack/ (Gibbed.DeusEx3.Pack.csproj Program.cs): Improved packing logic.

Rick pls are you planning to do X360 support ? Thank you

PS3 also please.

Thanks a lot.
## Post #45
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-24T18:33:07+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Big-endian support should already be present.
## Post #46
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-24T19:26:20+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> Big-endian support should already be present.

Yes sorry Rick i mean SVN
## Post #47
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-24T19:37:05+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

git? my repository is svn. But yes, I committed my changes already, the lines I quoted earlier were commits.
## Post #48
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-24T19:40:51+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> git? my repository is svn. But yes, I committed my changes already, the lines I quoted earlier were commits.

Yeah sorry i mean SVN 

Great Rick i compiled rev 12 and it works with BigEnd.... But all files are unknow, is that ok? There are not any filenames yet, any idea where are subtitles ? Thx for help u are the best 

EDIT : I guess i found it  Text is in the file "C8B69EE7.unknown" -X360
and "7CD333D3.unknown" -PC
## Post #49
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-24T19:57:17+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from michalss
>
> Rick wrote:git? my repository is svn. But yes, I committed my changes already, the lines I quoted earlier were commits.

Yeah sorry i mean SVN 

Great Rick i compiled rev 12 and it works with BigEnd.... But all files are unknow, is that ok? There are not any filenames yet, any idea where are subtitles ? Thx for help u are the best 

EDIT : I guess i found it  Text is in the file "C8B69EE7.unknown"
So, is it possible to change the language of subs?
If the answer is yes, please, make step-by-step instruction.
## Post #50
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-24T20:02:35+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I try to use the PS3 CACHE.001.

Rick, this is the ps3 file containing the text has as its unpaker Repak and work with him.
## Post #51
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-25T00:12:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from timartinelli
>
> I try to use the PS3 CACHE.001.

Rick, this is the ps3 file containing the text has as its unpaker Repak and work with him.Sorry, I don't understand. You'll want to unpack CACHE.000, not CACHE.001 (archives are series of numbered files, starting with .000).
## Post #52
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2011-08-25T00:19:53+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

any one know how to convert the .cpk ?
## Post #53
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-08-25T01:34:02+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> timartinelli wrote:I try to use the PS3 CACHE.001.

Rick, this is the ps3 file containing the text has as its unpaker Repak and work with him.Sorry, I don't understand. You'll want to unpack CACHE.000, not CACHE.001 (archives are series of numbered files, starting with .000).

So you mean he makes the unpaker .000 after the .001?

Edit:
that's right, I managed to extract all of the ps3.

The text file is the ps3 9DCD281E.unknown.
## Post #54
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T04:26:55+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

So, anyone figure out how to change subs yet?
## Post #55
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-25T04:31:54+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Larus
>
> So, anyone figure out how to change subs yet?

What u mean change?? You have ti translate them. Coz i think on X360 is only EN. So if you want to use Different Lang than you have to translate it. I will do some test tommorow and see if local.bin file is kind of tricky. You have to edit it in HEX.
## Post #56
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T04:33:39+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from michalss
>
> Larus wrote:So, anyone figure out how to change subs yet?

What u mean change?? You have ti translate them. Coz i think on X360 is only EN. So if you want to use Different Lang than you have to translate it. I will do some test tommorow and see if local.bin file is kind of tricky. You have to edit it in HEX.
 I meant on PC, is it possible to make game with English language sound, but with other-language subs?
## Post #57
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-25T04:37:10+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Larus
>
> michalss wrote:Larus wrote:So, anyone figure out how to change subs yet?

What u mean change?? You have ti translate them. Coz i think on X360 is only EN. So if you want to use Different Lang than you have to translate it. I will do some test tommorow and see if local.bin file is kind of tricky. You have to edit it in HEX.
 I meant on PC, is it possible to make game with English language sound, but with other-language subs?

Dont know about PC i'm not dealing with PC but with X360, so i have no idea.
## Post #58
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T04:42:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from michalss
>
> 

and "7CD333D3.unknown" -PC
Oh, there was this in your post, so i thought otherwise.
Really hope that someone will figure how to change subs on PC.
## Post #59
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-25T04:50:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Rick ,

How reliable is packing please ? Is it ok or is there any catch ?

Thank you
## Post #60
- Username: dubh
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 23, 2011 4:34 pm
- Post datetime: 2011-08-25T04:51:42+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Is it possible to change the max quantity of item stacks yet? Or are the unpack/pack tools not yet fully developed to create mods?
## Post #61
- Username: Pey
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Mar 26, 2011 6:14 pm
- Post datetime: 2011-08-25T05:04:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Larus
>
> So, anyone figure out how to change subs yet?

The folder "FFFFFD61" contains a file called "locals.bin" and it seems to have the whole English script.

Will try repacking the Spanish "locals.bin" with "bigfile_English.000" to see if it works.
## Post #62
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-25T05:32:40+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from michalss
>
> Rick ,

How reliable is packing please ? Is it ok or is there any catch ?

Thank youI think it's working decently now but it's largely untested.

> Reply from dubh
>
> Is it possible to change the max quantity of item stacks yet? Or are the unpack/pack tools not yet fully developed to create mods?Unpack / pack has nothing to do with actual game data. 

I am working on code to parse (and hopefully recreate) the .drm files.

> Reply from Pey
>
> The folder "FFFFFD61" contains a file called "locals.bin" and it seems to have the whole English script.

Will try repacking the Spanish "locals.bin" with "bigfile_English.000" to see if it works.Look at the bigfile.xml -- it will explain what the folder names mean,

such as:
```
<!-- FFFFFD61 = English, UnusedLanguages, UnusedFlags -->
```
## Post #63
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-25T05:39:51+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> michalss wrote:Rick ,

How reliable is packing please ? Is it ok or is there any catch ?

Thank youI think it's working decently now but it's largely untested.

That is Great Rick, please keep us informed about a new Revision. Thx
## Post #64
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T06:39:23+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Pey
>
> Larus wrote:So, anyone figure out how to change subs yet?

The folder "FFFFFD61" contains a file called "locals.bin" and it seems to have the whole English script.

Will try repacking the Spanish "locals.bin" with "bigfile_English.000" to see if it works.
Keeping my fingers crossed, and waiting for results.
Hope it works, and you'll be able to make step-by-step instructions.
## Post #65
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-25T07:05:39+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from killerpepo
>
> any one know how to convert the .cpk ?These are mislabeled, they should be .usm.

They're CRIWARE video data. There's a tool [here](http://hcs64.com/vgm_ripping.html) (search 'utf_tab suite') called usm_deinterleave but I don't know how well it works for DX3 videos.
## Post #66
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2011-08-25T13:36:43+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> killerpepo wrote:any one know how to convert the .cpk ?  These are mislabeled, they should be .usm.

They're CRIWARE video data. There's a tool here (search 'utf_tab suite') called usm_deinterleave but I don't know how well it works for DX3 videos.

thanks for reply 

I tried it but , it shows me error check screen



so I tried to search found this one [VGMToolbox](http://sourceforge.net/projects/vgmtoolbox/l) seems to extract well
## Post #67
- Username: Pey
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Mar 26, 2011 6:14 pm
- Post datetime: 2011-08-25T13:53:20+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hey rick, how do I repack "bigfile_English_unpack" into "bigfile_English.000"?

Dont know the exact console command.

Thanks in advanced.

Will post if the subs thingy worked once I know how to repack the file.
## Post #68
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-25T14:06:20+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Pey
>
> Hey rick, how do I repack "bigfile_English_unpack" into "bigfile_English.000"?

Dont know the exact console command.

Thanks in advanced.

Will post if the subs thingy worked once I know how to repack the file.Gibbed.DeusEx3.Pack.exe bigfile_English_unpack bigfile_English.000

Be careful not to overwrite your original.

Edit: if you are overwriting a locals.bin and you're on PC, you'll want to make your changes to patch0.000 since that archive contains updates to locals.bin.
## Post #69
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2011-08-25T14:17:14+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Can somebody post last Rick's Deus Ex Human Revolution tool compiled? Thanks.
## Post #70
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2011-08-25T14:33:42+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zeeh
>
> Can somebody post last Rick's Deus Ex Human Revolution tool compiled? Thanks.

here it is

edit : this include pack and unpack
[GIbbedDeus.zip](https://xentaxbackup.github.io/file/4663_GIbbedDeus.zip)
## Post #71
- Username: Pey
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Mar 26, 2011 6:14 pm
- Post datetime: 2011-08-25T14:39:18+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #72
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2011-08-25T16:11:27+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Pey
>
> Rick wrote:Pey wrote:Hey rick, how do I repack "bigfile_English_unpack" into "bigfile_English.000"?

Dont know the exact console command.

Thanks in advanced.

Will post if the subs thingy worked once I know how to repack the file.Gibbed.DeusEx3.Pack.exe bigfile_English_unpack bigfile_English.000

Be careful not to overwrite your original.

Edit: if you are overwriting a locals.bin and you're on PC, you'll want to make your changes to patch0.000 since that archive contains updates to locals.bin.

I dont have "Gibbed.DeusEx3.Pack.exe" 

edit: I was able to pack the file but the language files dont seem to be in bigfile_english or bigfile_spanish. In fact, if i rename bigfile_english file to bigfile_spanish and set the language to spanish, i still hear spanish voices. So the audio is definetly not in the 800mb files.

The videos of the game have multi language 

en , spa , ita , rus , pol , ger , fra

so that's may cause the Spanish voice you here
## Post #73
- Username: Pey
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Mar 26, 2011 6:14 pm
- Post datetime: 2011-08-25T17:10:18+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

No no  they are not hardcoded, read my post above.
## Post #74
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T17:11:45+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #75
- Username: Pey
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Mar 26, 2011 6:14 pm
- Post datetime: 2011-08-25T17:21:36+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #76
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T17:40:29+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #77
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T17:45:34+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #78
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T17:47:19+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #79
- Username: Pey
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Mar 26, 2011 6:14 pm
- Post datetime: 2011-08-25T17:56:35+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #80
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T17:59:55+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #81
- Username: Pey
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Mar 26, 2011 6:14 pm
- Post datetime: 2011-08-25T18:02:36+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Read my post above.
## Post #82
- Username: Tamxaun
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 10, 2011 7:48 pm
- Post datetime: 2011-08-25T18:04:34+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #83
- Username: eXpressionist
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 26, 2011 1:45 am
- Post datetime: 2011-08-25T18:04:54+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I'm renamed English to Russian. Fonts now are okay, but there is no sound and subtitles! Only text..
## Post #84
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T18:05:48+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Pey
>
> Read my post above.
oh, didnt notice the crack thing.
Hm, i wonder, will it work if i turn down auto update?
Cause i really don't want to use crack(
## Post #85
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T18:16:07+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Pey
>
> Well, i have the game on steam. I copied the game folder and used the crack and it does show Russian subs using bigfile_English.000. However if you want to have Russian subs without using a crack AND without having to download bigfile_Russian.000 , set Steam Language to English and then copy the file I uploaded. Of course, you need bigfile_English.000

Awaitin for finish download english version from Steam and try. Hopefully it works. Thanks for help, Pey.
## Post #86
- Username: Pey
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Mar 26, 2011 6:14 pm
- Post datetime: 2011-08-25T18:40:53+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Yeah, you´re right, I just entered the game and saw the menus. The bigfile_xlanguagex has to be English, there´s no doubt about it, but the problem with Russian is the charset, cause I tried Italian and Spanish subs and both of them work fine.
## Post #87
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T18:46:14+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Pey
>
> Yeah, you´re right, I just entered the game and saw the menus. The bigfile_xlanguagex has to be English, there´s no doubt about it, but the problem with Russian is the charset, cause I tried Italian and Spanish subs and both of them work fine.
IS there anyway you can help?
## Post #88
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T18:46:41+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Pey
>
> Yeah, you´re right, I just entered the game and saw the menus. The bigfile_xlanguagex has to be English, there´s no doubt about it, but the problem with Russian is the charset, cause I tried Italian and Spanish subs and both of them work fine.

So maybe try repack with files from russian version? Can u post a step-by-step instruction for repacking? Sorry, but i very lame in that "console stuff".
## Post #89
- Username: eXpressionist
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 26, 2011 1:45 am
- Post datetime: 2011-08-25T18:47:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

That's because Italy and Spain uses latin charset, I suppose.
Probably there is font file or something in Russian bigfile. btw, there is a russian sound in first video in patch0 (cause it appears even with English file). 

Russian sound is just so lame.. So I and many people would really appreciate if someone could make just Rus subtitles for the game.
## Post #90
- Username: madprof
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 26, 2011 2:29 am
- Post datetime: 2011-08-25T18:52:44+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Pey
>
> Yeah, you´re right, I just entered the game and saw the menus. The bigfile_xlanguagex has to be English, there´s no doubt about it, but the problem with Russian is the charset, cause I tried Italian and Spanish subs and both of them work fine.

Charset? May be problem with font? Usually russian subs in various games have different font from original.

Screens with english and russian text:
[](http://imageshack.us/photo/my-images/850/dxhr2011082521452626.png/)
[](http://imageshack.us/photo/my-images/696/dxhr2011082521461643.png/)
## Post #91
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T18:59:52+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Usually russian subs in various games have different font from original.
Thats why i suggest make repack from original files of russian version of DXHR. I'm not sure that will help, but why not try?
## Post #92
- Username: madprof
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 26, 2011 2:29 am
- Post datetime: 2011-08-25T19:04:52+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> Usually russian subs in various games have different font from original.
Thats why i suggest make repack from original files of russian version of DXHR. I'm not sure that will help, but why not try?

"Attempt is not torture" (c) L.P.Berija 

What tools using for unpack and repack DX data-files?
## Post #93
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T19:09:29+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> "Attempt is not torture" (c) L.P.Berija
Exactly! 

> What tools using for unpack and repack DX data-files?
"Gibbed.Deus" from Rick. Link on a 5 page. But i have no idea how it works without instruction. Yeah, ima lame.
## Post #94
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T19:12:13+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> "Attempt is not torture" (c) L.P.Berija 
Exactly! 

What tools using for unpack and repack DX data-files? 
"Gibbed.Deus" from Rick. Link on a 5 page. But i have no idea how it works without instruction. Yeah, ima lame.
Same here, finish download, but failed to use.
## Post #95
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T19:18:44+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Unpack of bigfile_Russian succesful. So... what next?
## Post #96
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T19:21:01+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> Unpack of bigfile_Russian succesful. So... what next?
How did you do that? Давай колись)
## Post #97
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T19:29:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

In CMD:
%path to tool%:\\Gibbed.DeusEx3.Pack.exe -o %filename_to_repack% %folder_for_unpacked_files%

when:
"-o" -- command to unpack
file for unpack must be in a root directory
folder for unpacked files must be created before

What next?

> По-русски (английский у меня просто «великолепен»)
>
> В командной строке все делается:
>
> %путь к программулине%:\\Gibbed.DeusEx3.Pack.exe -o %файл_который_распаковываем% %папка_куда_все_распакуется%
>
> 
>
> Где:
>
> «-о» -- команда для распаковки
>
> распаковываемый файл должен быть в корне (у меня так сработало по-крайней мере)
>
> папку, куда все ляжет, создать заранее
>
> 
>
> Что дальше?
## Post #98
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T19:34:22+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> In CMD:
%path to tool%:\\Gibbed.DeusEx3.Pack.exe -o %filename_to_repack% %folder_for_unpacked_files%

when:
"-o" -- command to unpack
file for unpack must be in a root directory
folder for unpacked files must be created before

What next?
По-русски (английский у меня просто «великолепен»)
В командной строке все делается:
%путь к программулине%:\\Gibbed.DeusEx3.Pack.exe -o %файл_который_распаковываем% %папка_куда_все_распакуется%

Где:
«-о» -- команда для распаковки
распаковываемый файл должен быть в корне (у меня так сработало по-крайней мере)
папку, куда все ляжет, создать заранее

Что дальше?
If i only knew.
Надежда на то что вернется кто-нибудь и поможет.
Hope that someone will return and help.
## Post #99
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T19:39:39+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Screw job, screw sleep! I want an original sound and i do this... or die! 

*sippin vodka and thikin*
## Post #100
- Username: eXpressionist
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 26, 2011 1:45 am
- Post datetime: 2011-08-25T19:47:27+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Russian guys attack the thread  Голактего опасносте)) 

And what's in unpacked file? Just bunch of files with unspecified extensions?
## Post #101
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T19:54:43+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Just bunch of files with unspecified extensions?
Yeah. And i dont know where i can find any information of charset. Not in xml file of patch.000 -- fact.  Not so simple, zermik, not so simple...
## Post #102
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T20:00:06+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Need a ORIGINAL file patch.000 from RUSSIAN version.
## Post #103
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T20:02:18+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> Need a ORIGINAL file patch.000 from RUSSIAN version.
Give me few minutes.
EDIT: [http://rghost.ru/19311041](http://rghost.ru/19311041)
There you go.
## Post #104
- Username: madprof
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 26, 2011 2:29 am
- Post datetime: 2011-08-25T20:08:12+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> Need a ORIGINAL file patch.000 from RUSSIAN version.

Now extracting from original russian clone-dvd

EDIT slow so slow... неуспел 

And what now?
## Post #105
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T20:11:33+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from madprof
>
> zermik wrote:Need a ORIGINAL file patch.000 from RUSSIAN version.

Now extracting from original russian clone-dvd

EDIT slow so slow... неуспел 

And what now?
Wait for Zermic to work his magic, and pray to Spector that it works.
## Post #106
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T20:13:55+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Give me few minutes.
>
> EDIT: http://rghost.ru/19311041
>
> There you go.
Tnx.

> Now extracting from original russian clone-dvd
>
> 
>
> EDIT slow so slow... неуспел 
>
> 
>
> And what now?
I dont know.  Something... ааа, метод научного тыка, в общем.
## Post #107
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-25T20:14:00+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Fonts are in bigfile.000 (physically should be located in bigfile.003).

ID/hash/filename = 0x47B84A2B

However that's for original english fonts.
## Post #108
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T20:23:16+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> Give me few minutes.
EDIT: http://rghost.ru/19311041
There you go. 
Tnx.

Now extracting from original russian clone-dvd

EDIT slow so slow... неуспел 

And what now? 
I dont know.  Something... ааа, метод научного тыка, в общем.
Cheering up for you fella!
## Post #109
- Username: Illusive Man
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 26, 2011 4:26 am
- Post datetime: 2011-08-25T20:28:48+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Давайте парни, вся страна на вас рассчитывает! Не дайте убогому переводу от нового диска загубить столь замечательную игру!
## Post #110
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T20:30:04+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Illusive Man
>
> Давайте парни, вся страна на вас рассчитывает! Не дайте убогому переводу от нового диска загубить столь замечательную игру!
С какого ты форума пришел?) ПРосто интересно)
So, still keeping my fingers crossed, and hoping for the best!
## Post #111
- Username: Illusive Man
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 26, 2011 4:26 am
- Post datetime: 2011-08-25T20:32:35+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Я не с форума) Я тоже пытался поменять озвучку, но температура и куча бинарных файлов в анпакере не дали мне осуществить мою задумку)
## Post #112
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T20:35:45+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Illusive Man
>
> Я не с форума) Я тоже пытался поменять озвучку, но температура и куча бинарных файлов в анпакере не дали мне осуществить мою задумку)
Oh, there is a problem with charset and fonts, as far as i understand. This is the translate-happiness stopper(
## Post #113
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-25T20:37:43+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

You should find russian fonts in bigfile.000 (and subsequent bigfiles) and replace them with english fonts (I already gave you ID/hash/filename for those).
## Post #114
- Username: Illusive Man
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 26, 2011 4:26 am
- Post datetime: 2011-08-25T20:44:03+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Ok, correct me if i'm wrong- you trying add russian language in bigfile_English, right? But it would be easier to add english voices in bigfile_Russian or it's impossible?
## Post #115
- Username: Tamxaun
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 10, 2011 7:48 pm
- Post datetime: 2011-08-25T20:44:21+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> You should find russian fonts in bigfile.000 (and subsequent bigfiles) and replace them with english fonts (I already gave you ID/hash/filename for those).

and what can we open them with?
## Post #116
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T20:46:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> You should find russian fonts in bigfile.000 (and subsequent bigfiles) and replace them with english fonts (I already gave you ID/hash/filename for those).
Thats my next step, after create a subtitiles file from "original russian files", just in case.
## Post #117
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T20:46:48+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Tamxaun
>
> mnn wrote:You should find russian fonts in bigfile.000 (and subsequent bigfiles) and replace them with english fonts (I already gave you ID/hash/filename for those).

and what can we open them with?
"Gibbed.Deus" from Rick. Link on a 5 page
## Post #118
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-25T20:51:42+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Well, you don't need to open the fonts. You just need to swap them.
## Post #119
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T20:55:48+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Ok, correct me if i'm wrong- you trying add russian language in bigfile_English, right?
Not so... we tryin replace a fonts.

> But it would be easier to add english voices in bigfile_Russian or it's impossible?
Hm... u possibly right. From bigfile_English replace to bigfile_Russian and set a russian lang in Steam... It may be work. I try after "font-sex" 

> Well, you don't need to open the fonts. You just need to swap them.
Yes, now i try do this.
## Post #120
- Username: BratSinot
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 26, 2011 4:46 am
- Post datetime: 2011-08-25T20:57:57+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

So, replacing English "locals.bin" on Russian "locals.bin" make russian subs with english voices? Or i wasting time?
## Post #121
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T20:59:14+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> Ok, correct me if i'm wrong- you trying add russian language in bigfile_English, right?
Not so... we tryin replace a fonts.
 But it would be easier to add english voices in bigfile_Russian or it's impossible? 
Hm... u possibly right. From bigfile_English replace to bigfile_Russian and set a russian lang in Steam... It may be work. I try after "font-sex" 
Well, you don't need to open the fonts. You just need to swap them.
Yes, now i try do this.
Cheering for you, and waiting for an update.
How much time, will it take approximately?
## Post #122
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T21:02:47+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Larus
>
> 
Cheering for you, and waiting for an update.
How much time, will it take approximately?

Dont know, maybe hour, maybe 30 min. Я сам не до конца понимаю, что именно делаю. 

Edit: Guys, give me a screenshot of default list of files/directories from russian version. Actually i forgot -- there is a file bigfile_Russian.000 by default?  In my DXHR directory now bardak.
## Post #123
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T21:04:30+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> Larus wrote:
Cheering for you, and waiting for an update.
How much time, will it take approximately?

Dont know, maybe hour, maybe 30 min. Я сам не до конца понимаю, что именно делаю.
But you will continue doing it today right? Than i shall await the results.
## Post #124
- Username: Furie31
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 26, 2011 4:05 am
- Post datetime: 2011-08-25T21:06:07+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Посоны, молю, сделайте это. D:
## Post #125
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T21:11:49+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Larus
>
> But you will continue doing it today right? Than i shall await the results.
Right. 

If i surrender -- i write here.
## Post #126
- Username: BratSinot
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 26, 2011 4:46 am
- Post datetime: 2011-08-25T21:15:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> Larus wrote:But you will continue doing it today right? Than i shall await the results.
Right. 

If i surrender -- i write here.
Remember, if you surrender you family dead. Sarif Industries find you, and "you'll never find them" =)
Запомни, если ты сдашься --  твоя семья мертва. Sarif Industries найдет тебя, и "you'll never find them" =)
P.S. This is not a threat!
## Post #127
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T21:20:39+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

mnn, how u identified "47B84A2B" as english font? I find it, but i really dont know, how i can find a russian font for replace english.
## Post #128
- Username: Tamxaun
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 10, 2011 7:48 pm
- Post datetime: 2011-08-25T21:24:53+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I have done it ! 
You need to copy all files from \bigfile_English\FFFFE081\__UNKNOWN\mul\      to       bigfile_Russian\FFFFE200\__UNKNOWN\mul\
and then pack bigfile_Russian with "Gibbed.DeusEx3.Pack"  and choose "Russian language" in steam before you run the game
## Post #129
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T21:28:51+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Tamxaun
>
> I have done it ! 
You need to copy all files from \bigfile_English\FFFFE081\__UNKNOWN\mul\      to       bigfile_Russian\FFFFE200\__UNKNOWN\mul\
and then pack bigfile_Russian with "Gibbed.DeusEx3.Pack"  and choose "Russian language" in steam before you run the game
Maaan! Im a dammit slowpoke. 

Wastin my time for fonts, and u was right before.
## Post #130
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T21:29:04+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Tamxaun
>
> I have done it ! 
You need to copy all files from \bigfile_English\FFFFE081\__UNKNOWN\mul\      to       bigfile_Russian\FFFFE200\__UNKNOWN\mul\
and then pack bigfile_Russian with "Gibbed.DeusEx3.Pack"  and choose "Russian language" in steam before you run the game
Have you tried it? Did it work? 
Upload the file, and make an instructions, please!
## Post #131
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T21:34:50+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Larus
>
> Tamxaun wrote:I have done it ! 
You need to copy all files from \bigfile_English\FFFFE081\__UNKNOWN\mul\      to       bigfile_Russian\FFFFE200\__UNKNOWN\mul\
and then pack bigfile_Russian with "Gibbed.DeusEx3.Pack"  and choose "Russian language" in steam before you run the game
Have you tried it? Did it work? 
Upload the file, and make an instructions, please!

Now try same method. If it work both of us -- Tamxaun is a genius. 

Instructions is simple: unpack files, then replace content, and pack again.

Step-by-Step with commands i can write later, or Tamxaun can.
## Post #132
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T21:37:19+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> Larus wrote:Tamxaun wrote:I have done it ! 
You need to copy all files from \bigfile_English\FFFFE081\__UNKNOWN\mul\      to       bigfile_Russian\FFFFE200\__UNKNOWN\mul\
and then pack bigfile_Russian with "Gibbed.DeusEx3.Pack"  and choose "Russian language" in steam before you run the game
Have you tried it? Did it work? 
Upload the file, and make an instructions, please!

Now try same method. If it work both of us -- Tamxaun is a genius. 

Instructions is simple: unpack files, then replace content, and pack again.

Step-by-Step with commands i can write later, or Tamxaun can.
Please, do so. I am complete and utter lost in this.
## Post #133
- Username: madprof
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 26, 2011 2:29 am
- Post datetime: 2011-08-25T21:38:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

God bless Tamxaun and zermik!
Спасибо, парни!
## Post #134
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T21:40:20+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from madprof
>
> God bless Tamxaun and zermik!
Спасибо, парни!
Сработало?
## Post #135
- Username: madprof
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 26, 2011 2:29 am
- Post datetime: 2011-08-25T21:42:54+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Unpacking, replacing and repacking now. Testing in process
## Post #136
- Username: Tamxaun
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 10, 2011 7:48 pm
- Post datetime: 2011-08-25T21:44:38+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from madprof
>
> Unpacking, replacing and repacking now. Testing in process

You are supposed to confirm it
## Post #137
- Username: popolski
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 25, 2011 10:43 pm
- Post datetime: 2011-08-25T21:47:13+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Does this tool work for Xbox360 files ? Thanks
## Post #138
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T21:48:44+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hmm... I have same ghay voices.

Tamxaun -- maybe need replace ALL content of files?
## Post #139
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T21:50:01+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> Hmm... I have same ghay voices.

Tamxaun -- maybe need replace ALL content of files?
What do you mean? Russian voices?
## Post #140
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T21:51:22+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Larus
>
> What do you mean? Russian voices?

Yeah... Mr. Page sounds like ванильный пидорас. 

EDIT: Make repack file with all content. Wait for results.
## Post #141
- Username: madprof
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 26, 2011 2:29 am
- Post datetime: 2011-08-25T21:51:57+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Tamxaun
>
> madprof wrote:Unpacking, replacing and repacking now. Testing in process

You are supposed to confirm it

Yep. Now prepared to pack bigfile_Russian

By the way, why different amount of files at \bigfile_English\FFFFE081\__UNKNOWN\mul\ (16013) and bigfile_Russian\FFFFE200\__UNKNOWN\mul\ (16019) ?
## Post #142
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T21:53:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> Larus wrote:What do you mean? Russian voices?

Yeah... Mr. Page sounds like ванильный пидорас. 

EDIT: Make repack file with all content. Wait for results.
But some of the voices became english, right?
## Post #143
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T22:08:07+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from madprof
>
> Tested with new game, "Language = russian" in THEGFW.ini
Result - first cut-scene with russian voice "Mr. Page sounds like ванильный пидорас" (c), then in-game - original voices with russian subtitles

Confirmed at 95%

Mmm... i quit game on cut-scene.  Try again.

Maybe for cut-scenes need copy in pack something else from bigfile_English?
## Post #144
- Username: madprof
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 26, 2011 2:29 am
- Post datetime: 2011-08-25T22:11:27+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> madprof wrote:Tested with new game, "Language = russian" in THEGFW.ini
Result - first cut-scene with russian voice "Mr. Page sounds like ванильный пидорас" (c), then in-game - original voices with russian subtitles

Confirmed at 95% 

Mmm... i quit game on cut-scene.  Try again.
Try skip cutscene 

> Reply from zermik
>
> Maybe for cut-scenes need copy in pack something else from bigfile_English?
May be, but even 95% original voices in this game - it's amazing!
## Post #145
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T22:12:38+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> madprof wrote:Tested with new game, "Language = russian" in THEGFW.ini
Result - first cut-scene with russian voice "Mr. Page sounds like ванильный пидорас" (c), then in-game - original voices with russian subtitles

Confirmed at 95% 

Mmm... i quit game on cut-scene.  Try again.

Maybe for cut-scenes need copy in pack something else from bigfile_English?
I heard there are multi versions of videos there, so, there must be a switch.
## Post #146
- Username: bm1
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2011-08-25T22:13:11+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Tamxaun
>
> rghost.ru  -  "File size limit is exceeded"
Please, try [http://nekaka.com](http://nekaka.com) or [http://www.onedayfiles.com](http://www.onedayfiles.com). Those sites don't require registration and don't cut upload/download speed.
## Post #147
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T22:13:49+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Larus
>
> Tamxaun wrote:rghost.ru  -  "File size limit is exceeded"
try here^ http://narod.yandex.ru/
Download limit 100Kb\s.

Full repack of file broke all voices in game, exept cut-scenes. So sounds of cut-scenes in another place.
## Post #148
- Username: keepinsafeman
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 26, 2011 5:54 am
- Post datetime: 2011-08-25T22:14:22+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from madprof
>
> Tested with new game, "Language = russian" in THEGFW.ini
Result - first cut-scene with russian voice "Mr. Page sounds like ванильный пидорас" (c), then in-game - original voices with russian subtitles

Confirmed at 95%
"In minimus maximus Deus" ©
And here we have 95%. It's enough for me to be happy & thank all people who made me smile
## Post #149
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T22:14:56+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> Larus wrote:Tamxaun wrote:rghost.ru  -  "File size limit is exceeded"
try here^ http://narod.yandex.ru/
Download limit 100Kb\s.

Full repack of file broke all voices in game, exept cut-scenes. So sounds of cut-scenes in another place.
Drat, we need to find them!
## Post #150
- Username: Tamxaun
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 10, 2011 7:48 pm
- Post datetime: 2011-08-25T22:19:31+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Oops guys ) First time I checked the ingame speech  so cutscenes have a russian voice ((
## Post #151
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T22:21:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Larus
>
> 
Drat, we need to find them!

> Oops guys ) First time I checked speech of ingame so cutscenes have a russian voice ((
Same problem.

Lets try replace all content, exept XML-file.
## Post #152
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T22:22:15+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Tamxaun
>
> Oops guys ) First time I checked speech of ingame so cutscenes have a russian voice ((
Can you be a hero, and find a way to make cut-scenes in english?
## Post #153
- Username: Illusive Man
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 26, 2011 4:26 am
- Post datetime: 2011-08-25T22:24:28+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Походу звуковые дорожки от катсцен лежат в другом паке, по другому бред какой-то выходит
## Post #154
- Username: madprof
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 26, 2011 2:29 am
- Post datetime: 2011-08-25T22:26:49+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Tamxaun
>
> Oops guys ) First time I checked the ingame speech  so cutscenes have a russian voice ((

Yep, but ingame original voices - it's awesome. Good work!
## Post #155
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T22:28:22+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Illusive Man
>
> Походу звуковые дорожки от катсцен лежат в другом паке, по другому бред какой-то выходит
Dont think so. Because after change language in Steam to english startin dowload just ONE file -- bigfileEnglish.000. And all voices in english.

Strange things.
## Post #156
- Username: Illusive Man
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 26, 2011 4:26 am
- Post datetime: 2011-08-25T22:31:55+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Ну язык переключается на английский, от того и врубаются англ. звуковые дорожки. Попробуй файл russian переименовать в english и запустить игру
## Post #157
- Username: madprof
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 26, 2011 2:29 am
- Post datetime: 2011-08-25T22:33:42+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Illusive Man
>
> Ну язык переключается на английский, от того и врубаются англ. звуковые дорожки. Попробуй файл russian переименовать в english и запустить игру

This shit was tested first of all. No result.
## Post #158
- Username: zermik
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Aug 26, 2011 1:17 am
- Post datetime: 2011-08-25T22:36:40+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Illusive Man
>
> Ну язык переключается на английский, от того и врубаются англ. звуковые дорожки. Попробуй файл russian переименовать в english и запустить игру

Steam will delete renamed file, and start dowload "original russian" file.

BTW: on license Steam version replace file is workin without any troubles, exept "russian voice" in cut-scenes. Thanks to Tamxaun.

Now we got only a small problem with cut-scenes, any ideas, because XML does not affect.
## Post #159
- Username: madprof
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 26, 2011 2:29 am
- Post datetime: 2011-08-25T22:43:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zermik
>
> BTW: on license Steam version replace file is workin without any troubles, exept "russian voice" in cut-scenes. Thanks to Tamxaun.

Now we got only a small problem with cut-scenes, any ideas, because XML does not affect.

Amen!
## Post #160
- Username: Illusive Man
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 26, 2011 4:26 am
- Post datetime: 2011-08-25T22:44:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

В моем случае, при переименование файла с bigfile_Russian в bigfile_English вся игра становится английской, в том числе и кат сцены.

In my case, rename the file from bigfile_Russian to bigfile_English the whole game become English, including the cut scenes.

А вообще парни реально молодцы, русская смекалка как всегда победила)
## Post #161
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-25T22:46:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Illusive Man
>
> В моем случае, при переименование файла с bigfile_Russian в bigfile_English вся игра становится английской, в том числе и кат сцены.

In my case, rename the file from bigfile_Russian to bigfile_English the whole game become English, including the cut scenes.

А вообще парни реально молодцы, русская смекалка как всегда победила)
This was tested at a very beginning.
You know that you can just change language in steam, right?
## Post #162
- Username: madprof
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 26, 2011 2:29 am
- Post datetime: 2011-08-25T22:50:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

WTF?!

Trying unpack bigfile_English, edit bigfile.xml with replacing English to Russian, pack back to bigfile_Russian - ...... russian voices at cutscenes!    

WTF?!!

Maybe cutscene voices at patch000?
## Post #163
- Username: Illusive Man
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 26, 2011 4:26 am
- Post datetime: 2011-08-25T22:54:43+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

likely the are in main bigfile's, and i think it will just voice tracks, not entire video

( Есть конечно абсолютно тупая идея, как найти эти дорожки- подсчитать все ролики, в т.ч. и обучение, и попытаться найти дорожки от них в основных файлах ища папку (ожидая, что они кончено же будут в отдельной папке) сод. приблизительно подходящее кол-во файлов. Либо найти того гуру, кот. разбирается в названиях аля 00A0EC11 и может сказать что это за файл)
( Либо может быть, что англ. и русские звуковые дорожки есть в обоих файлах, тогда можно попробовать вычислить их, ища схожие файлы в обоих распакованных архивах)
## Post #164
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-08-25T23:13:25+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Illusive Man
>
> В моем случае, при переименование файла с bigfile_Russian в bigfile_English вся игра становится английской, в том числе и кат сцены.

In my case, rename the file from bigfile_Russian to bigfile_English the whole game become English, including the cut scenes.

А вообще парни реально молодцы, русская смекалка как всегда победила)

> Reply from Illusive Man
>
> likely the are in main bigfile's, and i think it will just voice tracks, not entire video

( Есть конечно абсолютно тупая идея, как найти эти дорожки- подсчитать все ролики, в т.ч. и обучение, и попытаться найти дорожки от них в основных файлах ища папку (ожидая, что они кончено же будут в отдельной папке) сод. приблизительно подходящее кол-во файлов. Либо найти того гуру, кот. разбирается в названиях аля 00A0EC11 и может сказать что это за файл)
( Либо может быть, что англ. и русские звуковые дорожки есть в обоих файлах, тогда можно попробовать вычислить их, ища схожие файлы в обоих распакованных архивах)

Guys, here isn't a Russian forum. You are chating here like you chat in your country. 
Let the other people understand what you mean. Maybe the info shared here, can help the others.

Stay tuned!
## Post #165
- Username: garuspex
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 26, 2011 5:45 am
- Post datetime: 2011-08-25T23:24:49+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Almost all russian characters are russian versions of what was sad in english, other just suggestions and cheering.
## Post #166
- Username: Pey
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Mar 26, 2011 6:14 pm
- Post datetime: 2011-08-26T02:09:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #167
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-26T02:26:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hey rick when will the cimplete filelist be done?
## Post #168
- Username: bm1
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2011-08-26T02:29:11+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Does anyone know what files the music is and how to convert them?
## Post #169
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-26T02:59:07+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Musics are .mul files some have been identified and some have not. since its the pc version you can use this tool for the python program [http://hcs64.com/files/dxhr_deblockbe03.zip](http://hcs64.com/files/dxhr_deblockbe03.zip) to demux the channels, then use: [http://hcs64.com/files/fsb_mpeg012.zip](http://hcs64.com/files/fsb_mpeg012.zip) to convert the fsb's to mp3's and you can then join the mono channels together to make the track.
## Post #170
- Username: bm1
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2011-08-26T03:12:12+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

How do you use the python script? I never really used py scripts before and I would know how to go about using it.
## Post #171
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-26T03:12:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I have purged piracy-related posts in this thread. Further discussion of piracy of the game, pirated copies, or linking to sites where pirate copies can be obtained is not acceptable.
## Post #172
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-26T03:13:33+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from OrangeC
>
> Hey rick when will the cimplete filelist be done?It's a work in progress, it's not easy to obtain names of all files.
## Post #173
- Username: bm1
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2011-08-26T03:19:58+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Anyone? The only thing stopping me from getting the music is the py script.
## Post #174
- Username: bm1
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2011-08-26T03:56:06+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Ok I found out how to execute the py script, but it gives me thousands of empty fsb and xma files. Does this tool not work for the pc files?
## Post #175
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-26T03:57:52+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #176
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2011-08-26T04:13:24+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #177
- Username: bm1
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2011-08-26T04:19:42+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

This is what I get when I use the script on the file.
## Post #178
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-26T04:21:22+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Does anyone know, where video files are lying, and how to change there language?
## Post #179
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-26T04:28:01+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from popolski
>
> Does this tool work for Xbox360 files ? Thanks

Yes i'm doing translation to my lang
## Post #180
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-26T04:29:06+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> I have purged piracy-related posts in this thread. Further discussion of piracy of the game, pirated copies, or linking to sites where pirate copies can be obtained is not acceptable.

Agree  PPL common respect the author!!!

EDIT: Btw i have try repack on Bigendianes and it works perfect so far. So thank you for the effort mate
## Post #181
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-26T05:48:45+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Rick do you know of the format for Fonts or where are fonts located please ? Trying to find it in BIGFILE.000 but it is very hard to do it. Any idea please ?
## Post #182
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-26T05:49:39+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

If I had to guess they would be textures stored in the usual .drm files somewhere.
## Post #183
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-26T05:54:15+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> If I had to guess they would be textures stored in the usual .drm files somewhere.

Hmm. Is there any(simple) way how to identify them please ? If they are textures, than it would be in format dds or ddx, problem is there is 1000's of files
## Post #184
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-08-26T06:12:20+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I saw the font texture. I don't know where it is inside the files, but TexMod can extract from the game.
## Post #185
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-26T06:32:11+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Tamxaun
>
> Oops guys ) First time I checked the ingame speech  so cutscenes have a russian voice ((
What if, instead of altering russian file, you'll just add russian subs, to english version of the game? Suppose it will do? Or am i wrong?
Anyway, Does anyone knows, where cut-scenes lies? And how to alter there sound?
Guess there are in other bigfiles. We need to unpack them.
2Tamxaun, Any progress?
## Post #186
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-26T09:17:09+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> If I had to guess they would be textures stored in the usual .drm files somewhere.
0x47B84A2B for english fonts
## Post #187
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-26T09:24:01+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> Rick wrote:If I had to guess they would be textures stored in the usual .drm files somewhere.
0x47B84A2B for english fonts

How did you find out ? Is it for PC or X360?
## Post #188
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-26T09:31:33+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

It's for PC, maybe it's the same for X360, no idea.

I just know. You should look for russian fonts...
## Post #189
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-26T09:54:02+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

That file name is already known: pc-w\globaldatabase.drm

PS3 should be ps3-w\globaldatabase.drm and X360 should be xenon-w\globaldatabase.drm

Are you guys using my tools correctly? There are file lists under the 'projects' dir where Unpack/Pack are, Unpack uses it.
## Post #190
- Username: THE GAME:HHH
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 26, 2011 6:13 pm
- Post datetime: 2011-08-26T10:32:30+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

guys i'm very newby  
how can change subs with eng audio?
i want set audio eng and subs in italian, but how?
i download de compiler from rick, and now?
## Post #191
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-26T10:38:16+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Yeah, somebody please make a step-by-step instruction, of packing\unpackung. I'll try to make russ\eng version of the game.
Tamxaun, i'm still praying for you sucess with cut-scenes.
## Post #192
- Username: skyus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 03, 2010 3:27 pm
- Post datetime: 2011-08-26T11:24:29+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> 
Are you guys using my tools correctly? There are file lists under the 'projects' dir where Unpack/Pack are, Unpack uses it.

Tell me please to use File Lists by your program, I need just put *.filelist to dir with Gibbed.DeusEx3.Unpack.exe ?
## Post #193
- Username: sbabby
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 26, 2011 7:36 pm
- Post datetime: 2011-08-26T11:56:57+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #194
- Username: mNeko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 26, 2011 3:56 pm
- Post datetime: 2011-08-26T12:08:58+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

i guess ,we need  find files of russian fonts and replace it, and not replace cutscene files. Cutscene audio files cant be in bigfile.000 it would be nonsense. In bigfiles.000 animation,geometry, script for cutscene but audio in bigRussian file.
## Post #195
- Username: THE GAME:HHH
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 26, 2011 6:13 pm
- Post datetime: 2011-08-26T12:23:56+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

ok, replace .mul file in bigfile_eng to bigfile_lenguageyouset and it's work.
But in cuts'in still have audio ita.
audio ita very bad, it's like from a gay's actor, please find a way to set all audio in eng in game and cuts'in.
## Post #196
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-26T13:24:29+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Does anybody, have any idea how to change videos language, or where they are?
## Post #197
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-26T13:31:12+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Herdell
>
> Illusive Man wrote:В моем случае, при переименование файла с bigfile_Russian в bigfile_English вся игра становится английской, в том числе и кат сцены.

In my case, rename the file from bigfile_Russian to bigfile_English the whole game become English, including the cut scenes.

А вообще парни реально молодцы, русская смекалка как всегда победила)
Illusive Man wrote:likely the are in main bigfile's, and i think it will just voice tracks, not entire video

( Есть конечно абсолютно тупая идея, как найти эти дорожки- подсчитать все ролики, в т.ч. и обучение, и попытаться найти дорожки от них в основных файлах ища папку (ожидая, что они кончено же будут в отдельной папке) сод. приблизительно подходящее кол-во файлов. Либо найти того гуру, кот. разбирается в названиях аля 00A0EC11 и может сказать что это за файл)
( Либо может быть, что англ. и русские звуковые дорожки есть в обоих файлах, тогда можно попробовать вычислить их, ища схожие файлы в обоих распакованных архивах)

Guys, here isn't a Russian forum. You are chating here like you chat in your country. 
Let the other people understand what you mean. Maybe the info shared here, can help the others.

Stay tuned!
Sorry, emotions overwhelmed.
Post was about counting videos, and trying to find them. If anybody have info, where there are, please, speak up)
## Post #198
- Username: mNeko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 26, 2011 3:56 pm
- Post datetime: 2011-08-26T14:49:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

well, ULTRA create repack with russian subtitles and english voices. Like people said.
## Post #199
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-26T15:53:33+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mNeko
>
> well, ULTRA create repack with russian subtitles and english voices. Like people said.
Can somebody, take bigfile out of it and share it?
## Post #200
- Username: mNeko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 26, 2011 3:56 pm
- Post datetime: 2011-08-26T16:20:56+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

i download right now but my speed is suxxxx, and there iso file only.
## Post #201
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-26T16:29:54+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mNeko
>
> i download right now but my speed is suxxxx, and there iso file only.
got about 3 hours of download ahead of me. So same here.
## Post #202
- Username: Lygatt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 26, 2011 9:22 pm
- Post datetime: 2011-08-26T17:39:12+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi,

Thanks a lot Rick  for your pack/unpack tool. Thank you!

I still have some questions and sorry for the noob questions but it's the only way to progress.

1)I would like to know how to build the C# Solution. By the way thanks to killerpepo for the last build.
I downloaded all the files and created all folders according to here [http://svn.gib.me/public/deusex3/](http://svn.gib.me/public/deusex3/) but when I opened the Human Revolution.sln with Visual C# express, I have notifications that some files are missing:
NDesk.Options.csproj
Gibbed.IO.csproj
Gibbed.ProjectData.csproj
Where are these files?
It's the first time I use this, so if someone can explain me how to build the solution it will be very appreciated.

2)I used deblockbe03 with python to demux the channels from the .mul files (thanks to OrangeC for the links and to HCS for the tools).
I obtained several mono .fsb files. I have now to use fsb_mpeg to convert these files to mp3 and then join them.
But I don't understand how to use it:
fsb_mpeg file.fsb [-p N] [-b N]
 -p N: assume up to N bytes of padding per frame
 -b N: assume that streams are padded to N bytes
What are the -p and -b for? How can I find these values to convert the .fsb correctly?

3) When I unpacked the bigfile archive, I found .mus files. Are these audio files and if so how can I convert them.

Thank you.
## Post #203
- Username: Larus
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Aug 24, 2011 3:56 am
- Post datetime: 2011-08-26T17:58:20+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

File from repack, didn't work, so i guess videos are in another archive?
Ultra made fonts, to be loaded from external source so, wouldn't it be possible to just add them to englishbigfile along with subs? Tamxaun?
## Post #204
- Username: Tamxaun
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 10, 2011 7:48 pm
- Post datetime: 2011-08-26T19:01:41+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Larus
>
> File from repack, didn't work, so i guess videos are in another archive?
Ultra made fonts, to be loaded from external source so, wouldn't it be possible to just add them to englishbigfile along with subs? Tamxaun?
Repack has external fonts of Russian lang and some how he put together it with game...
Actually i have been trying to implement any opportunities to run the game in convenient way since my first attempt, but....
I have even tried to run the game by deleting all files from each folder in every bigfile stuff and i have discovered that bigfile_russian and _english definitely don't have any voices of cut-scenes as well as in bigfile.000( but I'm not sure this one entirely, though). 

I will try to do something at less until someone will do it first
## Post #205
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-08-26T20:04:25+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Lygatt
>
> 
1)I would like to know how to build the C# Solution. By the way thanks to killerpepo for the last build.
I downloaded all the files and created all folders according to here http://svn.gib.me/public/deusex3/ but when I opened the Human Revolution.sln with Visual C# express, I have notifications that some files are missing:
NDesk.Options.csproj
Gibbed.IO.csproj
Gibbed.ProjectData.csproj
Where are these files?
It's the first time I use this, so if someone can explain me how to build the solution it will be very appreciated.

For example use this to download the files: [http://tortoisesvn.net/downloads.html](http://tortoisesvn.net/downloads.html)
Not all files available under html access. And you don't have to download the files one by one, and create the tree structure!
## Post #206
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-26T20:14:06+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Lygatt
>
> Hi,

Thanks a lot Rick  for your pack/unpack tool. Thank you!

I still have some questions and sorry for the noob questions but it's the only way to progress.

1)I would like to know how to build the C# Solution. By the way thanks to killerpepo for the last build.
I downloaded all the files and created all folders according to here http://svn.gib.me/public/deusex3/ but when I opened the Human Revolution.sln with Visual C# express, I have notifications that some files are missing:
NDesk.Options.csproj
Gibbed.IO.csproj
Gibbed.ProjectData.csproj
Where are these files?
It's the first time I use this, so if someone can explain me how to build the solution it will be very appreciated.

2)I used deblockbe03 with python to demux the channels from the .mul files (thanks to OrangeC for the links and to HCS for the tools).
I obtained several mono .fsb files. I have now to use fsb_mpeg to convert these files to mp3 and then join them.
But I don't understand how to use it:
fsb_mpeg file.fsb [-p N] [-b N]
 -p N: assume up to N bytes of padding per frame
 -b N: assume that streams are padded to N bytes
What are the -p and -b for? How can I find these values to convert the .fsb correctly?

3) When I unpacked the bigfile archive, I found .mus files. Are these audio files and if so how can I convert them.

Thank you.

with fsb_mpeg use like: fsb_mpeg file.fsb -p 4
## Post #207
- Username: Lygatt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 26, 2011 9:22 pm
- Post datetime: 2011-08-27T00:27:05+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

@evin I installed tortoisesvn as you mentioned and I was able to download the files from the repository and build the solution correctly. Thanks to you I have the right method now.

@OrangeC I used -p 4 on mono .fsb and it worked thank you but I also used -p 16 and it worked too, so which one should we apply?

On the readme it's noted that for some games we have to specify a different padding than 16 bytes and other games used both padding (-p) and streams between padding (-b).
Depending on the game I only have to test because I still don't know how to determine these values with an Hex Editor or if someone know I will be interested.

Dear evin and dear OrangeC thank you again for your feedback.
## Post #208
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-27T00:41:03+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

i mainly use 4 and it seems to work on all of them.
## Post #209
- Username: Lygatt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 26, 2011 9:22 pm
- Post datetime: 2011-08-27T01:00:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Ok then I will use a padding of 4 or 16 bytes until I see a particular .fsb file format.
Thank you OrangeC.
## Post #210
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2011-08-27T13:37:01+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I still get a thousand of empty .fsb files, my version is PC, how come?
## Post #211
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-27T16:17:49+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hmm its probably maybe the deblocker isn't configured for pc yet. the ps3 and 360 version works though.
## Post #212
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2011-08-27T18:10:28+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #213
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-27T18:43:31+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Just use Towav for xma. ww2ogg is for OGG vorbis files.
## Post #214
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2011-08-27T19:15:34+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from OrangeC
>
> Just use Towav for xma. ww2ogg is for OGG vorbis files.

Since they don't get any headers, I added XMA header to it using QuickBMS (even XMA2) but STILL gives a messy .WAV file...?
## Post #215
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-28T00:07:54+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

You need to add a mono stereo header 44hz
## Post #216
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2011-08-28T03:52:49+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from OrangeC
>
> You need to add a mono stereo header 44hz

This may sound stupid, but...how do you do that? 
Do you have a .bms script I could use to make it's header become what you said?
## Post #217
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-28T04:41:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

```
set CH 1
set OFFSET 0x0

set MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x80\xbb\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x02\x02\x00\x64\x61\x74\x61\x00\x58\xa7\x00"
get SIZE asize
math SIZE -= OFFSET
callfunction addXMAheader 1
get NAME basename
string NAME += ".xma"
get SIZE asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE

startfunction addXMAheader
   set RIFFSIZE SIZE
   math RIFFSIZE += 0x34
   putVarChr MEMORY_FILE 0x04 RIFFSIZE long
   putVarChr MEMORY_FILE 0x24 FREQ long
   putVarChr MEMORY_FILE 0x31 CH byte
   putVarChr MEMORY_FILE 0x38 SIZE long
   append
   log MEMORY_FILE OFFSET SIZE
   append
endfunction
```
## Post #218
- Username: Andargor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 28, 2011 11:56 am
- Post datetime: 2011-08-28T04:46:57+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi all, nice work (especially Rick). Does anyone know what scripting engine they used? I'm trying to find some modifiable scripts, such as merchant inventory. Any idea of their location?

Seems *.drm is all media files, or are scripts embedded and in bytecode with some sort of interpreter?
## Post #219
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2011-08-28T05:03:22+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from OrangeC
>
> Code: Select allset FREQ 44100
set CH 1
set OFFSET 0x0

set MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x80\xbb\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x02\x02\x00\x64\x61\x74\x61\x00\x58\xa7\x00"
get SIZE asize
math SIZE -= OFFSET
callfunction addXMAheader 1
get NAME basename
string NAME += ".xma"
get SIZE asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE

startfunction addXMAheader
   set RIFFSIZE SIZE
   math RIFFSIZE += 0x34
   putVarChr MEMORY_FILE 0x04 RIFFSIZE long
   putVarChr MEMORY_FILE 0x24 FREQ long
   putVarChr MEMORY_FILE 0x31 CH byte
   putVarChr MEMORY_FILE 0x38 SIZE long
   append
   log MEMORY_FILE OFFSET SIZE
   append
endfunction

Alright, after this code I used "ToWav" it gave me a messy .wav file again, only this time you hear at certain spots among the messy bits actual understandable sequence, I wonder why?
## Post #220
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-28T08:01:25+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Andargor
>
> Hi all, nice work (especially Rick). Does anyone know what scripting engine they used? I'm trying to find some modifiable scripts, such as merchant inventory. Any idea of their location?

Seems *.drm is all media files, or are scripts embedded and in bytecode with some sort of interpreter?Scripts are part of DRM files yes, it's a custom scripting engine with bytecode. I'm still trying to make some headway on it.
## Post #221
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-28T11:11:08+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from FinalBlast
>
> OrangeC wrote:Code: Select allset FREQ 44100
set CH 1
set OFFSET 0x0

set MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x80\xbb\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x02\x02\x00\x64\x61\x74\x61\x00\x58\xa7\x00"
get SIZE asize
math SIZE -= OFFSET
callfunction addXMAheader 1
get NAME basename
string NAME += ".xma"
get SIZE asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE

startfunction addXMAheader
   set RIFFSIZE SIZE
   math RIFFSIZE += 0x34
   putVarChr MEMORY_FILE 0x04 RIFFSIZE long
   putVarChr MEMORY_FILE 0x24 FREQ long
   putVarChr MEMORY_FILE 0x31 CH byte
   putVarChr MEMORY_FILE 0x38 SIZE long
   append
   log MEMORY_FILE OFFSET SIZE
   append
endfunction

Alright, after this code I used "ToWav" it gave me a messy .wav file again, only this time you hear at certain spots among the messy bits actual understandable sequence, I wonder why?

Okay then specify the steps you used to parse and decode your mul files. Are they from the 360 version right?
## Post #222
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2011-08-28T11:30:11+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from OrangeC
>
> FinalBlast wrote:OrangeC wrote:Code: Select allset FREQ 44100
set CH 1
set OFFSET 0x0

set MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x80\xbb\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x02\x02\x00\x64\x61\x74\x61\x00\x58\xa7\x00"
get SIZE asize
math SIZE -= OFFSET
callfunction addXMAheader 1
get NAME basename
string NAME += ".xma"
get SIZE asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE

startfunction addXMAheader
   set RIFFSIZE SIZE
   math RIFFSIZE += 0x34
   putVarChr MEMORY_FILE 0x04 RIFFSIZE long
   putVarChr MEMORY_FILE 0x24 FREQ long
   putVarChr MEMORY_FILE 0x31 CH byte
   putVarChr MEMORY_FILE 0x38 SIZE long
   append
   log MEMORY_FILE OFFSET SIZE
   append
endfunction

Alright, after this code I used "ToWav" it gave me a messy .wav file again, only this time you hear at certain spots among the messy bits actual understandable sequence, I wonder why?

Okay then specify the steps you used to parse and decode your mul files. Are they from the 360 version right?

Yes, they are XB360 version, first I extract the .mul's .xma files using deblockbe(ver0.3) then I use the add stereo mono header .bms you gave me,
and finally I use towav to convert into normal playable files, I suspect it's perhaps from deblockbe's extracting them strangely, or maybe it's the .bms code?

Also upon using deblockbe(ver0.3) I get this after successfully extracting it's .xma files:

```
  File "D:\GAMES\deus ex\extractor\XB360\mul\deblock.py", line 116, in <module>
    zero1, block_payload_left, sampleoff, zero3 = unpack(">IIII", header_bytes)
struct.error: unpack requires a string argument of length 16
```
## Post #223
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-28T12:32:27+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hmm wait i don't think you don't have to add a header as deblocker does it for you. Just run the xma files through towav, as for the error ive never had that before, did you check in hex to see if the file looks right?
## Post #224
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2011-08-28T14:05:45+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #225
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-28T14:24:57+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I see now. apparently for some reason that few zero bytes at the beginning before the stream starts is suppose to be the header. Just it didn't ad correctly for some reason. So go ahead and remove the zero bytes and then try the header script and towav.
## Post #226
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2011-08-28T14:35:15+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Did that just now, but it gave the same results, strange...
## Post #227
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-28T14:48:45+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I just tried and it worked for me. Try setting the sample rate to 48hz, on the script as well.
## Post #228
- Username: UbsTRD
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 28, 2011 11:26 pm
- Post datetime: 2011-08-28T16:10:50+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

sup, i am new to this and can't figure out which files to exchange   
i have the xbox360 version of this game, i successfully unpacked the whole bigfiles.
i have two copies of the game: a english only and a german one. i want replace the english subs with german ones, but i want the game sound/voice to be english.

unpacked BIGFILE = 21.993 files



anyone can help out ?   
thanks alot.
## Post #229
- Username: gjinka
- Rank: Banned
- Number of posts: 95
- Joined date: Mon Apr 11, 2011 12:30 am
- Post datetime: 2011-08-29T02:21:57+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Is there any progress on the .drm format? 

I'm trying to get the original (higher res?) images for [this billboard](http://cloud.steampowered.com/ugc/596946618025783198/3154E15D46D15FAE0B12AA02F1934B47A627837E/) and the LIMB one, for making wallpapers.

For you guys who have been working with the formats.. is it your feeling that it will eventually be possible to extract these images? I'm not sure if the Crystal engine uses some ridiculous proprietary texture format along with their ridiculous proprietary BIGFILE and .drm formats.  Also I'm not sure if those are static images with the glowy effects being shaders, or if they're prerendered video.
## Post #230
- Username: skyus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 03, 2010 3:27 pm
- Post datetime: 2011-08-29T05:40:55+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Can any one compile last source from Rick? Thanks a lot.
## Post #231
- Username: bluetrain
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 29, 2011 6:04 pm
- Post datetime: 2011-08-29T10:41:18+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi guys, I'm going to sound a lot noob here. But I'm really struggling with this one and this seems to be the only source on the internet that has any idea what to do.
I've read through this whole thread; and whilst there were pointers that helped me get places, I simply do not understand enough about what I am doing.

My goal is fairly simple:
I want to extract the pre-rendered video files from the game. In any format that I can work with.
I don't care about audio at all.

I have purchased the steam version and my mate has the PS3 version. I've extracted video before from games and converted using radgametools but only with programs people have made already.
And they're usually a lot easier than this. For starters, I don't even really know what I'm looking for.
The .cpks, seems to be the most likely candidate. And using VGMTOOLBOX I was able to extract a .adx file. But as far as I could tell that was just audio static. Unless I am mistaken.

My preference would be to somehow extract the videos from the PS3 version. But I don't even know how to start there, I'm sure I have all the necessary hardware. 
If the PS3 idea is unrealistic, then I'm happy to go back to the steam version. As I'd only prefer the PS3 for it's better quality.
All this code is the problem, I don't know what I'm even reading or looking for and I have no experience at all.

However I get the feeling that surplus to what some of you are trying to do, something like this might seem (dare i say) easy.

If anyone could help me out, or point me in the right direction that would be amazing. Thanks.
## Post #232
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-29T13:54:50+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I wrote a tool to demux .mul files, it's available on my repository as Gibbed.DeusEx3.Demux.

Supports both PC and PS3 .mul files. X360 is totally untested.

I've hardcoded a list of valid sample rates which may be incomplete so it will crash if it gets something unexpected.

Also: for fsb_mpeg, the correct padding value seems to be 24 (at least for music FSBs).

ie, 
```
fsb_mpeg.exe dx1theme2000_0.fsb -p 24
```
## Post #233
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-08-29T14:12:47+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

could not compile. gives 
 error  : Unable to read the project file 'Gibbed.Squish.csproj'. 
The project file could not be loaded: Gibbed.Squish.csproj'.
I am using TortoiseSVN
## Post #234
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-29T14:31:33+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from bluetrain
>
> My goal is fairly simple:
I want to extract the pre-rendered video files from the game. In any format that I can work with.
I don't care about audio at all.

The .cpks, seems to be the most likely candidate. And using VGMTOOLBOX I was able to extract a .adx file. But as far as I could tell that was just audio static. Unless I am mistaken.*.cpk should be *.usm (I incorrectly labeled that file type). They can be "converted" with VGMToolbox (VGMToolbox → Misc. Tools → Stream Tools → Video Demultiplexer, change format to USM (CRI Movie 2)).
## Post #235
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-29T14:32:04+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from rengareng
>
> could not compile. gives 
 error  : Unable to read the project file 'Gibbed.Squish.csproj'. 
The project file could not be loaded: Gibbed.Squish.csproj'.
I am using TortoiseSVNI forgot to commit the new externals, I just fixed that. Update and try again.
## Post #236
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-08-29T18:10:13+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi Rick,

File names seems uncorrect. Is there a way to correct them? Or is it normal? Thanks.
## Post #237
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-08-29T20:01:27+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi everyone,
I wanna know if there's a way to increase font size of the in-game subtitles, 
cause the original game font size is a little small to me. In Mafia 2 game some guys
got it. Maybe there's a way to do the same in Deus Ex HR by editing some xml or
another file inside the .bigs.

Any idea?
## Post #238
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-29T20:41:56+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from JPulowski
>
> Hi Rick,

File names seems uncorrect. Is there a way to correct them? Or is it normal? Thanks.I need more information, how is it wrong?
## Post #239
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-08-29T21:20:04+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Herdell: Look back, I've posted where are fonts located. The format (at least for me) is a mystery.
## Post #240
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-08-29T21:54:24+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> Herdell: Look back, I've posted where are fonts located. The format (at least for me) is a mystery.

I know about the fonts, and is *.dds files (Direct Draw)


I wanna know if there's a way to increase the size of displaying text in-game.
[deusexfont.7z](https://xentaxbackup.github.io/file/4674_deusexfont.7z)
## Post #241
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-08-29T21:56:30+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> JPulowski wrote:Hi Rick,

File names seems uncorrect. Is there a way to correct them? Or is it normal? Thanks.I need more information, how is it wrong?
00A13F5D.drm
0D0E2E08.mus
01BE62D9.sam

For instance. I've found "bigfile.filelist" file in project folder you've mentioned few posts ago, but I don't know what to do with it.
## Post #242
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-29T22:37:32+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from JPulowski
>
> 00A13F5D.drm
0D0E2E08.mus
01BE62D9.sam

For instance. I've found "bigfile.filelist" file in project folder you've mentioned few posts ago, but I don't know what to do with it.Those names arn't wrong, you get those names if the name is unknown. The file lists are automatically used by Unpack but they need to be in the correct location ("projects" directory must be in the same directory Gibbed.DeusEx3.Unpack.exe is in)
## Post #243
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-08-29T23:10:28+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> JPulowski wrote:00A13F5D.drm
0D0E2E08.mus
01BE62D9.sam

For instance. I've found "bigfile.filelist" file in project folder you've mentioned few posts ago, but I don't know what to do with it.Those names arn't wrong, you get those names if the name is unknown. The file lists are automatically used by Unpack but they need to be in the correct location ("projects" directory must be in the same directory Gibbed.DeusEx3.Unpack.exe is in)
Okay, thanks made it, works perfectly. Also have one more question, I've updated repository and there is a new folder called "Gibbed.DeusEx3.DRMDecompress" I've built solution, but looks like it doesn't work. Is it WIP?
## Post #244
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-29T23:26:31+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from JPulowski
>
> Okay, thanks made it, works perfectly. Also have one more question, I've updated repository and there is a new folder called "Gibbed.DeusEx3.DRMDecompress" I've built solution, but looks like it doesn't work. Is it WIP?
> deusex3: rick * r24 Gibbed.DeusEx3.DRMDecompress/Program.cs: Remove overwrite files option from DRMDecompress.
## Post #245
- Username: Lygatt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 26, 2011 9:22 pm
- Post datetime: 2011-08-29T23:32:12+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> I wrote a tool to demux .mul files, it's available on my repository as Gibbed.DeusEx3.Demux.

Supports both PC and PS3 .mul files. X360 is totally untested.

I've hardcoded a list of valid sample rates which may be incomplete so it will crash if it gets something unexpected.

Also: for fsb_mpeg, the correct padding value seems to be 24 (at least for music FSBs).

ie, Code: Select allfsb_mpeg.exe dx1theme2000_0.fsb -p 24

Thank you Rick for the demux and the padding value, is it too much to ask you how you determine it.
## Post #246
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-29T23:44:19+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Lygatt
>
> Thank you Rick for the demux and the padding value, is it too much to ask you how you determine it.I guessed various ones until I got one that didn't lose sync.
## Post #247
- Username: Supremespeed
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 15, 2011 2:37 am
- Post datetime: 2011-08-30T00:59:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

*nevermind*
## Post #248
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-30T01:02:08+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Checkout / export the repository using a SVN client and you will get all of the code properly.
## Post #249
- Username: Supremespeed
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 15, 2011 2:37 am
- Post datetime: 2011-08-30T01:03:34+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> Checkout / export the repository using a SVN client and you will get all of the code properly.

Yeah I just realized my problem, heh it didn't acquire the entire repo. Thanks. Build success.

*EDIT* 

Trying to locate the sounds effects for things like PDA, menu interface and key clicks. So far I don't think they are .mul files.

*EDIT2*

Ok seems sound effects are located inside the .drm files with their respective devices. Shotguns sounds, textures and animations bundled in weapon_shotgun_equip.drm for example. Now I need to figure out how to extract the sounds from the .drm, I used DRMEdit but it looks like I can't get them to convert as a MUL or FSB.
## Post #250
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-30T04:36:04+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Herdell
>
> mnn wrote:Herdell: Look back, I've posted where are fonts located. The format (at least for me) is a mystery.

I know about the fonts, and is *.dds files (Direct Draw)


I wanna know if there's a way to increase the size of displaying text in-game.

Hi mate,

where did u get it from. What is the file name please in X360 version and location?

Thank you
## Post #251
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-30T05:18:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Supremespeed
>
> Ok seems sound effects are located inside the .drm files with their respective devices. Shotguns sounds, textures and animations bundled in weapon_shotgun_equip.drm for example. Now I need to figure out how to extract the sounds from the .drm, I used DRMEdit but it looks like I can't get them to convert as a MUL or FSB.Save the raw Wave data as a file then delete the first 16 bytes, should work as an FSB then.
## Post #252
- Username: bluetrain
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 29, 2011 6:04 pm
- Post datetime: 2011-08-30T05:40:57+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> *.cpk should be *.usm (I incorrectly labeled that file type). They can be "converted" with VGMToolbox (VGMToolbox → Misc. Tools → Stream Tools → Video Demultiplexer, change format to USM (CRI Movie 2)).

I followed your steps. Got the video. However it comes out an orange, yellow and red mess. I'm not sure why. Does anyone else get this?
## Post #253
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-08-30T09:03:34+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> rengareng wrote:could not compile. gives 
 error  : Unable to read the project file 'Gibbed.Squish.csproj'. 
The project file could not be loaded: Gibbed.Squish.csproj'.
I am using TortoiseSVNI forgot to commit the new externals, I just fixed that. Update and try again.
here is compiled [revision 25](http://www.mediafire.com/?5jub1d889e30652). I could not find font filename, is anyone figured it out?
## Post #254
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-30T12:18:32+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Anyone found the fonts filename and location of the file ?
## Post #255
- Username: skyus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 03, 2010 3:27 pm
- Post datetime: 2011-08-30T13:13:14+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

rengareng: thanks man!
## Post #256
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-08-31T04:43:58+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

SO anyone please found the fonts for x360 or PS3? I mean name and size ? thx
## Post #257
- Username: opticalsnare
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 27, 2011 11:38 pm
- Post datetime: 2011-08-31T14:53:19+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hey guys wanted to know if its possible to pack things back in. Ive managed to get the files unpacked from the bigfiles and loaded up some files in the DRM editor like textures and sounds, but is there a way to get the files back into the DRM package as the saveDRM is N/A
## Post #258
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-31T16:23:01+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

DRM files are complicated and I am the only one researching it. DRMEdit is not meant for anyone to be using it yet.
## Post #259
- Username: Weatherproof
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 01, 2011 9:25 am
- Post datetime: 2011-09-01T01:51:13+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hey all, I'm new but I've been following this thread.
First of all, thanks and props to Rick for all the code. The unpacker and demuxer are just what i was looking for!

So i'm trying to extract all the music from the game. After unpacking, you get a bunch of .mul files which you can run through the demuxer to get a bunch of .fsb files per .mul file.  
By using the fsb_mpeg tool, you can then get .mp3 files from the .fsb files. However, they are all mono channel, and need to be combined (I'm using Audacity but I don't know of a quicker program for just slapping left and right audio channels together into one file)
Not all the .mul files are able to be broken into .fsb files though (at this time).
For example: (i'm picking two random .mul files from the _UNKNOWN directory using Rick's current Unpack build)
D7109F0E.mul is 7883  kB and splits into 6 .fsb files (left and right fils for Ambient, Stress, and Combat situations)
By using fsb_mpeg, you have to input each of the .fsb file names (D7109F0E_0.fsb, D7109F0E_1.fsb, ect.) So you input six files, but you only wind up with 3 mp3 files!? fsb_mpeg will call the left and right channels the same filename when they are run, ugh. So i've been renaming one of the files manually and then combining them in audacity.

Another quick thing,
78435123.mul is 24991 kB but won't even run through Rick's demuxer, it will just crash.

Maybe me and/or somebody else could just write a script program that does the entire directory of .mul's, runs them through the fsb_mpeg tool (with separate filenames for left and right channel), and somehow combines the two into one audio file.

I hope this helps to clear up some .mul (music file) questions people have had on the thread! There's still a crapload of stuff for me to learn about audio for this game as well!
## Post #260
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-01T06:28:52+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Weatherproof
>
> Another quick thing,
78435123.mul is 24991 kB but won't even run through Rick's demuxer, it will just crash.
> deusex3: rick * r27 Gibbed.DeusEx3.Demux/ (Program.cs SoundStreamHeader.cs): Demux now properly supports .mul files that have cinematic and subtitle sections. Currently this data is ignored.
## Post #261
- Username: Weatherproof
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 01, 2011 9:25 am
- Post datetime: 2011-09-02T02:05:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I wrote a quick tool today that put all the .mul files in a directory through Rick's Demuxer, another tool that runs the .fsb's through the fsb_mpeg tool, and rewrote the fsb_mpeg tool to output the filenames different for this case where every even numbered .fsb is a left channel and odd numbered are the right channel.

I haven't combined the channels of the mp3's yet, but I put all the extracted audio in a .zip file.
I put it on Dropbox, the address for it is [http://db.tt/iRCcj4j](http://db.tt/iRCcj4j)
It's all the audio from DeusEx (or at least all the audio that the demuxer got  ) so it includes music, as well as augmentation soundfx and human grunting-damage sounds.

Enjoy!
## Post #262
- Username: JC Denton
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 02, 2011 2:26 pm
- Post datetime: 2011-09-02T06:30:45+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

If any of you can figure out how to extract the game dialogue, I can die happy.
## Post #263
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-09-02T07:12:12+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

You mean the subtitles/menu?
## Post #264
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-09-02T09:25:42+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I think the game have "not enough" blood and i think someone can make it.   

Soo.

Can some one prog/build an unpacker/packer for make NEW BIGFILE.0xx.
## Post #265
- Username: helifax
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 03, 2011 7:28 am
- Post datetime: 2011-09-02T23:32:21+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi Rick!!

Awesome tool!!! but I am wondering are you planning to finish the DRM Editor? basically what I want is to load my own texture and save it as a DRM file;)) I saw all the options are properly layed out (even if disabled atm). So I do believe you will add them later? The sooner the better;))

I don't want to sound selfish or anything..so it is up to you to decide when this should come;))

Anyway thanks again for this awesome tool!!!!
## Post #266
- Username: Groenbaek
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 02, 2011 11:39 pm
- Post datetime: 2011-09-03T17:07:03+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> http://svn.gib.me/public/deusex3/

Pack code is untested.

I've been following this thread closely for a while now, hopeing for a quick BMS tool or something simmerler (All I've ever worked/have experience with). I'm a nobe (obviosly) and can´t figure out how to use the "code" generosly provided by Rick.
I have downloaded Visual studio 2010 Express, but have no clue how to use it... Can some one please make a tutorial or something?

Thanks;)
## Post #267
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-03T18:27:17+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

[http://tortoisesvn.net/downloads.html](http://tortoisesvn.net/downloads.html)
download it from here. 
then make a new folder and click right and select checkout similar thing then enter that svn.gib.me\publlic\deusex3 fetch all child including external ones. then open .sln file with visual studio and build it.
## Post #268
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-03T18:43:07+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

[https://twitter.com/#!/dominictarason/s ... 0277101568](https://twitter.com/#!/dominictarason/status/110053490277101568)
## Post #269
- Username: Acleacius
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 04, 2011 4:29 am
- Post datetime: 2011-09-03T20:40:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Registered to say thanks for your work Rick.  

Also downloaded from the twitter link, it's a patch0.000 file with no instructions/pathing. Do we just drop this in the main install directory and hit ~ while in game as in a normal console activation or possibly a link to instructions. Actually I'm not registered on twitter, so if it's required a link to a possible alternative, if it isn't too much trouble. 

Do we need your compiler/decompiler to unpack the sound files? Something that really annoys me is we can't Turn Off (or shoot :p  ) the radio. It's painful to have to listen to that guy.      I was hoping it was possible to make a blank sound file then put it in the proper directory structure and the game would read it directly out of the folder instead of the pack file, as many games.

Thanks for any help.
## Post #270
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-03T20:44:34+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Acleacius
>
> Also downloaded from the twitter link, it's a patch0.000 file with no instructions/pathing. Do we just drop this in the main install directory and hit ~ while in game as in a normal console activation or possibly a link to instructions. Actually I'm not registered on twitter, so if it's required a link to a possible alternative, if it isn't too much trouble.Better instructions here: [http://forums.eidosgames.com/showthread.php?t=121245](http://forums.eidosgames.com/showthread.php?t=121245)

> Reply from Acleacius
>
> Do we need your compiler/decompiler to unpack the sound files? Something that really annoys me is we can't Turn Off (or shoot :p  ) the radio. It's painful to have to listen to that guy.      I was hoping it was possible to make a blank sound file then put it in the proper directory structure and the game would read it directly out of the folder instead of the pack file, as many games.

Thanks for any help.Yes, though I've no idea about modifying sounds or plans to. Good luck.
## Post #271
- Username: Acleacius
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 04, 2011 4:29 am
- Post datetime: 2011-09-03T23:49:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Thanks for the link and reply, Rick.

I tried to followed your link, there seems to be only source, unless I didn't find the right path. I'm mostly a n00b, so apologizes if this is a dumb question. Is it possible there is a exe version or some instructions on how to use .cs?

Thanks again for any help.
## Post #272
- Username: Groenbaek
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 02, 2011 11:39 pm
- Post datetime: 2011-09-04T06:29:19+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Acleacius
>
> Thanks for the link and reply, Rick.

I tried to followed your link, there seems to be only source, unless I didn't find the right path. I'm mostly a n00b, so apologizes if this is a dumb question. Is it possible there is a exe version or some instructions on how to use .cs?

Thanks again for any help.

Me too... I'm kinda lost...
## Post #273
- Username: helifax
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 03, 2011 7:28 am
- Post datetime: 2011-09-04T14:05:11+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi Rick!

Any news about the DRMEditor? Basically I am trying to replace a texture..in order to remove those dams blooms/glows around the lamp posts. I find them very un-natural. I managed to find the textures, extract them but how can I load them and save the new DRM file?

Thank you in advance!

Best regards,
Helifax
## Post #274
- Username: TobyDG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 04, 2011 8:34 am
- Post datetime: 2011-09-04T19:19:08+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Thanks for the tools Rick. I am using them now trying to find the weapon stats, the silent rifle is way too weak.
The DRMeditor will help this out alot.
## Post #275
- Username: Weatherproof
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 01, 2011 9:25 am
- Post datetime: 2011-09-05T02:19:07+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hey dudes, quick tutorial to run Rick's tools for ya:
Protip, use google if you're lost

1. Download and install c# express
2. Download and install SlikSvn (I used the command line version)
3. Make a new directory where you want the repository to be downloaded from
4. Open up the command window, navigate to that directory and type in "svn checkout [http://svn.gib.me/public/deusex3/](http://svn.gib.me/public/deusex3/)
5. Once the files are finished downloading, go to the 'trunk' directory inside and open up Human Revolution.sln with c# express
6. Either press F6 or goto Debug>Build Solution
7. Your .exe's are now built (ex: goto trunk/gibbed.deusex3.unpack/bin/release/ to see the .exe for Rick's unpacker

Hope this helps
## Post #276
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-05T02:51:14+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Weatherproof
>
> 7. Your .exe's are now built (ex: goto trunk/gibbed.deusex3.unpack/bin/release/ to see the .exe for Rick's unpackerMake sure you are building in Debug (not Release), in those mode, the executables will output to 'bin' (this directory has a 'projects' directory).
## Post #277
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2011-09-05T03:23:30+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Can’t seem to find anything that extracts the USM videos properly, usm_deinterleave does not work and vgmtoolbox exports a mess of an m2v file.
## Post #278
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-09-05T05:26:52+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi Rick is there any news about drm repack ?
## Post #279
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2011-09-05T15:52:38+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hey Rick,

Is there any way to bulk extract all items from DRM files (such as DDS textures), rather than having to look through everything with the basic interface of DRMEdit?

Apologies if this already came up, or if I missed this feature somehow - would much appreciate being able to do this.

Oh, and Weatherproof - thank you!
## Post #280
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-05T23:17:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi Rick,
Can you add A8 - 8bit texture format to PCD9File file class. Because, font file uses this format. And if I try to open somefiles with DRMedit program it gives NotSupportedException.
Thanks for your great effort to code this awesome repository.
## Post #281
- Username: RioTiZ
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 06, 2011 6:27 pm
- Post datetime: 2011-09-06T10:50:39+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hello, where can i find HUD Map texture?
## Post #282
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-09-06T11:27:02+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from rengareng
>
> Hi Rick,
Can you add A8 - 8bit texture format to PCD9File file class. Because, font file uses this format. And if I try to open somefiles with DRMedit program it gives NotSupportedException.
Thanks for your great effort to code this awesome repository.

Where did you find the font file, and what is the name of the file?
## Post #283
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-09-06T12:58:02+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from evin
>
> rengareng wrote:Hi Rick,
Can you add A8 - 8bit texture format to PCD9File file class. Because, font file uses this format. And if I try to open somefiles with DRMedit program it gives NotSupportedException.
Thanks for your great effort to code this awesome repository.

Where did you find the font file, and what is the name of the file?

Yes how did u identify the file, is it for X360 or PC?
## Post #284
- Username: zerze
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 06, 2011 9:19 pm
- Post datetime: 2011-09-06T13:23:03+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Weatherproof
>
> Hey dudes, quick tutorial to run Rick's tools for ya:
Protip, use google if you're lost

1. Download and install c# express
2. Download and install SlikSvn (I used the command line version)
3. Make a new directory where you want the repository to be downloaded from
4. Open up the command window, navigate to that directory and type in "svn checkout http://svn.gib.me/public/deusex3/
5. Once the files are finished downloading, go to the 'trunk' directory inside and open up Human Revolution.sln with c# express
6. Either press F6 or goto Debug>Build Solution
7. Your .exe's are now built (ex: goto trunk/gibbed.deusex3.unpack/bin/release/ to see the .exe for Rick's unpacker

Hope this helps
What version ? Link plz Express 2010 and Basic 2010 doesn't work.
## Post #285
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-09-06T13:42:16+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Always the latest, of course: [http://www.microsoft.com/visualstudio/e ... rp-express](http://www.microsoft.com/visualstudio/en-us/products/2010-editions/visual-csharp-express)
## Post #286
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-06T13:44:34+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from michalss
>
> Hi Rick is there any news about drm repack ?Work in progress. No ETA.

> Reply from relight
>
> Hey Rick,

Is there any way to bulk extract all items from DRM files (such as DDS textures), rather than having to look through everything with the basic interface of DRMEdit?

Apologies if this already came up, or if I missed this feature somehow - would much appreciate being able to do this.

Oh, and Weatherproof - thank you!I can probably whip something up, I will see.

> Reply from rengareng
>
> Hi Rick,
Can you add A8 - 8bit texture format to PCD9File file class. Because, font file uses this format. And if I try to open somefiles with DRMedit program it gives NotSupportedException.
Thanks for your great effort to code this awesome repository.Can you mention what files have A8 textures, and what files are causing crashes?

Hash or file name is fine.
## Post #287
- Username: zerze
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 06, 2011 9:19 pm
- Post datetime: 2011-09-06T14:12:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from evin
>
> Always the latest, of course: http://www.microsoft.com/visualstudio/e ... rp-express

Ok this is actually extracting .UNKNOWN files, what are we supposed to do with that ? Waiting for a realese of something able do extract real unpacked files, like .TGA, .OGG... ?
## Post #288
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-06T14:25:15+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #289
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-06T16:58:54+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

howdy, so in my ignorance i'll ask you experts here, i want to mod object statistics like, maybe a candbar, a beer, etc, like adding health to it or maybe changing the assault rifle stats, augmentation statistics as well.  How would I go about doing this?  I try to extract the bigfile.000 but it comes up with an error saying:  unhandled exception, system.io.pathtoolongexception... the specified path... or both are too long.  I do however have many files extracted, it stops more than half way through extraction.  I looked at the files with the drm edit but i see a bunch of numbers and symbols... hah.  Regardless, thanks Rick for putting up the debug mod!  Also the rest of you modders keep at it because maybe someone will enjoy your modding some day if you share... thnx
## Post #290
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2011-09-07T01:21:23+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Rick - thanks, that would be really useful, since as mentioned in some cases there is a .drm file with MANY files in it, and DRMEdit sort is by order, not by type, which means I have to go through a lot of files to find only textures for example. Would be super useful just to extract everything in original format (such as DDS) from DRM, perhaps contents of each DRM file would be put into a folder named with the name of the DRM file, and then I can sort / deal with it after that. Sorry, I don't know enough programming to edit your excellent tools to accomplish these functions myself  You rock 

> Reply from RioTiZ
>
> Hello, where can i find HUD Map texture?
My guess is that this is flash / vector, not a texture, this means you cannot extract it as a texture.

Did anyone find the skydome backgrounds yet? All I found is sky skydomes, not all the scenes with buildings and everything (where those backgrounds aren't 3D models, there are a number of background textures throughout the game).
## Post #291
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2011-09-07T01:23:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from abadjpyo
>
> I try to extract the bigfile.000 but it comes up with an error saying:  unhandled exception, system.io.pathtoolongexception... the specified path... or both are too long.  I do however have many files extracted, it stops more than half way through extraction.
When you're extracting, do so in a path as close to your root as possible. So copy all the bigfiles and the extraction program into X:\EXTRACT or whatever - choose a short name - and then extract in that directory. The problem occuring is that you're running into length limits of the directory / file tree.
## Post #292
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-07T02:05:43+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from relight
>
> Rick - thanks, that would be really useful, since as mentioned in some cases there is a .drm file with MANY files in it, and DRMEdit sort is by order, not by type, which means I have to go through a lot of files to find only textures for example. Would be super useful just to extract everything in original format (such as DDS) from DRM, perhaps contents of each DRM file would be put into a folder named with the name of the DRM file, and then I can sort / deal with it after that. Sorry, I don't know enough programming to edit your excellent tools to accomplish these functions myself  You rockDRM isn't a conventional archive but a resource blob containing many resources referred to by ID and interlinking pointer references, which is why there isn't an unpacker currently.
## Post #293
- Username: t2ntransg
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 07, 2011 7:45 pm
- Post datetime: 2011-09-07T12:06:38+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

How to edit local.bin file?
## Post #294
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-07T16:19:31+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

thnx relight!    however i'm still stumped as to how to edit information like the beer can.drm file and stuff like that.  When i open it under drmedit, i see a bunch of code which i don't understand.
## Post #295
- Username: TobyDG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 04, 2011 8:34 am
- Post datetime: 2011-09-07T17:07:10+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from abadjpyo
>
> thnx relight!    however i'm still stumped as to how to edit information like the beer can.drm file and stuff like that.  When i open it under drmedit, i see a bunch of code which i don't understand.

First you are going to have to locate where the stats for these items are stored. Once you do that then you will have to use and hex editor ( I use HxD) to find the right byte to change it. I have also been looking for these stats. Right now I am looking in the pickup.drm and in the BigFile extracted the weapon.drm , but so far no luck. I am somewhat new to hex editing as all I have done before was find hidden moves for smackdown vs raw series. Learning the basic of Hex Editing will help you out abadjpyo.
## Post #296
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-07T19:01:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

mighty obliged Toby, i'm new to this too, so whatever the case thanx and good luck in transforming the game way you want it to be played, if anyone finds this information let us know don't keep that knowledge to yourselves  peace
## Post #297
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-08T13:39:27+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hex editing is a combination of knowing what you're looking for, and knowing how to change it.   Here's an example from the Combat Rifle Ammo's item pickup entry.

The red section I've outlined is the item's dimensions - in this case, it's 2 grid by 1 grid.  The blue section is it's stack size, and is 50 items per stack for the combat rifle ammo.

There's generally speaking two kinds of entry in a hex editing scenario - either you're changing a value (the stack size or item dimensions, in this case), or you're enabling/disabling a flag, such as whether or not an attribute is active or not.  If you're changing a value, then you just need to know the hex value of your normal decimal value - say you're changing the stack size for combat rifle ammo to 500 per stack, then you need to take 500, and turn it into a hex value - the easiest way to do this is to open your trusty windows calculator, pull down the "View" menu, and switch it to programmer mode, enter 500 as your value, and hit the "Hex" radio button - this tells you that 500 in decimal is equal to 1F4 in hex.

Here comes the only tricky bit - some games have the bits switched - 1F4 on your calculator will be backwards and not enough digits for the game, so you have to "pad" the entry with extra zeroes (to make it the right number of digits), and then put it in backwards to get it read properly - first we reverse it, and type it out in batches of 2 - "F4 1", and then pad the extra zeroes "F4 01". Now you just go back to your file and replace the "32 00" to "F4 01".

The other kind of entry is a flag - and those are easy, it's just a 01 or a 00 - 1 is on, 0 is off.  The only hard part for that is figuring out which of the 0's and 1's is your flag 

That brings us to finding the data in the first place - for that, you mostly just have to practice, and you have to think like a program (or programmer).  You'll usually find item data in one of two places - either the item has it's own file (like our combat rifle ammo example), or there's a master database with all of that information in it.  Sometimes, as is the case with DX:HR, it's both - in DXHR we have our individual file entries, but they're enclosed in a container file (the pickup_database.drm file).

So far from looking at all of the pickup items, it looks like the first 255 bytes of the file are pertinent information for the item, the remainder of the file is the icon path.  It's up to us to figure out what that pertinent information actually is 



ammo_combatrifleAmmo.png (46.01 KiB) Viewed 137 times
## Post #298
- Username: zerze
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 06, 2011 9:19 pm
- Post datetime: 2011-09-08T15:01:55+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zerze
>
> evin wrote:Always the latest, of course: http://www.microsoft.com/visualstudio/e ... rp-express

Ok this is actually extracting .UNKNOWN files, what are we supposed to do with that ? Waiting for a realese of something able do extract real unpacked files, like .TGA, .OGG... ?
## Post #299
- Username: Weatherproof
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 01, 2011 9:25 am
- Post datetime: 2011-09-08T16:23:06+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

props to lapdragon
## Post #300
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-08T16:28:49+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from zerze
>
> Ok this is actually extracting .UNKNOWN files, what are we supposed to do with that ? Waiting for a realese of something able do extract real unpacked files, like .TGA, .OGG... ?
Did you try using the RebuildFileLists utility?

I usually start with that after compiling a new copy of the unpacker.  Rebuild your file lists, then unpack - I recommend unpacking each "bigfile" to its own directory - it keeps a lot of the un-pathed files out of the main directory.

I don't believe we'll ever get the ability to unpack "real" files directly, because of the way that the game is packed by the developers, at most it will be a 2-step process.  We'll have to unpack the DRM files with Rick's unpack utility here, and then once he gets the formats figured out to a point he is comfortable with, he may release a DRM unpacker that can break a .DRM file into it's component parts.
## Post #301
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-08T17:14:49+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I've broken down the weapon files a bit more and pulled out some data - here's what I know.
Colors reflect their highlighted locations in the file - the ID number I've used is the hex bit in question.

01 02.) in base game? (flag yes/no - DLC items are all 0)
25 26.) Item inventory dimensions (first byte is width, second is height)
29 2A.) item max stack size
2D.) Whether item is upgraded (there's a weapon file for each weapon and also one for it's specialized upgrade type - flechette, exploding, armor-piercing, etc)
31 32.) Item Type (values between 0 and A so far)
 0 - quest items
 1 - unknown
 2 - unknown
 3 - weapons
 4 - grenades / mines / AUDs
 5 - weapon upgrades
 6 - claymore ammo (?)
 7 - Ammo
 8 - Painkillers, energy bars, alchohol
 9 - hack programs
 A - non-inventory pickups (credits, pocket secretaries, etc)

35.) Damage Upgrade pips on item card
36.) base Damage pips on item card
37.) Ammo Capacity Upgrade pips on item card
38.) base Ammo Capacity pips on item card
39.) Rate of Fire Upgrade pips on item card
3A.) base Rate of Fire pips on item card
3B.) Reload Speed Upgrade pips on item card
3C.) base Reload Speed pips on item card
3D.) Can take laser sight? (flag yes/no)
3E.) Can take silencer? (flag yes/no)
55 56.) Clip Size
69 6A.) Price from vendors
7D.) Not sure - it appears to be related to pickup amounts.

The green section is the texture paths.


From digging through this information, it appears that there's not a solid "damage" number for each weapon - that being the case, I think it's more likely that we've got a base damage per round for the ammo, with multipliers being applied on the fly based on the base weapon stats and upgrades added to the weapon - so the combat rifle would do X*(2 + upgrades) damage per bullet.  Now I've just got to figure out where X is in the tables.



wpn_combat_rifle.png (46.18 KiB) Viewed 227 times
## Post #302
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-08T17:24:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

wow good job lapdragon!
## Post #303
- Username: flib
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 09, 2011 8:01 am
- Post datetime: 2011-09-09T00:14:29+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Is there any way yet to extract videos from the game for out-of-game use?
## Post #304
- Username: TobyDG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 04, 2011 8:34 am
- Post datetime: 2011-09-09T01:13:09+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Wow , thanks Lapdragon. I am gonna do some more looking later on tonight. With this info maybe we can find the changes. So theoretically could we miss and match mods ? Like giving the sniper rifle a silencer mod and armor piercing bullets. Gonna have some fun trying to figure these things out. Thanks once again.
## Post #305
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2011-09-09T01:28:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Flib- you can use vgmtoolbox to extract the audio and video from the usm’s but the video looks like crap don’t know what to do about that.
## Post #306
- Username: TobyDG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 04, 2011 8:34 am
- Post datetime: 2011-09-09T06:45:57+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Thanks so much dragon. I was able to put a silencer on a regular sniper rifle. The noise is still loud , but the enemies can not trace the sound like using a regular unmodded sniper rifle. Later I will try adding special mods to it to see if I can get them to work. I would like to try armor piercing bullets mod to it or the tracer. When you say     " base Damage pips on item card " What do you mean ? Does it mean amount of damage it adds when upgraded or or how many bars one upgrade offers ?
## Post #307
- Username: Acid
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 26, 2011 7:31 pm
- Post datetime: 2011-09-09T10:07:02+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

@ lapdragon

In your png image you show .dat files, which "big" files did you unpack to access .dat files ? Are you using the latest r30 build for this ?
## Post #308
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-09T10:47:43+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #309
- Username: Acid
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 26, 2011 7:31 pm
- Post datetime: 2011-09-09T11:33:10+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Strange, i only have 8 digit alpha numeric .drm files, none of them are specifically named.
## Post #310
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-09T13:35:01+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Acid
>
> Strange, i only have 8 digit alpha numeric .drm files, none of them are specifically named.

It sounds like you're not using an up-to-date file list.

Rebuild the file lists, and then re-extract the bigfile.000 - that's where all of the named .DRM files live.
## Post #311
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-09T13:42:16+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Rebuilding file lists isn't necessary if you have the lists already. All rebuild does is clean the file lists up.
## Post #312
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-09-09T14:55:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

any news about the Fonts ???
## Post #313
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-09-09T18:10:25+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Rick: How did you "extracted" filenames?
## Post #314
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-09T20:26:30+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

hey lapdragon or tobs, do you guys know how to put this information in game?  i used your information lapdragon, all solid and good, i used a hex editor and saved, buuut i don't know how to insert that new info into the game, i tried to put the directory folder bigfile_unpack from gibbeds tools into the pack program but it just looks at me with a blinking bar haha.  I guess i should pack it and replace the old bigfiles in the game directory but don't know how to... anyways i've been looking around and if anyone knows how to change nutrient bars to have health properties post it up because it would be useful for those who play without health regeneration... thnx and keep up the good work!  UPDATE!!!  the unpack works it just doesn't say anything in the black box command box so if you use it, don't get discouraged and stick with the process, you should see the bigfiles_unpack in a few minutes...
## Post #315
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-09T20:38:06+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from abadjpyo
>
> hey lapdragon or tobs, do you guys know how to put this information in game?  i used your information lapdragon, all solid and good, i used a hex editor and saved, buuut i don't know how to insert that new info into the game, i tried to put the directory folder bigfile_unpack from gibbeds tools into the pack program but it just looks at me with a blinking bar haha.  I guess i should pack it and replace the old bigfiles in the game directory but don't know how to... anyways i've been looking around and if anyone knows how to change nutrient bars to have health properties post it up because it would be useful for those who play without health regeneration... thnx and keep up the good work!Unpack bigfile, patch0 (Drag & drop onto Gibbed.DeusEx3.Unpack.exe)
If the file you want to modify is only in bigfile, copy it to the same layout in patch0, and modify the patch0's bigfile.xml to add the missing entry (use the entry for it in the bigfile's bigfile.xml).
Modify the file.
Drag & drop patch0_unpack onto Gibbed.DeusEx3.Pack.exe, it will create patch0_unpack.000.
Replace your patch0.000 in game directory with this file.
## Post #316
- Username: TobyDG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 04, 2011 8:34 am
- Post datetime: 2011-09-09T21:23:04+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Okay I have been playing around with it for a couple of hours and this is what I have discoverd :

1. Changing Stats does nothing. I put all stats to 10 like the rocket launcher and still nothing. Next I am going to try dropping the stats to 1 and have a gun upgraded using mods and see if that makes a difference.

2. Do not add a laser mod to the tranq or the double barrel shotgun it causes aiming problems.

3. Silencer can work on regular shotgun (so does laser mod) , standard sniper Rifle , and double barrel shotgun. When adding the silencer to the regular shotgun the sound becomes muffled, added to the double barrel the sound of the gun is completley gone , added to the regular sniper rifle the sound doesn't change , but works better than the silent sniper rifle as far as detection.

Still looking on how to add special mods to other guns , but no luck yet. I am comparing guns that share the same special mod and trying to see if they share a special byte. Though I still can't mod the stats further than cosmetically I am happy with the modded sniper rifle.

Edit : Next I am going to try dropping the stats to 1 and have a gun upgraded using mods and see if that makes a difference. This Worked.
## Post #317
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-09T22:59:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

thnx Rick n Tobs for the help, and Tob what do you mean modifying the base stats don't work?  the pips?  because I modified them and they show up as modified in game, for example, I put 4 damage on the combat rifle instead of 3 and the 4th bar is highlighted and works.  However I had to change the patch.000 file in order for that to work...
## Post #318
- Username: TobyDG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 04, 2011 8:34 am
- Post datetime: 2011-09-09T23:13:21+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from abadjpyo
>
> thnx Rick n Tobs for the help, and Tob what do you mean modifying the base stats don't work?  the pips?  because I modified them and they show up as modified in game, for example, I put 4 damage on the combat rifle instead of 3 and the 4th bar is highlighted and works.  However I had to change the patch.000 file in order for that to work...

I mean don't work as in going over the alloted pips on the stats bar. You can not go higher than 10, anything over that won't work. So for example if you want the double shotgun as a base stat to do more than 10 it can't. The pips will not show up and will be empty , but can not be upgraded. Staying between 1 - 10 pips works. I gave the silenced sniper rifle the byte of 06 04 and it made it stronger after upgrading it , but only to the 10th pip bar. (also it messed up the sound of the gun)
## Post #319
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-10T04:27:21+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from TobyDG
>
> Next I am going to try dropping the stats to 1 and have a gun upgraded using mods and see if that makes a difference. This Worked.

I messed around with the tranq rifle earlier when I was testing the numbers I was finding - it looks like you can change a weapon's stats (the number of pips), but the change doesn't appear to register in-game until you add a mod - I bumped the tranq up to 5 ammo pips with 5 ammo upgrade pips, but the gun didn't register that it could hold more than one round until I applied an upgrade - after that the ammo capacity went up to 36
## Post #320
- Username: Acid
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 26, 2011 7:31 pm
- Post datetime: 2011-09-10T08:24:00+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Has anyone managed to successfully unpack all or any of the big files, with there proper file names, without getting a "Unhandled Exception" ?

I ask because the unpacker i have acts like it cant handle the size of these particular files.
## Post #321
- Username: TobyDG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 04, 2011 8:34 am
- Post datetime: 2011-09-10T08:39:20+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Silenced Full Auto ( with option of single shot) laser sniper rifle is beyond awesome  . The gun borders on a cheat gun , but darn if it is not fun taking headshots and then turning the corner to unleash full auto hell. I am happy I got the gun I wanted. 

Now if we can only find out where augmentation files and stats are held. Also Lapdragon do you think it is possible to edit the damage upgrade mod to give more damage per upgrade. Instead of upping one pip it up about 3. I edit one byte on there and it became unusable. I think I might just have edited the wrong thing. Will Try again.
## Post #322
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-10T13:42:08+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

good job Tobs and Lapdragon!   hey Acid you should try to unpack the bigfiles with all the desired programs and folders inside the same folder...  In other words, create a folder or stick these files in the same folder, that is, put Rick's modding tools in the same folder as the bigfiles and drag the bigfile.000 into the unpacker file and it should extract automatically into a single new folder.  try that out.  (the key is unpacking in the same directory as the program unpacker itself... luck!
## Post #323
- Username: Acid
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 26, 2011 7:31 pm
- Post datetime: 2011-09-10T14:19:18+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Do you really need the games patch to use the tools ?
## Post #324
- Username: DeathPhoenix
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 03, 2010 3:36 am
- Post datetime: 2011-09-10T21:15:24+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Guys, do anyone know where to find Adam's textures? I mean in which bigfile

Thanks in advance
## Post #325
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-10T21:17:02+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Acid
>
> Do you really need the games patch to use the tools ?No, modifying the patch0 file just makes things much faster since you don't have to repack several GB of data.
## Post #326
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-11T02:15:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I know it may not be the best info provided but I just wanted to share with yall the information to modify healing properties on items!!!  It is good for playing without health regeneration...  This means that with these edits you can make candy bars heal you as well just like in the first deus ex while they heal energy as well.
Here it goes:  use  a hex editor program google it... 
next open up patch0.000 and edit with the hex editor... 
next MAKE SURE IT IS DISPLAYING HEX (in order to understand my info) go to view and make sure you have display as: hex
next on the fifth row (inclusive) up from the video\scaleform lines on all the pickup_objects, for example, beer can or stimpack or energy bar small, you name it, there will be 4 numbers on the row!
NOW:  for the stimpack for example (use ctrl-f and type stimpack) look at the fifth row up from its beginning line of video\scaleform, it will say 48 and 42 TWICE on the same row, this translates to 50 hitpoints gained, therefore simply change these values on any item you want, this applies for any other health data in that SAME ROW so if you want just 5 health points healed go ahead and copy and paste those values to the desired item...  thanks to tob lapdragon and rick for teaching and motivating me!
## Post #327
- Username: Acid
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 26, 2011 7:31 pm
- Post datetime: 2011-09-11T02:53:53+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> Acid wrote:Do you really need the games patch to use the tools ?No, modifying the patch0 file just makes things much faster since you don't have to repack several GB of data.
What i ment was, do you need the games first patch installed 1.0.622, or is the unpacker compatible with both versions ? I was trying to unpack files from a 1.0.618.8 version. I think that may have been what my problem was. 

I placed the projects folder inside the "deusex3\trunk\Gibbed.DeusEx3.Unpack\bin\Release" directory and the only file i can unpack with file names intact is the patch0.000 All other files i try i receive an error. I could paste the error if you would like to see it.
## Post #328
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-11T04:27:56+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Why aren't you updated to 1.0.622.0?
This is probably the path exception where it's crashing because the path is too long, unpack the file to a smaller initial directory (eg: X:\DXHR).
## Post #329
- Username: thattrunkmonkey
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 12, 2011 5:24 am
- Post datetime: 2011-09-11T21:31:24+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Alrighty, I signed up just for this.

So I don't have the time to look through the entire thread, and I need to know if "bigfile" and whatever is the right place to be looking for texture files/mouse icon/etc? 

I've been playing Human Revolution for two days already, and I love the look of EVERYTHING. I've been inspired to (attempt to)make a windows/linux theme that either looks exactly like HR's menus, or the "Exler" operating system in game. I absolutely have to make my computer look like the ones in Deus Ex: HR. 

So yeah, that's my question. Where can I find the texture files (for, let's say, the animated "screensaver" that's on all the computers, or the menus, or the mouse cursors. I'm not good at this kind of thing, at all, and I don't have the time to invest to learn.

So, any help?
## Post #330
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-11T22:08:27+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi folks!  I think I've discovered something very cool!  I of course prayed to God on each of my discoveries like the health modifier and stuff.  Well I have found out that in I THINK player globals whatever in the bigfile you can find the AUGMENTATIONS!!!  alright instead of using Ricks tools what I do is simply right click on BIGFILE (that is not bigfile .000 or 002) but rather the simply named bigfile (mine has a particular winrar icon for the file, it should be below the other bigfiles).  Alright there is everything there you need!  now in order to EDIT SPECIFIC AUGMENTATION UPGRADES, go search for the upgrades in your hex editor.  I open the file with a right click (the bigfile) and then I press ctrl-f to search and i put in upgrade or damage reduction.  I have found out that in damage reduction right above the video\scaleform beginnings of the damage reduction (dermal armor) upgrades are 4 important numbers!:  in the damage reduction version 3 upgrade it looks like this:  205 204 12 63 (THIS IS VIEWED IN DECIMAL) now I have found that tweaking the last number (63) higher to 255, when someone shoots you it says 000 health and you don't die, however if you go to 70 or so, you continually die easier, less armor.  I tried recently changing the number 63 to 60 and i lose health very slowly like snails pace, now changing the value to 61 is about 1 heath point per pistol shot and 62 is around 10 or 12 shots until you die which seems pretty balanced if you play without cover or health regeneration.  You should find every upgrade needed here and it is simple to change things mostly... just edit the values (keep the hex editor open with the file opened) and run deus ex, close and modify values, rinse and repeat until desired results are obtained!!!!!
UPDATE:  to continue to modify this value even more accurately, considering in decimal it does not let you go between the values of 62 and 63, considering going to a view which shows more numbers!!!  such as going to view, group by, words, or another setting and from there look at the value of 63 and choose a reasonable value between 62 and 63, for example in group by words, the value of 63 is 16,197 and so I recently chose 16,001 (MAKE SURE YOU DON'T INSERT THE COMMA LET THE PROGRAM DO THAT AUTOMATICALLY, FOR IF NOT IT WONT WORK!) and witch choosing 16,001 it is a number between 62 and 63 decimal, and closer to what i might want to balance the armor as!
## Post #331
- Username: TobyDG
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 04, 2011 8:34 am
- Post datetime: 2011-09-12T03:38:28+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Wow , you have been busy abadjpyo. Great job. I will start messing around with what you found after much needed school work and some more Dead Island time.
## Post #332
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-13T17:16:23+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

wutup guys.... i've been wondering does anyone know how to make it so that the silencer does not show up ingame (the texture) i don't like the way it looks and also I have original deus ex music which i like more than the human revolution track, i converted it to ogg but well, i'm lost as to how to put that in the game haha, anyone know?
thnx
## Post #333
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-13T19:26:17+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

howdy here with an update, its actually pretty easy changing the augmentations, remember edit with a hex editor the bigfile (the one with no numbers in the name) and look for the ACTUAL augmentation lines which usually have upgrade 1,2,3, depending on the augmentation if it has upgrades or not.  anywho... i was playing around with fortify, press ctrl-f and put fortify, first it comes up with the main augmentation, we dont want that so press f3 (next) and you should end up with the specific upgrades, put whatever you want (the version 1,2 or 3) and right above the video/scaleform part for version 3 you will see a 3 (viewed in DECIMAL!!! very important) it is about the fifth column from the left and on the last row, change that 3 to whatever you like, for example, 6, you will now have 6 for fortify at level 3 upgrade... cheers, very easy stuff
## Post #334
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-13T21:25:50+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from abadjpyo
>
> remember edit with a hex editor the bigfile (the one with no numbers in the name)

I'd be careful editing the main bigfile - if you mess something up, you can't roll back your changes and will end up having to re-download the whole bigfile.000 through Steam.

That's why we've been taking the specific files we need out of the bigfile and inserting them into the patch - if you mess something up, it's easier to restore a backup of the patch file.
## Post #335
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-13T23:01:00+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

wutup, hey for anyone scared of editing the bigfile, its simple, instead of messing with the patch which is much more time consuming ().  You simply edit the bigfile and press ctrl-f and you can easily find things, much faster than looking in the pc-w files and then putting them in a patch.  Here's the deal, its quite simple really, I've been doing it without any hassles:  SIMPLY MAKE A COPY OF THE ORIGINAL BIGFILE.  there you go, i've been doing it without a minor hitch, luck peoples. (also you can copy down what values you change and revert them as if nothing happened, you pick your choice).
## Post #336
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-13T23:12:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

One extra step of having to pack the patch0 is not time consuming. It's one drag&drop of a directory.
## Post #337
- Username: thattrunkmonkey
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 12, 2011 5:24 am
- Post datetime: 2011-09-13T23:56:29+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

So does anyone actually know where I could find the texture files/mouse cursors/images/ etc, or if it's even possible? I want to make an "Exler" operating system theme.
## Post #338
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-14T03:23:10+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from thattrunkmonkey
>
> So does anyone actually know where I could find the texture files/mouse cursors/images/ etc, or if it's even possible? I want to make an "Exler" operating system theme.

It's probably not going to be as simple as you're hoping - almost all of the textures are stored inside the .DRM container file that is the master to whatever element that the texture you want is a sub-element of.

You'll have to use the unpack tool to rip apart the bigfile.000, and then you can use the DRMEdit tool to look inside the DRM container files to find the textures that you want.  I'll see if I can find the UI DRM files - I've got to unpack the game again first tho
## Post #339
- Username: thattrunkmonkey
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 12, 2011 5:24 am
- Post datetime: 2011-09-14T05:57:25+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from lapdragon
>
> thattrunkmonkey wrote:So does anyone actually know where I could find the texture files/mouse cursors/images/ etc, or if it's even possible? I want to make an "Exler" operating system theme.

It's probably not going to be as simple as you're hoping - almost all of the textures are stored inside the .DRM container file that is the master to whatever element that the texture you want is a sub-element of.

You'll have to use the unpack tool to rip apart the bigfile.000, and then you can use the DRMEdit tool to look inside the DRM container files to find the textures that you want.  I'll see if I can find the UI DRM files - I've got to unpack the game again first tho

It certainly wouldn't go unappreciated if you did that for me! I was just hoping for someone to point me in the right direction on how I would go about doing all these things. 

Now I just have to figure out why my Ubuntu install keeps crashing.
## Post #340
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-09-14T09:46:04+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> One extra step of having to pack the patch0 is not time consuming. It's one drag&drop of a directory.But you do need to modify bigfile.xml file, right? Otherwise the packer doesn't know about the new files in patch0.000 bigfile.
## Post #341
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-14T12:23:45+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> But you do need to modify bigfile.xml file, right? Otherwise the packer doesn't know about the new files in patch0.000 bigfile.Only once.
## Post #342
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-09-14T12:31:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #343
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-09-14T12:48:41+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> Only once.But, for each file you want to modify, right?
## Post #344
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-14T12:58:14+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> But, for each file you want to modify, right?Yes, if the file is not already a part of the patch0 archive.
## Post #345
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-14T19:13:08+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from abadjpyo
>
> wutup, hey for anyone scared of editing the bigfile, its simple, instead of messing with the patch which is much more time consuming ().  You simply edit the bigfile and press ctrl-f and you can easily find things, much faster than looking in the pc-w files and then putting them in a patch.  Here's the deal, its quite simple really, I've been doing it without any hassles:  SIMPLY MAKE A COPY OF THE ORIGINAL BIGFILE.  there you go, i've been doing it without a minor hitch, luck peoples. (also you can copy down what values you change and revert them as if nothing happened, you pick your choice).

The other advantage to using the patch0.000 is that you can share your work - nobody's going to want to download the massive bigfile.000 archives just to get at a mod.  If you pack it up into the patch, then you are more likely to get users.  Additionally (and especially for DXHR), when there's not a SDK for a game, we end up having to build custom mods, so you can distribute just the parts that you change, then a user can pack their own mods, so that you can have my inventory mod, along with somebody else's no-intro mod, and Rick's debug mod, along with your HP or aug mods all in one pack.

On top of that, if I wanted to use your mod specifically, I can't - I'm not willing to permanently mod my bigfile.000, and without knowing which DRM you modified I can't replicate it at my end in the patch0.000.

Do a little homework and unpack the archive, figure out what you're modifying specifically, and then other people would be more willing to enjoy your work.
## Post #346
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-14T19:25:07+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Rick - I had a small request...

Could you make it so that if you set DRM files to open with the DRM Editor, it actually opens the DRM, instead of just opening DRMEdit and waiting for you to select a file?

That would be brilliant
## Post #347
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-14T19:51:49+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from thattrunkmonkey
>
> It certainly wouldn't go unappreciated if you did that for me! I was just hoping for someone to point me in the right direction on how I would go about doing all these things.

I found some of the UI elements for you - If I find more, I'll update this post as I find them.

dedicated_terminal_b.drm
computer_securityhub.drm
computer_shopping_a.drm

There's some map elements in these:
det_city__masterunit.drm
det_fema_masterunit.drm
det_sam__masterunit.drm
det_sarifhq__masterunit.drm
pan__masterunit.drm
pic__masterunit.drm
sha_city__masterunit.drm
sha_tym__masterunit.drm
sin_omega__masterunit.drm

(more to come)
## Post #348
- Username: thattrunkmonkey
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 12, 2011 5:24 am
- Post datetime: 2011-09-14T23:31:08+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from lapdragon
>
> thattrunkmonkey wrote:It certainly wouldn't go unappreciated if you did that for me! I was just hoping for someone to point me in the right direction on how I would go about doing all these things. 


I found some of the UI elements for you - If I find more, I'll update this post as I find them.

dedicated_terminal_b.drm
computer_securityhub.drm
computer_shopping_a.drm

There's some map elements in these:
det_city__masterunit.drm
det_fema_masterunit.drm
det_sam__masterunit.drm
det_sarifhq__masterunit.drm
pan__masterunit.drm
pic__masterunit.drm
sha_city__masterunit.drm
sha_tym__masterunit.drm
sin_omega__masterunit.drm

(more to come)

That kicks ass!

But if you don't mind me asking, how do I actually get to those files?
## Post #349
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-15T03:59:53+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from lapdragon
>
> Rick - I had a small request...

Could you make it so that if you set DRM files to open with the DRM Editor, it actually opens the DRM, instead of just opening DRMEdit and waiting for you to select a file?

That would be brilliant
> Reply from Revision 35
>
> deusex3: rick * r35 /trunk/ (26 files in 11 dirs): 
deusex3: - Add DRMUnpack project.
deusex3: - DRMEdit now supports file names on the command-line for opening files.
deusex3: - Add DFEngine no_ads project.
## Post #350
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-15T14:01:40+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> deusex3: - DRMEdit now supports file names on the command-line for opening files.
Perfect - just what I was looking for 

> Reply from thattrunkmonkey
>
> 
That kicks ass!
But if you don't mind me asking, how do I actually get to those files?
use this:  [http://www.mediafire.com/?m3x9s7bx4lzmugu](http://www.mediafire.com/?m3x9s7bx4lzmugu)
Unpack it into the DXHR game directory - it should unpack into the root directly, you don't want it sitting in it's own subfolder.
Once it's unpacked, you just run "unpack.bat" and it does the rest.
Make sure to change the drive letter that the batch file outputs to - it's presently set to unpack everything to D:\DXHR_Unpack\ - if you don't have a D:\ drive, that might be a problem
## Post #351
- Username: Satan Claus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 16, 2011 1:16 am
- Post datetime: 2011-09-15T17:24:10+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

hello guys
anyone figured which file contains augmentation tree data?
## Post #352
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-15T18:15:25+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

hey satan claus, what up?  i sure wouldnt want any holiday gifts from you, anyways look back a few posts at one of my posts, just copy the bigfile without numbers and in one of the copies (the one in the game directory you choose to keep and edit) simply edit with a hex editor, press ctrl-f and type in augment or augmentation or the specific augmentation you wish to edit, play around with the numbers, and if something gets messed up simply copy down the values changed beforehand to return the old values or simply look at the copied bigfile or copy and paste it.  anywho, all you have to do is copy AND LEAVE OPEN THE HEX EDITOR SO IT IS FAST WITH THIS METHOD and keep opening the game and changing values until you find your desired change, i have written down a few like damage reduction and fortify hack... gluck
## Post #353
- Username: DDC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 16, 2011 3:53 am
- Post datetime: 2011-09-15T20:06:11+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hey guys. Please forgive my noobyness but I was wondering if any one had gotten any of the character models out of the game. I would realy like to import some of the characters into 3dsmax so that I can studie them in detail. I am a complete noob and havnt got a clue how to do this and I'm hoping that some one on here might be kind enough to help me out. I understand that the process may be to hard to explain to someone with no prior knowlage in this matter. If this is the case then could somebody point me in the direction of some tutorials or even set up a torrent of the models if they have already been extracted. Thanks in advance for any help.
## Post #354
- Username: Satan Claus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 16, 2011 1:16 am
- Post datetime: 2011-09-15T22:27:55+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from abadjpyo
>
> hey satan claus, what up?  i sure wouldnt want any holiday gifts from you, anyways look back a few posts at one of my posts, just copy the bigfile without numbers and in one of the copies (
Well i read your post already. its strange but i cant find any traces of fortify or another aug names inside bigfile. Would you kindly provide hex offset for that "fortify" you already find and try to edit?
## Post #355
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-09-15T22:43:41+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I need somebody who can explain me with what i can unpack the text files (menu, subtitles - all text files) and the textures.

Me and my translation team left the other games in the background and now we want to focus on this game. So, can anyone explain me how i can unpack the text files from the .000 archives and how to repack it again so the game can read the text normally.  

And my second question is: Where are the font files?

 

To Rick: I searched in your blog about your tools for the game but i don't find download link....
## Post #356
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-16T02:35:08+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Teryal5532
>
> To Rick: I searched in your blog about your tools for the game but i don't find download link....

That's because he's not providing a downloadable copy.  If you want a copy, then you have to either wait for one of us to post an updated copy of the binaries, or you have to compile a copy from the latest version of his SVN.

I personally recommend compiling your own copy - there's instructions on how to do so a few pages back.  Just look for the instructions that call for the use of SlikSVN - that's the method that I use and it works pretty well.

For those that can't handle compiling their own copy, here's a gimmie for today - rev38 all bundled up, with my unpacker batch file - remember to change the %output% variable if you don't want to use D:\DXHR_Unpack\

[http://www.mediafire.com/?zbkqkcyrgkil53z](http://www.mediafire.com/?zbkqkcyrgkil53z)
## Post #357
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-16T08:36:23+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Finally set up an automated build system,

[http://svn.gib.me/builds/deusex3/](http://svn.gib.me/builds/deusex3/)

Note that these are compiled with Mono but they should work under MS's .NET. If you have an issue with an automated build please let me know the revision and build number that you downloaded.
## Post #358
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-09-16T11:37:58+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I downloaded the tools and unpacked bigfile_English.000 but there are only .mul files and audio files.

I think that there are the text files, voices.. because when i delete bigfile_English.000 and leave bigfile_Russian.000, everything in the game is in Russian.

That's why i think that in this archive is everything (Voices, text files, textures...).
## Post #359
- Username: Eilarais
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 12, 2011 7:41 am
- Post datetime: 2011-09-16T18:24:08+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Can anyone confirm that .drm files can still be unpacked/decompressed/repacked into patch file after yesterday's update?
## Post #360
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-16T19:11:09+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Eilarais
>
> Can anyone confirm that .drm files can still be unpacked/decompressed/repacked into patch file after yesterday's update?No difference, why?
## Post #361
- Username: thattrunkmonkey
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 12, 2011 5:24 am
- Post datetime: 2011-09-16T20:51:23+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Alright, so I've unpacked everything, and I've really got to thank you for helping me with that.
Now, there's a different problem (it's probably just me). Most of the files are .drm files, and from what I've searched, .drm files are music files? How exactly are textures and stuff stored like that?
And how am I supposed to open them?
## Post #362
- Username: abadjpyo
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Sep 07, 2011 12:50 am
- Post datetime: 2011-09-16T22:01:53+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

wutup satanic claus!  anywho its real simple FIRST: make sure you hex edit the bigfile without the numbers (the 1.41 gb file!) the one that is not bigfile 000, 001 or 002, when in there simple find, ctrl f() and put fortify, etc.  the offset for fortify is :  41622560 on mine, it begins there, HOWEVER! in order to modify the upgrades you need to press F3 or next to go to the particular upgrades just press F3 and it will take you to:
SharedTextures\Icons\Augmentations\Upgrades\icon_hacking_fortify_level_1
for example!
## Post #363
- Username: Eilarais
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 12, 2011 7:41 am
- Post datetime: 2011-09-16T22:43:44+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> No difference, why?

Just wanted to be sure since it's on Steam and there's no going back once you've updated. I haven't heard of any plans to lock down the packfiles, but it's been known to happen.
## Post #364
- Username: Eilarais
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 12, 2011 7:41 am
- Post datetime: 2011-09-16T23:09:14+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

BTW, I found one minor thing: There's a time limit in the first mission where if you amble around the office long enough, the hostages will be killed in the warehouse. If you're a rabid completionist (like me) and this bugs you, the fix is in s_scn_det_sarif_industries_part01_det_sarif_industries.drm:

These offsets should be changed from 00 00 61 43 to 00 00 E1 44:
0xBE470
0xBE474
0xBE4B0
0xBE4B4

These offsets should be changed from 00 00 E1 43 to 00 00 61 45:
0xBE490
0xBE494
0xBE4D0
0xBE4D4
0xBE530
0xBE534

Offsets are for the compressed .drm file, no need to decompress it. If you don't see what you expect at that location, just search for float values of 225 and 450 and change them to 1800 and 3600.

Congratulations, you now have 2 hours of wandering around the office before being bothered!
## Post #365
- Username: Satan Claus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 16, 2011 1:16 am
- Post datetime: 2011-09-16T23:52:10+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from abadjpyo
>
> make sure you hex edit the bigfile without the numbers (the 1.41 gb file!) the one that is not bigfile 000, 001 or 002, when in there simple find, ctrl f() and put fortify, etc.  the offset for fortify is :  41622560 on mine, it begins there,
for example!
Hi! I find that string myself already, but it stored in bigfile.000 (globalplayerinfo.drm) for me   
But thank you for the point , always good to compare results. Now its a time to find proper values
## Post #366
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-09-17T00:54:06+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I lost my whole day to try to find the text files and the textures but i don't find nothing.

I will ask again ->

Where (in which archive) are the text files and where are the textures stored?



Thanks in advance.
## Post #367
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-17T01:04:10+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Text is in bigfile_Language, textures are in bigfile.
## Post #368
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-17T01:56:08+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from thattrunkmonkey
>
> Alright, so I've unpacked everything, and I've really got to thank you for helping me with that.
Now, there's a different problem (it's probably just me). Most of the files are .drm files, and from what I've searched, .drm files are music files? How exactly are textures and stuff stored like that?
And how am I supposed to open them?

In DXHR, the .drm files are "container" type files (sort of like a zipfile) - inside each DRM you'll find textures, scripts, and any other sort of information related to the item that the DRM is about.  The weapon_combatrifle_equip.drm, for example, has most of the textures, scripts, sounds, and other raw data for the combat rifle all stored in the one DRM file.
## Post #369
- Username: dynath
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 17, 2011 12:53 pm
- Post datetime: 2011-09-17T05:00:57+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

has anyone been able to load any of the DXHR models into a 3d program? DRMunpack exports them as BIN files and I'm wondering if anyone knows their format or how to open them?
## Post #370
- Username: thattrunkmonkey
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 12, 2011 5:24 am
- Post datetime: 2011-09-17T06:55:22+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from lapdragon
>
> thattrunkmonkey wrote:Alright, so I've unpacked everything, and I've really got to thank you for helping me with that.
Now, there's a different problem (it's probably just me). Most of the files are .drm files, and from what I've searched, .drm files are music files? How exactly are textures and stuff stored like that?
And how am I supposed to open them?

In DXHR, the .drm files are "container" type files (sort of like a zipfile) - inside each DRM you'll find textures, scripts, and any other sort of information related to the item that the DRM is about.  The weapon_combatrifle_equip.drm, for example, has most of the textures, scripts, sounds, and other raw data for the combat rifle all stored in the one DRM file.

Alright, I understand that now. So do I unzip them?
## Post #371
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-17T09:14:30+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from thattrunkmonkey
>
> Alright, I understand that now. So do I unzip them?

You can view all the bits inside them with DRMEdit, and then use DRMUnpack to "unzip" the ones you want.

Both tools are in the latest couple versions of Rick's DXHR tools.
## Post #372
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-09-17T10:33:33+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> Text is in bigfile_Language, textures are in bigfile.
Not quite true. Original language files are in bigfile_Language files. However, subsequent patches contains updated texts, so you should look into patchX.000. If you want to change them, modify the latest patch file (currently patch1.000)
## Post #373
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-09-17T10:58:04+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> Rick wrote:Text is in bigfile_Language, textures are in bigfile.
Not quite true. Original language files are in bigfile_Language files. However, subsequent patches contains updated texts, so you should look into patchX.000. If you want to change them, modify the latest patch file (currently patch1.000)

Thanks for the info but in the unpacked bigfile_English/Russian/French/Italian... there are only .mul files and audio files. There are no text files or i cannot find them.

I'm fan of the [Deus Ex] series and this is my favorite game and we with my team want to translate it (text + textures - maybe and the voices in future).
## Post #374
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-09-17T11:06:35+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Archives of Beta seems to differ from Release version?
## Post #375
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-09-17T11:35:11+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Teryal5532: There are texts. ID/hash is 0x7CD333D3.
## Post #376
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-09-17T11:46:38+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> Teryal5532: There are texts. ID/hash is 0x7CD333D3.

"mnn" i don't understand what do you mean with "ID/hash"

Sorry but i'm like a newbie noob
## Post #377
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-17T12:25:06+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> Teryal5532: There are texts. ID/hash is 0x7CD333D3.Why use hash? It's pc-w\local\locals.bin.
## Post #378
- Username: thattrunkmonkey
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 12, 2011 5:24 am
- Post datetime: 2011-09-17T21:48:33+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from lapdragon
>
> thattrunkmonkey wrote:Alright, I understand that now. So do I unzip them?

You can view all the bits inside them with DRMEdit, and then use DRMUnpack to "unzip" the ones you want.

Both tools are in the latest couple versions of Rick's DXHR tools.

I hate being so annoying, and you all have been a great help already, but where can I get his tools? I'm searching through the thread right now, and I checked Rick's blog, but I haven't found them yet.
## Post #379
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-09-17T22:08:09+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from thattrunkmonkey
>
> lapdragon wrote:thattrunkmonkey wrote:Alright, I understand that now. So do I unzip them?

You can view all the bits inside them with DRMEdit, and then use DRMUnpack to "unzip" the ones you want.

Both tools are in the latest couple versions of Rick's DXHR tools.

I hate being so annoying, and you all have been a great help already, but where can I get his tools? I'm searching through the thread right now, and I checked Rick's blog, but I haven't found them yet.

This link is taken from the Rick's post at page 23 - [http://svn.gib.me/builds/deusex3/](http://svn.gib.me/builds/deusex3/)

My problem is that i don't know how to unpack the text files from the .bin archive and i'm waiting if somebody can help me but i see that no one want to help me
## Post #380
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-09-17T23:46:03+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> Why use hash? It's pc-w\local\locals.bin.
Well, because my tools are not that "cool" - they don't use filenames...
## Post #381
- Username: Lazarus
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 28, 2010 11:00 am
- Post datetime: 2011-09-18T00:45:10+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Greetings All:

Yet another total "noob" here, perusing the 26 odd pages of this forum, attempting to determine exactly how ( in a coherent step by step fashion ) to accomplish the following using Gibbed's tools:

1:  Edit Adam Jensen's base ( i.e. non-augmented ) movement speed and jump height.

2:  Edit augmentation properties ( particularly the Cybernetic Leg Prosthesis sprint enhancement value - would like to double it).

3:  Edit weapon/weapon upgrade properties ( e.g. base damage, accuracy, etc.)

4:  Edit the maximum stack sizes of consumables ( e.g. painkillers ).

5:  Re-pack edited .drm files into the patch1.000 file mod that I'm already using.

Thus far, I've managed to at least partially unpack the bigfile.000 and located some of what appear to be the relevant weapon.drm files. I can't seem to locate anything on augmentations, however.  I've unpacked some of the .drm files ( e.g. weapon_tranquilizergun_ammo_world.drm ) using the Gibbed.DeusEx3.DRMUnpack.exe.  I've also tried simply viewing the .drm files using Gibbed.DeusEx3.DRMEdit.exe.  

I suspect that I'm supposed to directly edit the .drm files using the DRMEdit utility, correct?  If this is the case, which of the DTPData "strings" ( or whatever they're called ) should I be editing?  Since all of the data contained within the aforementioned "strings" is in hex, has anyone developed a "legend" for determining which bytes need to be changed?  I'm definitely feeling like the proverbial "chimpanzee trying to operate a starship" here.  Any assistance would be much appreciated.  Thanks!
## Post #382
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-18T02:47:42+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Lazarus
>
> 
1:  Edit Adam Jensen's base ( i.e. non-augmented ) movement speed and jump height.
2:  Edit augmentation properties ( particularly the Cybernetic Leg Prosthesis sprint enhancement value - would like to double it).

I've not really worked on the augmentations - one of the other guys in the thread has, but I don't know if he's willing to break down what he knows into patchable info - he keeps modifying the bigfile.000

> Reply from Lazarus
>
> 
3:  Edit weapon/weapon upgrade properties ( e.g. base damage, accuracy, etc.)
4:  Edit the maximum stack sizes of consumables ( e.g. painkillers ).

See the first post on page 21.

> Reply from Lazarus
>
> 
5:  Re-pack edited .drm files into the patch1.000 file mod that I'm already using.

See the last post on page 21 

> Reply from Lazarus
>
> 
Thus far, I've managed to at least partially unpack the bigfile.000 and located some of what appear to be the relevant weapon.drm files. I can't seem to locate anything on augmentations, however.  I've unpacked some of the .drm files ( e.g. weapon_tranquilizergun_ammo_world.drm ) using the Gibbed.DeusEx3.DRMUnpack.exe.  I've also tried simply viewing the .drm files using Gibbed.DeusEx3.DRMEdit.exe.  

I suspect that I'm supposed to directly edit the .drm files using the DRMEdit utility, correct?  If this is the case, which of the DTPData "strings" ( or whatever they're called ) should I be editing?  Since all of the data contained within the aforementioned "strings" is in hex, has anyone developed a "legend" for determining which bytes need to be changed?  I'm definitely feeling like the proverbial "chimpanzee trying to operate a starship" here.  Any assistance would be much appreciated.  Thanks!

The weapon and painkiller info isn't actually in the wpn_*.drm files - it's all in the pickup_database.drm.  Again (unfortunately), I'm not sure where the augmentation data is 

The DRM editor (at least last time I used it) is actually more of a DRM viewer - to actually edit them you need use a hex editor.  To identify which bytes to change, see that post I mentioned on page 21
## Post #383
- Username: thattrunkmonkey
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 12, 2011 5:24 am
- Post datetime: 2011-09-18T03:38:38+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Teryal5532
>
> thattrunkmonkey wrote:lapdragon wrote:

You can view all the bits inside them with DRMEdit, and then use DRMUnpack to "unzip" the ones you want.

Both tools are in the latest couple versions of Rick's DXHR tools.

I hate being so annoying, and you all have been a great help already, but where can I get his tools? I'm searching through the thread right now, and I checked Rick's blog, but I haven't found them yet.

This link is taken from the Rick's post at page 23 - http://svn.gib.me/builds/deusex3/

My problem is that i don't know how to unpack the text files from the .bin archive and i'm waiting if somebody can help me but i see that no one want to help me

Thanks a million. I can now unpack them! My new problem is that I have no idea how to open/view a .bin file.
## Post #384
- Username: Lazarus
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 28, 2010 11:00 am
- Post datetime: 2011-09-18T03:59:35+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> I've not really worked on the augmentations - one of the other guys in the thread has, but I don't know if he's willing to break down what he knows into patchable info - he keeps modifying the bigfile.000 Yes, I believe that was abadjpyo?

Lapdragon, I went ahead and downloaded your DXHR_Pickups.xlsx file, but unfortunately I don't have Excel installed, and the latest version of Excel Viewer I could find is 3 years old.  On a related topic, I can't seem to find the pickup_database.drm file you mentioned ( possibly because I was only partially successful in unpacking the bigfile.000 ).  

I tried unpacking it again, but the DeusEx3.Unpack.exe consistently crashes after unpacking 1.54 GB of the 2+ GB of data from the bigfile.000.  I then get the following error message:

> Gibbed.DeusEx3.Unpack has encountered a problem and needs to close. We are sorry for the inconvenience.  Clicking on the "What data does this error report contain?" link provides the following:

```
P3:  4e7309b2  P4:  mscorlib  P5:  4.0.0.0  P6:  4ba1da6f  P7:  3fe6
P8:  1f  P9:  system.io.pathtoolongexception
```


> Thanks a million. I can now unpack them! My new problem is that I have no idea how to open/view a .bin file.  Yeah, same issue here.

Finally, with regards to a hex editor, I've got Cheat Engine 5.5 installed, will that be compatible?
## Post #385
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-18T04:52:09+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Lazarus
>
> Yes, I believe that was abadjpyo?
Yup, that sounds right.

> Reply from Lazarus
>
> I tried unpacking it again, but the DeusEx3.Unpack.exe consistently crashes after unpacking 1.54 GB of the 2+ GB of data from the bigfile.000.  I then get the following error message: <snip>
Your output path is too long - try this command instead:
(remember to change the drive letter if you aren't unpacking to your D: drive.)

```
Gibbed.DeusEx3.Unpack.exe -o bigfile.000 d:\dxhr_unpack\bigfile
```


> Reply from Lazarus
>
> Yeah, same issue here.
Finally, with regards to a hex editor, I've got Cheat Engine 5.5 installed, will that be compatible?
I don't think that CE is an actual hex editor - I use EditPad Pro (although the free version probably works just as well).
## Post #386
- Username: Lazarus
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 28, 2010 11:00 am
- Post datetime: 2011-09-18T06:52:22+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from lapdragon
>
> Your output path is too long - try this command instead:
(remember to change the drive letter if you aren't unpacking to your D: drive.)
Code: Select allGibbed.DeusEx3.Unpack.exe -o bigfile.000 d:\dxhr_unpack\bigfileMan, here's where my "noobness" becomes glaringly apparent.    Do I enter the aforementioned command line into the Windows Command Prompt?  In my case, I've got Gibbed's editor installed in a folder on my desktop ( C: drive ).

I found EditPad Lite, the free version of EditPad Pro, but nothing in the release notes indicated anything about hex editing.
## Post #387
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-18T16:42:19+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Lazarus
>
> lapdragon wrote:Your output path is too long - try this command instead:
(remember to change the drive letter if you aren't unpacking to your D: drive.)
Code: Select allGibbed.DeusEx3.Unpack.exe -o bigfile.000 d:\dxhr_unpack\bigfile
Man, here's where my "noobness" becomes glaringly apparent.    Do I enter the aforementioned command line into the Windows Command Prompt?  In my case, I've got Gibbed's editor installed in a folder on my desktop ( C: drive ).

If you're comfortable with the command line environment, then you can certainly run it from one (I assumed you were, but if not it's no biggie), but it's probably easiest to just put that command into a batch file (make a new blank text file, put that line into it, and then save it as unpack.bat).  You also want to move it and the Gibbed tools package into your Deus Ex directory, so that you don't have any pathing wierdness.  Just dump all of the Gibbed files into the DXHR directory, sitting right alongside the bigfile.000 and the unpack.bat file that you're gonna make.  After that, it's just a simple matter of double-clicking the batch file and going to the kitchen for a sandwich (the full unpack will take probably 10-15 minutes).  If you want to unpack the whole game, you'll need 3 more lines - if you want to skip one of them (but still keep it in the batch file for future use), then put the word "rem" in front of the command you don't want, like I did for the third line below.  The following batch file is what I actually use to unpack the game.

```
Gibbed.DeusEx3.Unpack.exe -o bigfile.000 d:\dxhr_unpack\bigfile
rem Gibbed.DeusEx3.Unpack.exe -o bigfile_english.000 d:\dxhr_unpack\bigfile_english
Gibbed.DeusEx3.Unpack.exe -o patch0.000 d:\dxhr_unpack\patch0
Gibbed.DeusEx3.Unpack.exe -o patch1.000 d:\dxhr_unpack\patch1

```


> Reply from Lazarus
>
> I found EditPad Lite, the free version of EditPad Pro, but nothing in the release notes indicated anything about hex editing.

Good thing you checked - it turns out that Lite doesn't do hex editing (which is a shame).  Looks like you'll have to go with the demo version of EditPad Pro (it has all of the features, it just bugs you to buy when you open it, like WinZip does).

[http://www.editpadpro.com/download.html](http://www.editpadpro.com/download.html)
## Post #388
- Username: JohnBloggs
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 19, 2011 1:11 am
- Post datetime: 2011-09-18T17:30:33+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

hello all!
first of all, thank you very much for creating these extractiontools!
i read through most of the pages and i have two questions:
where is the pickup_database.drm? as far as i understood it contains the properties of all pickupobjects. i searched in the folders of the unpacked bigfile and patch0 aswell as with a hexeditor in the packed files and i couldnt find it.

how can i convert the textures toa useable format (and convert them back)? drmeditor can only export but not import them.
when i extract a drm with the unpacker, the header of the .bin files in the renderresourcefolder says "PCD9DXT1" which is supposedly a driectx compressed texture but if i rename the file to .dds its invalid.

about the interfacetextures:
there are a few in the globaloutershell.drm in patch0, mostly from the mainmenus and loadingscreen
generalbank.drm in patch0 contains the textures for the buttons on keypads.
globalscaleformdatabase.drm in patch0 contains textures for hudelements e.g. minimap and the ingamemenus for augmentation, objectives etc. but not the textures for the maps.
keypad_a.drm in bigfile contains the hacking iu-textures
## Post #389
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-18T17:56:34+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from JohnBloggs
>
> hello all!
Where is the pickup_database.drm? as far as i understood it contains the properties of all pickupobjects. i searched in the folders of the unpacked bigfile and patch0 aswell as with a hexeditor in the packed files and i couldnt find it.

It's in the root directory of bigfile.000's \default\pc-w\
If you're not getting filenames (only hashnumbers) then it's at hash A9F8A050
## Post #390
- Username: JohnBloggs
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 19, 2011 1:11 am
- Post datetime: 2011-09-18T18:06:29+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

thanks for the quick answer
its not there    all files have names, not hashes. the only file with a "pi" at the beginning in this folder is pirate_radio.drm.
im using the files from deusex3-r41_b17.zip for extraction, could this be the reason for the missing file?

did anybody find all of adams textures yet? all i could find are the normalmaps for him and the hairdiffusetexture in 
pc-w\object\characters\base\mesh\adam_jensen\art\textures
## Post #391
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-18T18:09:21+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from JohnBloggs
>
> its not there    all files have names, not hashes. the only file with a "pi" at the beginning in this folder is pirate_radio.drm

You're missing a LOT of files - I have 10 "pi" files (including pirate_radio.drm) in the root folder of my extract.
How many total files do you have in your extract of the bigfile?
Mine is 15,975 files and 6,161 folders



WOW, Rick!
You completely ID'd the entire bigfile_english today?
Now to just iron out those last few mystery files in bigfile.000 and you'll have the whole thing licked
## Post #392
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-09-18T19:56:00+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Is there a way to decode "locals.bin" file?
## Post #393
- Username: JohnBloggs
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 19, 2011 1:11 am
- Post datetime: 2011-09-18T20:57:14+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from lapdragon
>
> You're missing a LOT of files - I have 10 "pi" files (including pirate_radio.drm) in the root folder of my extract.
How many total files do you have in your extract of the bigfile?
Mine is 15,975 files and 6,161 folders
i have 6,555 files in 2,703 folders. upon unpacking the file again i saw that it crahes halfway through the unpacking, i didnt notice it the first time because i let it run in the background

does anybodyhave a similiar problem?

sorry if the image to large, i couldnt find any hide or spoiler tags
## Post #394
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-09-18T21:15:32+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from JPulowski
>
> Is there a way to decode "locals.bin" file?
That file is actually pretty simple.

```
{
    public int languageID;
    public int headerSize; // 12 bytes
    public int entryCount;
}

class StringEntry
{
    public int offset;
    public string value;
}
```

Loading (pseudo)code:

```

entries = new StringEntry[header.entryCount];

for (i = 0; i < header.entryCount; i++)
{
    entries[i].offset = readInt32();
}

for (i = 0; i < header.entryCount; i++)
{
    entries[i].value = readString();    // standard null-terminated string
}
```

Strings are stored in UTF8, if I remember correctly.
## Post #395
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-18T23:03:55+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from JohnBloggs
>
> lapdragon wrote:You're missing a LOT of files - I have 10 "pi" files (including pirate_radio.drm) in the root folder of my extract.
How many total files do you have in your extract of the bigfile?
Mine is 15,975 files and 6,161 folders
i have 6,555 files in 2,703 folders. upon unpacking the file again i saw that it crashes halfway through the unpacking, i didn't notice it the first time because i let it run in the background
does anybody have a similar problem?

sorry if the image to large, i couldn't find any hide or spoiler tags

Lol, you're having the same problem Lazarus is - your output path is too long.
You need to output your unpack command to a directory off the root of one of your drives.
Copy the following commands into a batch file - put the batch file and all of the DXHR tools files into the same directory as the source bigfiles, then all you have to do is run the batch and it'll do the rest.

```
Gibbed.DeusEx3.Unpack.exe -o bigfile.000 d:\dxhr_unpack\bigfile
Gibbed.DeusEx3.Unpack.exe -o bigfile_english.000 d:\dxhr_unpack\bigfile_english
Gibbed.DeusEx3.Unpack.exe -o patch0.000 d:\dxhr_unpack\patch0
Gibbed.DeusEx3.Unpack.exe -o patch1.000 d:\dxhr_unpack\patch1

```
## Post #396
- Username: Lazarus
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 28, 2010 11:00 am
- Post datetime: 2011-09-18T23:34:14+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

O.K. Lapdragon, I've finally managed to get the bigfile.000 unpacked ( many thanks for your .bat file suggestion   ).  Next I used DRMEdit to view the various DTPData "subfiles" contained within the pickup_database.drm file.  Following your instructions on page 21, I selected and saved a few of the DTPData "subfiles" as .dat files for viewing/editing in EditPad Pro.  That's where my "noobness" once again reared its vile head.   

As I indicated earlier, one of things I'm trying to do is change the stack sizes of some of the consumable items, e.g. painkillers.  I'm only vaguely familiar with hex editing, but I can convert decimal to hexadecimal and back again.  So if the normal stacksize for painkillers is 5 ( 05 in hex ), is it simply a matter of finding that byte in the file below, and changing it to say 10 ( 0A ) with EditPad Pro?  



Once that's been accomplished, how do I go about "repacking" the edited InventoryItems\painkillers.dat file back into the original pickup_database.drm file, and then incorporating the pickup_database.drm file into the patch1.0000 file?
## Post #397
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-19T00:24:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Lazarus
>
> O.K. Lapdragon... <snip>

As I indicated earlier, one of things I'm trying to do is change the stack sizes of some of the consumable items, e.g. painkillers.  I'm only vaguely familiar with hex editing, but I can convert decimal to hexadecimal and back again.  So if the normal stacksize for painkillers is 5 ( 05 in hex ), is it simply a matter of finding that byte in the file below, and changing it to say 10 ( 0A ) with EditPad Pro?  

Once that's been accomplished, how do I go about "repacking" the edited InventoryItems\painkillers.dat file back into the original pickup_database.drm file, and then incorporating the pickup_database.drm file into the patch1.000 file?

You're mostly correct - the only reason you've extracted the painkillers.dat at all is so that you can isolate the painkillers info out of the whole pickup_database.drm, which gets very confusing to look at.  You'll actually be editing the whole pickup_database.drm in Editpad (which is where having Editpad's tabs is a miracle).

Open both files in Editpad, then hit ctrl+f to open the "find" function at the bottom (and then hit the little magnifying glass icon, to fully expand the find panel - you only have to do that once tho)

For Painkillers, I'd search for "CE 3C CF 3C 01 01 00 00", which is the 8 bytes just in front of the stack size byte - those 8 bytes are pretty much unique for every item, so they're good for finding your items in the pickup_database.drm.  After I've found it, I change the bytes (there's actually 2 bytes to the stack size) to what I want - up to "FF 00" for 255 items to the stack, or "FF FF" for 65k items to the stack.  If you're going for a number over 255, you'll need to invert the bytes - for example, 5000 is 1388 in hex, but in the game files it would have to be entered as "88 13".

After you've made your changes to the pickup_database.drm, save it to the same place in the directory structure in a copy of the patch1.000 unpack, then drag/drop that unpack folder onto Gibbed.DeusEx3.Pack.exe, and then change the name of the resultant file to patch1.000.

As that probably made no sense, I'll break the whole process down a little.  

1.) Unpack bigfile.000 (c:\DXHR_Unpack\bigfile)
2.) Unpack patch1.000 (c:\DXHR_Unpack\patch1)
   2a) Back up your original copy of patch1.000
3.) Make a copy of your patch1 directory (c:\DXHR_Unpack\patch1_copy)
3.) Find and edit pickup_database.drm (c:\DXHR_Unpack\bigfile\default\pc-w\pickup_database.drm)
4.) Save your edited pickup_database.drm into your copied patch1.000 directory (c:\DXHR_Unpack\patch1_copy\default\pc-w\pickup_database.drm)
   4a)  DO NOT SAVE YOUR EDITS TO THE ORIGINAL FILE!!!!!!!!  
5.) Again use the tabs in Editpad - open the bigfile.xml that's in c:\DXHR_Unpack\bigfile, and the bigfile.xml that's in c:\DXHR_Unpack\patch1_copy
6.) Copy the bigfile.XML hash path for your edited files (if there's more than one) from bigfile's XML into the copied patch's XML. Save your changes to the patch's XML, and close Editpad.
7.) Open windows explorer, and drag/drop the whole c:\DXHR_Unpack\patch1_copy directory onto Gibbed.DeusEx3.Pack.exe in your DXHR directory. (makes patch1_copy.000)
8.) Rename your new patch1_copy.000 to patch1.000 and put it into the DXHR game directory, so that the game can use it.
9.) Play DXHR
## Post #398
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-19T01:03:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I've made a fairly comprehensive DXHR unpacking batch file - much fancier than the short one I've been handing out.

Copy/paste the following code into a blank notepad, and save it as DXHR_Unpack.bat (or whatever you want to name it).
The batch file needs to be run from the same directory that you've unpacked the Gibbed.DeusEx3 tools into (which no longer needs to be the DXHR install directory)

```
cls

SET output=D:\DXHR_Unpack
SET lang=english
SET steam=D:\Games\Steam\
SET DXHR=steamapps\common\deus ex - human revolution
SET TML=steamapps\common\dxhrml

rem The preceding three entries are the ONLY things that an end-user should be changing.
rem Output = Where you want the DXHR Files unpacked.
rem Lang = the language for your game (for most US users it will be "english").
rem Steam = Your Steam install directory
rem DXHR = the installation directory for the DXHR game, by default it should be 
rem        steamapps\common\deus ex - human revolution
rem TML = the installation directory for the Missing Link DLC, by default it should be 
rem        steamapps\common\dxhrml
rem If you've installed to a custom Steam directory, you will need to update this entry.
rem 
rem DO NOT CHANGE ANYTHING BELOW THIS LINE!
rem ----------------------------------------------------------------------------------------

echo.
echo   This file will unpack the DX:HR bigfiles for you.
echo   You need to place this file into the directory where 
echo   you've put Gibbed's DXHR tools.
echo.
echo  It is recommended to use a short unpack pathname, off of the 
echo  root of one of your drives.  A long path name or deep directory
echo  structure WILL cause errors, and the unpack will not complete.
echo.
echo    Presently, the output directory is:    %output%
echo    The game language is set to:           %lang%
echo    The DX:HR game files are located in:           
echo        %STEAM%%DXHR%
echo    The DX:HR-TML game files are located in:           
echo        %STEAM%%TML%
echo.
echo  If any of these are incorrect, select option Q to cancel, and
echo  edit the "SET output", "SET lang", or "SET steam" entries in
echo  this batch file.
echo.
echo.
echo  Select an Option:
echo.
echo  Main Game:
echo   A.) Unpack All Files           (8.15 Gb)
echo   P.) Unpack All Patches         (48.2 Mb)
echo.
echo   1.) Unpack bigfile.000         (7.31 Gb)
echo   2.) Unpack bigfile_%lang%.000 (~820 Mb)
echo   3.) Unpack Patch0.000          (28.7 Mb)
echo   4.) Unpack Patch1.000          (19.4 Mb)
echo   5.) Unpack Patch2.000          (18.0 Mb)
echo.
echo  Missing Link DLC:
echo   E.) Unpack All Files           (1.92 Gb)
echo   6.) Unpack bigfile.000         (1.61 Gb)
echo   7.) Unpack bigfile_%lang%.000 (~326 Mb)
echo.
echo  Music:
echo   M.) Demux .mul files to .fsb files
echo.
echo   R.) Rebuild File Lists
echo.
echo   Q.) Cancel
echo.
echo  This batch file will automatically time out if no choice is
echo  made within 30 seconds.
echo.

CHOICE /C ap12345e67mrq /T 30 /D q
IF ERRORLEVEL 13 GOTO None
IF ERRORLEVEL 12 GOTO Rebuild
IF ERRORLEVEL 11 GOTO Music
IF ERRORLEVEL 10 GOTO TML_Region
IF ERRORLEVEL 9 GOTO TML_Bigfile
IF ERRORLEVEL 8 GOTO TML_All
IF ERRORLEVEL 7 GOTO Patch2
IF ERRORLEVEL 6 GOTO Patch1
IF ERRORLEVEL 5 GOTO Patch0
IF ERRORLEVEL 4 GOTO Region
IF ERRORLEVEL 3 GOTO Bigfile
IF ERRORLEVEL 2 GOTO All_Patches
IF ERRORLEVEL 1 GOTO All_Files

:None
echo     Canceled or timed out...
GOTO End

:Rebuild
Gibbed.DeusEx3.RebuildFileLists.exe
GOTO End

:Music
MKDIR "%output%\music\"
FOR /R "%output%\bigfile\default\pc-w\audio\streams\music\" %%M IN (*.mul) DO Gibbed.DeusEx3.Demux.exe %%M
FOR /R "%output%\bigfile\default\pc-w\audio\streams\music\" %%M IN (*.fsb) DO MOVE /Y "%%M" "%output%\music\"
FOR /R "%output%\bigfile\default\pc-w\music\" %%M IN (*.mul) DO Gibbed.DeusEx3.Demux.exe %%M
FOR /R "%output%\bigfile\default\pc-w\music\" %%M IN (*.fsb) DO MOVE /Y "%%M" "%output%\music\"
DEL "%output%\music\*amb*" "%output%\music\det1_limbclinic_2*" "%output%\music\det1_limbclinic_3*" "%output%\music\*roomtone*"
GOTO End

:TML_Region
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%TML%\bigfile_%lang%.000" "%output%\TML_bigfile_%lang%"
GOTO End

:TML_Bigfile
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%TML%\bigfile.000" "%output%\TML_bigfile"
GOTO End

:TML_All
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%TML%\bigfile.000" "%output%\TML_bigfile"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%TML%\bigfile_%lang%.000" "%output%\TML_bigfile_%lang%"
GOTO End

:Patch2
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch2.000" "%output%\patch2"
GOTO End

:Patch1
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch1.000" "%output%\patch1"
GOTO End

:Patch0
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch0.000" "%output%\patch0"
GOTO End

:Region
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\bigfile_%lang%.000" "%output%\bigfile_%lang%"
GOTO End

:Bigfile
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\bigfile.000" "%output%\bigfile"
GOTO End

:All_Patches
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch0.000" "%output%\patch0"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch1.000" "%output%\patch1"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch2.000" "%output%\patch2"
GOTO End

:All_Files
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\bigfile.000" "%output%\bigfile"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\bigfile_%lang%.000" "%output%\bigfile_%lang%"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch0.000" "%output%\patch0"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch1.000" "%output%\patch1"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch2.000" "%output%\patch2"
GOTO End

:End
pause

```
## Post #399
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-19T07:57:25+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I don't know if he posts here, but I'd like to give a thanks to Ekey for contributing a sizable amount of the remaining unknown file names. We're now at 31960/31999 (99%) completion for file names. 39 left.
## Post #400
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-09-19T11:03:32+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hm who knows how to xenon are video files? Example file epilogue.usm

PC

```
pc-w\design_database\videos\cinematics\final_cinematics\cut_22_epilogue\epilogue.usm
```

PS3

```
ps3-w\design_database\videos\cinematics\final_cinematics\cut_22_epilogue\epilogue.usm
```

XBOX - Im trying use this but invalid.

```
xenon-w\design_database\videos\cinematics\final_cinematics\cut_22_epilogue\epilogue.usm
```


In DRM found 2 path's

```
cinematics\final cinematics\cut_22_epilogue\cinematics\final_cinematics\cut_22_epilogue\epilogue.avi
```


trying

```
xenon-w\design_database\videos\cinematics\final cinematics\cut_22_epilogue\cinematics\final_cinematics\cut_22_epilogue\epilogue.usm
```

Invalid!

any idea ?
## Post #401
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-19T15:33:09+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Ekey
>
> any idea ?Are they actually usm files? Maybe the 360 version has wmv or something instead?
## Post #402
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2011-09-19T15:43:17+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hello just found this website, love google.

I'm trying to edit the dialogue, audio and subtitles.  Basically implementing a profanity filer by just blanking out the offending words.  I have figured out how to do this with the subtitles (open the locals.bin in the latest patch.000 file with a hex editor and space it out the offending words) but how do I know which mul files are connected to which parts of the dialogue script?
## Post #403
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-09-19T16:18:54+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> Ekey wrote:any idea ?Are they actually usm files? Maybe the 360 version has wmv or something instead?
No. It's USM file's.

[http://img64.imageshack.us/img64/7975/123gm.png](http://img64.imageshack.us/img64/7975/123gm.png)
[http://img225.imageshack.us/img225/5936/1234ho.png](http://img225.imageshack.us/img225/5936/1234ho.png)
## Post #404
- Username: JohnBloggs
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 19, 2011 1:11 am
- Post datetime: 2011-09-19T18:51:16+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

thank you for the batchfile! it extracted everything now 

in case somebody is looking for the character textures, they are in the pc-w folder:
friendly maincharacters have the prefix "civilian" and bosses "npc".
there are also textures for the main maincharacters in packs with "cinematic" prefix.
adams textures have the prefix "jensen" (who would have guessed that?) and there are also textures of him in the three jensen cinematic packs.
## Post #405
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-09-19T21:25:24+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> JPulowski wrote:Is there a way to decode "locals.bin" file?
That file is actually pretty simple.
Code: Select allclass LangHeader
{
    public int languageID;
    public int headerSize; // 12 bytes
    public int entryCount;
}

class StringEntry
{
    public int offset;
    public string value;
}
Loading (pseudo)code:
Code: Select allreadHeader();

entries = new StringEntry[header.entryCount];

for (i = 0; i < header.entryCount; i++)
{
    entries[i].offset = readInt32();
}

for (i = 0; i < header.entryCount; i++)
{
    entries[i].value = readString();    // standard null-terminated string
}
Strings are stored in UTF8, if I remember correctly.
Thank you so much for your help. Also for the other .BIN files, is the file architecture same? I've unpacked .DRM files, when viewing via Gibbed.DeusEx3.DRMEdit.exe it is fine. But when unpacked I see only .BIN files.
## Post #406
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-09-19T21:29:25+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

JPulowski: No idea, but most likely not.
## Post #407
- Username: DDC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 16, 2011 3:53 am
- Post datetime: 2011-09-19T23:38:39+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

has anyone managed to get any of the character models into a 3d package like maya or 3ds max?
## Post #408
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-21T09:25:41+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Ekey
>
> No. It's USM file's.

http://img64.imageshack.us/img64/7975/123gm.png
http://img225.imageshack.us/img225/5936/1234ho.pngI figured out the names. 

```
xenon-w\design_database\videos\cinematics\final_cinematics\cut_22_epilogue\english\epilogue.usm
```


(Note the 'english\' before the file name)

In your case it's probably:

```
xenon-w\design_database\videos\cinematics\final_cinematics\cut_22_epilogue\russian\epilogue.usm
```
## Post #409
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-09-21T10:37:10+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Oh gj  It is a pity under Xbox360 isn't present emulator.
## Post #410
- Username: GrundyTheGolem
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 23, 2011 10:14 am
- Post datetime: 2011-09-23T02:18:56+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I've made some progress on the render meshes stored in the DRM packages.


Revolver ammo


Peps ammo


Nutrient jar


Beer bottle

I'm still working on the triangle order and I haven't found the UV coordinate data yet though.  The offsets aren't consistent in each mesh file but I haven't found an offset that is stored in the mesh itself yet.
## Post #411
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-23T10:27:41+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from GrundyTheGolem
>
> I've made some progress on the render meshes stored in the DRM packages.

I'm still working on the triangle order and I haven't found the UV coordinate data yet though.  The offsets aren't consistent in each mesh file but I haven't found an offset that is stored in the mesh itself yet.Pointers in sections are managed by each section's resolver data, so they're typically 0xEBEBEBEB by default in the file data.

Look at section.Resolver.LocalDataResolvers / section.Resolver.RemoteDataResolvers.
## Post #412
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-09-23T12:52:30+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

New Fname found. PC, XBOX

xenon-w\imf\imf_props\imf_furniture\imf_bed\bed_zhao_a\bed_zhao_a.drm

pc-w\imf\imf_props\imf_furniture\imf_bed\bed_zhao_a\bed_zhao_a.drm
## Post #413
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-23T13:26:01+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Ekey
>
> New Fname found. PC, XBOX

xenon-w\imf\imf_props\imf_furniture\imf_bed\bed_zhao_a\bed_zhao_a.drm

pc-w\imf\imf_props\imf_furniture\imf_bed\bed_zhao_a\bed_zhao_a.drmThanks, I saw your mail but forgot to merge it in.
## Post #414
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-09-23T17:19:09+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Rick, I just downloaded and compiled a copy of rev 70, but Visual C# spat out a half-dozen errors like this:



dx3_rev70_error.png (19.69 KiB) Viewed 106 times


The following solution folders were all "unavailable":
Deus Ex 3
Tomb Raider 8
Misc
Games
Engine

After compiling it, I ended up with a bin_dx3 and bin_tr8 folder - it did compile tho, but I've not tried unpacking with it.

Additionally, the Solution this time is named "Crystal Dynamics", instead of er.. whatever it used to be named 

You probably know all this already, lol... but I figured that I should speak up just in case you didn't.

ps. are we supposed to get these warnings? 
deusex3\trunk\Gibbed.DeusEx3.FileFormats\DRM\Resolver.cs(82,17): warning CS0162: Unreachable code detected
deusex3\trunk\Gibbed.DeusEx3.FileFormats\DRMFile.cs(87,17): warning CS0162: Unreachable code detected
deusex3\trunk\Gibbed.DeusEx3.FileFormats\DRM\SectionHeader.cs(92,13): warning CS0162: Unreachable code detected
deusex3\trunk\NDesk.Options\Options.cs(707,14): warning CS0618: 'NDesk.Options.OptionSet.GetOptionForName(string)' is obsolete: 'Use KeyedCollection.this[string]'

I always get both of them - this build had these three "unreachable code" errors and I always get the Obsolete string error with each build.
## Post #415
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-23T17:32:34+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from lapdragon
>
> Rick, I just downloaded and compiled a copy of rev 70,

(snip)Express doesn't support solution folders yes, that's normal and shouldn't cause any issues other than not being there.

The solution did get renamed (check the commit history). I'm planning on eventually migrating the repo to crystaldynamics (vs deusex3) in the future.

Those warnings are normal (debug code throwing exceptions before real code for testing purposes).
## Post #416
- Username: sephiroth99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 24, 2011 3:23 am
- Post datetime: 2011-09-23T19:27:39+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hello all, newbie here   

Rick, I saw you started to add support for TR8 in your project. I dunno if you know about UnpackTRU. If you do, forget about this message! If not, check it out here: [http://www.tombraiderforums.com/showthread.php?t=142318](http://www.tombraiderforums.com/showthread.php?t=142318) It was made by Dusan and is able to extract quite a few objects from the different files used by the CDC engine in TR8. The source is available too.

I know there may be some important differences between TR8 and DEHR (in the drm files for example) but maybe it could help (I hope it will!)
## Post #417
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-23T19:40:44+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I'm aware of it, it's not 'real' support, I'm only writing some tools so I can compare data against DX3.
## Post #418
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-09-23T22:22:05+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Rick check mail 

> Reply from sephiroth99
>
> Hello all, newbie here   

Rick, I saw you started to add support for TR8 in your project. I dunno if you know about UnpackTRU. If you do, forget about this message! If not, check it out here: http://www.tombraiderforums.com/showthread.php?t=142318 It was made by Dusan and is able to extract quite a few objects from the different files used by the CDC engine in TR8. The source is available too.

I know there may be some important differences between TR8 and DEHR (in the drm files for example) but maybe it could help (I hope it will!)
For TRU left 2 files. build_number and unknown DRM (size 74 bytes). I think this two files not used in game. Need PS or XBOX version for check. Thanks for link. Added for collection
## Post #419
- Username: GrundyTheGolem
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 23, 2011 10:14 am
- Post datetime: 2011-09-24T01:06:04+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> Pointers in sections are managed by each section's resolver data, so they're typically 0xEBEBEBEB by default in the file data.

Look at section.Resolver.LocalDataResolvers / section.Resolver.RemoteDataResolvers.

The mesh files do have 0xEBEBEBEB at the very beginning.  I was ignoring this data since it appears to be the same in each mesh file.  This is supposed to be offset information?  Is section.Resolver.LocalDataResolvers a file inside bigfile?
## Post #420
- Username: viperman3
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 24, 2011 4:53 am
- Post datetime: 2011-09-24T02:53:32+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

When I run Gibbed.DeusEx3.RebuildFileLists.exe I always get "Could not detect install path."
As a result, the BIGFILE.000 gets unpacked as "unknown"

What am I missing here?  I've tried the .bat files and same issue.  How can I set the install path for this (I've got the xbox360 version)

Thanks
## Post #421
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-24T02:57:53+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from viperman3
>
> When I run Gibbed.DeusEx3.RebuildFileLists.exe I always get "Could not detect install path."
As a result, the BIGFILE.000 gets unpacked as "unknown"

What am I missing here?  I've tried the .bat files and same issue.  How can I set the install path for this (I've got the xbox360 version)

ThanksEdit projects\Deus Ex 3 (Xenon).xml to indicate your path.
## Post #422
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-24T03:05:30+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from GrundyTheGolem
>
> The mesh files do have 0xEBEBEBEB at the very beginning.  I was ignoring this data since it appears to be the same in each mesh file.  This is supposed to be offset information?  Is section.Resolver.LocalDataResolvers a file inside bigfile?I had assumed you were using my code as a base to read DRM data -- this information is per each section, and the pointers in the data are filled in at runtime using this data.

In my code:

Gibbed.DeusEx3.FileFormats.DRM.Section has a field named 'Resolver', of type:Gibbed.DeusEx3.FileFormats.DRM.Resolver, which has various lists of pointers that are to be updated on load (there are different pointer types that update differently).
## Post #423
- Username: viperman3
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 24, 2011 4:53 am
- Post datetime: 2011-09-24T05:13:00+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> viperman3 wrote:When I run Gibbed.DeusEx3.RebuildFileLists.exe I always get "Could not detect install path."
As a result, the BIGFILE.000 gets unpacked as "unknown"

What am I missing here?  I've tried the .bat files and same issue.  How can I set the install path for this (I've got the xbox360 version)

ThanksEdit projects\Deus Ex 3 (Xenon).xml to indicate your path.

Edited projects\Deus Ex 3 (Xenon).xml as follows:
<project>
	<name>Deus Ex 3 (Xenon)</name>
	<dependencies>
		<dependency>Shared</dependency>
	</dependencies>
	<list_location>Deus Ex 3 (Xenon)</list_location>
	<install_locations>
		<install_location>
			<action type="path">e:\xbox\DXHR</action>
		</install_location>
	</install_locations>
</project>

Run Gibbed.DeusEx3.RebuildFileLists.exe and still get same error (Could not detect install path.)

Run Gibbed.DeusEx3.Unpack.exe bigfile.000 out

here's a snippet of the unpacking:

[189/21994] default\__UNKNOWN\drm\2304DB4F.drm
[190/21994] default\__UNKNOWN\drm\DCE68BB1.drm
[191/21994] default\__UNKNOWN\drm\781E3C71.drm
[192/21994] default\__UNKNOWN\drm\11B106DA.drm
[193/21994] default\__UNKNOWN\drm\88C2DFE0.drm


I must be still missing something here.  Please help.
## Post #424
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-24T06:05:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Oh, you probably need to edit current.txt too to use Deus Ex 3 (Xenon) instead of Deus Ex 3 or pass -p "Deus Ex 3 (Xenon)" to unpack.
## Post #425
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-09-24T14:42:49+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #426
- Username: viperman3
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 24, 2011 4:53 am
- Post datetime: 2011-09-24T15:17:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> Oh, you probably need to edit current.txt too to use Deus Ex 3 (Xenon) instead of Deus Ex 3 or pass -p "Deus Ex 3 (Xenon)" to unpack.

That was it.  Unpacked without issues

Thanks
## Post #427
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-24T15:41:41+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #428
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-09-25T12:20:35+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> Use -b when unpacking.
Thanks.. 

TRU8 PS2 : 823/1382 <- HATE PS2  
TRU8 PS3 : 3201/3205
TRU8 XBOX360: 2524/2524 and 1601/1602
## Post #429
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-09-25T22:49:51+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Sorry to bother you irc rick, i couldn't figure out why the svn was asking for a user and pass. then i realized i was indeed doing it wrong. i just had to reinstall my applications due to a hardware crash, and tourtise svn wasn't displaying the svn checkout option at first, so naturally i assumed "import" was the correct one in my list of options. it was not.
## Post #430
- Username: viperman3
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 24, 2011 4:53 am
- Post datetime: 2011-09-26T02:58:16+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

tried the demux tool on .mul files extracted from the xbox360 version.  Doesn't seem to generate .fsb files (all I see are 0 byte .fsb files and the app crashes)

Here's the message when the app crashes:
Unhandled Exception: System.FormatException: One of the identified items was in an invalid format.
   at Gibbed.DeusEx3.Demux.Program.Main(String[] args)

Are the 360 version .mul files supported?
## Post #431
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-26T06:00:28+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Provide a sample of a .mul file that doesn't work.
## Post #432
- Username: viperman3
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 24, 2011 4:53 am
- Post datetime: 2011-09-26T11:06:00+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Rick
>
> Provide a sample of a .mul file that doesn't work.

file uploaded here:

[http://www.mediafire.com/?81j7dg32f6qzeju](http://www.mediafire.com/?81j7dg32f6qzeju)
## Post #433
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-09-26T14:13:42+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from viperman3
>
> Rick wrote:Provide a sample of a .mul file that doesn't work.

file uploaded here:

http://www.mediafire.com/?81j7dg32f6qzejuI'm guessing there's some form of compression going on here that I don't know how to support. I will look into it when I can.
## Post #434
- Username: viperman3
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 24, 2011 4:53 am
- Post datetime: 2011-09-27T00:52:34+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

if I run the dxhr_deblockbe03 python script, this yields .xma files (which are xbox audio files), but the header information is missing and towav.exe can't correctly process the files.

Hope this additional information helps
[dxhr_deblockbe03.zip](https://xentaxbackup.github.io/file/4741_dxhr_deblockbe03.zip)
## Post #435
- Username: FatDaddyCool
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 08, 2011 3:46 am
- Post datetime: 2011-10-07T20:38:14+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hey all 
Very new here and very n00b.  
I used the cheat file to access the debug menu and it seems to have killed my game audio.  I have reversed the cheat by replacing with the back up of Patch1 and Patch0 but my sound is still out for the count.

System specs

AMD Phenom II X6 1090T 3.72 GHz
Asus Crosshair V
2 AMD 6800 series Radeon Crossfire
On Board sound Realtek High Definition
Win 7 Pro
Steam Edition DXHR 

Any help would be very appreciated
## Post #436
- Username: FatDaddyCool
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 08, 2011 3:46 am
- Post datetime: 2011-10-07T21:21:11+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from FatDaddyCool
>
> Hey all 
Very new here and very n00b.  
I used the cheat file to access the debug menu and it seems to have killed my game audio.  I have reversed the cheat by replacing with the back up of Patch1 and Patch0 but my sound is still out for the count.

System specs

AMD Phenom II X6 1090T 3.72 GHz
Asus Crosshair V
2 AMD 6800 series Radeon Crossfire
On Board sound Realtek High Definition
Win 7 Pro
Steam Edition DXHR 

Any help would be very appreciated

Disregard it was a hardware issue.
## Post #437
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2011-10-08T17:12:47+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

There is 30 pages! and i don't know if is there any research on how to get some game files for modding or not. Please if it is, update first entry or clear useless posts! Thx
## Post #438
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-10-09T22:20:45+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Gocha
>
> There is 30 pages! and i don't know if is there any research on how to get some game files for modding or not. Please if it is, update first entry or clear useless posts! Thx

It depends on what you want to "mod"...

There's a number of posts about 1/3 of the way through the beginning that deal with making a translation mod, but I think most of the interest in that died once the game was officially released in the major languages.
I've got a writeup on how to mod the ingame equipment on page 21.
Abadjpyo has written a number of entries on how to mod the augmentations and abilities.
There's a number of people working on extracting the movies and music/sound effects.

Honestly, most of this thread's posts are useful - if you're too lazy and/or ADD to read and understand them, then that's your own problem.  We're not here to spoonfeed you precisely what you want, and as far as that goes, you've not even said what you DO want.
## Post #439
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2011-10-14T19:05:05+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Rick you release patch that skips intros. If i am not wrong those videos are Scaleform format (.usm) videos and i wish to know how did you made it so to skip intros; that you depack/repack .000 i know, just which file u've modified
## Post #440
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-10-14T19:46:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Gocha
>
> Rick you release patch that skips intros. If i am not wrong those videos are Scaleform format (.usm) videos and i wish to know how did you made it so to skip intros; that you depack/repack .000 i know, just which file u've modified
Nope. Edited GUI scripts in DRM's.
## Post #441
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-10-14T21:06:28+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

So how do I unpack DRM files in Tomb Raider Underworld?
## Post #442
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-10-14T21:18:52+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from C00L12345
>
> So how do I unpack DRM files in Tomb Raider Underworld?
Try PM or Mail to Rick. Maybe he can adding support TRU DRM's files for DRMEdit.
## Post #443
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-10-14T22:15:13+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Gocha
>
> Rick you release patch that skips intros. If i am not wrong those videos are Scaleform format (.usm) videos and i wish to know how did you made it so to skip intros; that you depack/repack .000 i know, just which file u've modifiedThe intro scaleform SWF had logic in it already for skipping, I just forced it to be enabled by patching the flash bytecode.
## Post #444
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-10-15T18:43:25+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

So on Tomb Raider Underworld I've done the following:

Used a tool to extract the drm file from the bigfile.000.
Used a tool to inflate the CDRM file -> DRM

Before:



After:



I tried to use the DEUS Ex DRM Edit and it failed to load the file normally and inflated.

Someone help me 

What am I supposed to do? How do i split the DRM files to output Models, Sound effects, Scripts, Textures etc?
## Post #445
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-10-16T17:28:15+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Anyone got any ideas?
## Post #446
- Username: Straylight
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 19, 2011 1:19 am
- Post datetime: 2011-10-18T17:21:23+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I, for one, am anxiously awaiting the UI elements of this. I cant wait to try it when I return home.

Woot!
## Post #447
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-10-20T18:39:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Just a little info on The Missing Link DLC - texts are stored in bigfile.000 and NOT in bigfile_english.000 (or other locale files). The ID/hash of the texts is the same, format is the same.
## Post #448
- Username: JCDentonMale
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 22, 2011 12:24 am
- Post datetime: 2011-10-21T16:32:39+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Just thought it could be useful: I corrected a minor bug in the batch file found on page 27 (bigfile_english.000 was hard-coded), added support for patch2.000 and added an option M that demuxes all the music of the game and move all the .fsb to the "music" directory. Ambient sounds are automatically deleted. Then you just have to drag and drop your FSB files to "Music Player Ex" ([http://jerome.jouvie.free.fr/musicplayer/index.php](http://jerome.jouvie.free.fr/musicplayer/index.php)) if you want to listen to the music or convert it to MP3/WAV.

Here it is:

```
cls

SET output=C:\dx3_out
SET region=english
SET DXHR=C:\Program Files\Steam\SteamApps\common\deus ex - human revolution

rem The preceding three entries are the ONLY things that an end-user should be changing.
rem Output = Where you want the DXHR Files unpacked.
rem Region = the region for your game (for most US users it will be "english" but can be "french" for example).
rem DXHR = the installation directory for your DXHR game, by default it should be 
rem C:\Program Files\Steam\steamapps\common\deus ex - human revolution
rem If you've installed to a custom Steam directory, you will need to update this entry.
rem 
rem DO NOT CHANGE ANYTHING BELOW THIS LINE!
rem ----------------------------------------------------------------------------------------

echo.
echo   This file will unpack the DX:HR bigfiles for you.
echo   You need to place this file into the directory where 
echo   you've put Gibbed's DXHR tools.
echo.
echo  It is recommended to use a short unpack pathname, off of the 
echo  root of one of your drives.  A long path name or deep directory
echo  structure WILL cause errors, and the unpack will not complete.
echo.
echo    Presently, the output directory is:    %output%
echo    The game language is set to:           %region%
echo    The game files are located in:           
echo        %DXHR%
echo.
echo  If any of these are incorrect, select option 8 to cancel, and
echo  edit the "SET output", "SET region", or "SET DXHR" entries in
echo  this batch file.
echo.
echo.
echo  Select an Option:
echo.
echo   1.) Unpack All Files           (8.15 Gb)
echo   2.) Unpack All Patches         (48.2 Mb)
echo.
echo   3.) Unpack bigfile.000         (7.31 Gb)
echo   4.) Unpack bigfile_%region%.000 (~820 Mb)
echo   5.) Unpack Patch0.000          (28.7 Mb)
echo   6.) Unpack Patch1.000          (19.4 Mb)
echo   7.) Unpack Patch2.000          (18.0 Mb)
echo.
echo   8.) Rebuild File Lists
echo.
echo   M.) Demux .mul files to .fsb files
echo.
echo   9.) Cancel
echo.
echo  This batch file will automatically time out if no choice is
echo  made within 30 seconds.
echo.

CHOICE /C 123456789M /T 30 /D 9
IF ERRORLEVEL 10 GOTO Music
IF ERRORLEVEL 9 GOTO None
IF ERRORLEVEL 8 GOTO Rebuild
IF ERRORLEVEL 7 GOTO Patch2
IF ERRORLEVEL 6 GOTO Patch1
IF ERRORLEVEL 5 GOTO Patch0
IF ERRORLEVEL 4 GOTO Region
IF ERRORLEVEL 3 GOTO Bigfile
IF ERRORLEVEL 2 GOTO All_Patches
IF ERRORLEVEL 1 GOTO All_Files

:None
echo     Canceled or timed out...
GOTO End

:Music
MKDIR "%output%\music\"
FOR /R "%output%\bigfile\default\pc-w\audio\streams\music\" %%M IN (*.mul) DO Gibbed.DeusEx3.Demux.exe %%M
FOR /R "%output%\bigfile\default\pc-w\audio\streams\music\" %%M IN (*.fsb) DO MOVE /Y "%%M" "%output%\music\"
FOR /R "%output%\bigfile\default\pc-w\music\" %%M IN (*.mul) DO Gibbed.DeusEx3.Demux.exe %%M
FOR /R "%output%\bigfile\default\pc-w\music\" %%M IN (*.fsb) DO MOVE /Y "%%M" "%output%\music\"
DEL "%output%\music\*amb*" "%output%\music\det1_limbclinic_2*" "%output%\music\det1_limbclinic_3*" "%output%\music\*roomtone*"
GOTO End

:Rebuild
RebuildFileLists.exe
GOTO End

:Patch2
Gibbed.DeusEx3.Unpack.exe -o "%DXHR%\patch2.000" "%output%\patch2"
GOTO End

:Patch1
Gibbed.DeusEx3.Unpack.exe -o "%DXHR%\patch1.000" "%output%\patch1"
GOTO End

:Patch0
Gibbed.DeusEx3.Unpack.exe -o "%DXHR%\patch0.000" "%output%\patch0"
GOTO End

:Region
Gibbed.DeusEx3.Unpack.exe -o "%DXHR%\bigfile_%region%.000" "%output%\bigfile_%region%"
GOTO End

:Bigfile
Gibbed.DeusEx3.Unpack.exe -o "%DXHR%\bigfile.000" "%output%\bigfile"
GOTO End

:All_Patches
Gibbed.DeusEx3.Unpack.exe -o "%DXHR%\patch0.000" "%output%\patch0"
Gibbed.DeusEx3.Unpack.exe -o "%DXHR%\patch1.000" "%output%\patch1"
Gibbed.DeusEx3.Unpack.exe -o "%DXHR%\patch2.000" "%output%\patch2"
GOTO End

:All_Files
Gibbed.DeusEx3.Unpack.exe -o "%DXHR%\bigfile.000" "%output%\bigfile"
Gibbed.DeusEx3.Unpack.exe -o "%DXHR%\bigfile_%region%.000" "%output%\bigfile_%region%"
Gibbed.DeusEx3.Unpack.exe -o "%DXHR%\patch0.000" "%output%\patch0"
Gibbed.DeusEx3.Unpack.exe -o "%DXHR%\patch1.000" "%output%\patch1"
Gibbed.DeusEx3.Unpack.exe -o "%DXHR%\patch2.000" "%output%\patch2"
GOTO End

:End
pause
```
## Post #449
- Username: JCDentonMale
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 22, 2011 12:24 am
- Post datetime: 2011-10-21T18:21:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I made a small mix of the Hive music, if someone is interested 
The mix is 12 minutes and contains the 3 parts of the Hive music. Someone could probably do better, especially at transitions, but I couldn't wait for a mix of it! I extracted the music myself from the FSB, so it is not made of the mono tracks found on the web.

Download: [http://www.wilduniverse.org/music/sha1_ ... ixed_2.mp3](http://www.wilduniverse.org/music/sha1_thehive_music_mixed_2.mp3)
## Post #450
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2011-10-24T12:15:00+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I've updated the unpacker batch file with support for the latest revision of the main game, and added in support for unpacking the Missing Link DLC.  I also put in JCDentonMale's music demux, but if there's any issues with it, you'll have to work with him to fix it - I don't know the first thing about demuxing the music.

You can replace your existing batch file with the one below - be aware that I've changed several of the old menu's hotkeys to letters instead of numbers.

```
cls

SET output=D:\DXHR_Unpack
SET lang=english
SET steam=D:\Games\Steam\
SET DXHR=steamapps\common\deus ex - human revolution
SET TML=steamapps\common\dxhrml

rem The preceding three entries are the ONLY things that an end-user should be changing.
rem Output = Where you want the DXHR Files unpacked.
rem Lang = the language for your game (for most US users it will be "english").
rem Steam = Your Steam install directory
rem DXHR = the installation directory for the DXHR game, by default it should be 
rem        steamapps\common\deus ex - human revolution
rem TML = the installation directory for the Missing Link DLC, by default it should be 
rem        steamapps\common\dxhrml
rem If you've installed to a custom Steam directory, you will need to update this entry.
rem 
rem DO NOT CHANGE ANYTHING BELOW THIS LINE!
rem ----------------------------------------------------------------------------------------

echo.
echo   This file will unpack the DX:HR bigfiles for you.
echo   You need to place this file into the directory where 
echo   you've put Gibbed's DXHR tools.
echo.
echo  It is recommended to use a short unpack pathname, off of the 
echo  root of one of your drives.  A long path name or deep directory
echo  structure WILL cause errors, and the unpack will not complete.
echo.
echo    Presently, the output directory is:    %output%
echo    The game language is set to:           %lang%
echo    The DX:HR game files are located in:           
echo        %STEAM%%DXHR%
echo    The DX:HR-TML game files are located in:           
echo        %STEAM%%TML%
echo.
echo  If any of these are incorrect, select option Q to cancel, and
echo  edit the "SET output", "SET lang", or "SET steam" entries in
echo  this batch file.
echo.
echo.
echo  Select an Option:
echo.
echo  Main Game:
echo   A.) Unpack All Files           (8.15 Gb)
echo   P.) Unpack All Patches         (48.2 Mb)
echo.
echo   1.) Unpack bigfile.000         (7.31 Gb)
echo   2.) Unpack bigfile_%lang%.000 (~820 Mb)
echo   3.) Unpack Patch0.000          (28.7 Mb)
echo   4.) Unpack Patch1.000          (19.4 Mb)
echo   5.) Unpack Patch2.000          (18.0 Mb)
echo.
echo  Missing Link DLC:
echo   E.) Unpack All Files           (1.92 Gb)
echo   6.) Unpack bigfile.000         (1.61 Gb)
echo   7.) Unpack bigfile_%lang%.000 (~326 Mb)
echo.
echo  Music:
echo   M.) Demux .mul files to .fsb files
echo.
echo   R.) Rebuild File Lists
echo.
echo   Q.) Cancel
echo.
echo  This batch file will automatically time out if no choice is
echo  made within 30 seconds.
echo.

CHOICE /C ap12345e67mrq /T 30 /D q
IF ERRORLEVEL 13 GOTO None
IF ERRORLEVEL 12 GOTO Rebuild
IF ERRORLEVEL 11 GOTO Music
IF ERRORLEVEL 10 GOTO TML_Region
IF ERRORLEVEL 9 GOTO TML_Bigfile
IF ERRORLEVEL 8 GOTO TML_All
IF ERRORLEVEL 7 GOTO Patch2
IF ERRORLEVEL 6 GOTO Patch1
IF ERRORLEVEL 5 GOTO Patch0
IF ERRORLEVEL 4 GOTO Region
IF ERRORLEVEL 3 GOTO Bigfile
IF ERRORLEVEL 2 GOTO All_Patches
IF ERRORLEVEL 1 GOTO All_Files

:None
echo     Canceled or timed out...
GOTO End

:Rebuild
Gibbed.DeusEx3.RebuildFileLists.exe
GOTO End

:Music
MKDIR "%output%\music\"
FOR /R "%output%\bigfile\default\pc-w\audio\streams\music\" %%M IN (*.mul) DO Gibbed.DeusEx3.Demux.exe %%M
FOR /R "%output%\bigfile\default\pc-w\audio\streams\music\" %%M IN (*.fsb) DO MOVE /Y "%%M" "%output%\music\"
FOR /R "%output%\bigfile\default\pc-w\music\" %%M IN (*.mul) DO Gibbed.DeusEx3.Demux.exe %%M
FOR /R "%output%\bigfile\default\pc-w\music\" %%M IN (*.fsb) DO MOVE /Y "%%M" "%output%\music\"
DEL "%output%\music\*amb*" "%output%\music\det1_limbclinic_2*" "%output%\music\det1_limbclinic_3*" "%output%\music\*roomtone*"
GOTO End

:TML_Region
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%TML%\bigfile_%lang%.000" "%output%\TML_bigfile_%lang%"
GOTO End

:TML_Bigfile
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%TML%\bigfile.000" "%output%\TML_bigfile"
GOTO End

:TML_All
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%TML%\bigfile.000" "%output%\TML_bigfile"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%TML%\bigfile_%lang%.000" "%output%\TML_bigfile_%lang%"
GOTO End

:Patch2
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch2.000" "%output%\patch2"
GOTO End

:Patch1
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch1.000" "%output%\patch1"
GOTO End

:Patch0
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch0.000" "%output%\patch0"
GOTO End

:Region
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\bigfile_%lang%.000" "%output%\bigfile_%lang%"
GOTO End

:Bigfile
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\bigfile.000" "%output%\bigfile"
GOTO End

:All_Patches
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch0.000" "%output%\patch0"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch1.000" "%output%\patch1"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch2.000" "%output%\patch2"
GOTO End

:All_Files
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\bigfile.000" "%output%\bigfile"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\bigfile_%lang%.000" "%output%\bigfile_%lang%"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch0.000" "%output%\patch0"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch1.000" "%output%\patch1"
Gibbed.DeusEx3.Unpack.exe -o "%STEAM%%DXHR%\patch2.000" "%output%\patch2"
GOTO End

:End
pause

```
## Post #451
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-10-24T15:46:02+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Help on Tomb Raider Underworld
## Post #452
- Username: JCDentonMale
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 22, 2011 12:24 am
- Post datetime: 2011-10-25T06:22:07+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I may not reply often, so I explain a little what the following lines in the batch do:

```
FOR /R "%output%\bigfile\default\pc-w\audio\streams\music\" %%M IN (*.mul) DO Gibbed.DeusEx3.Demux.exe %%M
FOR /R "%output%\bigfile\default\pc-w\audio\streams\music\" %%M IN (*.fsb) DO MOVE /Y "%%M" "%output%\music\"
FOR /R "%output%\bigfile\default\pc-w\music\" %%M IN (*.mul) DO Gibbed.DeusEx3.Demux.exe %%M
FOR /R "%output%\bigfile\default\pc-w\music\" %%M IN (*.fsb) DO MOVE /Y "%%M" "%output%\music\"
DEL "%output%\music\*amb*" "%output%\music\det1_limbclinic_2*" "%output%\music\det1_limbclinic_3*" "%output%\music\*roomtone*"
GOTO End
```


1. I create the "music" directory in "%output%"
2. I search for all the .mul files in "%output%\bigfile\default\pc-w\audio\streams\music\", then I demux each of them
3. I move the demuxed files (.fsb files) in the "%output%\music\" directory
4. I search for all the .mul files in "%output%\bigfile\default\pc-w\music\", then I demux each of them
5. I move the demuxed files (.fsb files) in the "%output%\music\" directory
6. I delete all the ambient sounds. Those are not music and are not part of the soundtrack. Any filename containing "amb", "det1_limbclinic_2", "det1_limbclinic_3" or "roomtone" is an ambient sound.

What to do with your FSB files ?

FSB a kind of FMOD file format ([http://en.wikipedia.org/wiki/FMOD](http://en.wikipedia.org/wiki/FMOD)). It can be played or converted to WAV or MP3 format using the "Music Player Ex" music player, for example.

MUL files are multiplexed FSB files. It means that two or more FSB files are contained in a single MUL file. The demuxer is used to separate each file. More information on multiplexing: [http://en.wikipedia.org/wiki/Demuxer](http://en.wikipedia.org/wiki/Demuxer)

Hope this helps!
## Post #453
- Username: billpayer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 30, 2011 3:53 am
- Post datetime: 2011-10-29T19:58:12+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Thank you to the whole community for all your effort decoding DXHR.

I would like to ask,

Has the community been able to export models ?

Is there an existing Adam Jensen model with bionic arms ? (preferably fbx or obj)

Thank you !
## Post #454
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-10-30T11:08:02+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #455
- Username: JCDentonMale
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 22, 2011 12:24 am
- Post datetime: 2011-11-01T08:26:17+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Updated my mix of "The Hive" club music with stereo sources and better transitions: [http://wilduniverse.org/music/sha1_theh ... ixed_4.mp3](http://wilduniverse.org/music/sha1_thehive_music_mixed_4.mp3)
## Post #456
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2011-11-04T18:44:27+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Anyone know of a updated modkit?  I'm still trying to edit the dialogue but have only managed to change the subtitles so far, the audio is still a problem.
## Post #457
- Username: DDC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 16, 2011 3:53 am
- Post datetime: 2011-11-16T02:37:32+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I too would like to thank you all for your efforts in decodeing this game and would also like to know if anyone has got any working character models out of the game yet?
## Post #458
- Username: AlteredRealitii
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 14, 2011 10:44 pm
- Post datetime: 2011-12-14T19:15:49+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from DDC
>
> I too would like to thank you all for your efforts in decodeing this game and would also like to know if anyone has got any working character models out of the game yet?

Thank you all too, and I am wondering exactly the same thing.
## Post #459
- Username: DDC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 16, 2011 3:53 am
- Post datetime: 2011-12-22T16:54:22+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I hope it ok to post this on here. For anyone who is looking for an Adam Jensen model I found this today. [http://o0crofty0o.deviantart.com/art/De ... -270382451](http://o0crofty0o.deviantart.com/art/DeusEx-HR-Adam-Jensen-270382451)
## Post #460
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2012-01-20T16:49:04+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

How did you extract this model?
DRMEditor -> rendermesh?
And how do you import it to the 3d editor?
## Post #461
- Username: bugmenotty
- Rank: Banned
- Number of posts: 10
- Joined date: Wed Mar 16, 2011 6:26 pm
- Post datetime: 2012-01-21T09:12:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Could someone please upload a compiled version of revision 93?
## Post #462
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-01-21T09:55:03+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Could someone please upload a compiled version of revision 93?
Compiled version here : [http://svn.gib.me/builds/deusex3/](http://svn.gib.me/builds/deusex3/)
## Post #463
- Username: Valor
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 24, 2012 6:22 pm
- Post datetime: 2012-01-24T10:26:19+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

How can I open/decode/translate/encode locals.bin step-by-step? It says ingame that invalid UTF8 encoding.
## Post #464
- Username: DDC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 16, 2011 3:53 am
- Post datetime: 2012-02-06T15:59:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

@erik945
Sorry man I didn't exetract the model, I just found it while brousing the web. Thought I'd post it here because so many people like my self have been asking for these models.
## Post #465
- Username: opti2000
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 11, 2012 8:23 am
- Post datetime: 2012-02-11T00:29:33+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hey all 

I searched in this post about it but i foung nothing. So what im searching is how to unpack the ingame soundeffects like doors open or reloading sounds. 

Can someone help me?
## Post #466
- Username: opti2000
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 11, 2012 8:23 am
- Post datetime: 2012-02-16T21:18:27+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

noone can help me?
## Post #467
- Username: kerdsonz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 22, 2012 10:31 pm
- Post datetime: 2012-02-22T21:31:40+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

rick you could extract the texts in Spanish and English of the Deus ex the missing link?

I'm from Brazil

and would like to translate into our language

but do not know how to extract the text

please help me
## Post #468
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-26T22:40:35+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from kerdsonz
>
> but do not know how to extract the text
-> pc-w\local\locals.bin
## Post #469
- Username: ninja81
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 03, 2012 3:38 am
- Post datetime: 2012-03-02T19:49:39+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi all, i read this post in eidos forum to disable radar (unreadable) :

"Open globalplayerinfo.drm go to offset 00013550 and change C8 41 to C8 78 (or try instead of 78 any value up from 42) and Radar becomes unreadable."


I've opened golbalplayerinfo.drm with hex editor, i've find offset 00013550 but i've not find "c8 41" value.
Pls help me, i'm looking for disable radar range, tanx.

edit:

-Solved searching directly c8 41 in hex string globalplayerinfo.drm radar disabled
## Post #470
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-03T00:38:43+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Where are animations stored? in the drm?
## Post #471
- Username: ninja81
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 03, 2012 3:38 am
- Post datetime: 2012-03-03T02:26:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I'm looking for edit health regen and energy regen with hex editor, where are?
## Post #472
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-03T02:49:47+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I don't think they're stored in the archive?
## Post #473
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-03T18:17:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from C00L12345
>
> Where are animations stored? in the drm?
Yep
## Post #474
- Username: Keito
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Mar 05, 2012 4:53 pm
- Post datetime: 2012-03-05T09:43:48+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hello.
Where can i find background main menu video and how can i convert it into something easily playable?
## Post #475
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-05T10:58:13+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Video (USM) you can convert with [VGMToolbox](http://sourceforge.net/projects/vgmtoolbox/files/vgmtoolbox/)
## Post #476
- Username: Keito
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Mar 05, 2012 4:53 pm
- Post datetime: 2012-03-05T12:43:57+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Thank you.
And where exactly can i find them?
## Post #477
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-05T13:18:47+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Keito
>
> Thank you.
And where exactly can i find them?
[http://sourceforge.net/projects/vgmtool ... gmtoolbox/](http://sourceforge.net/projects/vgmtoolbox/files/vgmtoolbox/)
## Post #478
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-05T17:04:51+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

How to unpack Tomb Raider Legend .drm?????
## Post #479
- Username: Keito
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Mar 05, 2012 4:53 pm
- Post datetime: 2012-03-05T17:39:33+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> http://sourceforge.net/projects/vgmtool ... gmtoolbox/
I mean in which directory should i search for this background video? I've found no filenames, that can describe file as main menu video in "video" directory. Only hud and stuff.
## Post #480
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-05T18:24:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Background on Mainmenu not video. It's textures and you can found in globaloutershell.drm file.
## Post #481
- Username: Keito
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Mar 05, 2012 4:53 pm
- Post datetime: 2012-03-05T18:29:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

What a shame. Just wanted to make animated wallpaper using this video.
Well, thank you anyway.
## Post #482
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-05T18:39:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Small update for Missing Link : found 201 filenames.
[dxhrml_fnames.rar](https://xentaxbackup.github.io/file/5145_dxhrml_fnames.rar)
## Post #483
- Username: Polorboy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 23, 2012 10:32 am
- Post datetime: 2012-03-23T02:54:36+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hello everybody, just spent the past few hours reading through as much as I could handle before asking a few questions.  I am pretty much a noob at this but, i have been trying to learn how to enable the debug menu in the DXHRML dlc and get the same inventory management tweaks as in the patch0.000 for the base game.  I figured out how to use the tools, unpack the bigfile.000, view/edit the .drm files, and I am familiar with hexed editors in doing some really basic modding in other games (specifically editing ME2 saves).  I have made backups of the original's from TML already so I can just copy them back in if I screw anything up.  The .drm files I am looking to mod are: globaloutershell.drm, globalscaleformdatabase.drm, and pickup_database.drm, correct?  Those seem to be the ones that are different from the originals in the base game.  Sorry for so many questions, but just one more, in the pickup_database.drm (if I understand correctly from page 21) I need to find and modify each item's stats to get it to fit the way I want, or is there some global that can be changed in one spot?  Thanks a lot for any help.  Again, sorry for asking so many questions in one post.
## Post #484
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-05-05T09:31:48+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

How can i unpack and repack ps3 file ?
Thanks
## Post #485
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-05-10T20:07:27+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

In what program i can use these script : 
```
http://svn.gib.me/public/deusex3/trunk/Gibbed.DeusEx3.Unpack/
```
## Post #486
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-10T20:57:34+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

It's source code. For compile need MSVS 2010

you can use already compiled version here - [http://svn.gib.me/builds/deusex3/](http://svn.gib.me/builds/deusex3/)

For extract/repack PS3 version open file current.txt in projects folder and change line Deus Ex 3 to Deus Ex 3 (PS3)
## Post #487
- Username: Lazarus
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 28, 2010 11:00 am
- Post datetime: 2012-07-23T09:40:33+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Greetings All:

Been about 10 months since I last "attempted" to mod DXHR, so I'm trying to get up to speed again. Had some success with editing the stack sizes of consumables in the pickup_database.drm file last time around.  However, I'm still trying to determine which .drm files contain the following info:

1: Adam Jensen's base ( i.e. non-augmented ) movement speed and jump height.

2: Augmentation properties ( particularly the Cybernetic Leg Prosthesis sprint enhancement value - would like to double it).

3:  Magazine capacity of the the stun gun and tranquilizer rifle.

I've used EditPad Pro 7 to view the contents of the following .drm files in attempt to find the aforementioned data:

globalplayerinfo.drm
human_player.drm
weapon_stungun_equip.drm

Trouble is, I still can't determine which hex addresses might include the data I'm looking for, and as far as I know, nobody's developed a "noob-friendly" utility that converts all that hex into readable text ( if that's the appropriate terminology ).  Anyone know if the aforementioned .drm files contain the data I'm looking for, or had any success modding those attributes?  Thanks in advance.
## Post #488
- Username: fanat1910
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 29, 2012 11:26 pm
- Post datetime: 2012-07-29T15:34:02+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hello All!

I want to port(to .wav) weapon sounds from Deus Ex: HR, I port many of them, but has little problem, I can't find Silenced Sniper Rifle( [http://www.youtube.com/watch?v=n9EmUaR9JlE](http://www.youtube.com/watch?v=n9EmUaR9JlE) ) bolt cocking sound, this is not present in "weapon_silencedsniperrifle_equip.drm", reloading sounds(magazine insert, etc) I find, but bolt sound I can't find it, who can help?

And, can I extract models from this game?
## Post #489
- Username: fanat1910
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 29, 2012 11:26 pm
- Post datetime: 2012-07-29T15:41:46+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

My little tutorial "how to extract sounds"
1. Open with Gibbed.DeusEx3.DRMEdit a DRM file.
2. Select Wave section and press "View Section", you can see name of sound.
3. Press "Save to File"
4. Save file with .fsb extension
5. Open with Music Player Ex and convert using this into .wav or .ogg, or other format
6. ???????
7. PROFIT!!!
## Post #490
- Username: TYLERR
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 09, 2012 1:13 am
- Post datetime: 2012-08-08T17:18:41+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hello All!

I have extracted data from big English file. Could please anyone tell how EXACTLY can I extract texts from .mul files?
## Post #491
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-08T22:04:34+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

.mul files it's sounds. Text in pc-w\local\locals.bin
## Post #492
- Username: TYLERR
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 09, 2012 1:13 am
- Post datetime: 2012-08-09T10:14:30+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Thanks. I found it. How to get the texts from it?
## Post #493
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-09T12:41:55+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Try [this](https://github.com/sephiroth99/translatr/downloads). This tool for translate TRU maybe work on Deux Ex.
## Post #494
- Username: TYLERR
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 09, 2012 1:13 am
- Post datetime: 2012-08-09T16:48:49+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Thanks. But can't understand how to use these tools.
## Post #495
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-09T21:15:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Read README

> How to use:
>
> *Extract mode: translatr extract bigfile_path [patch_path]
>
> 
>
> Arguments:
>
>  bigfile_path: path to folder where bigfile.000 was extracted
>
>  patch_path  : (optional) path to folder where patch.000 was extracted
>
> 
>
> To unpack files from the game, use Gibbed.TombRaider.Unpack from Rick (see
>
> below).
>
> If the game has a patch (like TRU and LCGoL), it is recommended to install and
>
> unpack it, as it will make patching back the modifications easier.
>
> 
>
> *Patch mode  : translatr apply translations_path
>
>  translations_path: path to modified translations.xml file
>
> 
>
> This will create the new files in a folder named "newpatch". If a patch.000
>
> archive was specified during extract mode, the patch will be inserted too. You
>
> can then pack the patch archive back, replace it in the game directory and
>
> enjoy!
>
> 
>
> Unfortunately, this will not work for TRL and TRA as they do not have a
>
> separate patch archive. You will have to copy the content of the "newpatch"
>
> folder into the folder where the bigfile.000 was extracted. Then, you have to
>
> pack the "bigfile.000" archive. It is much longer than just packing the patch
>
> files, but it is the only way.
>
> 
>
> To pack a folder into an archive, use Gibbed.DeuxEx3.Pack from Rick (see
>
> below). You will have to modify it to support Tomb Raider though.
## Post #496
- Username: alanrikkin1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 14, 2012 5:11 am
- Post datetime: 2012-08-21T09:27:28+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Debug Menu* on PS3, it's possible ?
## Post #497
- Username: B25
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 03, 2010 11:31 am
- Post datetime: 2012-08-21T11:17:07+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi modders, 

   question about HEAVY RIFLE MODDING. The heavy rifle has spin-up time (delay before firing consumed to spin-up barrels, cca 2,4-2,5s), has anybody of you found where to change it? The idea is set it to 0.
## Post #498
- Username: fellon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 15, 2012 8:57 am
- Post datetime: 2012-11-16T00:13:10+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hello,

I am an artist living in germany and I am planing to make a work about Deus Ex: Human Revolution and my behaviour towards NPC.
To do this, I need to move without limitations inside the maps. Ideally I get the maps in a format that every 3D program is able to open.
I don't want to be in game to be limited to the body of Adam. 

TL;DR: 
Is is possible to extract the maps from the game?
If yes, please tell me how. If no, then we will see. 

Thanks in advance. =)
## Post #499
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-12-27T16:37:38+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Anyone know if fonts are in DDS or GFX and what file exactly in X360 please ? Rick mention file globaldatabase.rdm but i can only see small textures in it and in X360 swizeled i can open them but still there is too many to check.

Thx
## Post #500
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2013-03-03T20:27:32+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

hey is there any programs to open the .drm to like maybe .obj or 3ds max?
## Post #501
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-03-04T20:44:44+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Repository has moved to [http://svn.gib.me/public/crystaldynamics/](http://svn.gib.me/public/crystaldynamics/).
## Post #502
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2013-03-05T02:44:26+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I tried to use the Gibbed.DeusEx3.DRMUnpack code or script thing didnt work for me is there a eaiser way to convert the .drm files to something readable?
## Post #503
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2013-03-08T18:59:56+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

so I've been seraching googles and found this if you guys can talk to this guy name dragon_child from [http://thefree3dmodels.com](http://thefree3dmodels.com) here is the link to what I founded


[http://thefree3dmodels.com/stuff/charac ... 4-1-0-3729](http://thefree3dmodels.com/stuff/characters/namir/14-1-0-3729)


there is more like

[http://thefree3dmodels.com/stuff/charac ... 4-1-0-4080](http://thefree3dmodels.com/stuff/characters/shirtless_jensen/14-1-0-4080)

I dont know what he use to export the 3d models my request is if someone can talk to him and find out how he did it I try to pm him but I dont know if it went throu any ways thats what I found
## Post #504
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2013-03-22T22:27:49+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Since it's possible to get all files with names now... does anyone still work on the model format? Maybe it's similar to the one from TR9 not sure
## Post #505
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-23T08:02:14+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from o0Crofty0o
>
> Since it's possible to get all files with names now... does anyone still work on the model format? Maybe it's similar to the one from TR9 not sure
Names for what ? If you need unpack DRM's use DRMUnpacker from [this](http://svn.gib.me/builds/crystaldynamics/deusex3/deusex3-r117_b75.zip) pack.
## Post #506
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2013-03-23T20:30:11+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Ekey
>
> o0Crofty0o wrote:Since it's possible to get all files with names now... does anyone still work on the model format? Maybe it's similar to the one from TR9 not sure
Names for what ? If you need unpack DRM's use DRMUnpacker from this pack.

Yeah i used that one but i meant the model files inside the .drm
## Post #507
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-23T21:34:35+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from o0Crofty0o
>
> Yeah i used that one but i meant the model files inside the .drm
Well you can try use TR9 plugin for Noesis maybe work.
## Post #508
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2013-03-26T01:18:34+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Crofty didnt you extract them already??? I mean you got Yelena Federova model right? was that not you?
## Post #509
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-26T14:11:50+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from reappper
>
> Crofty didnt you extract them already??? I mean you got Yelena Federova model right? was that not you?

That was done through Ninja Ripper and custom weight paint.
## Post #510
- Username: reappper
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 11, 2010 8:03 am
- Post datetime: 2013-03-27T02:37:17+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I look up your ninja ripping does it really work?? I'm going to do some tests on it to see if it does work hmm...
## Post #511
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-28T08:01:27+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Works perfectly fine here by letting the NR to choose between Dx9/11 

Also, the topic is 35 (now) pages, there's a way to extract textures? Without texmod, just by unpacking files?
## Post #512
- Username: Lazarus
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 28, 2010 11:00 am
- Post datetime: 2013-09-07T21:16:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Greetings All:

Been over 2 years since DXHR's release. Seems like there's little ( or no ) interest in modding the game anymore, but what the heck, I'll ask anyway.  Has anyone ever had any luck determining which .drm files contain the following info?

1: Adam Jensen's base ( i.e. non-augmented ) movement speed and jump height.

2: Augmentation properties ( particularly the Cybernetic Leg Prosthesis sprint enhancement value - would like to double it).

3: Magazine capacity of the the stun gun and tranquilizer rifle.

I've used EditPad Pro 7 to view the contents of the following .drm files in attempt to find the aforementioned data:

globalplayerinfo.drm
human.drm
human_player.drm
weapon_stungun_equip.drm

Still can't determine which hex addresses might include the data I'm looking for, and as far as I know, nobody's developed a "noob-friendly" utility that converts all that hex into readable text ( if that's the appropriate terminology ). Anyone know if the aforementioned .drm files contain the data I'm looking for, or had any success modding those attributes? Thanks in advance.
## Post #513
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2013-10-23T08:11:50+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Director's Cut for PC just got released. Is anybody working on filelists for its bigfiles?

Gibbed: your repository for DXHR is unavailable - does that mean you're working on Director's Cut support for your tools?
## Post #514
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-10-23T12:50:12+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from mnn
>
> Gibbed: your repository for DXHR is unavailable - does that mean you're working on Director's Cut support for your tools?No, it was moved at some point to a new repository to generalize name to engine.

[http://svn.gib.me/public/crystaldynamics/trunk](http://svn.gib.me/public/crystaldynamics/trunk)
## Post #515
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2013-10-23T15:11:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Rick: Thanks for information. I think I did not notice that (I did notice, that you added support for more games based on Crystal Dynamics engine).

So my question is: do you plan on taking a look at the Director's Cut version of the game? At least making some filelists. Thanks.
## Post #516
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-10-27T20:49:16+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I added some file lists for DX3DC.
## Post #517
- Username: Zashibu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 19, 2011 6:58 am
- Post datetime: 2013-11-02T15:14:24+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Found about 400 filenames for Directors Cut.
[bigfile.zip](https://xentaxbackup.github.io/file/6751_bigfile.zip)
## Post #518
- Username: Zashibu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 19, 2011 6:58 am
- Post datetime: 2013-11-04T21:50:59+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

+170 new names for Directors Cut.
31351/33885 (92%)
[bigfile.zip](https://xentaxbackup.github.io/file/6753_bigfile.zip)
## Post #519
- Username: Zashibu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 19, 2011 6:58 am
- Post datetime: 2013-11-27T15:34:11+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Almost complete filelists for:

Deus Ex 3
bigfile.filelist: 15972/15974 (99%)
-----------
Deus Ex 3 - The Missing Link
bigfile.filelist: 5148/5157 (99%)
bigfile_english.filelist: 5665/5665 (100%)
-----------
Deus Ex 3 - Director's Cut
bigfile.filelist: 33878/33887 (99%)
[projects.7z](https://xentaxbackup.github.io/file/6806_projects.7z)
## Post #520
- Username: timkango
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 12, 2011 4:16 pm
- Post datetime: 2013-11-27T15:55:07+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Well done, Zashibu. Thanks for the update.
## Post #521
- Username: opti2000
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 11, 2012 8:23 am
- Post datetime: 2013-12-13T16:52:21+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hi

i try to decompile the .drm files with the Gibbed.DeusEx3.DRMDecompress file but it is not working.
I drag and drop the .drm's on the Gibbed.DeusEx3.DRMDecompress but the window closes immediately and nothing happens.

Is there any other way to get the textures from the .dmr's?
## Post #522
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2014-03-30T22:35:14+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

For me the program crashes after unpack 30.000 files (aprox) , i have deusex3-r122_b79.zip 

Downloaded from here: [http://svn.gib.me/builds/crystaldynamics/deusex3/](http://svn.gib.me/builds/crystaldynamics/deusex3/)

Im using the last bigfile.filelist (; 33878/33887 (99%)) attached in this forum and the version of the game it's Deus Ex Human Revolution Directors Cut with update 1 applied.

This is the command line i used 
```
Gibbed.DeusEx3.Unpack.exe BIGFILE.000
```


Any idea/hint?

Thanks
## Post #523
- Username: opti2000
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 11, 2012 8:23 am
- Post datetime: 2014-09-30T01:57:08+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

please help
## Post #524
- Username: Flash
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 22, 2014 6:16 pm
- Post datetime: 2015-04-12T18:39:43+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

So, there is still no way convert models?
## Post #525
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-04-14T13:25:27+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

> Reply from Flash
>
> So, there is still no way convert models?
This game runs on the same engine as some Tomb Raider games. I assume the format should be close or pretty much the same. Got any samples?
## Post #526
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-01-02T22:39:05+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

In case everybody is too uninterested in solving some problems for us here, I will revive this thread only because nobody will reply it back anyway.
## Post #527
- Username: Reclaimer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 31, 2016 12:14 am
- Post datetime: 2016-03-30T16:23:33+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Is there currently anyway for me to extract the skybox textures from Human Revolution. In particular the Belltower docks section?
## Post #528
- Username: gs11
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 06, 2016 8:38 pm
- Post datetime: 2016-05-06T12:43:44+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Is it possible to modify radar option, could You tell me how to do it? Or make it as separate option?

I wanne to make  radar 2 lvl range 25 m mod ( 50 m is to much and not really good visible).
i found sth like this 

> Open globalplayerinfo.drm go to offset 00013550 and change C8 41 to C8 78 (or try instead of 78 any value up from 42) and Radar becomes unreadable.
where/how to do it?i wanne change radar range/zoom. i can't find this file, PC version DX:HR DC

I red whole this topic, but have no experiance with coding at all, don't  understand pretty anything.
If You could tell me how to do it (hex editor or how You exactly did it ) I'll be very gratefull.

thanks in advance
## Post #529
- Username: Berzee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 15, 2016 8:04 pm
- Post datetime: 2016-06-15T13:44:02+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Probably a long shot at this point, but I am looking for a way to replace some character models in the game with other character models. I don't want to extract or edit the models, just replace one with another in the game (as a random example -- making some civilian, or all civilians, in Detroit look like Pritchard). Alternatively, I would like to be able to edit a level to remove a non-essential NPC (i.e. cause some generic guard or civilian not to spawn). I haven't really seen much discussion on either of these feats, so I am not terribly optimistic but I figured I would ask. I am poking around the DRM files currently but a definitive yea or nay would save me a lot of time. Thanks!
## Post #530
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2016-08-20T20:34:06+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Did anyone get translatr to work with the DC? I can only manage to crash it. Hex editing dialogue might work but it rather limits sentence length.
## Post #531
- Username: CorinthMaxwell
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 25, 2016 8:42 am
- Post datetime: 2016-12-25T04:00:37+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

I know that this is a rather old thread, but I could really use some assistance.

[redacted]After much searching, I was finally led to this particular message board, and I've learned quite a bit already about the rather large files in the DXHR:DC installation folder. Having endured quite a bit of difficulty, I managed to extract them to an external drive so that I can attempt to create my own mod for the game. Unfortunately, I now seem to have hit a rather large roadblock.

Is there some specific reason that unpacking a *.drm file with "Gibbed.DeusEx3.DRMUnpack.exe" only extracts the contents as *.bin files? I read earlier in the thread that Lapdragon was modifying *.dat files that he had extracted from the *.drm files, so I'm kind of wondering if I've somehow skipped a step or two.

I would very much like to be able to learn how to resolve and/or figure out problems like this (or any future issues I may run into) on my own and not be a bother to anyone here, but in this case, I seem to need as much help as I can get. 


EDIT: Found what I was looking for, but I still have a question or two. Is there any way to modify the game's numerous Intellicams so that destroying them doesn't automatically set off the alarm system of any given level?
## Post #532
- Username: blackrock89
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 01, 2018 9:41 am
- Post datetime: 2018-12-01T02:12:32+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hello guys! I export "locals.bin" file to text and edited.But i cant import (repack) back !
I tried Hex Editor but i got an error "invalid utf8 encoding".Please help me guys!
## Post #533
- Username: madeyoulook
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 03, 2018 8:36 am
- Post datetime: 2018-12-07T08:49:45+00:00
- Post Title: Re: BIGFILE.000 - Deus Ex Human Revolution Unpack

Hey, I'm trying to do two things, and I need some help.

1. I'm trying to allow to allow the "armor piercing system" weapon upgrade to be used on other weapons, specifically the silenced sniper rifle. I imagine it's the hex code of "pickup_database.drm" like all the other weapon upgrades, but I don't know how to find it. Does anyone know?

2. I want to make the lethal takedown just as quiet as non-lethal takedowns. I have no idea how to do this. Does anyone else?
