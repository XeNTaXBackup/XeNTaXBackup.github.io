## Post #1
- Username: xenexabc
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Sep 03, 2018 7:02 am
- Post datetime: 2022-06-07T03:45:46+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

How to extract textures from Texture2DArray?

I'm trying to extract textures from Rainbow Six Mobile, game on Unity engine. Standard Texture2D works, but I'm missing a lot of textures that I think are stored in Texture2DArray. How can I extract those? I only end up with single texture, or can export .DAT file. Any help appreciated.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-07T19:11:51+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

Can you upload a few samples?
## Post #3
- Username: xenexabc
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Sep 03, 2018 7:02 am
- Post datetime: 2022-06-07T22:34:50+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

[https://www34.zippyshare.com/v/ykiTuXj5/file.html](https://www34.zippyshare.com/v/ykiTuXj5/file.html) - extracted Texture2DArray as .DAT

[https://www23.zippyshare.com/v/oqCIhI8A/file.html](https://www23.zippyshare.com/v/oqCIhI8A/file.html) - original game file .bundle
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-09T19:56:01+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

Well, I couldn't find a tool that supports your samples. 
UnityEx Ultimate extracts only ATEX files from the bundle (basically the same as DAT files you have provided) without converting them to usable format.
Asset Studio doesn't recognize Texture2DArray entries at all.

As for ATEX/DAT files, they may be encrypted or compressed as I couldn't preview them in TextureFinder.
Also I didn't saw any index array in those files, so it may be hidden elsewhere.
Without index, you won't be able to extract data with proper filenames - even if the compression\encryption method will be known.

If you want to try some other programs,
you can start with tools listed here [http://wiki.xentax.com/index.php/List_of_Unity_Tools](http://wiki.xentax.com/index.php/List_of_Unity_Tools)
## Post #5
- Username: xenexabc
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Sep 03, 2018 7:02 am
- Post datetime: 2022-06-09T20:32:10+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

What would the index array look like? I really want to get these textures.

I found some tools for the Unity editor itself, but im not proficiant in that engine to use them, and I'm not sure if they would accept the .dat files either..
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-09T22:16:44+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

> What would the index array look like?
Index is a data structure with information needed for assets extraction like: filename, compressed size, uncompressed size, file offset, file hash etc.
Those fields can be stored in any order in archive.
## Post #7
- Username: xenexabc
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Sep 03, 2018 7:02 am
- Post datetime: 2022-06-09T22:22:47+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

Would it help if i shared all the game files?
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-10T16:39:53+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

> Reply from kixpress ↑Fri Jun 10, 2022 6:22 am at Fri Jun 10, 2022 6:22 am
>
> 
Would it help if i shared all the game files?

No. It's forbidden to share whole games on this forum.   

Besides, I'm not really into Unity files. You can try to wait for other users research
or try to find some community focused on Unity games.

You can also try to raise an issue on some Unity tools github pages,
for example UABEA [https://github.com/nesrak1/UABEA/issues](https://github.com/nesrak1/UABEA/issues)
## Post #9
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-06-12T12:43:07+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

Here is script for converting such dat files into respective astc, compatible with PVRTexTool or similar tools. Not sure if the game is using different compression formats though, there was only 6x6 in the example.

Update: Script is updated to actually extract all textures from texture array. Only square textures (512 and 1024) are supported because of hardcoded sizes.



 rs6mobile_textures_v2.zip
(765 Bytes) Downloaded 25 times
## Post #10
- Username: xenexabc
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Sep 03, 2018 7:02 am
- Post datetime: 2022-06-13T15:08:27+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

sorry for previous post! i totally missed the name of the tool.
i installed the pvrtextool, i am able to open the astc files, but i totally can't find a way to cycle through multiple images within the file. that's what array is for, right? to store multiple images. i clicked every option but i don't seem to be able to preview anything more than the default image.
## Post #11
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-06-13T17:21:39+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

@kixpress: I think you just misunderstood something. Original bundle contains texture array as a single object, but upon extraction it's split into separate elements (textures, in this case dat files). And after that both script and PVRTexTool are working with single textures. If you want to somehow put them back into array and bundle, it's probably possible only in unity itself.
## Post #12
- Username: xenexabc
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Sep 03, 2018 7:02 am
- Post datetime: 2022-06-13T17:27:08+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

hmm.
do i?
the problem i'm encountering there is a lot of level textures missing in the game assets that i was able to extract/decompress.
searching online about texture array, it looks like it's storing multiple textures in single file. some .DAT files are even 10mb, which would be a lot just for a single texture.

[https://imgur.com/a/RKzx0t7](https://imgur.com/a/RKzx0t7)

i have went through all ~1500 extractable textures, and they are definietly not available here. looking at the picture above, it looks i'm only able to access the first texture in the array.
also attempting to create a new array itself in the pvr tool shows such possibility.

if i could get those missing textures, i could complete my task.




this is a texture in 11mb .ASTC file. i can save it as .TGA and it takes less than 1mb. so what is the remaining 10mb of data in that file?
## Post #13
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-06-13T19:56:33+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

@kixpress: Welp, you're right, original script was able to extract only first texture from an array. I was confused by the whole data addressed at once. Script is now updated for proper extraction of all textures, though it's currently limited to square 512 and 1024 textures.

There are a few problems here (not really) - tools like PVRTexTool are expecting mips after array of respective textures, while in those dat files mips are following each respective texture, so direct wrapping doesn't work (it would be too easy). In the same time, basic astc format doesn't support mips and creating something like pvr format with quickbms doesn't worth it (even though it can support both array and mips in a single file).
In case if someone else will stumble across this topic, you can take a look how to calculate block sizes for different compressions [here](https://developer.apple.com/forums/thread/701426) and also [here](https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_astc). Or just take a look how they're calculated in popular decoder solutions. Again, implementing something like this in a quickbms script doesn't make much sense, but for python one it would be much better than hardcoded values.
## Post #14
- Username: xenexabc
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Sep 03, 2018 7:02 am
- Post datetime: 2022-06-13T22:07:46+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

wow, this seems to work! however this time it quickly errors out and stops.

```
       Can't read 626016 bytes from offset 0000018c.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0    99%   395        396        . offset 0000018c

Last script line before the error or that produced the error:
  42  log MEMORY_FILE OFFSET BLOCK

- OFFSET       0x0000007c
- SIZE         0x00098e70
  coverage file 0    99%   395        396        . offset 0000018c
  coverage file -1    0%   0          16         . offset 00000000

```


do you have any idea how to fix it?
## Post #15
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-06-13T23:15:57+00:00
- Post Title: Rainbow Six Mobile (Unity) - extracting textures

@kixpress: You can run quickbms with "-." option to ignore errors in batch processing. As already said above, script supports only square textures of certain sizes, the rest will not work. Consider it more like proof-of-concept, since I'm not going to write a full-fledged converter for all possible texture types. But you can provide more samples of non-working files (not just one or two though), maybe some of them can be supported without much hassle.
