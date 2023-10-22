## Post #1
- Username: Kailyz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 13, 2022 3:15 am
- Post datetime: 2023-01-26T17:54:05+00:00
- Post Title: Treasure Island game (2005) - DAT archives

I made this post a month ago but left it due to work making it go to the shadows and still got no solution so im reposting it. 
I have tried anything i could to get the animations of the characters that appear in this game with no avail and tried to get help in discord servers and failed,if someone could somehow find these for me i will be deeply thankful. Thanks in advance!

Here's a link to the game,the page and the game itself is in Russian so i recommend using a translator,most of the files are in english. <link removed by moderator>
To be more clear,i have already attempted to unpack some files with Dragon Unpacker and i only got assets (TGA and BMP) that have no animation in game,all the chapters and common in the DATA folder. I have zero idea on where the animations are located. The script.dat file does contain the name of them,probably sprite sheets,but i could not find anything more than that.
## Post #2
- Username: Kailyz
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-01-26T21:30:25+00:00
- Post Title: Treasure Island game (2005) - DAT archives

So I've checked DAT archives from "DATA"  folder in "Treasure Island" game.



screenshot000309.png (61.92 KiB) Viewed 262 times



It seems like it is a custom archive format with encrypted index.
The data itself is not encrypted, that's why you can rip for example some WAV files from "Sound.dat"
using Dragon Unpacker or any other ripper from this article [http://wiki.xentax.com/index.php/Extraction_tools](http://wiki.xentax.com/index.php/Extraction_tools)


But if you would like to know where are the animations, it would require some reverse engineering,
e.g. using debugger to find out which function is responsible for decrypting
More info here [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
My guess is that they are stored in "ChapterX.dat" or in "Common.dat" 


EDIT: all archives share the same signature "D0 34 90 DF", so this may be XOR.
## Post #3
- Username: Kailyz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 13, 2022 3:15 am
- Post datetime: 2023-01-27T08:42:58+00:00
- Post Title: Treasure Island game (2005) - DAT archives

Thank you so much! do you know what can i do from there? i sadly have no idea about XOR files and my experience on reverse engineering is very little,is it similar to ZIP files?
## Post #4
- Username: Kailyz
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-01-27T18:14:11+00:00
- Post Title: Treasure Island game (2005) - DAT archives

> what can i do from there?
You have 2 options here:
1. Learn more about reverse engineering (for example from the tutorials I've linked in the previous post)
and then try to break the encryption yourself
2. Wait until someone solve the issue for you and share some script or program capable of extracting the data you want

> is it similar to ZIP files?
No, it seems to be custom.
## Post #5
- Username: Kailyz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 13, 2022 3:15 am
- Post datetime: 2023-01-27T18:46:31+00:00
- Post Title: Treasure Island game (2005) - DAT archives

I sadly don't have enough time in my hands for now to learn so i'll have to wait for someone to give me a hand,but thank you!
## Post #6
- Username: Kailyz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 13, 2022 3:15 am
- Post datetime: 2023-01-31T06:31:48+00:00
- Post Title: Treasure Island game (2005) - DAT archives

I sadly think i'll get no one to help,do you by any chance know anyone who could provide me a script or similar? i been with this for months now and im really getting frustrated
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2023-01-31T20:13:59+00:00
- Post Title: Treasure Island game (2005) - DAT archives

Header and entry table is encrypted by modified RC4 

Anyway here tool and code
[https://github.com/Ekey/TI.DAT.Tool](https://github.com/Ekey/TI.DAT.Tool)
## Post #8
- Username: Kailyz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 13, 2022 3:15 am
- Post datetime: 2023-02-07T18:26:44+00:00
- Post Title: Treasure Island game (2005) - DAT archives

Thank you so much!!! it means a bunch,now i sadly need to find a way to see the files,they are bta and seem to be very rare,could it also be encrypted?
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2023-02-20T23:09:05+00:00
- Post Title: Treasure Island game (2005) - DAT archives

> Reply from Kailyz ↑Wed Feb 08, 2023 2:26 am at Wed Feb 08, 2023 2:26 am
>
> 
Thank you so much!!! it means a bunch,now i sadly need to find a way to see the files,they are bta and seem to be very rare,could it also be encrypted?

I don't know about the content, but the files inside the archives are not encrypted or compressed.
## Post #10
- Username: Kailyz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 13, 2022 3:15 am
- Post datetime: 2023-02-21T18:11:29+00:00
- Post Title: Treasure Island game (2005) - DAT archives

Yeah i searched and i could not find anything on this file type,it seems to be exclusive from the game engine it was made on,is there anything i can do from here to try to see the image,like see if it has bmp or tga code inside? or is it impossible?
