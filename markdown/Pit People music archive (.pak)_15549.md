## Post #1
- Username: loreberg
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 28, 2016 6:43 pm
- Post datetime: 2016-11-28T10:52:50+00:00
- Post Title: Pit People music archive (.pak)

Hey, I have problems accesing the data (music) in the following archive (from Pit People game):
[http://www.megafileupload.com/803a/music.pak](http://www.megafileupload.com/803a/music.pak)

Unfortunately, doing stuff reccomended for previous Behemoth games doesn't seem to work, Dragon unpacker and Hyperripper can't find anything. Pretty stuck here, hoped some extractions guru's from here could guide me on some way as I'm very inexperienced
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-12-05T18:41:06+00:00
- Post Title: Pit People music archive (.pak)

Here's a QuickBMS script for extracting the .fsb files from music.pak:

```
get DUMMY long	# maybe version
get FILE_COUNT long
get FILE_SECTION_OFFSET long
get STRING_SECTION_OFFSET long
get STRING_SECTION_LENGTH long
get DUMMY long	# 0
get DUMMY long	# 0

for i = 0 < FILE_COUNT
	xmath OFFSET "0x20 + i * 0x20"
	goto OFFSET
	
	get DUMMY long	# maybe checksum
	get FILE_OFFSET long
	get FILE_LENGTH long
	get DUMMY long	# always 0
	get STRING_OFFSET long
	get DUMMY long	# always 0
	get DUMMY long	# always 0
	get DUMMY long	# always 0
	
	math FILE_OFFSET += FILE_SECTION_OFFSET
	math STRING_OFFSET += STRING_SECTION_OFFSET
	
	goto STRING_OFFSET
	get FILE_NAME string
	
	log FILE_NAME FILE_OFFSET FILE_LENGTH
next i
```
## Post #3
- Username: loreberg
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 28, 2016 6:43 pm
- Post datetime: 2016-12-08T00:05:59+00:00
- Post Title: Pit People music archive (.pak)

Holy, almost gave up on this, huge thanks herbert!

So far Aezay FSB extractor can get headerless audio (.ogg) data from these. If I get this right, it's pretty much blind luck now, trying to import this as raw audio attaching different type of metadata to make this correctly playable. I'll try to make something out of it, thanks a lot again
## Post #4
- Username: loreberg
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 28, 2016 6:43 pm
- Post datetime: 2016-12-08T11:35:32+00:00
- Post Title: Pit People music archive (.pak)

UPDATE: SUCCESS

Thanks to herbert's QBMS script and tmiasko's fsb-vorbis-extractor ([https://github.com/tmiasko/fsb-vorbis-extractor](https://github.com/tmiasko/fsb-vorbis-extractor)), 50 playable music files were extracted. Mostly spent time on trying make my broken ubuntu install work with cmake and libboost, all real work done by guys mentioned!

Extracted package:
[http://www.megafileupload.com/grNH/out.zip](http://www.megafileupload.com/grNH/out.zip)

Cheers!
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-12-14T21:52:09+00:00
- Post Title: Pit People music archive (.pak)

Nice!

[http://www.xentax.com/downloads/music/bp/out.zip](http://www.xentax.com/downloads/music/bp/out.zip)
## Post #6
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2017-01-23T21:45:26+00:00
- Post Title: Pit People music archive (.pak)

Hi,
the game (early released) might have changed the way pak files work because it no longer works. Can someone please look into it?

I've attached a small .pak file I found.
[data.rar](https://xentaxbackup.github.io/file/12273_data.rar)
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-01-24T23:10:43+00:00
- Post Title: Pit People music archive (.pak)

if version flag is 3 (as your samples are), the structure is different. the file table/names are scrambled (maybe xor'ed with a value)

using only 2 samples we can guess the xor key 

the format is identical to the v0 script above.

so the xor key is dead simple to figure out (A^B = B^A)

```
 73 65 63 6B 72 69 74 79 74 68 72 6F 75 67 68 6F 
```


subtitles are compressed xml files - offzip can give you anything not understood

> +------------+-----+----------------------------+----------------------+
>
> | hex_offset | ... | zip -> unzip size / offset | spaces before | info |
>
> +------------+-----+----------------------------+----------------------+
>
>   0x00000240 . 112 -> 145 / 0x000002b0 _ 576 8:7:26:0:1:94072ffa
>
>   0x000002b0 . 119 -> 257 / 0x00000327 _ 0 8:7:26:0:1:8ea354be
>
>   0x00000330 . 136 -> 306 / 0x000003b8 _ 9 8:7:26:0:1:52585fcf
>
>   0x000003c0 . 107 -> 139 / 0x0000042b _ 8 8:7:26:0:1:5dff2d17
>
>   0x00000430 . 179 -> 874 / 0x000004e3 _ 5 8:7:26:0:1:32680afb
>
>   0x000004f0 . 113 -> 145 / 0x00000561 _ 13 8:7:26:0:1:c09a307f
>
>   0x00000570 . 127 -> 176 / 0x000005ef _ 15 8:7:26:0:1:25e23833
>
>   0x000005f0 . 110 -> 143 / 0x0000065e _ 1 8:7:26:0:1:4e782f76
>
>   0x00000660 . 147 -> 678 / 0x000006f3 _ 2 8:7:26:0:1:d346d7c4
>
>   0x00000700 . 190 -> 1436 / 0x000007be _ 13 8:7:26:0:1:a18cc8e1
>
>   0x000007c0 . 111 -> 242 / 0x0000082f _ 2 8:7:26:0:1:021b4d91
>
>   0x00000830 . 141 -> 570 / 0x000008bd _ 1 8:7:26:0:1:0df1b817
>
>   0x000008c0 . 480 -> 3153 / 0x00000aa0 _ 3 8:7:26:0:1:b1d0c319
>
>   0x00000aa0 . 108 -> 139 / 0x00000b0c _ 0 8:7:26:0:1:52072cd6
>
>   0x00000b10 . 204 -> 1146 / 0x00000bdc _ 4 8:7:26:0:1:c8706d3f
>
>   0x00000be0 . 426 -> 4238 / 0x00000d8a _ 4 8:7:26:0:1:031b2e58
>
>   0x00000d90 . 328 -> 1914 / 0x00000ed8 _ 6 8:7:26:0:1:fa58436c
>
>   0x00001000
>
> 
>
> - 17 valid compressed streams found
## Post #8
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2017-01-25T11:33:49+00:00
- Post Title: Pit People music archive (.pak)

Okay so according to your findings, I tried offzip on them again and it did work, but not on "Fonts" and "Design" .pak files. However, I didn't get what you did exactly using the XOR key, okay so you figured it out by comparing both files, but what did you use the Key for? I mean if offzip was able to do the job, then the XOR is only for the table?

And btw many thanks for the help!!

The two mentioned files Fonts and Design are [here.](https://www.dropbox.com/sh/9sz4w4f41dbgr78/AAAH4dC20r7voLT_QlvsFZlGa)


Edit: So one thing I know is that XOR with 0 is unchanged, so we can expect the letters to show up following through the method the first guy unpacked.

Here are the values that I obtained from various files, where ? are not english alphabet.

```
?fes??ir???tk?gu
pces?tir???t?hgu
qces?tir???u?hgu
ces?uiro???t?hgu
?ces??ir???p?ogu
zcesyvir??ht?igu
?des??ir?????jfu
dces?vir??ht?jgu
rcesyuir??ml?hgu

```


How did you obtain the key from those?


Update 2:
I manually calculated some files, and to my amazement XOR is really an amazing thing! I was able to find out the XOR key again, but only as 16 Bytes, meanwhile I'm sure the key is a bit longer. (24/32), or it is 16 bytes twice.

Update 3:

The XOR key is:

```
73 65 63 75 72 69 74 79 74 68 72 6F 75 67 68 6F
```


Update 4:

I've extracted the files successfully but I'm unable to figure out the encoding of the names.
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-01-25T20:48:35+00:00
- Post Title: Pit People music archive (.pak)

> Reply from thethiny
>
> I've extracted the files successfully but I'm unable to figure out the encoding of the names.

the names are in their own table at the bottom as version 0 were. they are also xor'd.

also only subtitles are packed. the shaders are non-compressed binary though
## Post #10
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2017-01-26T16:40:15+00:00
- Post Title: Pit People music archive (.pak)

> Reply from WRS
>
> the names are in their own table at the bottom as version 0 were. they are also xor'd.
Using the same XOR technique is producing non English Letters. Are you sure about that?
## Post #11
- Username: ali07saad
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 16, 2017 6:11 am
- Post datetime: 2017-02-15T22:15:23+00:00
- Post Title: Pit People music archive (.pak)

> Reply from Mr.Mouse
>
> Nice!

http://www.xentax.com/downloads/music/bp/out.zip

Thank you so much! i've been looking for the soundtrack " 1.music_story_sofiacapture.ogg " for over a month now.
tried a lot of programs to unpack the music.pak but with no luck.

you've made my day. Thanks again!
