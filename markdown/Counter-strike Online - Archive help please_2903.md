## Post #1
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2008-01-23T07:34:05+00:00
- Post Title: Counter-strike Online - Archive help please

Hello there

I was wondering if somebody might be able to look at this file for me. It is for another version of Counter-strike and after the success or Mr Mouse with CS for XBox I thought I would ask again!

The game uses "nar" files, and I have attached the smallest one in it's entirety as it is only 100kb.

I hope someone scan help me out as I STILL do not understand the nuances of archives!

Cheers for now
[resource.zip](https://xentaxbackup.github.io/file/1429_resource.zip)
## Post #2
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2008-01-23T21:19:30+00:00
- Post Title: Counter-strike Online - Archive help please

Just to see if it might help I've used filecutter to get 512 samples of the other two archives.

[cstrike.nar](http://www.talismanisland.com/xentax/cstrike.nar.zip)

[valve.nar](http://www.talismanisland.com/xentax/valve.nar.zip)

Cheers for now
## Post #3
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2008-01-23T22:23:45+00:00
- Post Title: Counter-strike Online - Archive help please

The more I stare at these files in Hex Workshop, the more convinced I am that the content of the archives is actually listed in Korean.... I can find references to filetypes common in the game such as bsp, nav, mdl and wav, but nothing to do with common English names... <sigh>
## Post #4
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2008-01-23T23:58:38+00:00
- Post Title: Counter-strike Online - Archive help please

Small update... I read a bit of the Wiki and came across some other applications that help with extraction.

[http://wiki.xentax.com/index.php?title=Extraction_tools](http://wiki.xentax.com/index.php?title=Extraction_tools)

I managed to extract all of the sound files using Audiorip from the Wiki Link, but unfortunately they are all unnamed.

I tried Bitmaprip from the Wiki link too, but it identifies several supposed jpeg files, but none have headers so cannot be viewed in any application.

I will attach one of the odd jpeg files and would be grateful if someone could have a look to see what they think. It could just be that they have been detected in error.

So, the files are definitely in there.. it's just a matter of finding the offsets..  "Just"!
[cstrike.nar.0162.zip](https://xentaxbackup.github.io/file/1430_cstrike.nar.0162.zip)
## Post #5
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2008-01-24T14:02:46+00:00
- Post Title: Counter-strike Online - Archive help please

Okay. Whilst I was driving home today, I had a moment of clarity and was thinking outside the box regarding the problem with these NAR files. 

They must have all the information in them that I would like, but it doesn't seem to be listed in any obvious way. Having managed to find wav/mp3/bik files using Extractor etc it would seem that the files aren't compressed in any way, but by the same token the files within do not appear to be named in any meaningful way.

I then thought about the format of CS mdl files and found that each file starts and ends in the same way -

[http://www.talismanisland.com/xentax/mdl_comparison.jpg](http://www.talismanisland.com/xentax/mdl_comparison.jpg)

I was wondering if it was possible to get a program to search/scan for these "attributes" in the same way as the audioripper etc work?

I've uploaded the example mdl files if that helps.

[http://www.talismanisland.com./xentax/m ... arison.zip](http://www.talismanisland.com/xentax/mdl_comparison.zip)

Can anyone please give me a pointer as to where to start with this or tell me that I am way off base?

Cheers for now and thanks for any input.

PS - I realise I've posted 5 times in the same thread, but each post was a fresh moment of clarity and inspiration!
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-25T08:09:26+00:00
- Post Title: Counter-strike Online - Archive help please

> Reply from Rusty_le_Cyborg
>
> Having managed to find wav/mp3/bik files using Extractor etc it would seem that the files aren't compressed in any way
Since wav/mp3/bik files are already compressed it wouldn't make sense to compress them again. So this doesn't tell us if compression is used for other files. It might be an indication that files aren't encrypted.

> but by the same token the files within do not appear to be named in any meaningful way.
There don't have to be filenames in the archive. You may also use a hash table. In fact, I really wonder why most games use the names nevertheless.
If you want to dig deeper into this, you may have a look at Blizzard's MPQ format, this is a real masterpiece of GRAF also using hash tables. ([http://www.zezula.net/](http://www.zezula.net/))

Many games also encrypt headers and filenames to prevent extracting them. Might also be the case here.

> I was wondering if it was possible to get a program to search/scan for these "attributes" in the same way as the audioripper etc work?
You might get yourself some sourcecode of a file scanner and modify it. But I guess what you want is a tool that actually rips those mdl files out of the archive, right? This really depends on the mdl format, if it is possible to somehow calculate its size, it is possible to rip it. I don't believe the tail is always constant, guess it's coincidence.

EDIT: But you may try TriID [http://mark0.net/soft-tridnet-e.html](http://mark0.net/soft-tridnet-e.html)
With TriIDScan you can scan your files and create signatures, so you may at least scan for them with TriID.
## Post #7
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2008-01-25T17:19:43+00:00
- Post Title: Counter-strike Online - Archive help please

> Reply from Rheini
>
> But I guess what you want is a tool that actually rips those mdl files out of the archive, right? This really depends on the mdl format, if it is possible to somehow calculate its size, it is possible to rip it. I don't believe the tail is always constant, guess it's coincidence.

Yeah it would be better to extract the mdl file in it's entirety, but I'm beginning to think this won't be possible (especially with my limited knowledge and lack of skill!)

I am pretty sure that all model files have the same small start to them, but there are a few types of model within the game, Terrorist, Counter Terrorist, VIP, etc etc. It would seem that all CT models share the same ending, all T models share the same ending, etc, but each model file seems have it's own "style".

Whether this is any use or not is anyone's guess, but the file size of a mdl file is not consistent due to the sizes of different textures etc within it.

I presume the small file I uploaded does not give any immediate clues as to anything within it? I would hazard a guess that the resource file only contain a small text file but they are known to have tga files in them, but the size would not point to this.

Thanks for the reply though as it's given me something else to try. I shall see if I can make any sense of the program you linked to and report back 

Cheers for now
## Post #8
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2008-01-27T01:43:49+00:00
- Post Title: Counter-strike Online - Archive help please

Well, unfortunately I can't get that program to do much. The scan part of it finds nothing at all.

I guess I will just have to sit tight and wait. So close to these files and yet so far!

Ah well, such is life 

If anyone happens to have any ideas, I'd love to hear them though. I can even make the large files available if it will help.

Cheers for now

PS - I have uploaded the "filesystem_nar.dll" in case that might be of any use. I would have thought it should have some useful information in it?
[FileSystem_Nar.zip](https://xentaxbackup.github.io/file/1433_FileSystem_Nar.zip)
## Post #9
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2008-01-29T23:16:37+00:00
- Post Title: Counter-strike Online - Archive help please

I've just been musing over these problems again. If anyone is still interested in having a look at the resource.nar file up in the first post.

If you change the language of a regular Steam install to Korean, it downloads the Korean language files for you.

In the resource folder of the new Korean files there are a couple of files which MAY also be in the resource.nar file. They are mostly renamed text files of one size or another.

cstrike_koreana.txt  and CareerBotFrame.res.

This may of course be a total shot in the dark again, but I don't know what else to suggest.

Cheers for now
## Post #10
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2008-02-03T01:19:49+00:00
- Post Title: Counter-strike Online - Archive help please

I am led to believe that the NAR file format is used in another Nexon game called ZerA: Imperan Intrigue. Though I don't really know anything about that game...
## Post #11
- Username: undeadwalker
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 25, 2008 12:06 pm
- Post datetime: 2008-04-25T19:55:56+00:00
- Post Title: Counter-strike Online - Archive help please

HI 

You know about gcf files? [Grid(or Game) Cache file](http://developer.valvesoftware.com/wiki/Game_Cache_File) is used in steam. Nar file seems to be repacked gcf by nexon. They use filesystem_nar.dll. there are some programs can extract gcf file, but I can't find nar format files, too. I live in korea

I'm interesting about this post
## Post #12
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2008-04-26T21:12:20+00:00
- Post Title: Counter-strike Online - Archive help please

> Reply from undeadwalker
>
> You know about gcf files?
Yes, unfortunately NAR files bear no relation to standard GCF files as confirmed by the author of GCFScape 

It seems that Nexon have done enough to stop people gaining access to these files, which is a great pity.
