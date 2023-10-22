## Post #1
- Username: Noodz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 11, 2023 7:04 am
- Post datetime: 2023-06-10T23:08:23+00:00
- Post Title: Help me find how to translate Paradise Killer please

Hello everyone,

I'm new to the translating scene, and I have a lot to assimilate. One of the project I'd love to make is translating Paradise Killer in my native language.
I tried to find where to find are the text files, tried to unpack the .pak file (I can't find a proper .bms script). Maybe I'm not on the good road for this but I'm trying to find it. It's hard to know how to go to your goal when you have little idea where to go. 

Will someone help me figure out finding how where are the texts, how to extract them, etc... I have little knowledge, but I'm willing to learn and really determinated.

Thanks for reading me !
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-11T07:48:20+00:00
- Post Title: Help me find how to translate Paradise Killer please

Hi, this game is on Unreal Engine v4.24.3.
In standard cases, for UE games you should always visit this wiki page to test some UE tools [http://wiki.xentax.com/index.php/List_o ... #PAK_Tools](http://wiki.xentax.com/index.php/List_of_Unreal_Engine_Tools#PAK_Tools)

But for your case you need to use specific version of unrealpak to extract data.
Here is download link [https://drive.google.com/file/d/1MYq7uX ... sp=sharing](https://drive.google.com/file/d/1MYq7uXIbGyIl-R0bHm16Y0ntap-v5j1b/view?usp=sharing)

You should execute it like this:

```
UnrealPak.exe <pak_file> -Extract <output_directory>
```


Then you will have all files extracted from PAK and you can search for text like this [https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)
I've already did this for you, so I know that texts are in directory "\ParadiseKiller\Content\Localization\Game\en\"

There is a file "Game.locres" in this directory. You can use UnrealLocres tool [https://github.com/akintos/UnrealLocres ... /tag/1.1.1](https://github.com/akintos/UnrealLocres/releases/tag/1.1.1)
to output text to "Game.csv" file and then translate it to your language.
## Post #3
- Username: Noodz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 11, 2023 7:04 am
- Post datetime: 2023-06-11T13:35:12+00:00
- Post Title: Help me find how to translate Paradise Killer please

Oh man this is so incredible, thank you sooo so much !! This coming week is a loaded one for me, I'll barely have time to look into it but as soon as I'm back I'm definitely putting my head into it. I'll try to be as autonomous as possible but if I ever need a bit of help , can I count you ? 

Again, thanks so much, to be honest I wasn't expecting to be lucky ahah

EDIT : Oh just one question, I'll guess when I'm done I'll have to repack it some way or another, how do I do that ? Do I have to rebuild the locres file with UnrealLocres tool and then rebuild the pak with UnrealPak ? Thanks !
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-11T13:50:19+00:00
- Post Title: Help me find how to translate Paradise Killer please

> if I ever need a bit of help , can I count you ?
Sure 

> Do I have to rebuild the locres file with UnrealLocres tool and then rebuild the pak with UnrealPak ?
Yes, that's the easiest way to do this.
There are also some other methods for modding UE games (like using ModManager etc.)
Everything is described here [https://web.archive.org/web/20230507163 ... 251#p56251](https://web.archive.org/web/20230507163024/https://zenhax.com/viewtopic.php?f=9&t=1005&p=56251#p56251)
## Post #5
- Username: Noodz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 11, 2023 7:04 am
- Post datetime: 2023-06-11T13:56:49+00:00
- Post Title: Help me find how to translate Paradise Killer please

Again, thaaaaaaaanks a lot ! You're amazing !

I've downloaded all you gave me and bookmarked the links  I think another problem I might (and probably will) encounter is the modification of fonts, I'm french and we have other letters like é è ç etc, I'm working with a friend on another game translation and while the extraction and translation are going great, the font modification part is one thing that make us scratch our head, and I think I'll be having this again here  

EDIT : I managed to access the csv file, I can actually start modifying stuff ! Incredible ! But what would be the command to rebuild the pak file ? I managed to rebuild the locres file (I think) but I'm stuck with rebuilding the pak, to test stuff. I tried running 
```
UnrealPak.exe <pak_file> -Import <output_directory>
```


just to try it out, but it doesn't seem to be that because I get an error..
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-11T17:06:38+00:00
- Post Title: Help me find how to translate Paradise Killer please

Editing fonts for this game is easy. All fonts are located in the "\ParadiseKiller\Content\Assets\Fonts" directory.
Fonts have UFONT extension and they are in fact TTF fonts. So you can just change it for example from "Kargi.ufont" to "Kargi.ttf"
and you can edit font in any TTF editor (e.g. High-Logic Font Creator) [https://www.high-logic.com/font-editor/fontcreator](https://www.high-logic.com/font-editor/fontcreator)


As for rebulding PAK file, usually unrealpak should be enough to do it, but for this game it just throws errors when I try to use "-Create" option.
So I don't have any solution for this issue right now. You can try to do your own research on this topic.


EDIT: Ok, I have a solution. Game seems to work fine with unpacked files. So you just need to unpack with unrealpak,
then copy all files to match original directory structure and then DELETE pak file to make this work.

I did a small test and edited file "\Paradise Killer\ParadiseKiller\Content\UI\MainMenu\MainMenuWidget.uexp"
It holds a first text that is displayed after launching the game.

This is my edit:



screenshot000473.png (6.23 KiB) Viewed 159 times



And this is how it looks in game:



screenshot000475.png (119.95 KiB) Viewed 159 times



So bad news from this test are that this game doesn't use LOCRES file at all, so you need to either force the game to use locres file (I don't really know how to do it) or you can edit UEXP files directly. Tough luck.
## Post #7
- Username: Noodz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 11, 2023 7:04 am
- Post datetime: 2023-06-12T11:16:55+00:00
- Post Title: Help me find how to translate Paradise Killer please

I tried again to repack with UnrealPak, still get errors, and didn't find any info, no luck so far... I'll try posting on the site to get some help

And for the alternate method, at least the screenshot show that it could work but I've been looking at all the uexp files, it could work but it instantly makes the work 100x tiresome given that everything is spread in so many files, I'll definitely miss some xD But it could be a solution indeed. As for the locres files not being used, it could be a problem. What it makes me think is that even if we manage to rebuild the .pak file, in the end the locres file could not be used... I'll try to gather some more info on that !

At least I can take a look in the font matter, it does indeed seem rather easy ahah !
Top
## Post #8
- Username: enarkay
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 26, 2023 12:46 pm
- Post datetime: 2023-07-02T23:30:52+00:00
- Post Title: Help me find how to translate Paradise Killer please

paradise killer.jpg (152.55 KiB) Viewed 119 times


This is a screenshot of the in-game text just by editing the locres file - I haven't touched anything else like uassets/uexp.

So if you're still interested, I can confirm and tell you the good news that you probably only have to work with the locres file.
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-03T05:45:28+00:00
- Post Title: Help me find how to translate Paradise Killer please

> you probably only have to work with the locres file.

And how did you do this? Did you changed something in game INI settings?
## Post #10
- Username: enarkay
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 26, 2023 12:46 pm
- Post datetime: 2023-07-03T06:21:09+00:00
- Post Title: Help me find how to translate Paradise Killer please

No like I said, I only edited the locres. Here, I'll include a patch file with only the locres file so you can try and see for yourself.
[https://www.dropbox.com/s/jv53v04qypqav ... p.pak?dl=0](https://www.dropbox.com/s/jv53v04qypqav4w/ParadiseKiller-WindowsNoEditor_p.pak?dl=0)
## Post #11
- Username: Noodz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 11, 2023 7:04 am
- Post datetime: 2023-07-18T01:16:40+00:00
- Post Title: Help me find how to translate Paradise Killer please

I didn’t see you updated the topic ! Lately personal stuff is happening to me but I’ll definitely take a look at what you said. I’m glad to see we’ll be able to work with only the locres, it’s going to help a lot !
## Post #12
- Username: enarkay
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 26, 2023 12:46 pm
- Post datetime: 2023-07-18T14:32:27+00:00
- Post Title: Help me find how to translate Paradise Killer please

Yup feel free to contact me anytime in the future if you need further help.
