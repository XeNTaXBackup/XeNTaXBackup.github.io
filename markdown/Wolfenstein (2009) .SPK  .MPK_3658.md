## Post #1
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-08-20T06:05:17+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

I tried to unpack the archives of the new Wolfenstein game and thought it would be as easy as all IDtech based games(zip archives)... however this time raven build their own simple format...

there are .SPK (Singlepack?) files with one file inside and .MPK (Multipack?) with multiple files inside

i used offzip -a with standart settings first on a .MPK file and got multiple smaller zlibbed chunks... each of therse chunks then contains an amount of files (1 byte in the archive = number of files) after that follows the filetable and after that the raw data.

i hope this can be automated easily cause unpacking and unpacking again is highly annoying 

i don't have example archives right now(maybe someone else can upload some? ) since i'm at work but i'll upload some later when im home again...
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-08-20T10:45:00+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

I can already unpack the music, but i cant for the 360 archives;

[http://www.megaupload.com/?d=0JG22HON](http://www.megaupload.com/?d=0JG22HON)
## Post #3
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-08-20T13:42:16+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

i can unpack all files in the spk / mpk's (pc version) but it's tedious work :/

i dunno if quickbms can handle this on its own? 

maybe with a little batchfile
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-20T14:13:51+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

It should not be to hard once I get a sample file ill look at it for you.
## Post #5
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-08-20T16:58:15+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

here it is:
[http://www20.zippyshare.com/v/89027429/file.html](http://www20.zippyshare.com/v/89027429/file.html)

some files from the castle map, 47mb... couldn't get it smaller :/

also i think that MPK means Master Pack and SPK means Slave Pack or something like that xD
## Post #6
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-08-20T20:57:40+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

I'm currently working on an unpacker for MPK/SPK-files. I'm almost finished, but I have problems to restore the original file extensions, because they aren't stored in the SPK/MPK-ZLIB-streams. I could need any help to finsish the  translation table for these sub-formats.
As far as I could find out there are these ZLIB-sub-streams within the MPK/SPK-files:

```
;DECL -> decls
;ENTS -> entities
;MODL -> md5r
;PROC -> procb	
;TXTR -> dds

```

Once I know what extensions these files have I will provide an unpacker for it. Please contact me per PM or (better) put an answer to the "Little Extractor"-thread.
Thank you.
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-08-21T02:25:57+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

Well all i know is that the music files are mp3 original.
## Post #8
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-08-22T09:57:47+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

> Reply from asmxtx
>
> I could need any help to finsish the  translation table for these sub-formats.
As far as I could find out there are these ZLIB-sub-streams within the MPK/SPK-files:
Code: Select all"AASS","BRAI","DECL","ENTS","HKXA","HKXR","HKXS","MODL","PBBF","PROC","SKEL","SNDS","TXTR"
;DECL -> decls
;ENTS -> entities
;MODL -> md5r
;PROC -> procb	
;TXTR -> dds

have you tried looking in the multiplayer pak files? those can be opened normally and use the same folder structure... 

and because we can read most of the path in the singleplayer paks you could check the extensions that are in the multiplayer paks under the same folder?
## Post #9
- Username: Frosty
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 15, 2009 5:15 am
- Post datetime: 2009-08-24T23:09:33+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

Whats in the .mpk and .spk files? and does anyone know whats with all the cachemaps files?
## Post #10
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-08-24T23:41:38+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

> Reply from Frosty
>
> Whats in the .mpk and .spk files? and does anyone know whats with all the cachemaps files?
Seems like it contains only map-specific data: sounds, music, textures, etc.
## Post #11
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-08-26T01:15:57+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

Here's an experimental unpacker for the decls files.
[WOLF2DEC.RAR](https://xentaxbackup.github.io/file/2316_WOLF2DEC.RAR)
## Post #12
- Username: Frosty
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 15, 2009 5:15 am
- Post datetime: 2009-08-26T08:40:07+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

Where are the mulitplayer paks at?
## Post #13
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-08-26T17:30:46+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

> Reply from Frosty
>
> Where are the mulitplayer paks at?

```
WOLFDIR\MP\base\pak1.pk4
WOLFDIR\MP\base\pak2.pk4
WOLFDIR\MP\base\pak3.pk4
WOLFDIR\MP\base\zpak_english000.pk4

```
## Post #14
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-08-26T23:29:47+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

Here are all (15) available file types WOLF2 seems to access (as far as I could find out).
To finish my extractor I could need some help regarding proper assignable file extensions.

```

```


```
BRAI -> ???
DECL -> decls
ENTS -> entities                    
HKXA -> ???
HKXR -> ???
HKXS -> ???
MODL -> md5r                        
PBBF -> MD5RBin (Not sure)
PROC -> procb
SGFX -> ???
SKEL -> ???
SNDS -> mp3 (Not sure)
TXTR -> dds
VIDO -> bik (Not sure)

```
## Post #15
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-08-27T06:20:29+00:00
- Post Title: Wolfenstein (2009) .SPK / .MPK

I know at 100% this items

> SNDS -> mp3
>
> VIDO -> bik

Still looking
## Post #16
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-08-27T23:30:59+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

Hi all,
I've updated my program.
The resulting file structure is not compatible with that produced by the previous experimental unpacker I released.
But, now the program supports packing the files back into a .decls container, so, you get a lame, but fully functional .decls packer/unpacker.
Note: the packed file won't be identical to the originals in Wolfenstein 2, but it will work. I tested only with these two files though:

```
<WOLF>\SP\base\assets.pk4\maps\game\global\global_vo_english.decls
```

If you find bugs, let me know and if I have time, I might fix them.

*Update*
I was contacted by a user named HeyBuddy on another forum. Here's what he had to say:

> Hey Csimbi,
>
> I contacting you kinda via a side route, what I'm really interested is your posts on xentax, specifically your Wolf2Dec. It's unfortunate that xentax is is set up for admin-activates-account, and for whatever reason hasn't done mine. In this case it is preventing genuine feedback and information.
>
> 
>
> Anyway, to the point. Your Wolfenstein globals unpacker/packer tool unfortunately seems to be a non stand alone build from c++ builder 6 or something? It's complaining about missing files, vcl60.bpl among others.
>
> Naturally this problem won't come up on your system since you have them installed with the compiler.
>
> Due to the obscurity of the files I haven't had much luck finding working copies online.
>
> 
>
> So, to restate, while your wolf2dec has 27 downloads on xentax, I'd guess that no one that's downloaded can use it, and because of xentaxs registration policy can't post to the thread to tell you.
>
> 
>
> I appreciate your work on this, and hopefully you can resolve the tool problem.
>
> 
>
> Secondly some feedback to asmxtx on the same xentax post, if you could post this I would be very grateful:
>
> AASS -> aas28
>
> BRAI -> brain
>
> DECL -> decls
>
> ENTS -> emap
>
> HKXA -> ???
>
> HKXR -> ???
>
> HKXS -> ???
>
> The only file extension I've seen referenced is .HKX, so this is a puzzle.
>
> MODL -> md5r
>
> PBBF -> MD5RBin (Not sure)
>
> PROC -> proc
>
> SGFX -> tga or dds (not sure), possibly the engines texture loader handles differences so we won't see differentiation in the file system
>
> SKEL -> ???
>
> SNDS -> mp3 (Not sure) - possibly ogg, should be testable on extraction
>
> TXTR -> dds
>
> VIDO -> bik
>
> Wolf SP is a distant branch of id tech 4, it's nearest ancestor is Quake 4, the changes to the filesystem are significant however due to id tech originally being a pc engine and wolf being multiplatform.
>
> Wolf MP is of the ETQW branch of id tech 4 (and handled by a separate team than sp), so it's not really useful to look at file wise.
>
> There's not much information of the files being streamed from the engine, no useful debug cvars (while there is for normal file access).
>
> 
>
> I think a preliminary release of the asmxtxs extractor so we could examine the files would be useful.
To amend the first part of the problem, I have uploaded the program with the RTLs properly linked into the executable (well, I hope so, if still missing something, please let me know).
The second half if for asmxtx, so I let him decide what to do with the second half of the message.

PS. I am having tons of fun with the modded weapons; it puts the meaning of "shooter" back into FPS as opposed to "first person slomo" 
[WOLF2DEC.RAR](https://xentaxbackup.github.io/file/2334_WOLF2DEC.RAR)
## Post #17
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-08-30T19:27:00+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

I tried the wolf2dec, but..it works? i tried with the menu.mpk but don't works (or i dont' know how to make it work)

i did:

> WOLF2DEC.EXE u menu.mpk testing
and i get

> PLZ OPEN FILE "menu.mpk"?
>
> O NOES
>
> VISIBLE MESSAGE
>
>   Error loading input file: menu.mpk.
>
> KTHXBYE
## Post #18
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-08-30T22:27:31+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

> Reply from Savage
>
> I tried the wolf2dec, but..it works? i tried with the menu.mpk but don't works (or i dont' know how to make it work)
Right. Because wolf2dec is not for SPK/MPK/whatever files; it is only for decls files.
Decls files are containers where the game resources (scripts and other text formats) are merged and indexed by clauses for fast access.
Take a look at <WOLF>\SP\base\assets.pk4\maps\game\global\global.decls - and you will see what I mean.
## Post #19
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-08-30T23:55:00+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

@Csimbi: ([viewtopic.php?p=31437#p31437](http://forum.xentax.com/viewtopic.php?p=31437#p31437))

Are you really sure that these identification assignments are correct? ->

```
AASS -> aas28 (is this really true?)

```


PBBF -> MD5RBin - If "HeyBuddy" got this by himself and not by following my xentax-post I'll get it as a fact.

"SGFX" is in no case a TGA-graphic file.
"SNDS" might be ".MP3" for 99%.

@HeyBuddy:
I did have the same difficulties like you when I tried to sign this site. I gave up hope until XENTAX granted me access many days (or some weeks) later. Maybe you should simply wait...
## Post #20
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2009-08-31T20:59:40+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

XFGS are *.GFX files (flash files designed with Scaleform GFx);
SNDS are *.MP3 files (look at end of each sound file: LAME 3.96.1 encoded).
## Post #21
- Username: NBayer
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 30, 2009 1:10 am
- Post datetime: 2009-09-30T17:53:04+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

Most of you have probably found that tool here already: Wolfenstein SPK/MPK Extractor at: daedalus-tools.mx.tc

I tried contacting the author of his webpage, but my messages over the contact form and guestbook are not coming through (Array( [captcha] => CAPTCHA invalid.). Of course I typed in the Captcha correct .

Maybe someone of you knows the answer: How relyable is that extractor? There was still some confusion in this thread on which file extensions are used for which files? Is that solved by now?

In case the author of the tool reads this: It would be very helpful if that tool would be able to get ALL spk/mpk from Wolfenstein and extract it in one folder. That would save a lot of time.

Thanks!
## Post #22
- Username: bellox
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 30, 2009 4:58 am
- Post datetime: 2009-10-01T15:50:49+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

@NBayer hi, i guess since i'm the author:

How relyable is that extractor?
well, to my knowledge it extracts the files correctly, allthough some extensions are still unknown, but i doubt that you could do anything with the unknown files, since they are mostly compiled

the reason why not all files are extracted into one folder: the spk/mpk files contain paths + filenames, so the extraction is done accordingly
## Post #23
- Username: NBayer
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 30, 2009 1:10 am
- Post datetime: 2009-10-02T00:51:20+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

Thanks for your fast reply.

I didn't formulate that very precise. It would be great if it would take all spk/mpk it can find from the Wolfenstein folder and extract it to a folder including the following recursive directories that are encoded in the spk/mpk files. So in the end e.g. under maps/game/... you would have all map files from all single player maps etc.;

Thanks!



> Reply from bellox
>
> 

the reason why not all files are extracted into one folder: the spk/mpk files contain paths + filenames, so the extraction is done accordingly
## Post #24
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-08T20:22:16+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

Just to crash in on a discussion here, I'd like to briefly mention the PK4 files, which seem not to be standard ZIP files. As extraction fails. Does anyone know why? Password?
## Post #25
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-10-09T01:03:02+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

> Reply from Mr.Mouse
>
> Just to crash in on a discussion here, I'd like to briefly mention the PK4 files, which seem not to be standard ZIP files. As extraction fails. Does anyone know why? Password?
Because they changed the structure a bit; these are still valid ZIP archives though.
You can use PKZipFix to fix the ZIP structure - or WinRAR.
When you create the archives, you can use any ZIP packer.
## Post #26
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-09T05:58:05+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

Thanks for the tip! Then I'll write a little app to fix the structure. Else I would have searched for a password somewhere, which is a lot more painstaking.
## Post #27
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2009-10-09T22:06:40+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

That would be handy, thank you.
## Post #28
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-12T20:37:34+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

> Reply from asmxtx
>
> 
@HeyBuddy:
I did have the same difficulties like you when I tried to sign this site. I gave up hope until XENTAX granted me access many days (or some weeks) later. Maybe you should simply wait...

What is up with that? I only just read the last comment. People MUST write a REASON TO JOIN while signing up. Bots are stupid and don't know this extra field, so won't fill it in. All that sign up without filling in that field will not have their registration entered in the database. We need a text written there, blanks are ignored or not saved.
## Post #29
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-12T20:39:40+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

On another note, asmxtx, did you find out the format of the MPK files? The directory at the top of each file seems to be padded. Do you know the padsize?
## Post #30
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-26T23:25:02+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

what about the files which start with the sequence of bytes "0f f6 12" ?
for example that music_church_combat1_lp.spk file which was linked some posts before
## Post #31
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-09-23T12:31:54+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

Anybody know where are the text files for the Single-Player?

I know where are the text files for the Multiplayer but i cannot find the texts for SP.

The fonts are in the - English.spk but where are the t. files?
## Post #32
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-11-08T07:32:14+00:00
- Post Title: Re: Wolfenstein (2009) .SPK / .MPK

Sorry for necroposting, but are there programs that can decompress/unpack Wolfenstein (2009) .spk/.mpk files?

samples:
[https://mega.nz/folder/lXpXkZwS#Vm8ThEjrESswMmsjIixfDA](https://mega.nz/folder/lXpXkZwS#Vm8ThEjrESswMmsjIixfDA)
