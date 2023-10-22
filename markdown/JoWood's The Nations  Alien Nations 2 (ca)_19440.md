## Post #1
- Username: glupiekonto
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 20, 2019 12:07 am
- Post datetime: 2019-02-03T20:34:57+00:00
- Post Title: JoWood's The Nations / Alien Nations 2 (*ca)

So for few days now I'm trying to extract Alien Nations archives. So far I've managed to succesfuly extract music files. Yet when using same method for tga files I can't open images (manually copied data from file body and saved as TGA, it is working for mp3). I'm think Im missing something. Maybe I need dimensions and palette of some kind?

Archive is starting with magic "binary.archive00", then there is offset which contains file names. There is something before header ending but I cant figure it out.
I've found file names, reversed file types (gami = imag, ewav = wave, pmac = camp(aign), txet = text etc.), files length, files data offsets and files bodies.

One strange thing, there are some file names which are too long for 16 chars limit so they miss extension yet they still have file type
[music.PNG](https://xentaxbackup.github.io/file/15645_music.PNG)
## Post #2
- Username: glupiekonto
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 20, 2019 12:07 am
- Post datetime: 2019-02-03T20:40:44+00:00
- Post Title: JoWood's The Nations / Alien Nations 2 (*ca)

Header ending is always 01 but byte before varies from C0 to C1.
This 38 bookmark I can't figure out as well as 3C
[header.PNG](https://xentaxbackup.github.io/file/15648_header.PNG)
## Post #3
- Username: glupiekonto
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 20, 2019 12:07 am
- Post datetime: 2019-02-03T20:46:29+00:00
- Post Title: JoWood's The Nations / Alien Nations 2 (*ca)

So teal is filename obviously, gray for type, pink for file size and yellow is file body offset. Values before red endings varies in different archives
[ending.PNG](https://xentaxbackup.github.io/file/15649_ending.PNG)
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2019-02-05T06:58:01+00:00
- Post Title: JoWood's The Nations / Alien Nations 2 (*ca)

Would need example files if want someone's help on this as else it's just guessing work without being able to try.

Anyway do the files have tga extensions on name or where the TGA assumption is from? It's often that name has the input image extension and yet the stored one may not be TGA/generic format anymore and if it is, it is missing possibly the native headers along the info and uses game's own.

Since you extract the files using the proper offsets, the files need to be figured out and in comparison MP3 is the most easiest format to extract/play as it holds playback header info all across the file so even wrong offset extracted mp3 would play, heck you can probably rename the archive holding mp3s into .mp3 and play it that way too unless archive is compressed.

Ah game(s) is as old as year 2001-2003, that makes one question if they used TGA, anyhow filename in archives being cut is not an issue often as archives usually store a file format type flag and thus game's don't make use of the file extension and the value would obviously differ in archives storing different files.
## Post #5
- Username: glupiekonto
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 20, 2019 12:07 am
- Post datetime: 2019-02-05T20:12:53+00:00
- Post Title: JoWood's The Nations / Alien Nations 2 (*ca)

> Reply from Apollo
>
> Would need example files if want someone's help on this as else it's just guessing work without being able to try.

Anyway do the files have tga extensions on name or where the TGA assumption is from? It's often that name has the input image extension and yet the stored one may not be TGA/generic format anymore and if it is, it is missing possibly the native headers along the info and uses game's own.

Since you extract the files using the proper offsets, the files need to be figured out and in comparison MP3 is the most easiest format to extract/play as it holds playback header info all across the file so even wrong offset extracted mp3 would play, heck you can probably rename the archive holding mp3s into .mp3 and play it that way too unless archive is compressed.

Ah game(s) is as old as year 2001-2003, that makes one question if they used TGA, anyhow filename in archives being cut is not an issue often as archives usually store a file format type flag and thus game's don't make use of the file extension and the value would obviously differ in archives storing different files.

Well, many of static sprites do share .tga extension (and gami (imag) flag) yet there is no "truevision" keyword in archives.

Here you can take a look: [https://mega.nz/#F!yRclAa5I!K_8muFSNW2XvVXrMO_UTrQ](https://mega.nz/#F!yRclAa5I!K_8muFSNW2XvVXrMO_UTrQ)
It contains Kaitai Struct definision, my python extractor and smallest game archive (there are 21 files of which 3 are .tga)
## Post #6
- Username: Kedar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 22, 2022 4:31 pm
- Post datetime: 2022-05-28T17:17:46+00:00
- Post Title: JoWood's The Nations / Alien Nations 2 (*ca)

Hello,

I would like to bump this thread and also ask for help.

Thanks to instructions from @glupiekonto I was able to extract files from archives by myself.
Additionally, I deducted that first two bytes of image is width and next two bytes is height. Then I was trying to understand the rest part of image contents, which by looking at game.exe strings it somehow should be ARGB4444, but without success. Image size seems too small for me, take a look at button_50.tga (50x15):

Not sure if extracted file size is wrong or there is superb compression here.

Here you will find description of everything that I know + files: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1oaCIXKInJg225m_7iBp3LP4LpIqEgqUN?usp=sharing)

<Post has been edited by moderator. Paid requests are not allowed here.>
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-31T21:07:48+00:00
- Post Title: JoWood's The Nations / Alien Nations 2 (*ca)

Well, I did my own research on those CA archives.
Here is the file format description and some additional info [http://wiki.xentax.com/index.php/The_Nations_CA](http://wiki.xentax.com/index.php/The_Nations_CA)

And here is my quickbms script to extract all data
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/The%20Nations/The_Nations_CA_script.bms)

My theory is that those archives use some kind of custom hash function for storing filenames.
I think that's why some of the names are trimmed. So those visible strings are really a partial source names, not the actual filenames.
Hash function needs to be reverse engineered to get real names.

As for TGA files, they are definitely compressed or encrypted. They can't be viewed in Texture finder and they don't match TGA file format.
But good news are that in enon/none entries there are some RAW files that can't be viewed without issues.
[https://imgur.com/a/JLvanY5](https://imgur.com/a/JLvanY5)
[https://imgur.com/a/55ht3YS](https://imgur.com/a/55ht3YS)
## Post #8
- Username: Kedar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 22, 2022 4:31 pm
- Post datetime: 2022-06-13T11:10:56+00:00
- Post Title: JoWood's The Nations / Alien Nations 2 (*ca)

> Reply from ikskoks ↑Wed Jun 01, 2022 5:07 am at Wed Jun 01, 2022 5:07 am
>
> 
My theory is that those archives use some kind of custom hash function for storing filenames.
I think that's why some of the names are trimmed. So those visible strings are really a partial source names, not the actual filenames.
Hash function needs to be reverse engineered to get real names.

As for TGA files, they are definitely compressed or encrypted. They can't be viewed in Texture finder and they don't match TGA file format.
But good news are that in enon/none entries there are some RAW files that can't be viewed without issues.
https://imgur.com/a/JLvanY5
https://imgur.com/a/55ht3YS

If hashing is involved here, then there is nothing that we can do, as hashing is an irreversible operation.
However, while debugging the game, I can see that there is a function DataCache::loadImage which takes the full file name as parameter and then this name is truncated to 16 chars. Basically, at the start, it creates a key for cache with 4 chars of type name and 16 chars of file name. Nonetheless, as the full name is passed to the function, then somewhere it needs to be stored.

Also, I found a place in the assembly code where archive entry is loaded. The first 20 bytes of the image archive entry are metadata. Then there is a loop with fancy operations and after the end of this loop, in memory we have 2 * imageWidth * imageHeight bytes:
Image: [https://imgur.com/a/ukgV1Fb](https://imgur.com/a/ukgV1Fb)
File: [https://drive.google.com/file/d/19lfbcP ... sp=sharing](https://drive.google.com/file/d/19lfbcPiuyk2mF4duiQYEI4G78IiSdfzw/view?usp=sharing)
Now it's just a matter of understanding what is going on in this loop 
Or maybe there is some kind of tool/way to find out the compression algorithm based on the source and result without looking at the actual code?
## Post #9
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-06-14T12:21:47+00:00
- Post Title: JoWood's The Nations / Alien Nations 2 (*ca)

> Reply from Kedar ↑Mon Jun 13, 2022 7:10 pm at Mon Jun 13, 2022 7:10 pm
>
> 
Also, I found a place in the assembly code where archive entry is loaded. The first 20 bytes of the image archive entry are metadata. Then there is a loop with fancy operations and after the end of this loop, in memory we have 2 * imageWidth * imageHeight bytes:
Image: https://imgur.com/a/ukgV1Fb
File: https://drive.google.com/file/d/19lfbcP ... sp=sharing
Now it's just a matter of understanding what is going on in this loop 
Or maybe there is some kind of tool/way to find out the compression algorithm based on the source and result without looking at the actual code?

The format uses a 16 bit run length encoding to compress the files. In short, after reading the metadata the remainder of the file is converted to a uint16 array. Iterating this array, a value of < 0x100 is a direct copy of n bytes (plus an optional extra 1 or 2) otherwise it is a back-reference on the output buffer.

A C# decompression implementation can be found [here](https://gist.github.com/barncastle/b4ff6d88d488a3f337b566f05a4eefba).
## Post #10
- Username: glupiekonto
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 20, 2019 12:07 am
- Post datetime: 2023-05-19T15:54:09+00:00
- Post Title: JoWood's The Nations / Alien Nations 2 (*ca)

Based on a barncastle's code I've put some scraps together (mostly ChatGPT code) and created C# decompressor along with Python converter from binary to png.

It is kinda working, 600 or so images aren't converted (out of 2100), program is throwing some exceptions, I have no knowledge how to fix it, maybe someone will improve it in the future. I can't program for sure, these are mostly hacks.

I was really interested in characters avatars and these are not converted   

[https://imgur.com/a/7BR5jEB](https://imgur.com/a/7BR5jEB)

Run CAProcessor with arguments <inputpath> <outputpath> .tga
Edit converter.py paths to convert .raw files into .png

[https://github.com/xpawelsky/TheNationsDecompressor](https://github.com/xpawelsky/TheNationsDecompressor)

EDIT:
Turns out these avatars are actually 72x90 and not 72x72. I don't know why program got those wrong. It works if you provide dimensions manually for these 600 images (these are labeled as 72x72)
