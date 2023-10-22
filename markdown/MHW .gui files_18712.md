## Post #1
- Username: Haldi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 21, 2018 4:32 am
- Post datetime: 2018-08-20T21:07:06+00:00
- Post Title: MHW .gui files

Howdy...

I'm trying to rearange the HUD in Monster Hunter World.
Unpacking the chunk0.bin in /ui/hud there seem to be all hud elements separate as ***.gui
Sadly most part of the .gui file gibberish for me, if opened in text editor with UTF-8.
I do see stuff like PosX, PosY, PosZ at the end of the file, which would be what i'm looking for, but i cannot find where the coordinates for this value would be...

Anyone has some clues on how to decrypt that?

I've uploaded some examples of .gui files in the .zip.
[hud.zip](https://xentaxbackup.github.io/file/14768_hud.zip)
## Post #2
- Username: CrazyT
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 10, 2011 1:07 am
- Post datetime: 2018-09-04T10:38:47+00:00
- Post Title: MHW .gui files

Edit:
Forgot to mention that i looked at the file "hud_questinfo.gui".

Well the offsets within the file seem to be relative to the start of the strings.
For example "questName" starts 0x10B00 and PosX starts at 0x10ECE resulting in a relative offset of 0x03CE.

Searching in the file for the hex-value 0xCE03 (google for "Little-Endian" to know why i reverse it) you will find multiple positions.(those positions follow D303 after some bytes wich is 0x03D3 wich results in PosY ... probably no coincidence).
My guess is that somewhere nearby(probably pos of offset +  that stored offsets the value must be stored,too.
Of course the question is wich value you need to change since there are mutiple locations for PosX/-Y/-Z (there is probably one for every element).

You figure it out by trail and error, or by translating all values first and try to guess wich might be the correct one.
## Post #3
- Username: CrazyT
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 10, 2011 1:07 am
- Post datetime: 2018-09-04T11:21:27+00:00
- Post Title: MHW .gui files

The following script maybe could help:
[https://pastebin.com/G0kigWkM](https://pastebin.com/G0kigWkM)
Sadly i was not able to figure out what defines the borders of elements ... so you only get a list of properties.
Some property-values seem also to reference locations of other properties.

Edit:
Currently trying to create a 010 Editor Template:
[https://gist.github.com/TheCrazyT/1d1e7 ... 48f886a594](https://gist.github.com/TheCrazyT/1d1e75ef9201b23b5fd4e848f886a594)

Guess it does not even cover 60% yet :/
## Post #4
- Username: Gennyswiss0
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 04, 2019 8:21 pm
- Post datetime: 2019-03-04T12:50:15+00:00
- Post Title: MHW .gui files

How will I be able to get over these files as they have already created a lot of ipod touch problems which I connected in my laptop having this problem?
