## Post #1
- Username: personperson
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 03, 2020 4:41 am
- Post datetime: 2020-09-04T14:51:16+00:00
- Post Title: General Artifex Mundi File Extractor

I'm a big fan of Hidden Object Games and Artifex Mundi develops/publishes quite a few. They're silly, quirky, have bad voice acting and usually worse plots. But the art direction really appeals to me and I find myself endeared to these games. An option typically included in these games has been to download wallpapers from a selection of the scenes in the games (also a subset of the soundtrack). However, over the years, I've found this to be insufficient. Either the particular scene (or song) I like best is not among the choices, or there are other artifacts added on the wallpaper. I decided to find a way to extract the information from these games.

Some searching found there were a few questions about it (some even on this forum), but for the most part this particular space was unexplored. I did find a post from 2015 outlining the basics of opening CUB archives here: [https://epw14.wordpress.com/2015/12/24/ ... undi-cube/](https://epw14.wordpress.com/2015/12/24/artifex-mundi-cube/). From this basic code and with the help of the community on the XeNTaX discord, I was able to build what I think is a general Artifex Mundi asset extractor.

The C++ code included should have just about everything you need to run it, except for the lz4 library which you will need to download from here: [https://github.com/lz4/lz4/blob/dev/lib/lz4.h](https://github.com/lz4/lz4/blob/dev/lib/lz4.h). I am also running on a linux machine, so if some of the file operations don't work on Windows or Mac, you may have to make some adjustments for this to work on your machine.

The program has two modes based on the input:
1. CUB extraction: When a CUB file is detected, it will attempt to extract the files into a folder named after the input file. It will make some adjustments based on the version of CUB detected, 1.0 or 1.1 (byte ordering of length and offset are different). Text, sound, movie, binary, and image files will all be extracted, with the majority of texture files being the proprietary type STEX.
2. STEX extraction: When a STEX file is detected, it will attempt to extract the raw DDS data stream from it, outputting it in a similarly named .raw file. It's worth noting here that the output file size and dimensions are something you'll have to manually get/set. I have things set for the large textures of 2048x2048, but if you want something else, you would have to make the adjustment. This file can be processed by RawtexCmd.exe to prepend the DDS header onto it. All the DSS data I've seen has been with DXT5 compression. The corresponding call to RawtexCmd might look like this: RawtexCmd.exe Game_1080_9000_DarkCity.Extras.ExtrasMain_4.raw DXT5 0 2048 2048. This would yield a file Game_1080_9000_DarkCity.Extras.ExtrasMain_4.dds for further use to you  .

I've extracted files from about a dozen games in my library and this code seems to work with all of them. I've tried games published between 2015-2020, so games that are from before that or in the future may not work with this tool without modification. I've tried to comment the code and explain some of the fishier parts.

Enjoy!
[AM.cpp.tar.gz](https://xentaxbackup.github.io/file/18693_AM.cpp.tar.gz)
