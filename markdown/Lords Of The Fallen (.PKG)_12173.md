## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-30T18:51:17+00:00
- Post Title: Lords Of The Fallen (*.PKG)

Unpacker

About hashes - I have pirated game version but is not working. Unfortunately I do not know which algorithm is used. In game library i found 2 hash function djb2 and sdbm but no good results. Who knows? 
[LoFPKGUnpacker_0.0.1_r1.rar](https://xentaxbackup.github.io/file/8002_LoFPKGUnpacker_0.0.1_r1.rar)
## Post #2
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2015-01-08T23:38:36+00:00
- Post Title: Lords Of The Fallen (*.PKG)

That's cool, i was curious about LOTF since a while.
I also found Quick BMS script which does about the same as your tool but extracts .dat files from the PKG.

I hope someone will try and chew through file formats, because at the bottom game seems to use pretty straightforward formats, plus anything in patch folder will override packages, so modding is a real possibility here.
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-01-09T00:09:31+00:00
- Post Title: Lords Of The Fallen (*.PKG)

> Reply from SkacikPL
>
> That's cool, i was curious about LOTF since a while.
I also found Quick BMS script which does about the same as your tool but extracts .dat files from the PKG.

I hope someone will try and chew through file formats, because at the bottom game seems to use pretty straightforward formats, plus anything in patch folder will override packages, so modding is a real possibility here.
My tool unpack the same files that QuickBMS, just without extensions
## Post #4
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2015-01-09T01:37:37+00:00
- Post Title: Lords Of The Fallen (*.PKG)

> Reply from Ekey
>
> SkacikPL wrote:That's cool, i was curious about LOTF since a while.
I also found Quick BMS script which does about the same as your tool but extracts .dat files from the PKG.

I hope someone will try and chew through file formats, because at the bottom game seems to use pretty straightforward formats, plus anything in patch folder will override packages, so modding is a real possibility here.
My tool unpack the same files that QuickBMS, just without extensions
Though, different question is whether there is a way to get what's inside unpacked files.
## Post #5
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2018-10-08T07:35:08+00:00
- Post Title: Lords Of The Fallen (*.PKG)

Nothing new?
I'd still like to fix some Italian texts in this game. There's no need of repacker: you can just put files in "patch\" but they won't work if you alter just a single byte!
The problem is understanding that number block in blue:
[](https://postimg.cc/dZwSkbFr)
From a comparision between the French.bin and Italian.bin ([see msg here with attachments](https://zenhax.com/viewtopic.php?p=32497#p32497)) the first block is the same: FC89C5A3, next 4 bytes change between languages… If we understand that we should be able to edit the text and use it in the game simply putting the modified .bin under "...\Lords Of The Fallen\bundles\patch", skipping the unnecessary repack process.
## Post #6
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2018-10-08T17:01:04+00:00
- Post Title: Lords Of The Fallen (*.PKG)

Can you upload/send me your modified .bin file? I don't have the game, so I can't test my script for recalculating the hash.
## Post #7
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2018-10-08T18:05:25+00:00
- Post Title: Lords Of The Fallen (*.PKG)

> Reply from merlinsvk
>
> Can you upload/send me your modified .bin file? I don't have the game, so I can't test my script for recalculating the hash.
You have PM
## Post #8
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2018-10-08T18:25:28+00:00
- Post Title: Lords Of The Fallen (*.PKG)

Attached some .bin files (original, unmodified). If you need more language files tell me...
[https://nofile.io/f/aS3AAYoZTva/languages_bin.7z](https://nofile.io/f/aS3AAYoZTva/languages_bin.7z)
## Post #9
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2018-10-09T15:19:53+00:00
- Post Title: Lords Of The Fallen (*.PKG)

```
# Lords Of The Fallen language *.bin CRC fixer
# Script version: 0.2
#------------------------------------------------
idstring "\xFC\x89\xC5\xA3"		# just a test if the input file is a supported .bin file

encryption crc 0x01800063 "32 0 0 19 1 1"
get SIZE asize
xmath TXTSIZE "SIZE - 0x18"		# 0x18 = size of header
log MEMORY_FILE 0x18 TXTSIZE	# 0x18 = start of the data block
encryption "" ""

get NAME basename
get EXT extension
string NAME p= "%s.%s_FIXED" NAME EXT
get SIZE asize
log MEMORY_FILE2 0 SIZE							# create copy of file into RAM
putVarChr MEMORY_FILE2 0x04 QUICKBMS_CRC long	# write new CRC value on position 0x04
putVarChr MEMORY_FILE2 0x14 TXTSIZE long		# write text block size
log NAME 0 SIZE MEMORY_FILE2					# write new file on disk

```


EDIT: Updated script. Now it also recalculates the size of "text block".
## Post #10
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2018-10-09T17:09:03+00:00
- Post Title: Lords Of The Fallen (*.PKG)

> Reply from merlinsvk
>
> Code: Select all#------------------------------------------------
# Lords Of The Fallen language *.bin CRC fixer
#------------------------------------------------
idstring "\xFC\x89\xC5\xA3"		# just a test if the input file is a supported .bin file

encryption crc 0x01800063 "32 0 0 19 1 1"
get SIZE asize
math SIZE - 0x18  				# 0x18 = size of header
log MEMORY_FILE 0x18 SIZE		# 0x18 = start of the data block
encryption "" ""

get NAME basename
get EXT extension
string NAME p= "%s.%s_FIXED" NAME EXT
get SIZE asize
log MEMORY_FILE2 0 SIZE							# create copy of file into RAM
putVarChr MEMORY_FILE2 0x04 QUICKBMS_CRC long	# write new CRC value on position 0x04
log NAME 0 SIZE MEMORY_FILE2					# write new file on disk


Use this script on language .bin file. It will create new file with "_FIXED" extension. 
Rename it and put the fixed file into \patch folder.
 

It does work! 
It seems I can finally be able to fix broken Italian text!  
Thank you very much!

Can I ask one more thing? As you can see in [the picture above](http://forum.xentax.com/viewtopic.php?p=144832#p144832) with hex-editor starting from byte 18->end is reported (red square in the pic) the size of the whole text block in reverse order. Could you automate also that part and improve the script?
## Post #11
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2018-10-09T17:16:32+00:00
- Post Title: Lords Of The Fallen (*.PKG)

And how do you want to edit this text? By hand in hex editor?

EDIT: There has to be something else (a mean some length check or another hash) because, when I make single string bigger, recalculate the length of that string, recalculate text block size and CRC, some strings in the game are missing. 

[](https://ibb.co/jPfOZU)
## Post #12
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2018-10-09T19:07:29+00:00
- Post Title: Lords Of The Fallen (*.PKG)

Indeed there are more string checks:
[](https://postimg.cc/CRNKDVF5)
The red square byte (0x98) defines the length of the string…
BUT, there is still a problem: if I make it shorter (e.g. 95), and I turn 98->95 it still won't work, unless I replace extra bytes (since I shortened the string) with 0x00 keeping file structure (and length) intact 
Maybe we have to respect some bytes alignment when we extend/shorten strings.
## Post #13
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2018-10-09T20:19:38+00:00
- Post Title: Lords Of The Fallen (*.PKG)

> Maybe we have to respect some bytes alignment when we extend/shorten strings.

Yes, exactly. That's padding. When I added one NULL byte after my test string, all missing text was back.
But that means, you will need proper tool to recalculate all paddings and lengths. Or it will be nightmare to do it all manually.
## Post #14
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2018-10-09T20:37:20+00:00
- Post Title: Lords Of The Fallen (*.PKG)

> Reply from merlinsvk
>
> Maybe we have to respect some bytes alignment when we extend/shorten strings.

Yes, exactly. That's padding. When I added one NULL byte after my test string, all missing text was back.
But that means, you will need proper tool to recalculate all paddings and lengths. Or it will be nightmare to do it all manually.

Indeed it works as I supposed.
When I manually "pad" them (thanks for the term, didn't know how to call it ) I can safely change strings length, as explained in the picture below.
E.g.:
[](https://postimg.cc/RqL6WbZc)
I can extend/shrink the text in the cyan rectangle (even colliding the red rectangle) but then I must always add this padding at the end: 0x00000000 80000000 respecting 4bytes+4bytes and, in case, adjusting with null bytes the string length.

Yep, would be great if your script would automagically do:
- recalculate final block length (written in reverse order into the bin)
- add padding correction
- recalculate strings length (the byte before the string itself)

EDIT: there is also the padding variant 0x00000001 80000000 used after dialogue strings...
## Post #15
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2018-10-09T20:42:32+00:00
- Post Title: Lords Of The Fallen (*.PKG)

I think that repacker/converter from .bin to .txt and back would be better. My script is only for the final stage - CRC fixing.
## Post #16
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2018-10-31T18:46:28+00:00
- Post Title: Re: Lords Of The Fallen (*.PKG)

> Reply from merlinsvk
>
> I think that repacker/converter from .bin to .txt and back would be better. My script is only for the final stage - CRC fixing.Can you explain me more about this CRC? I'm not familiarized with quickbms encryption, more precisely, what that two values means: 
```
0x01800063 "32 0 0 19 1 1"
```
## Post #17
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2018-10-31T18:52:36+00:00
- Post Title: Re: Lords Of The Fallen (*.PKG)

I have no idea. I just used Aluigi's CRC scanner and these values were in the results.
## Post #18
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2018-11-01T06:45:59+00:00
- Post Title: Re: Lords Of The Fallen (*.PKG)

Thanks, I'll ask about it to the aluigi.
