## Post #1
- Username: Heldraw
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 31, 2008 12:41 am
- Post datetime: 2008-08-31T11:25:32+00:00
- Post Title: Settlers II : Rise of Culture

Watch this topic first : link.
Hi, I would like to decrypt the Settlers II : Rise of Culture files to make a translation or to customize some files.
Here's the demo : [http://www.ubi.com/DE/Downloads/Info.aspx?dlId=2548](http://www.ubi.com/DE/Downloads/Info.aspx?dlId=2548) (German).
This game is based on Settlers II : Next Generation, same graphic engine, etc.
The files are encrypted in the same way that SII:NG.
But when i use the program linked in the thread, it don't works.
The headers are similar : "12 18 09 06" (hex) and 4 chars, in SII:NG, it was "rc00", here it's "sadk", "beta" or "demo".
When I replace this by "rc00" and try to decrypt : 

```
briefings.txt :: retail version detected
password invalid - file renamed?
```

So the password/key has changed, how to find it ?
I hope you can help me.
Attached : some new encrypted files.
[voices.rar](https://xentaxbackup.github.io/file/1619_voices.rar)
## Post #2
- Username: ednet
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 31, 2008 8:27 pm
- Post datetime: 2008-08-31T19:32:52+00:00
- Post Title: Settlers II : Rise of Culture

Hi,

I also prefere to make some changes to gameplay (by editing in the crypted *.lua-script-files i did on 10th Anniversary or Die nächste Generation in German). The german title of this nice game is Aufbruch der Kulturen.

The game encrypts nearly every file, like savegames, scripts, maps, buildings + objects(dds), publisher and developer logos on intro (also dds files) and much more.

I uploaded a few very little files from the original and the same files from demo, opened in a hex-editor not more than 10 to 20 lines, i think smaller files are better to understand how this tricky encryption works. You need bigger files just let me know.

I think they didnt change the encryption method, just using an other key or xor mask in view of Die nächste Generation. Go to [http://www.gameformats.de.vu](http://www.gameformats.de.vu) and look at Game Resource -> Die Siedler 2: Die nächste Generation to find the tool which is able to decrypt the files from 10th Anniversary.

[EDIT]
Every XML-file has to start with 
```
<?xml version=
```
 I read about that the file first packed with an LZSS algorithm and then encryptet. I guess this information should help a little bit.

This is the decryptet (and extracted decals.xml file from 10th Anniversary, by S2Ed which could be found on [http://www.gameformats.de.vu](http://www.gameformats.de.vu) and also some source of it (link was postet by Heldraw in the first post).

```
<Decals>
	<Texture name="data\gfx\decals.dds"/>
	<Texture name="data\gfx\uiTutorialCircle.dds"/>
</Decals>
```
[/EDIT]

Its such a nice game, not a simple remake so much improvements, especially they implemented 3 differnt cultures in gameplay, economy and military. Also new is now there are two groups of military units, some close combat fighters and some distant shooting people. Now islands can be attacked and the game is not over, cause it turns to an endless game like in DnG if there no free harbor-place available on the island. The new settler is a mixture between S2 and S3+S4.

Thanks so far, i hope i get a respond, ideas, ways to find out the new key, tips, etc.

Greetings
Eddy
[sadk.rar](https://xentaxbackup.github.io/file/1620_sadk.rar)
## Post #3
- Username: Heldraw
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 31, 2008 12:41 am
- Post datetime: 2008-09-01T08:45:13+00:00
- Post Title: Settlers II : Rise of Culture

I think some files have not changed between Next Generation and Rise of Culture, like .lua files of editor.
\data\scripts\editor\copypaste.lua = 125 bytes for each versions.
The key may be easier to found with these files.
[copypaste.rar](https://xentaxbackup.github.io/file/1623_copypaste.rar)
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-01T20:47:37+00:00
- Post Title: Settlers II : Rise of Culture

> Reply from ednet
>
> Thanks so far, i hope i get a respond, ideas, ways to find out the new key, tips, etc.
I found out the algorithm of 10th Anniversary by debugging the exe. Was a hard piece of work, this is a crazy algorithm.
Don't know what they changed here. I guess they simply changed something like the key, it was the filename in 10th Anniversary (and a fixed one for maps), maybe they added some more.
Or they only changed the header, so the programs don't work anymore.
## Post #5
- Username: ednet
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 31, 2008 8:27 pm
- Post datetime: 2008-09-02T15:59:24+00:00
- Post Title: Settlers II : Rise of Culture

Hi Rheini,

thank you for response. Long years ago i was doing some very simple reverse engineering with the software W32Dasm. Which software did you use?

I already find out that there 2 4 Byte long data are the same, the same in demo, sadk full version and 10th anniversary. look at:



Hex.jpg (138.37 KiB) Viewed 1868 times



What do your programm do with the 4 Bytes in Line 2 (10h). Is this still some part of a header, or a checksum?

I read on your page that the (mostly text)files first compressed by a simple LZSS compression and after this it will be encrypted. So that we can find out how the encryption works its neccesary to know how the file lokks after LZSS encryption.

In your software for 10th Anniversary you first decrypt the file and then unpack the LZSS compression, right?
Are you agree with me if i would go this way:
1. Coding or find a tool which uses LZSS compression.
2. packing the unpacked and decrypted copypaste.lua from 10th Anniversary cause I want to find out how the data looks like if its just packed and not even crypted.
3. find out (maybe debugging helps, i dont know it was so long time since i did this the last time) how the encryption changed in view of 10th Anniversary

Can you give me some more info about your programm, especially how you decrypt the data.
Example: Filename: copypaste.lua. Your program do the following:
1. Byte + Ascii(c) = encryptet 1. Byte
2. Byte + Ascii(o) = encryptet 2. Byte
3. Byte + Ascii(p) = encryptet 3. Byte
4. Byte + Ascii(y) = encryptet 4. Byte
5. Byte + Ascii(p) = encryptet 5. Byte
...
10. Byte + Ascii(.) = encryptet 10. Byte
11. Byte + Ascii(l) = encryptet 11. Byte
12. Byte + Ascii(u) = encryptet 12. Byte
13. Byte + Ascii(a) = encryptet 13. Byte

EDIT:

> Reply from Rheini
>
> Or they only changed the header, so the programs don't work anymore.No i tried this already. It would be to easy.

I hope you understand how i mean this.
Btw: Do you like the new settler?

Looking forward to hear for you.

Greetings
Eddy
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-02T16:14:40+00:00
- Post Title: Settlers II : Rise of Culture

Believe me, this ecnryption is too strong to be found out by simply looking at an LZSS-compressed version of the file.

W32Dasm is not bad, but if you really want to reverse stuff by disassembling it, go get IDA.
I personally debugged it using OllyDbg, as I already said, I needed about two weeks, since the code containing the decryption code was quite weird to me and of unknown style.
The encryption consists of 2 stages, that second stage brought me to the verge of despair, since only a few bytes are changed there, it was nearly undetectable ^^

Well the structure of 10th A.'s files is as follows:

```
	uint uk; // belongs to header
	uint fcc; // rc00
	uint datacrc; // crc of the (decompressed I think) data
	uint pwcrc; // think this was the crc of the filename, which is used in the encryption process
	uint unpackedSize; // size of unpacked data
} head;
```


EDIT: k started reversing that damn thing. the structure seems to be the same, as well as the low-level encryption function.
The pwcrc is still computed using the filename, but they somehow changed something in there.
As well they seem to have changed the 2nd encryption stage.



Ok I modified my program to support AdK, this is a quick n dirty release, only made to allow you to have a look at the files.
ONLY FOR TESTING, DOESN'T WORK PROPERLY YET!
[AdKEd.rar](https://xentaxbackup.github.io/file/1628_AdKEd.rar)
## Post #7
- Username: ednet
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 31, 2008 8:27 pm
- Post datetime: 2008-09-03T16:47:38+00:00
- Post Title: Settlers II : Rise of Culture

Hello again,

very good news thanks so much. I got IDA and reserched the file i found a lot information like the error messages writen to Logfile_0.txt and the file names but i dont know how to work with that program. i have to search for some tuts and i heard it should not be easy and takes at least 2 weeks.

I dont know why i can't find that strings with W32Dasm, then maybe i could do some reverse engineering but IDA is much complicater to use. I remeber that I read about if you would do reverse engineering you have to use IDA oder Softice. But i think SoftIce is dead.

Maybe you compare just the sections from 10th Anniversay and AdK to find the little thing wich has changed.

Greetings
Eddy
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-03T17:21:35+00:00
- Post Title: Settlers II : Rise of Culture

> Reply from ednet
>
> very good news thanks so much. I got IDA and reserched the file i found a lot information like the error messages writen to Logfile_0.txt and the file names but i dont know how to work with that program. i have to search for some tuts and i heard it should not be easy and takes at least 2 weeks.
At least it took me 2 weeks to dismantle 10th A.'s encryption back then. But I was kinda unexperienced.

> maybe i could do some reverse engineering but IDA is much complicater to use. I remeber that I read about if you would do reverse engineering you have to use IDA oder Softice. But i think SoftIce is dead.
Of course it's more complicated but it's also more powerful. Using SoftIce isn't necessary if you use the NoCD, since SecuROM is already removed there.

> Maybe you compare just the sections from 10th Anniversay and AdK to find the little thing wich has changed.
Unfortunately this doesn't work. Compilers don't always create the same code, and additionally SecuROM messes around with the code, tries to obfuscate stuff and so on.

It's a search for the needle in the haystack, I found some values they changed although my old code still works (at least the first encryption stage)   I guess this will take some time.
## Post #9
- Username: takysoft
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 18, 2006 8:02 am
- Post datetime: 2008-09-06T08:14:15+00:00
- Post Title: Settlers II : Rise of Culture

Hi!
The alpha AdKEd worked for me like a charm. (for the text files, and dds too.)
I'm a hungarian game translator. I translated S2 10th anniv, and the wikinger addon to hungarian.
I'd like to translate thig game too, and (as I see) the decrypter is already working.

I'm just asking... are you planning to make an encrypter too? I won't start to translate the texts, till I'm sure I'll be able to use them:D

Thank you for your work.

Laszlo
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-24T01:43:53+00:00
- Post Title: Settlers II : Rise of Culture

No it doesn't work. Files with less than 8KB have 1 corrupt byte, bigger files have more. Just take goods.lua. At the end of the file the decompression fails.
And I still don't know why the crc check fails on files like data.lua where the decryption seems to work properly.

The problem with making an encrypter is to write an LZSS compressor. But I got to figure out the full encryption scheme first.

EDIT:
Small update. Still working on it, but SecuROM is driving me crazy. Discovered many parts of the code, but it is very time-consuming.
btw, just in case somebody is interested in the code, I ripped the full buildings.lua
[buildings.org.rar](https://xentaxbackup.github.io/file/1652_buildings.org.rar)
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-24T17:35:31+00:00
- Post Title: Settlers II : Rise of Culture

Ok, I posted v0.2 of my tool at [viewtopic.php?f=21&t=3165](http://forum.xentax.com/viewtopic.php?f=21&t=3165)
It now decrypts files flawlessly.
## Post #12
- Username: Eddi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 01, 2010 4:20 am
- Post datetime: 2010-03-03T12:36:01+00:00
- Post Title: Settlers II : Rise of Culture

> Reply from Rheini
>
> I guess they simply changed something like the key, it was the filename in 10th Anniversary (and a fixed one for maps)is there any information on what's the key for savegames? on the entire net, this is the only reference to it i have found.
## Post #13
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-03-03T12:40:38+00:00
- Post Title: Settlers II : Rise of Culture

The key for saved games is fixed IIRC.
## Post #14
- Username: Eddi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 01, 2010 4:20 am
- Post datetime: 2010-03-04T21:39:53+00:00
- Post Title: Settlers II : Rise of Culture

yes. it's fixed, i read that... but what is it? or where is it stored? and are there some more details on the savegame format somewhere?
## Post #15
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-03-04T22:08:59+00:00
- Post Title: Settlers II : Rise of Culture

Ah savegames, I thought you were talking about maps. Maps have a fixed pwcrc.
No clue.
