## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-03-05T19:26:15+00:00
- Post Title: Wario Land: The Shake Dimension GFA files

I believe I may have posted this before a long time back, but it was in conjunction with another game, which I think is asking too much.
These files are a pain. They are internal files from Wario Land: The Shake Dimension, a game for the Nintendo Wii. I have, for quite a long time, been trying to extract the graphics from these files but to no avail. I'm close to getting so frustrated I'd tear my hair from my head in rage. I can't express how important these graphics are to me, so I've coem to you all, who are the smartest bunch of people I've met online when it comes to these things. I really hope you lot can help me this time, as this is one of the last steps in my personal project. Below is a link to a sendspace page where the download link for a zip file is. In this zip file are some sample .GFA files that I am assured contain the graphic data. Now, upon looking at them in a hex editor, I have noticed a re-occurrence of an element labelled '.brres'. This leads me to believe that there are even FURTHER files within these. If that is the case I would like to request now a method of extracting from them as well. It is absolutely vital I receive these files by May 20th, lest my project fall through. Please help me if you're able to. It will be very appreciated, and come May 20th, may be well rewarded if I am able to acquire the images within.

Zip File Download Link: [http://www.sendspace.com/file/dgglz1](http://www.sendspace.com/file/dgglz1)

I thank you for reading this and for any potential help you may be. Please PM me if you wish to remain anonymous among your peers, or for any other reason. If you need more instances of these files, please let me know either in this topic or in a PM.

Any other question please post here or PM me. I would be happy to assist in any way possible in decrypting these files and obtaining the images.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-05T19:36:12+00:00
- Post Title: Wario Land: The Shake Dimension GFA files

i have not looked at these files but this should point you in the right direction.
[viewtopic.php?f=10&t=3875&p=33962](http://forum.xentax.com/viewtopic.php?f=10&t=3875&p=33962)
## Post #3
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-03-05T21:31:12+00:00
- Post Title: Wario Land: The Shake Dimension GFA files

That's a good start, however that program only accepts brres files, which are archived together in these GFA files, which I need extracted properly. Then that program would be most useful. Also, does anyone know where to get the dolphin disk utility?
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-03-05T23:07:10+00:00
- Post Title: Wario Land: The Shake Dimension GFA files

Here's some quickbms to extract the gfa

```
# Wario Land: The Shake Dimension GFA

Endian little

# Main header
IDString "GFAC"
Get HEADER_1_1 long
Get HEADER_1_2 long
If HEADER_1_1 != 1
   Print "Strange HEADER_1_1 = %HEADER_1_1%, may crash..."
EndIf
If HEADER_1_2 != 1
   Print "Strange HEADER_1_2 = %HEADER_1_2%, may crash..."
EndIf
Get FILE_TABLE_OFFSET long
Get FILE_TABLE_SIZE long
Get DATA_OFFSET long
Get DATA_SIZE long

# Read compressed data header
GoTo DATA_OFFSET

IDString "GFCP"
Get HEADER_1_1 long
Get CTYPE long
If HEADER_1_1 != 1
   Print "Strange GFCP HEADER_1_1 = %HEADER_1_1%, may crash..."
EndIf
If CTYPE == 1
   ComType bpe
ElseIf CTYPE == 2
   ComType lz77wii_raw30
Else
  Print "Unknown compression %CTYPE%"
  Exit
EndIf

Get RAW_DATA_SIZE long
Get COMPRESSED_DATA_SIZE long

Set CDATA_OFFSET DATA_OFFSET
Math CDATA_OFFSET + 0x14

# Decompress
Clog MEMORY_FILE CDATA_OFFSET COMPRESSED_DATA_SIZE RAW_DATA_SIZE

# Extract files
GoTo FILE_TABLE_OFFSET
Get FILE_COUNT long
SavePos READ_OFFSET

For I = 0 < FILE_COUNT
   GoTo READ_OFFSET

   # Read the file entry
   Get CRC32 long # guess
   Get NAME_OFFSET long
   Get FILE_SIZE long
   Get FILE_OFFSET long

   SavePos READ_OFFSET

   Math FILE_OFFSET - DATA_OFFSET

   GoTo NAME_OFFSET
   Get FILE_NAME string

   Log FILE_NAME FILE_OFFSET FILE_SIZE MEMORY_FILE
Next I
```

Luigi's compression format scanner came in handy here.

This'll give you the .brres and other files.  However I'm afraid there's some other custom formats in here that you might have trouble with.

[edit]updated GFCP stuff to handle 2 compression types, this compressed body is seen also in the contained files but used with RLE.
## Post #5
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-03-06T00:11:42+00:00
- Post Title: Wario Land: The Shake Dimension GFA files

Oh...so..."gfo3" files are inside these...crud...how will I manage to decrypt those then? Anyone have ideas?
## Post #6
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-03-06T01:57:36+00:00
- Post Title: Wario Land: The Shake Dimension GFA files

I'm fairly certain that this extracts the textures and palettes, but graphics isn't really my field.

```
# Wario Land: The Shake Dimension .gfo3

Endian Big

# Just pull out the GTEX elements for now
FindLoc OFFSET string "GTEX"
If OFFSET == ""
Exit
Endif

GoTo OFFSET
IDString "GTEX"
Get GTEX_SIZE long
Get COUNT1 short
Get COUNT2 short

SavePos READ_OFFSET

For I = 0 < COUNT1

Set FILENAME "pal"
String FILENAME + I

GoTo READ_OFFSET
Get FILE_OFFSET long
SavePos READ_OFFSET
GoTo FILE_OFFSET

Get VAL_1 short
Get VAL_2 short
If VAL_1 != 0
  Print "VAL_1 == %VAL_1%, possible error"
EndIf
If VAL_2 != 0
  Print "VAL_2 == %VAL_2%, possible error"
Endif

Math FILE_OFFSET + 4

Log FILENAME FILE_OFFSET 0x200

Next I
For I = 0 < COUNT2

Set FILENAME "tex"
String FILENAME + I

GoTo READ_OFFSET
Get FILE_OFFSET long
SavePos READ_OFFSET
GoTo FILE_OFFSET

# width x height?
Get VAL_1 short
Get VAL_2 short

Get VAL_3 long
If VAL_3 != 1
  Print "VAL_3 == %VAL_3%, possible error"
Endif

Get TEX_SIZE long

Math FILE_OFFSET + 12

# GFCP
Endian Little
IDString "GFCP"
Get HEADER_1_1 long
Get CTYPE long
If HEADER_1_1 != 1
   Print "Strange GFCP HEADER_1_1 = %HEADER_1_1%, may crash..."
EndIf
If CTYPE == 1
   ComType bpe
ElseIf CTYPE == 2
   ComType lz77wii_raw30
Else
  Print "Unknown compression %CTYPE%"
  Exit
EndIf

Get RAW_DATA_SIZE long
Get COMPRESSED_DATA_SIZE long
Math TEX_SIZE - 0x14
If TEX_SIZE != COMPRESSED_DATA_SIZE
  Print "TEX_SIZE (%TEX_SIZE%) != COMPRESSED_DATA_SIZE (%COMPRESSED_DATA_SIZE), may crash"
Endif

Endian Big

Set CDATA_OFFSET FILE_OFFSET
Math CDATA_OFFSET + 0x14

# Decompress
Clog FILENAME CDATA_OFFSET COMPRESSED_DATA_SIZE RAW_DATA_SIZE

Next I

```


I identified some bytes that are probably texture width and height, I'm gonna try putting together BMPs assuming that the palette is 5551 RGBA like the N64 (since that's all I know).
## Post #7
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-03-06T02:03:40+00:00
- Post Title: Wario Land: The Shake Dimension GFA files

Oh! Thank you! I can't express how much I appreciate your help. I hope we get this solved soon, but even so I can try to use any color information from the brres files in the output of the gfo3's.
## Post #8
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-03-06T13:17:25+00:00
- Post Title: Wario Land: The Shake Dimension GFA files

Well here I am, 15 straight hours later: [gfo2png 0.2](http://hcs64.com/files/gfo2png02.zip).  Seems to work on all the .gfo2 and .gfo3 files that come out of the .gfas that you had put up.  There was a whole lot to discover, so I wouldn't be surprised if you come across new issues in other files.
## Post #9
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-03-06T18:26:30+00:00
- Post Title: Wario Land: The Shake Dimension GFA files

Wow...amazing! It works perfectly! Though I wish there were an easier program to use to extract brres PNGs. But this works just fine! Thank you so very much! You're excellent!
