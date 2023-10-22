## Post #1
- Username: Blue Mantis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 05, 2015 10:35 am
- Post datetime: 2015-02-05T02:45:36+00:00
- Post Title: Scott Pilgrim vs. The World (360) - help extracting?

I'd really appreciate it if you guys could help me out with this. I purchased this game a few years ago, but I'd like to study the pixel art in this game properly as the art style interests me and I'd like to better learn it. Unfortunately, it seems difficult to extract the data since it seems to be in a format I can't figure out. This isn't my expertise, so forgive my ignorance. I used wxPirs to extract the main contents of the package.

The contents are several PNGs that cannot be opened (they're only a few kilobytes each), of course the signature and default file and then a gamedata file, and another with the extension FAT. (Not a standard FAT file it seems since I got a program for opening these and it did not recognise it.) There are a few directories. One called 00, and the files inside are a couple of "toc" files and another 1KB file without an extension. Another directory in the root is "Audio" with many .pk (and a few .spk) files inside, and two directories in that called "English" and "Native". In those are some .lpk files. The other folder in the root is "Localization" with a bunch of .bof language files, which of course contain the language strings.

Like I said, I'd be very grateful if you could help me out here. It's the main reason I registered. I don't know if it's allowed, but I can provide the gamedata files if needed, or any others requested. Thanks!
## Post #2
- Username: Blue Mantis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 05, 2015 10:35 am
- Post datetime: 2015-02-05T03:03:08+00:00
- Post Title: Scott Pilgrim vs. The World (360) - help extracting?

Sorry, this might belong in the Game Archive forum. Please move if so.
## Post #3
- Username: Blue Mantis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 05, 2015 10:35 am
- Post datetime: 2015-02-05T20:05:21+00:00
- Post Title: Scott Pilgrim vs. The World (360) - help extracting?

I've uploaded the 306KB gamedata.fat file. [https://www.sendspace.com/file/ohxy8i](https://www.sendspace.com/file/ohxy8i)
Aside from audio, the main data is in the gamedata (no extension) file which is 55.7MB. You can find that here: [https://www.sendspace.com/file/yevjva](https://www.sendspace.com/file/yevjva)

By the way, there was an old thread on this game: [viewtopic.php?f=10&t=5001](http://forum.xentax.com/viewtopic.php?f=10&t=5001)
## Post #4
- Username: Blue Mantis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 05, 2015 10:35 am
- Post datetime: 2015-02-13T23:32:52+00:00
- Post Title: Scott Pilgrim vs. The World (360) - help extracting?

Bump
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-14T15:45:08+00:00
- Post Title: Scott Pilgrim vs. The World (360) - help extracting?

you could run offzip on the gamedata file.
offzip -a gamedata D:\extracted 0

Will tell you that some data in the file is not in zip format
and purge 17077 "valid zip blocks" in 1,69 GB into the extracted folder.

But seems there's no senseful data extracted.

using offzip on gamedata1.fat:

```
  0x00003352 ...... 11125 --> 16384
  0x00005eec ...... 11029 --> 16384
  0x00008a26 ...... 12279 --> 16384
  0x0000ba42 ...... 10634 --> 16384
  0x0000e3f1 ..... 9318 --> 16384
  0x0001087c ...... 10406 --> 16384
  0x00013147 ....... 13157 --> 16384
  0x000164d1 ....... 14159 --> 16384
  0x00019c45 ....... 14092 --> 16384
  0x0001d376 ....... 14164 --> 16384
  0x00020aef ....... 12726 --> 16384
  0x00023cca ....... 12292 --> 16384
  0x00026cf3 ....... 13226 --> 16384
  0x0002a0c2 ....... 13494 --> 16384
  0x0002d59d ... 5710 --> 6867
  0x00033170 ..... 9551 --> 16384
  0x000356e4 ..... 9248 --> 16384
  0x00037b29 ..... 9480 --> 16384
  0x0003a056 ..... 9721 --> 16384
  0x0003c674 .... 7811 --> 16384
  0x0003e51c .... 7505 --> 16384
  0x00040292 .... 7837 --> 16384
  0x00042154 .... 7534 --> 16384
  0x00043ee7 .... 6781 --> 16384
  0x00045989 .... 7963 --> 16384
  0x000478c9 .... 7594 --> 16384
  0x00049698 .... 8028 --> 16384
  0x0004b619 ... 5039 --> 10593
```


The reason why WRS' bms script is not running with this fat file:
the data from 0x00000 to 0x929 is not zip compressed.

I tried something like
log MEMORY_FILE 0 0x92A 1
but CHUNKS is negative then.

Are there other gamedata and fat files?
I would suggest to try out them all with the above mentioned bms script.

(gamedata.fat has to be renamed to gamedata1.fat)

edit: ok, to answer my own question guess there is no other (or standard) fat file.
A standard fat file could be extracted as one block, as for Might&Magic, duel of champs:

+------------+-------------+-------------------------+
| hex_offset | blocks_dots | zip_size --> unzip_size |
+------------+-------------+-------------------------+
  0x00000000 ................................................... 102552 --> 204829

So there's no way around to analyze/understand the structure of Scott Pilgrim gamedata.fat.
(search for 010000 40 000000 002040 0000 010001 which is contained 28 times)

There's an uncompressed xml file contained at 0x2EBF0:

```
<xml>
	<ResourceInfo>
		<CustomDebugInfo/>
		<TypeName>IndexBufferPool</TypeName>
		<SourceDataDescription>not available</SourceDataDescription>
		<SlotRamRequired __type='Int'>0</SlotRamRequired>
		<SlotVramRequired __type='Int'>67724</SlotVramRequired>
		<OtherRamRequired __type='Int'>0</OtherRamRequired>
		<OtherVramRequired __type='Int'>0</OtherVramRequired>
	</ResourceInfo>
...
	<ResourceInfo>
		<CustomDebugInfo/>
		<TypeName>Mipmap</TypeName>
		<SourceDataDescription>Waybar_in.dds</SourceDataDescription>
		<SlotRamRequired __type='Int'>0</SlotRamRequired>
		<SlotVramRequired __type='Int'>0</SlotVramRequired>
		<OtherRamRequired __type='Int'>0</OtherRamRequired>
		<OtherVramRequired __type='Int'>0</OtherVramRequired>
	</ResourceInfo>
</xml>
```
## Post #6
- Username: Blue Mantis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 05, 2015 10:35 am
- Post datetime: 2015-04-03T16:30:34+00:00
- Post Title: Scott Pilgrim vs. The World (360) - help extracting?

Do you believe it would be very difficult to extract the data from this, then? Seems like a format you haven't encountered before. I wish I could offer my own input, but I'm an absolute beginner here. I haven't studied much about file structures, or the means of doing this with games and I've only used a hex editor a few times in my life. Thanks for your help. (And sorry for the delay, too!)
