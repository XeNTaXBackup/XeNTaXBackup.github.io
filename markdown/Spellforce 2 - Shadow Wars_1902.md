## Post #1
- Username: PierreDeVega
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 14, 2006 11:32 pm
- Post datetime: 2006-05-14T16:25:40+00:00
- Post Title: Spellforce 2 - Shadow Wars

Hello

I'am need edit pak and cff files in Spellforce 2 game.

Demo: [ftp://download20.gamershell.com/pub/Win ... 2_demo.zip](ftp://download20.gamershell.com/pub/Windows/public.gamershell.com/patsboom/demo/sf2_demo.zip)

Please help me.

Thanks
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-15T05:01:33+00:00
- Post Title: Spellforce 2 - Shadow Wars

Downloading...
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-15T08:49:01+00:00
- Post Title: Spellforce 2 - Shadow Wars

lots of standard formats in those archives.
mp3 files, xml files, wav, dds textures etc etc.

ripped with jaeder naub, nothing is packed or encrypted.
and i think mr.mouse would be able to create a plugin for the archive kinda fast 

dont use jaeder naub to rip mp3 or xml from these archives though, it was done with my
own testversion that is not released yet and will find more stuff than the released version do right now :/
## Post #4
- Username: Stormer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 20, 2006 10:33 am
- Post datetime: 2006-06-20T02:38:05+00:00
- Post Title: Spellforce 2 - Shadow Wars

Any luck with this guys?  Strobe, your program does a nice job of ripping the texture files (.dds) out of the .pak files but I can't seem to get at the models.  Incredible work both of you on your software.  If anyone can unpack these new .pak files, you guys will!
## Post #5
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2006-10-16T11:58:24+00:00
- Post Title: Spellforce 2 - Shadow Wars

Hi
I found .pak extractopr for Spellforce 2 in thic forum:

```
http://spellforce.jowood.com/forum/showthread.php?t=41575
```


There is fukll working pak extractor with readme and some hints
You have to be registered to downlaod it

Some talks about it:

> Hi
>
> 
>
> Finally I can present a working pak file extractor. With it you can extract the .pak files located in the "SpellForce 2\base\pak" folder.
>
> 
>
> If you want to mod some files you dont need a repacker. You just need to place the file with the correct folder path under "SpellForce 2\base\" because SF2 reads these files preferred against the files in the pak archive.
>
> 
>
> In the package there is also a short manual included.
>
> 
>
> Credits
>
> Programmed by Match
>
> File Format Research: Match, Starcraftfreak
>
> 
>
> Have fun,
>
> Kubi
## Post #6
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-10-19T09:44:43+00:00
- Post Title: Spellforce 2 - Shadow Wars

> Reply from PierreDeVega
>
> Hello

I'am need edit pak and cff files in Spellforce 2 game.

Demo: ftp://download20.gamershell.com/pub/Win ... 2_demo.zip

Please help me.

Thanks
Little tip, this archiv used Zlib in the footer data, 
more may can i not say.
Sincerely xennex
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-19T20:38:53+00:00
- Post Title: Spellforce 2 - Shadow Wars

Okay, here's a plugin for MexCom. Just copy it to the plugins/pak folder of MexCom. This will open Spellforce PAK files and extract files for you.

It was actually a simple format. 

```
// Header

byte {3}  - Magic Word "PAK" 
byte      - Version number ?
uint32    - Offset to tail
uint32    - Uncompressed size of tail
uint32    - Compressed size of tail

byte{}     - File data

// Tail - Zlib compressed, first uncompress, then :

uint32    - Number of resources

  // For each resource
  uint32    - Size of filename
  byte{}    - Filename (string)
  uint32    - Offset of file (start)
  uint32    - End-offset of file (end)

```

[example.JPG](https://xentaxbackup.github.io/file/939_example.JPG)

[spellforce2.zip](https://xentaxbackup.github.io/file/938_spellforce2.zip)
## Post #8
- Username: Hurvi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 19, 2006 9:24 pm
- Post datetime: 2007-01-23T07:13:38+00:00
- Post Title: Spellforce 2 - Shadow Wars

When I use this plugin, can it extract text files? Because I heard it is a big problem to get out (and then get back) text files - if you want to translate them.
## Post #9
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2008-11-07T21:07:49+00:00
- Post Title: Spellforce 2 - Shadow Wars

PakBrowser

I found this tool accidentally, while I was searching on Google for a different tool. I guess this is something the "I'm feeling lucky" button on the Google page should do - give me what I really want 
Anyway, this tool was made by TimeSlip, and it requires the Microsoft .NET Framework 2.0 to be installed on your PC.

It allows you to unpack files one by one, and create Pak files, too (!).
Just unpack and execute from a directory of your choice.

Here's original post from [http://timeslip.chorrol.com/b_07.html](http://timeslip.chorrol.com/b_07.html)

> 28th of February 07 (Updated)
>
> 
>
> I had an oem copy of spellforce 2 free with my PC. I'm not usually a huge fan of RTS games, but spellforce 2 was enough of an RPG to be worth playing anyway.* It's not without its own problems though; the first thing I noticed after installing it was that none of the bik movies had any sound. I managed to fix that by replacing the old (v1.5.21.0) version of the bik dll provided with spellforce 2 with the newer (1.7.3.0) version that came with oblivion. I'm guessing that's not a common problem, since it wasn't mentioned in the FAQ, hasn't been fixed in the two patches that have been released so far and didn't seem to be mentioned in the first couple of pages of the tech support forums. The second problem was that on a specific level near the end of the single player campaign, moving the camera to a specific part of the screen caused an instant crash. That one turned out to be self inflicted though; I was using a nocd patch, and using the original exe fixed the crash, so it just meant that I had to play with the CD in for a level.
>
> 
>
> Anyway, after playing for a bit I ended up trying to mod it. For one test I was trying to do, I needed a pak creator.** There's already an extractor ( http://spellforce.jowood.com/forum/s...ad.php?t=41575 ) floating around, but oddly enough nothing to create them with,^ so I spent an hour knocking one up. Luckily, compared to bsa's, the pak file format turned out to be relatively simple. (No need to spend ages with a debugger trying to work out weird hashing algorithms this time...) If anyone one else wants it, you can download it here ( http://timeslip.chorrol.com/current/PakBrowser.7z ) . As well as creating paks, you can also browse existing ones, and extract single files from them instead of unpacking the whole thing. (I didn't want to sign up to the spellforce forums just to download one file, so I haven't tested the original unpacker, but it looks like it unpacks everything without giving you any options, and a few people were having problems with it.)
>
> 
>
> Edit: Looks like there was a problem with that pak browser that crashed it when trying to open pak 11. It's fixed now, as are a couple of other things to do with the double click file preview.
>
> 
>
> *Plus the oem version has the added advantage that it doesn't ship with starforce. My previous starforce problems turned out to be another oem game. Slightly insanely, that particularly game doesn't require the CD in to play anyway, and neither does it use a licence key, even for online play...
>
> 
>
> **Pak's are the spellforce 2 equivelent of bsa's.
>
> 
>
> ^In a similar way to morrowind/oblivion, spellforce 2 will preferentially load files from its base directory if they have the same names as files contained in a pak, so a pak creator isn't essential to modding. Also like morrowind/oblivion, it's still nice to have anyway.
## Post #10
- Username: Dristok
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-07T22:44:38+00:00
- Post Title: Spellforce 2 - Shadow Wars

Nice find!!

I've attached it here, for safe keeping 
[pakbrowser.zip](https://xentaxbackup.github.io/file/1729_pakbrowser.zip)
