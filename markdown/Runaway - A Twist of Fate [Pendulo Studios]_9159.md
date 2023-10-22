## Post #1
- Username: gyeben
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 19, 2011 10:43 pm
- Post datetime: 2012-06-27T21:05:36+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

EDIT: removed all the illegal links. I really do feel like an ultra-noob for not reading the forum's rules. A demo version is legally available here: [http://www.gamershell.com/download_54508.shtml](http://www.gamershell.com/download_54508.shtml)

Hi!

I need some help in identifying and unpacking the archives of Runaway - A Twist of Fate.
EDIT: A demo can be downloaded from here: [http://www.gamershell.com/download_54508.shtml](http://www.gamershell.com/download_54508.shtml)

As far as I know - Pendulo Studios uses similar weird file names and archives in ALL of their games - but the latest ones (TNBT and Yesterday) files' have some differences compared to the Runaway series' files.

DATAAA.000: should be containing audio files - definetely all the speech
I could extract some of it with the help of a script posted by Axsis here: [viewtopic.php?f=10&t=8647&hilit=Runaway](http://forum.xentax.com/viewtopic.php?f=10&t=8647&hilit=Runaway) , but the extracted files' overall size is smaller than the archive, and the script gives an error during the process, so it's not perfect. If we extract the file, we get 2 short wav files, a short mp3 file and a quite big (nearly 5 hours) wav file. They're are playable, but the last, big one's order is completely unfollowable.

RESOURCE.002, .003, .004, .005: I have generally no idea what do these files contain. They have pretty small sizes, so maybe the texts and dialogues of the game? Or some hard-to-follow internal scripts?

RESOURCE.S?? - these files mostly contain music and there are some tools already out there that can extract them: [http://www.ctpax-x.ru/index.php?goto=fi ... 82&lang=en](http://www.ctpax-x.ru/index.php?goto=files&show=82&lang=en)

RESOURCE.SP? : these might be audio files as well, but I'm not so sure. Need further investigation.

RESOURCE.A??, .B??, .C??, .D??, .E??, .F??, .H01: have no idea about the content of these files. Maybe graphics?

DATAV???.000 (all the files in the Datav directory): these are simple Bink video files. All we have to do is to rename them. The only problem is that they only contain the speeches, so they don't have all the sound effects and background music. (Maybe they're are stored in the .S?? or .SP? files)
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-06-28T15:06:06+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

Well one script surely won't work, some of the files don't even look like they can be extracted.

Anyway this should unpack DATAAA.000 only.

```
# DatAAAA.000
# By MrNightmareTM
# Version 0.1a

get FILES long

for i = 0 < FILES
get NAME basename
get OFFSET long
get SIZE long
get TYPE byte

string NAME += "."
string NAME += i
log NAME OFFSET SIZE

next i

```
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-06-29T06:11:49+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

gyeben, why did you not read the game rules?
## Post #4
- Username: gyeben
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 19, 2011 10:43 pm
- Post datetime: 2012-08-14T12:50:59+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

I've just removed all the illegal links.
I feel like such a noob for not reading the rules...
## Post #5
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2017-04-09T07:08:25+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

Anyone knows how to extract the fonts from the game executable?

Greets
## Post #6
- Username: ripper
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 20, 2014 4:52 am
- Post datetime: 2017-04-24T23:00:37+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

I'm apologize for my English. But i'll try help. Don't know Quick BMS or MultiEx Commander script syntax, so use general data types definitions.

RESOURCE.000 containts fonts.
Offsets: 
0x054441CB
0x0667E584
0x06688BEF

Structure:
UINT32 - relative offset;
UINT8 - symbol padding from top;
UINT8 - symbol height;
UINT8 - symbol width;

Fonts Graphic data placed before tabels, some fonts 24-bit, some 8-bit. Just compare height*width first's symbol width relative offset of second.

Text in RESOURCE.003
Structure:
UINT32 - number of entities. 
UINT32 x number of entities - unknown. 
BYTE[401] - text entity.

Each entity XOR-ed by prev byte. First decode byte is entity order number (0, 1, 2 ...)

About RESOURCE files:
RESOURCE.000 and RESOURCE.002 - font for Hollywood Monster, RA1, RA2, RA3.
RESOURCE.003 - in-game text.
RESOURCE.004 - don't know. Different in each official localization, but all OK if change data only in RESOURCE.003
RESOURCE.005 - In RA3 contains program errors.

RESOURCE.[A-Z]XX - except SXX and SPX. Game scenes (background, mask, items, overlay scene images etc.)
RESOURCE.SXX - sound effects
RESOURCE.SPX - don't know.
## Post #7
- Username: micTronic
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Dec 16, 2020 6:28 am
- Post datetime: 2021-06-12T22:09:19+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

Sorry for reviving this old post, but I've recently starting looking into for a way for extracting some of the images from the Runaway series of games, and there isn't a whole lot of information available on that topic in general. In fact, ripper's info from above was the best I could find and it was super useful in decoding the text (thanks!).

However, the image data (e.g. in RESOURCE.A??) does not make much sense to me at the moment. I can get the individual files, but I'm not sure about the format, as there does not appear to be any headers. Are they raw uncompressed RGB data? This would be strange, not being compressed at all. And even then, I can't get them to render properly. Dimensions are missing too and I doubt they can be "guessed". Any help is greatly appreciated. 

Also, someone in another thread mentioned the "DATAV*" files in "datav" dir would be Bink videos that just need to be renamed, but I wasn't able to confirm that. Looking at them, I cannot see a [bink file header](https://wiki.multimedia.cx/index.php/Bink_Container).
## Post #8
- Username: ripper
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 20, 2014 4:52 am
- Post datetime: 2021-06-13T14:41:08+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

There is 2 types of images:
1. RAW image data. I didn't found any tips about width or height, just guessing (in most cases there width=1024 or height=600(768) for A Road Adventure);
2. Bunch of rows with x and y offsets.

```
foreach row
    UINT16 - x
    UINT16 - y
    UINT16 - pixels count
endforeach
```

Pixel format: 16-bit R5 G6 B5

About video:
For A Twist of Fate videos you need just change extention to .bik
For A Road Adventure and A Dream of the Turtle there are DATAVC00.000 files with encrypted filenames and headers for them.

```
UINT32 - entities count

foreach entity
    byte[15] - encrypted filename (decryption is similar to RESOURCE.003, but first decrypt byte = first byte of the DATAVC00.000)
endforeach

foreach entity
    byte[1024] - encrypted header (same as filename)
    byte[1024] - unknown
endforeach
```

Now you need to replace first 1024 bytes of videofiles with decrypted header from DATAVC00.000 and you'll get correct bik file.
## Post #9
- Username: micTronic
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Dec 16, 2020 6:28 am
- Post datetime: 2021-06-13T20:24:12+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

Hey ripper, I am amazed how much you were able to discover about these resource formats. 
I will play around a bit with the image data, R5G6B5 sounds good, the two format types probably confused me a bit.
Also I was indeed looking at the bik's for the first two games, and your code there is also super helpful - wouldn't have figured that out myself.

The last mystery remaining to be solved are now the strings for the first game. They seem to be in "RESOURCE.003" too, but using a different format. I did not see an offset table, but there seem to be blocks of ~321 bytes, possibly one per string. I compared the file from the English and German version, and the differences are probably the strings in each language (they rest may be garbage or meta data). Here's an image of part of the two files side by side:
[https://ibb.co/S7tKDZz](https://ibb.co/S7tKDZz)
However, the XOR decoding from Twisted Fate does not work apparently (I tried with different bytes and offsets). I know I asked already a lot, but if you happen to have a solution for that too, that would make my day. 

Thanks once again for your help!
## Post #10
- Username: ripper
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 20, 2014 4:52 am
- Post datetime: 2021-06-14T21:13:50+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

First game totally different story (like Hollywood Monsters [1997]). For decrypting you need to substract key from encrypted text byte by byte. I hope this will help you.

```
UINT32 — data offset

----------[0]----------
**GOTO position = (data offset - 20006)**
**UINT8 — short rows count**
**UINT16 — long rows count**
**GOTO position = data offset**

foreach short_rows_count
  byte[41] — encrypted text (there should be items and actions text, but they move it to executable)
endforeach

foreach long_rows_count
  byte[321] — encrypted text (there should be items and actions text, but they move it to executable)
endforeach

----------[1]----------
**GOTO position = current_position + 100000**
UINT8 — short rows count
UINT16 — long rows count

foreach short_rows_count
  byte[41] — encrypted text (there should be items and actions text, but they move it to executable)
endforeach

foreach long_rows_count
  byte[321] — encrypted text (there should be items and actions text, but they move it to executable)
endforeach
```


You should repeat [1] untill end of the file.

I think there is a better way to manage [0], but IMHO this enought for localization purposes.
## Post #11
- Username: micTronic
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Dec 16, 2020 6:28 am
- Post datetime: 2021-06-15T20:02:30+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

Thanks again for your explanation regarding the RA1 strings, they were very helpful! With the key, I was able to extract the strings easily. In fact there are more of the blocks you mentioned, but I managed to find them quickly by searching for "FF FF 00 00 00 00" in the resource file.

However, regarding the images - at least for RA2 - it did not turn out quite as expected (did not check the other games yet).

> Reply from ripper ↑Sun Jun 13, 2021 10:41 pm at Sun Jun 13, 2021 10:41 pm
>
> 
2. Bunch of rows with x and y offsets.
Code: Select allUINT16 - rows count
foreach row
    UINT16 - x
    UINT16 - y
    UINT16 - pixels count
endforeach
Pixel format: 16-bit R5 G6 B5

When I checked a couple of files, I found a similar format, but not quite that. I captured some hex dumps from these "x/y row" files indicating what I mean. The red lines would be the x, the green the y, and the yellow the pixel count, according to your spec. But there's at least one byte missing, which is usually 1, but also sometimes 0 (it's the cyan byte in the image).
[https://ibb.co/CKpbNk8](https://ibb.co/CKpbNk8)
Also, the number of bytes following the count sometimes exactly the pixel count, sometimes twice the count, and sometimes 3 times. I suppose that could mean different pixel formats (bit depths)? There are even cases where the number does not seem to match at all, like in the first example: The pixel count is "4", but the actual bytes following is 11. It does not make sense to me.
Also, I am not sure what the x/y coordinates are supposed to mean. Should the pixels be drawn at that position? Sometimes the same pairs appear multiple times...
In any case, this seems to require more investigation.
## Post #12
- Username: ripper
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 20, 2014 4:52 am
- Post datetime: 2021-06-22T23:02:22+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

Yeah, the second type valid only for for RA1.

Looks like they go further and add some types to reduce images size.

```
FOREACH entity
  UINT16 — X
  UINT16 — Y
  UINT8 — type
  UINT16 — pixels count
  byte[] — data
ENDFOREACH

IF type == 0 — data = pixels count * 2 (I think that is R5G6B5 pixel format)
IF type == 1 — data = pixels count * 3 (I think that is R8G8B8 pixel format)

```

There is one thing that confuse a lot. Some images:

```
IF type == 1 — data = pixels count

```

This is the reason for my ~10 days silence.

For RA3 general format same as RA2

```
IF type == 2 — data = 0
IF type == 4 — data = pixels count

```

And looks like there no "confusing things". But I cheked only A01 pak.

I didn't check how those images looks, so some adjustments might required.
## Post #13
- Username: micTronic
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Dec 16, 2020 6:28 am
- Post datetime: 2021-06-23T07:55:46+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

Hey ripper, nice to hear back from you!
I also did a couple of investigations over the last week, and together with your research, many things have become more clear.
The basic format for all images seems to be the one you posted above, i.e. records of

```
X, Y, [type,] count, [data]
```

where those in brackets are optional. In fact, also the "entitiy count" at the beginning does not appear in all files.
To make things complicated, all of the above can be specified as BYTE or UINT16, depending on the file. I have not found any "index" that tells me which format a file uses, and there is no header.

RA1 does not specify the type per record, but uses either 1 or 2 bytes with X and Y as either BYTE or UINT16.
RA2 and beyond (including Next Big Thing and Yesterday, which I checked too for fun) introduces the per-record types. I encountered:

```
 type 1: BGR565 + 1b alpha
 type 2: just a count, maybe clipping region?
 type 4: alpha values for type 2 or 8
 type 5: GBRA32
 type 6: BGR24
 type 7: ARGB32
 type 8: just a count, maybe shadow?
```

Some of the "images" actually black-and-white clipping regions only.

Also, some files contain multiple image frames. You can check by aligning the header to 14 bytes. After an initial count (UINT16), there are count 14-byte records, where the first UINT32 is the offset (for RA1 0 starts *after* the header!) and then follow some UINT16 dimensions.

With that, most of the files from the Pendulo games are clear now. There are only a few left with a rather rigid 4-byte structure that I don't understand (e.g. for RA2, the 2nd entry in RESOURCE.A08 AND .A09).
Also, I have no idea about the image format for "Hollywood Monsters" - does not seems to be a default pixel format. Maybe it uses a palette?
## Post #14
- Username: ripper
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 20, 2014 4:52 am
- Post datetime: 2021-06-23T17:18:30+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

> Reply from micTronic
>
> Also, some files contain multiple image frames. You can check by aligning the header to 14 bytes. After an initial count (UINT16), there are count 14-byte records, where the first UINT32 is the offset (for RA1 0 starts *after* the header!) and then follow some UINT16 dimensions.

This is animation sequence. In the RA2 they separate header data from images. They, usually, going before animation frames

```
FOREACH frame
  UINT32 — offset to the data
  UINT16 — X1
  UINT16 — Y1
  UINT16 — X2
  UINT16 — Y2
  UINT16 — rows count
ENDFOREACH
```

In RA1 and RA3 header and frames in the same file.

> Reply from micTronic
>
> There are only a few left with a rather rigid 4-byte structure that I don't understand (e.g. for RA2, the 2nd entry in RESOURCE.A08 AND .A09).
This is where I finished my research. I stopped with something like this

```
UINT16 — X or Y pos?

```


If I recall correctly, there 3 formats left from scene files. In RA2 A09 there are second, third and fourth entry.

In Hollywood Monsters there is 24-bit palette after raw image. In *00 files full 768 bytes palette and 528 bytes palette in *01, *02... I suppose those 528 bytes palettes overwriting palette from *00 files.
## Post #15
- Username: micTronic
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Dec 16, 2020 6:28 am
- Post datetime: 2021-06-29T19:48:36+00:00
- Post Title: Runaway - A Twist of Fate [Pendulo Studios]

Thanks for the hints regarding the Hollywood Monsters palette files, works perfectly (once you find out which palette belongs to which file, that is  ).
I also stopped there with the files from Runaway, the ones you mentioned are remaining, but I doubt they are very important. Might try again some other time
