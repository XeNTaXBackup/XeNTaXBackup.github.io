## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-06-16T00:04:56+00:00
- Post Title: PS2 Valkyrie Profile 2 SLZ help

I come across to SLZ type 3 which is unsupported in QuickBMS. I am quiet sure it is a kind s of LZ variation.
Could someone take a look for it, please!

[Here is some examples](http://www.sendspace.com/file/4zd02w)

Thanks
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-06-16T07:59:33+00:00
- Post Title: PS2 Valkyrie Profile 2 SLZ help

OK, I found something that the compression is in block fromat!
2-bytes(16-bits) for compression Flag
32-bytes(16*2) for compression data

so for a compression flag = 1; read 2-bytes of uncompression data!
But no cue on compression flag = 0???

And I am not quite figure out the flag is low bit first or high bit first!?

Any help is appreciated. Thanks
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-06-16T09:03:59+00:00
- Post Title: PS2 Valkyrie Profile 2 SLZ help

You should try to obtain the uncompressed file from a ramdump or a savestate, that will help for sure
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-06-16T20:03:33+00:00
- Post Title: PS2 Valkyrie Profile 2 SLZ help

Thank you for the advice but I am unable to run any emulator in my computer! And there is no filename in the archive so it is almost impossible to find it in ram!!!

Anyway I think I had figured out the format now!

WORD(2-byte) compression Flag in Left Bit Shift
32-bytes(16*2) for compression data

for Flag:1, read 2 bytes data as uncompressed one
for Flag:0, read WORD(2-bytes) 
High 4 bits as repeat (need to add 2 for real count), each repeat is 2-bytes!
low 12 bits as offset (need to multipy 2 for the real offset)
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-16T23:03:29+00:00
- Post Title: PS2 Valkyrie Profile 2 SLZ help

Do you have a max function like your king of fighters function you could share on your site?
## Post #6
- Username: Boulotaur2024
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 04, 2011 1:12 am
- Post datetime: 2011-10-14T16:57:04+00:00
- Post Title: PS2 Valkyrie Profile 2 SLZ help

Sorry for bumping this thread but it seems no one has been able to decrypt SLZ type 3, at least here on Xentax because apparently someone managed to do it over there at romhacking. Unfortunately, all the links are dead, and no one seems to even reply to my [reupload request](http://www.romhacking.net/forum/index.php?topic=7790.0).

I really wish I had the knowledge to do it on my own, but I guess everyone has a particular skill in life...
Cheers !
## Post #7
- Username: Boulotaur2024
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 04, 2011 1:12 am
- Post datetime: 2011-10-16T09:11:22+00:00
- Post Title: PS2 Valkyrie Profile 2 SLZ help

Here is an example .pk1 file
[DOWNLOAD](http://www.sendspace.com/file/zu1639)
## Post #8
- Username: boodrl
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 03, 2011 8:56 am
- Post datetime: 2011-10-20T18:34:01+00:00
- Post Title: PS2 Valkyrie Profile 2 SLZ help

The slz decompressor has been uploaded on Romhacking.net if anyone is interested.

[http://www.romhacking.net/utilities/819/](http://www.romhacking.net/utilities/819/)

and a triace unpacker [http://www.romhacking.net/forum/index.php?topic=7790.0](http://www.romhacking.net/forum/index.php?topic=7790.0)

I've used the triace unpacker and it produced alot of different files

.SlZ
.SLE
.SEQ
.000 (I've looked at two of these and they only contain zeros)
.UNK
.BIN
.PK1
.PK3
.010
.CRC
.MC
.PK2
.020

All these files are still compressed however. Does anyone have any ideas or tools to decompress them?

The .slz decmpressor only works for two fiels 0002.slz and 0006.slz and turns them into .raw0 files.Can someone explain why the decompressor isn't working?
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-10-22T18:56:17+00:00
- Post Title: PS2 Valkyrie Profile 2 SLZ help

You might have better luck asking on romhacking forums, or whoever wrote the tool.
## Post #10
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-10-24T13:19:16+00:00
- Post Title: PS2 Valkyrie Profile 2 SLZ help

> Reply from Boulotaur2024
>
> 

Here is an example .pk1 file
DOWNLOAD
Just from the look of the screenshot. Doesn't the data of this file looks like a filelist? 4 bytes name and the rest some unknown bytes (size and offset? - the first file is 0x70 big the next file starts at 0x70).
## Post #11
- Username: boodrl
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 03, 2011 8:56 am
- Post datetime: 2011-10-24T20:47:22+00:00
- Post Title: PS2 Valkyrie Profile 2 SLZ help

@finale00: Thanks for the advice.   I'll continue this on romhacking.net and hopefully find the files I'm looking for (models and textures)

I'll post the link to the forum if anyone is interested keeping tabs on it 

[http://www.romhacking.net/forum/index.p ... 90.15.html](http://www.romhacking.net/forum/index.php/topic,7790.15.html)
## Post #12
- Username: boodrl
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 03, 2011 8:56 am
- Post datetime: 2011-11-04T00:37:07+00:00
- Post Title: PS2 Valkyrie Profile 2 SLZ help

Does anyone know what game engine was used for Valkyrie Profile 2? It's the same as Radiata Stories and Star Ocean 3. I've tried googling it and all I keep getting are links to Tri-Ace's new "sneek peek" at the new shiny graphics engine for the ps3.
