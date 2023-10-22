## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-02-03T22:15:44+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

Right, on popular demand, I will post any new scripts for MexScriptor here. 

Copy the scripts into notepad, recopy them and then paste into MexScriptor. It may be that there are some left-over [enter]s at the end of each line. Remove them if necessary. (Remove everything that comes after a ; sign). 

Explanation of these symbols :

[X]  added in a new release
[ ] to be added in future releases

Latest entry: Port Royale *.CPR files 

>>>>>>>>>>>>>>>>>>>>>>>>
[ ] - Name : Port Royale - CPR files
Info : Extract and Replace - Needs new executable (v3.9.71)
Date : 26-4-2004
SCRIPT:

ImpType Standard ;
IDString 0 ASCARON_ARCHIVE ;
Set D Long 40 ;
GoTo D 0 ;
Get FC Long 0 ;
Get S Long 0 ;
For T = 1 TO FC ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get S Long 0 ;
Get FN String 0 ;
Log FN FO FS FOO FSO ;
Next T ;

>>>>>>>>>>>>>>>>>>>>>>>>
[ ] - Name : Mechwarrior 4  :Mercenaries - MW4 files

Info : Extract only, not complete, does not decompress any files in there that need decompression. 
Date : 3-2-2004
SCRIPT:

IDString 0 #VBD ;
Get D Long 0 ;
Get D Long 0 ;
Get START Long 0 ;
Get Item_Count Int 0 ;
Get Item_Count Int 0 ;
For T = 1 To Item_Count ;
GetDString TIME 8 0 ;
Get OS Long 0 ;
Get NS Long 0 ;
Get RO Long 0 ;
Get IC Int 0 ;
Get BS Byte 0 ;
GetDString IN BS 0 ;
Set IO Long RO ;
Math IO += START ;
Log IN IO NS 0 0 ;
Next T ;

>>>>>>>>>>>>>>>>>>>>>>>>

[ ]Name : Prince of Persia : Sands of Time PopData.BF format

Info : Only verified to work on that particular file, Extract Only
Date: 5-2-2004
SCRIPT:

Get ST Long 0 ;
Set STE Long ST ;
Math STE += 4 ;
For T = 0 To ST ;
Get DOff Long 0 ;
SavePos OffOff 0 ;
Get Off Long 0 ;
Math Off += STE ;
SavePos SizeOff 0 ;
Get Size Long 0 ;
Get D Long 0 ;
Get BS Long 0 ;
GetDString FN BS 0 ;
Log FN Off Size OffOff SizeOff ;
Math T -= 1 ;
Math T += 20 ;
Math T += BS ;
Next T ;

>>>>>>>>>>>>>>>>>>>>>>>>

[ ]Name : City of Heroes *.PIGG format

Info : Will need new executable to work, wait until new release or get this unsupported fix : [viewtopic.php?t=576](http://forum.xentax.com/viewtopic.php?t=576)
Date: 10-3-2004

ImpType Standard ;
ComType ZLib1 ;
Set D Long 12 ;
GoTo D 0 ;
Get C Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Set J Long 24 ;
SavePos D 0 ;
Set JF Long 48 ;
Math JF *= C ;
Math JF += 28 ;
For T = 1 To C ;
SavePos UCSO 0 ;
Get UCS Long 0 ;
Get D Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos D 0 ;
Math D += J ;
GoTo D 0 ;
SavePos CSO 0 ;
Get CS Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
SavePos D 0 ;
GoTo JF 0 ;
Get FNS Long 0 ;
GetDString FN FNS 0 ;
SavePos JF 0 ;
GoTo D 0 ;
CLog FN FO CS FOO CSO UCS UCSO ;
Next T ;

>>>>>>>>>>>>>>>>>>>>>>>>
## Post #2
- Username: rav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 28, 2004 11:54 am
- Post datetime: 2004-02-28T03:55:55+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

"Info : Extract only, not complete, does not decompress any files in there that need decompression."

I might be making by newbieness obvious but how do I decompress the files that need decompression? Specifically I'm after the script files (*.abl) which are just text files. When I open them up in a text editor all I see is jibberish. Any help would be greatly appreciated.
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-02-28T07:54:37+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

> Reply from rav
>
> "Info : Extract only, not complete, does not decompress any files in there that need decompression."

I might be making by newbieness obvious but how do I decompress the files that need decompression? Specifically I'm after the script files (*.abl) which are just text files. When I open them up in a text editor all I see is jibberish. Any help would be greatly appreciated.

If I knew I would have done it.
## Post #4
- Username: rav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 28, 2004 11:54 am
- Post datetime: 2004-02-28T08:29:27+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

Thanks for the quick reply, I thought there might be some standard text file compression or something.

Anyway, if I work it out I'll post it here.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-02-28T09:17:44+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

> Reply from rav
>
> Thanks for the quick reply, I thought there might be some standard text file compression or something.

Anyway, if I work it out I'll post it here.

Much obliged!
## Post #6
- Username: rav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 28, 2004 11:54 am
- Post datetime: 2004-02-28T23:45:22+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

Ok so I've managed to get both compressed and uncompressed copies of a few of these text files, there must be a systematic method for working out the algorithm.... right?! :)

Compression 101 is harder than I had thought.
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-02-29T09:07:57+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

That's true. You could now let lose known compression algorhitms/compressors on the uncompressed ones and compare the resulting compressed files with the compressed files in the game.  Good job, how did you obtain them??
## Post #8
- Username: Ralph0
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Mar 01, 2004 10:43 am
- Post datetime: 2004-03-01T02:51:27+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

*post deleted*

heh, I think that may not be legal.
## Post #9
- Username: rav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 28, 2004 11:54 am
- Post datetime: 2004-03-01T03:37:29+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

I was able to get uncompressed and compressed files by making custom missions, nothing complicated. :)

The following methods of compression don't seem to bear any resemblance to the one mw4 uses: zip, cab, bh, bz2, gz, jar, lha, 7z, bga, ace, arj, rar and yz1.

Thanks for the info Ralph but I think I'd be getting even further out of my depth with ASM. It's annoying too because one of the modding groups has the decompression figured but are playing the "it's my toy and you can't have it" game.
## Post #10
- Username: Ralph0
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Mar 01, 2004 10:43 am
- Post datetime: 2004-03-01T03:45:17+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

What kinds of uncompressed files? Are the uncompressed files understandable enough to edit?
## Post #11
- Username: rav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 28, 2004 11:54 am
- Post datetime: 2004-03-01T04:34:24+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

The ones I am interested in are just scripting files, so yes for them being understandable when uncompressed.
[mw4script.zip](https://xentaxbackup.github.io/file/7_mw4script.zip)
## Post #12
- Username: Ralph0
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Mar 01, 2004 10:43 am
- Post datetime: 2004-03-01T04:52:21+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

Interesting.

But I think when making missions you only get mission-related uncompressed files, no? 

Or do you get every file in the game uncompressed?
## Post #13
- Username: rav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 28, 2004 11:54 am
- Post datetime: 2004-03-01T05:45:58+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

> Reply from rav
>
> I was able to get uncompressed and compressed files by making custom missions, nothing complicated. :)

The only uncompressed files I have are ones I put in to custom missions.
## Post #14
- Username: Ralph0
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Mar 01, 2004 10:43 am
- Post datetime: 2004-03-01T05:58:34+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

I found an interesting page on different file compressions: [http://ce.et.tudelft.nl/~robbert/sparse ... ssion.html](http://ce.et.tudelft.nl/~robbert/sparse_matrix_compression.html)

also: [http://www.kyz.uklinux.net/packers.php](http://www.kyz.uklinux.net/packers.php)
## Post #15
- Username: rav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 28, 2004 11:54 am
- Post datetime: 2004-03-06T04:05:32+00:00
- Post Title: SCRIPTS - SCRIPTS - SCRIPTS ! GET THEM HERE !

I'm still messing around with these mw4 files and I've managed some basic modding by just renaming and moving around the compressed files. With multiex to extract and mw4append to append there are a few things possible. [http://www.mektek.net/sections.php?op=v ... &artid=122](http://www.mektek.net/sections.php?op=viewarticle&artid=122)

I've found a problem with the bms script tho.... it isn't able to extract one file from every saved game. In every saved game there is a file {Lancemates} that gives a 'Corrupted file info' message when I click on it and when I try to extract it. Don't know what's going on there....

As far as the compression algorithm is concerned, I'm pretty sure it isn't a dictionary method. Changing the uncompressed file in a systematic way does not change the compressed file in a systematic way. There also seems to be a minimum file size before the file is actually compressed.
## Post #16
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-10T20:39:48+00:00
- Post Title: 

Are you sure the {Lancemates} file is not zero or bigger than the actual GRA?
## Post #17
- Username: rav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 28, 2004 11:54 am
- Post datetime: 2004-03-10T23:01:04+00:00
- Post Title: 

The {Lancemates} file is not of zero length, but I see now that the file after is always a zero length file called {Mission}. There aren't any corruption errors when clicking on or trying to extract the {Mission} file, it's just always the file before it, {Lancemates}, that has problems.

I would attach a sample save game file if I wasn't at work.... maybe I should install mw4mercs here *grin*.

I tried doing lots of different things in the game to make the {Mission} file actually have content but couldn't, wonder why it is even there?!
## Post #18
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-11T07:55:38+00:00
- Post Title: 

It may just be a label, or a map name, that the game uses. Or where the resources were saved originally. 

Still, if it is always the file after that is zero length, perhaps in Options you can disable the "ascendingly" check and try again. Also, check the "ignore 0 sized files" Or perhaps you already did.
## Post #19
- Username: rav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 28, 2004 11:54 am
- Post datetime: 2004-03-12T06:18:02+00:00
- Post Title: 

The "ascendingly" check did the trick, thanks.

Problem is now I'm having problems repacking them without the game crashing when I try to use the repacked files. I'm using mw4append (linked earlier) to pack the files after I change them but I think it really only does what it says (append!) and misses something in the header. Is it easy for you to change the bms so that multiex can be used to pack mw4 files as well?
## Post #20
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-12T09:33:24+00:00
- Post Title: 

I dunno if it will work. I can give it a shot, but can't this mw4append create new ones? It can only update existing ones?
## Post #21
- Username: rav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 28, 2004 11:54 am
- Post datetime: 2004-03-14T22:11:52+00:00
- Post Title: 

It can only update existing ones. Any mw4 file that mw4append creates can be opened and extracted by multiex fine - but not by the actual game, it just crashes to the desktop. The game must be more pedantic about the header than multiex.

I've checked files by extracting them and using mw4append to put them back together. The only difference in the file is the header (or whatever you call the bit that lists the archive's contents). The real files seem to have extra symbols between the archived file names, go figure :/
## Post #22
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-14T22:27:14+00:00
- Post Title: 

Interesting. You say the "real" files, so the "retail" files, have EXTRA symbols between the filenames?

Would it be possible to attach an area from the header of both the "real" file and the "appended" one with files extracted by MultiEx? It might give me a clue, perhaps I have made a mistake in the script that I should fix first.
## Post #23
- Username: rav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 28, 2004 11:54 am
- Post datetime: 2004-03-15T02:21:30+00:00
- Post Title: 

As raw text they look identical but it's easy to see all those magic symbols in a hex editor.
[savegame.zip](https://xentaxbackup.github.io/file/10_savegame.zip)
## Post #24
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-15T07:00:55+00:00
- Post Title: 

OKay, well, this problem lies with the program you are using, mw4append. It's just not written to modify these Merc files. It doesn't handle compressed files! You see, some files in there are compressed, and in the original file there will be two size variables for each resource, uncompressed size, and compressed size. If both are equal then the resource in question is not compressed. 
MultiEx Commander extracts the files WITHOUT decompressing them first, so you will end up with a mix of uncompressed and compressed files. mw4append just puts them back, not caring for compression. So it will put a compressed file back and set the size variables the same (mistake).
The game will then load it up and try to use that compressed file as an uncompressed file. This obviously fails.
## Post #25
- Username: sharok
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 14, 2005 8:21 pm
- Post datetime: 2005-04-14T12:29:14+00:00
- Post Title: 

Hi there,

I'm quite glad to know that there are people hacking away at MechWarrior 4 files.
I am in the process of trying to get a grip on weapon data from the core.mw4 file for MW4:Mercs.
Has anyone understood how the weapon descriptors work ? I cannot seem to find any relationship between the file contents and the stats I know concerning the given weapon.
Could someone give me a pointer (or three) ? I'd like to add new variants of the weapons. Of course, unusable in multiplayer, but humor me, OK ?

Sharok.
## Post #26
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-09T12:44:35+00:00
- Post Title: 

The Witcher simple BIF extraction script for MultiEx Commander

[http://www.xentax.com/?p=154](http://www.xentax.com/?p=154)

Enjoy!
## Post #27
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-11T06:35:33+00:00
- Post Title: 

[http://www.xentax.com/?p=156](http://www.xentax.com/?p=156)

Jagged Alliance 2 Extractor/Importer script for MultiEx Commander.
## Post #28
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2007-12-17T07:25:12+00:00
- Post Title: 

> Reply from rav
>
> "Info : Extract only, not complete, does not decompress any files in there that need decompression."

I might be making by newbieness obvious but how do I decompress the files that need decompression? Specifically I'm after the script files (*.abl) which are just text files. When I open them up in a text editor all I see is jibberish. Any help would be greatly appreciated.

the .abl file is just a txt file?  Have you opened one of these successfully before?  It sounds like if you open them in notepad and all you see is jibberish it's most likely coded, the ppl developing the game probably have a coding utility that allows them to export into the game's abl format.  Either that, or like you mentioned it may be compressed still, which means you'll have to decompress it.
## Post #29
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-07-23T20:18:32+00:00
- Post Title: 

[blog/](http://forum.xentax.com/blog/) Some new scripts at the blog.
## Post #30
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-03-10T22:43:36+00:00
- Post Title: 

```
#SAMPLES.CAT
ImpType Standard ;
SavePos ST 0 ;
Get FileNum Long 0 ;
Math FileNum /= 2 ;
Math FileNum /= 4 ;
GoTo ST 0 ;
For T = 1 To FileNum ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Set FN String T ;
String FN += ".bin" ;
Log FN FO FS FOO FSO ;
Next T ;

```


For X-COM UFO Defense / Enemy Unknown.
