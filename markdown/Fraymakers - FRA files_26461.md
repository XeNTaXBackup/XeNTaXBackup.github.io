## Post #1
- Username: MessiasOF
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 13, 2023 12:01 am
- Post datetime: 2023-02-12T16:27:49+00:00
- Post Title: Fraymakers - FRA files

First of all, hi! I'm new here.

I really hope this post doesn't break the forum rules but the McLeodGaming team has already given their stance on modding and according to them it's ok, as long as it's not for cheating or piracy, my intention is to mod the menu UI elements appearence and stuff like that.

Let's cut to the chase: .FRA are probably authoritarian file format from McLeodGaming for the development of Fraymakers.
But I think it's not that impossible to study this file type, considering that amount of info about the game and its engine:

Details about game custom content creation tool (but it reveals some details about the game engine too):
[https://www.reddit.com/r/gamedev/commen ... ating_and/](https://www.reddit.com/r/gamedev/comments/jzk62r/discussing_our_custom_tool_for_creating_and/)

The engine and technologies used in the game that were detected by SteamDB:
[https://steamdb.info/app/1420350/info/](https://steamdb.info/app/1420350/info/)
(Also, they confirmed the use of Heaps Engine).

Another information is that their tool for custom content creation (Fraytools) is capable of generating .FRA files when exporting the content to be used in-game. Maybe this could be useful somehow since we also know what technologies Fraytools and Fraymakers uses.

Extra info:
- I found out that .FRA files are used for custom characters too and that they are encrypted in B64, some guys on the McLeod Discord managed how to get part of the code from the .FRA file that includes custom characters.

- I also found that it probably works as .DAT files. With code, images, sounds, etc. Kind of predictable as all the custom character sprites, sounds, code, manifests, etc. are stored in a single .FRA.

This is out of my league, but I really want to be able to work with these .FRA files and I'm having a lot of fun so far trying to do various things to parse the file. But it got to the point where I got stuck. If someone with more experience could give me some tips on what to do. Some of the information cited must surely be useful and I just don't know how to use it properly.
I'm sure it shouldn't be impossible any tips are welcome.  

By the way, it's something new to learn, I'm really enjoying it, messing around with HEX editors, binary parsers, etc.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-02-12T18:58:43+00:00
- Post Title: Fraymakers - FRA files

Those FRA files seems to be encrypted or compressed. No header, no index table, nothing.
Heaps Engine? Never heard of it. No information on our wiki either.

You can post few samples of FRA files, so someone else could check them out.
And if you want to do more of your own research, I would recommend to read this post first [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)


EDIT: I've checked your steamdb link and it seems more games uses this engine [https://steamdb.info/tech/Engine/Heaps/](https://steamdb.info/tech/Engine/Heaps/)
I recognize "Darksburg" and "Northgard" from some other topic on this forum, but they were using PAK archives instead [http://wiki.xentax.com/index.php/Shiro_Games_PAK](http://wiki.xentax.com/index.php/Shiro_Games_PAK)
## Post #3
- Username: MessiasOF
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 13, 2023 12:01 am
- Post datetime: 2023-02-17T17:29:57+00:00
- Post Title: Fraymakers - FRA files

Hi, sorry about the delay to respond I was kinda busy.

> And if you want to do more of your own research, I would recommend to read this post first viewtopic.php?f=29&t=22266
>
> 
>
> EDIT: I've checked your steamdb link and it seems more games uses this engine https://steamdb.info/tech/Engine/Heaps/
>
> I recognize "Darksburg" and "Northgard" from some other topic on this forum, but they were using PAK archives instead http://wiki.xentax.com/index.php/Shiro_Games_PAK
Thank you very much for the help ikskoks! I will definitely read the reverse engineering thread, I would never find it on my own. I'm going to do some experiments on top of PAK files, it may be that FRA files are similar to PAK files with just a few small differences since both games use the same engine.

> You can post few samples of FRA files, so someone else could check them out.
Of course! I have provided a link to all .FRA files available at the moment: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1MLN11j78w6ioO3wmzqzH2e1pbtk7ptic?usp=sharing)

EDIT: dat25.fra was identified as an audio file in Google Drive, interesting.

EDIT2: for some reason dat9, dat31, dat37, dat38, dat43, dat44, dat61, dat62, dat63, dat64 are missing in the game directory, maybe something incomplete since the game is on Early Access. So don't be surprised if it looks like there are files missing from the drive folder.

Any feedback is welcome.   
By the way, I'll try to post some updates if I discover anything else. I am very hopeful that .FRA is a type of .PAK
