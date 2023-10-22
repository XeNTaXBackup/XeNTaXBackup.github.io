## Post #1
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2016-05-02T22:30:44+00:00
- Post Title: Get DDS file size

Hello, this is my first post so i hope i'm posting in the correction section.

Today i started to try to mod a game called "Ultimate Spiderman" released in 2005. My goal is to write a tool to extract all files from its PCPACKs(unknown ones will be exported as binaries)
I opened a PCPACK file(most probably where the files i want are stored) and i find some unencrypted DDS files inside them, like the web texture, but after looking a little more i found that there are more DDS files than that and the size is variable. Analyzing the DDS_HEADER structure doesn't seem to help too.

So my question is how to get DDS file size so it's easier to export? 

I can upload the file that i talked about if needed.

Thanks in advance.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-05-03T21:01:09+00:00
- Post Title: Get DDS file size

> Reply from krystalgamer
>
> Analyzing the DDS_HEADER structure doesn't seem to help too.

why not? what does that structure contain? i have no idea what it looks like!

the dds version will help - different formats pack the texture data differently. it might be stored as another value somewhere. do you also have the width and height?
## Post #3
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-05-04T02:26:27+00:00
- Post Title: Get DDS file size

you have to do this for each mip
but here is what i use for the main mip.

```
DXT5    - dataSize = (imgWidth * imgHeight * 8) // 8
RGBA32 - dataSize = (imgWidth * imgHeight * 8)
```
## Post #4
- Username: krystalgamer
- Rank: beginner
- Number of posts: 31
- Joined date: Tue May 03, 2016 6:20 am
- Post datetime: 2016-05-04T20:11:02+00:00
- Post Title: Get DDS file size

Sorry for being so vague, i thought that there was an undocumented variable of DDS_FILE header the contained its size but now i understand it can be anywhere in the archive.

> Reply from WRS
>
> krystalgamer wrote:Analyzing the DDS_HEADER structure doesn't seem to help too.

why not? what does that structure contain? i have no idea what it looks like!

the dds version will help - different formats pack the texture data differently. it might be stored as another value somewhere. do you also have the width and height?

The texture i extracted is DXT3, its height and width is 64x64. I included the 0x00 at the end because at the time i had no ideia if they're required.

> Reply from chrrox
>
> you have to do this for each mip
but here is what i use for the main mip.
Code: Select allDXT1    - dataSize = (imgWidth * imgHeight * 4) // 8
DXT5    - dataSize = (imgWidth * imgHeight * 8) // 8
RGBA32 - dataSize = (imgWidth * imgHeight * 8)

Hmm any suggestion for DXT3? I uploaded the file i extracted.


I'll look more in the archive i've been so busy that i couldn't look more deeply into PCPACKs. I'll post an update ASAP.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-05-04T21:13:15+00:00
- Post Title: Get DDS file size

Dxt3 and 5 are identical size only difference is how alpha channel is read
