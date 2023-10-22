## Post #1
- Username: Lexar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 21, 2022 2:17 am
- Post datetime: 2022-08-20T18:44:37+00:00
- Post Title: AFK Arena (Android) - LZAP files

I apologize in advance for the English. I have a file with the extension "lzap" which starts with the header "LZ4PNG" and contains the header "PKM 10" at the beginning and in the middle. I didn’t manage to unpack using “lz4”, I tried to extract bytes from the beginning of one “PKM 10” to the beginning of the second one in order to unpack it in this form using etc1tool, but the output is just noise with rare stripes of the original image. I also know that the first part of the image is the image itself, and the second part is a mask for overlaying the alpha layer for first image. I've been sitting on this for two days, and so I didn't come up with anything, I rummaged through Google, but I didn't find any information. I ask you for help with this.

[Compressed image](https://drive.google.com/file/d/10BLbMkPefcPGEAcGOGV465M56XzThnFe/view?usp=sharing)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-21T11:20:05+00:00
- Post Title: AFK Arena (Android) - LZAP files

What game is it from?
And which platform?
## Post #3
- Username: Lexar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 21, 2022 2:17 am
- Post datetime: 2022-08-21T11:28:56+00:00
- Post Title: AFK Arena (Android) - LZAP files

> Reply from ikskoks ↑Sun Aug 21, 2022 7:20 pm at Sun Aug 21, 2022 7:20 pm
>
> 
What game is it from?
And which platform?
Game: AFK Arena
Platform: Android
## Post #4
- Username: Lexar
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-21T12:57:01+00:00
- Post Title: AFK Arena (Android) - LZAP files

Here is the file format [http://wiki.xentax.com/index.php/AFK_Arena_LZAP](http://wiki.xentax.com/index.php/AFK_Arena_LZAP)

And here is script for unpack/pack [https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/AFK%20Arena/AFK_Arena_LZAP_script.bms)


After decompressing, you can try to open your files in texture cooker and find the proper
resolution and format [https://imgur.com/a/HAQsdYI](https://imgur.com/a/HAQsdYI)

This info is stored as well in the atlas file [https://imgur.com/a/UhstYpQ](https://imgur.com/a/UhstYpQ)
(at least for original file, not sure if it also matches output texture...)
For your sample it should be 2020x2020 and RGBA4444.
## Post #5
- Username: Lexar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 21, 2022 2:17 am
- Post datetime: 2022-08-21T15:34:47+00:00
- Post Title: AFK Arena (Android) - LZAP files

> Reply from ikskoks ↑Sun Aug 21, 2022 8:57 pm at Sun Aug 21, 2022 8:57 pm
>
> 
And here is script for unpack/pack https://github.com/bartlomiejduda/Tools ... script.bms
This script only unpacks the first image, followed by the second one. I don't know the language it's written in, so can you edit it so that it unpacks the second image as well?
## Post #6
- Username: Lexar
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-21T21:11:28+00:00
- Post Title: AFK Arena (Android) - LZAP files

Sure. Script has been updated:
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/AFK%20Arena/AFK_Arena_LZAP_script.bms)

It's written in MexScript [https://en.wikipedia.org/wiki/MexScript](https://en.wikipedia.org/wiki/MexScript)
and it should be used with quickbms [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
## Post #7
- Username: CM4786
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 05, 2023 3:23 am
- Post datetime: 2023-04-04T19:57:36+00:00
- Post Title: AFK Arena (Android) - LZAP files

The script is working perfectly on the LZAP files for the game's hero animation sprite sheets, but the LZAP files for the hero artwork are giving out an error.

See here: [https://imgur.com/a/PkwSKC1](https://imgur.com/a/PkwSKC1)
As a sample, here's the same LZAP file from the image above: [https://drive.google.com/file/d/1YiqFQU ... share_link](https://drive.google.com/file/d/1YiqFQUiA55C2kfpLd8sSJod1ArSoORMP/view?usp=share_link)

The 2 first PKMs that are extracted are working fine, but since the 3rd PKM is giving an error, the script won't move on to the next LZAP in the folder.

Hope it's fixable, thanks in advance 

Edit:
I'm not familiar with MexScript, but I changed the code a bit and it's working fine atm, hopefully I didn't break something else XD
Here's the change: [https://imgur.com/a/v7bEWas](https://imgur.com/a/v7bEWas)
