## Post #1
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-11-28T00:27:41+00:00
- Post Title: DJMAX Technika Q .FPK (OGG Array?)

I've been in this f2p game for the phone for a while and wondered how they stored the songs and stuff.

They store it in a .fpk custom format which seems to be custom since i didn't find it anywhere, but the format itself is not a big deal.

You can actually save it as an .ogg and pretty much get all the .oggs together, but it seems to be some kind of .ogg array and my problem here is that i don't know how  it's possible to cut it into different parts and where is each stored

Not sure if someone has experience with this kind of stuff, i'm new when it comes into sound formats, but this is not even considered a "new format" since it has the Oggs things from the .ogg format, it's just a lot of .oggs together.

For what i've seen, they start this way:



It seems to be a header with unknown stuff, you cuold think it contains the number of .oggs in it, but it's not the case, or maybe yes, but i didn't manage to count all of them since they are a lot...

After that there is just a lot of .ogg vorbis standard format.

then you get to the end and this appears:



The name of the song, genre, etc, and a bunch of Oggs, which are the ones that appear before in the order they are in the file.

If we go back to hex mode we can see it this way:


I should assume it's the start and end in seconds or something? i just can't manage to get it right.

So here my question is if someone is able to find how to split the oggs, because i have no experience at all in sound formats and this seems to be a pretty straightfoward format and i thought someone could manage to get where the cuts are and i can cut them manually or something.

Here's the .fpk: [http://puu.sh/d8ban/6eb5e8abfb.fpk](http://puu.sh/d8ban/6eb5e8abfb.fpk)

The fpk is just in the files so it's not encrypted or packed or anything, so it's pretty much easy to get it and the game is free so i just wanted to get the job done for anyone that wants to take a look

Thanks in advance
Seyren
## Post #2
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-12-05T23:53:10+00:00
- Post Title: DJMAX Technika Q .FPK (OGG Array?)

QuickBMS script
Extracts files with filenames, there might be compressed files so let me know if there's something you can't open.

```
#Script by TGE
endian little
get dummy long
get dummy long
get PSIZE long
get PZSIZE long
get INFO_OFFSET long
get FILES long
goto INFO_OFFSET
for i = 0 < FILES
	savepos START_POS
	get OFFSET long
	get SIZE long
	get ZSIZE long
	get STRINGLEN long
	getdstring NAME STRINGLEN
	savepos END_POS
	log NAME OFFSET ZSIZE
	goto END_POS
	math INFO_SIZE = END_POS
	math INFO_SIZE -= START_POS
	math BLOCKOFFSET = 0x90
	math BLOCKOFFSET -= INFO_SIZE
	goto BLOCKOFFSET 0 SEEK_CUR
next i

```
## Post #3
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-12-15T18:22:36+00:00
- Post Title: DJMAX Technika Q .FPK (OGG Array?)

Sorry for the late reply, works like a charm, thanks so much ^^, if something goes wrong(hopefully not), i'll let you know.

This quickbms thing is awesome for what i've seen, i should learn how this works too, now that i got more or less the hang of the 3d model formats, this must be harder though.
## Post #4
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-01-11T00:08:15+00:00
- Post Title: DJMAX Technika Q .FPK (OGG Array?)

> Reply from Seyren
>
> Sorry for the late reply, works like a charm, thanks so much ^^, if something goes wrong(hopefully not), i'll let you know.

This quickbms thing is awesome for what i've seen, i should learn how this works too, now that i got more or less the hang of the 3d model formats, this must be harder though.
QuickBMS isn't all that hard if the format you're dealing with isn't extremely complicated.
Everything is documented nicely so it's easy to get into.
