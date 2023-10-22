## Post #1
- Username: StijnDark
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 28, 2021 7:00 pm
- Post datetime: 2021-11-06T12:09:27+00:00
- Post Title: Editting Uasset / blueprint files and weird symbols/text while editing in a text/hex editor

Heyy   ,

So i have a lot of .uasset and .uexp files (Unreal Engine), some blueprints and some models/textures/materials etc. But i opened it with a text editor / hex editor and there is some weird symbols/text in it and i don't know what it means and how to translate it. 



Screenshot_764.png (83.24 KiB) Viewed 94 times



This file is a blueprint file and i can't edit and open it in unreal engine cuz its cooked.
Now my question is, how am i able to open this and edit this? And what does those random symbols / characters mean? And how can i "translate" them into normal text or whatever it's meant to be?
## Post #2
- Username: StijnDark
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 28, 2021 7:00 pm
- Post datetime: 2021-11-06T12:16:46+00:00
- Post Title: Editting Uasset / blueprint files and weird symbols/text while editing in a text/hex editor

So for example:

There is a line with GrowthStages, GrowthTimeMinutes, Health and HealthRegenAmount.



Screenshot_765.png (4.14 KiB) Viewed 90 times



You can change them all but i don't know what to put there and what is there atm. Cuz i have no clue what those symbols / characters are at the end of each one of them. There is probably something easy for this that i don't know and haven't seen before.
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-06T21:38:47+00:00
- Post Title: Editting Uasset / blueprint files and weird symbols/text while editing in a text/hex editor

So you're trying to edit binary files with text editor. It's wrong, you shouldn't do that.

You can use hex editor (like Hex Workshop) for direct editing 
or some more advanced tools like umodel [https://www.gildor.org/downloads](https://www.gildor.org/downloads)
Please also try to google something like "uasset xentax", because I think there were several similar topics already.

And here's the file format [http://wiki.xentax.com/index.php/Unreal_Engine_4_UASSET](http://wiki.xentax.com/index.php/Unreal_Engine_4_UASSET) for reference.
## Post #4
- Username: StijnDark
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 28, 2021 7:00 pm
- Post datetime: 2021-11-07T10:09:49+00:00
- Post Title: Editting Uasset / blueprint files and weird symbols/text while editing in a text/hex editor

> Reply from ikskoks ↑Sun Nov 07, 2021 5:38 am at Sun Nov 07, 2021 5:38 am
>
> 
So you're trying to edit binary files with text editor. It's wrong, you shouldn't do that.

You can use hex editor (like Hex Workshop) for direct editing 
or some more advanced tools like umodel https://www.gildor.org/downloads
Please also try to google something like "uasset xentax", because I think there were several similar topics already.

And here's the file format http://wiki.xentax.com/index.php/Unreal_Engine_4_UASSET for reference.

Ahhh i see. Thx for your reply!  

Though i don't really understand the file format, how do i use it and how am i able to understand it?

And i am not using a text editor to edit them, i am using a hex editor for that. But it shows exactly the same so it was a bit easier to make a screenshot in the text editor (atleast for me).
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-07T10:38:49+00:00
- Post Title: Editting Uasset / blueprint files and weird symbols/text while editing in a text/hex editor

> Though i don't really understand the file format, how do i use it and how am i able to understand it?
To understand reverse engineering file formats, you need to learn few things,
you can start here [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)

But it's a long way and if you want "faster" solution you can use one of Gildor's tools (umodel etc.)
or some script/tool which already exist 
(try google "uasset script" or "uasset tool")

Maybe something like this would be a good start [https://github.com/kaiheilos/Utilities](https://github.com/kaiheilos/Utilities)
## Post #6
- Username: StijnDark
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 28, 2021 7:00 pm
- Post datetime: 2021-11-07T20:25:45+00:00
- Post Title: Editting Uasset / blueprint files and weird symbols/text while editing in a text/hex editor

alright tyvm! I will take a look at that!
