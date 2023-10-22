## Post #1
- Username: AbsoluteZero
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 04, 2021 6:05 am
- Post datetime: 2023-01-23T23:01:41+00:00
- Post Title: Epic Mickey Language Files (*.dct) [Tool Release]

Hello!

I've been working on a lot of the formats used in the first Epic Mickey game, and I made a quick script to decompile the lines to a JSON file and compile a JSON file to the proprietary format. Unfortunately, these lines are scrambled when it comes to ordering, but it should suffice. Enjoy!

USAGE:
dct.py [path to JSON/DCT file]

DOWNLOAD:


 dct.zip
(14.74 KiB) Downloaded 34 times
## Post #2
- Username: heraldino
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 01, 2023 1:54 am
- Post datetime: 2023-01-31T18:09:01+00:00
- Post Title: Epic Mickey Language Files (*.dct) [Tool Release]

In fact, the text doesn't matter if I put words with accents, is there a way to solve this?
I want to translate to Portuguese.

Edit 1, I was able to import with accents, the whole point now is to import into the .PAK, the bigger file doesn't matter, since I barely edit the text file I'm going to import into the PAK and it doesn't matter because it's bigger, if anyone could see this PAK issue would be great.
## Post #3
- Username: AbsoluteZero
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 04, 2021 6:05 am
- Post datetime: 2023-02-02T22:11:52+00:00
- Post Title: Epic Mickey Language Files (*.dct) [Tool Release]

> Reply from heraldino ↑Wed Feb 01, 2023 2:09 am at Wed Feb 01, 2023 2:09 am
>
> 
In fact, the text doesn't matter if I put words with accents, is there a way to solve this?
I want to translate to Portuguese.

Edit 1, I was able to import with accents, the whole point now is to import into the .PAK, the bigger file doesn't matter, since I barely edit the text file I'm going to import into the PAK and it doesn't matter because it's bigger, if anyone could see this PAK issue would be great.

I'm working on a tool to streamline a lot of the modding aspects, give me a few weeks. I have been able to create a packfile constructor/deconstructor but I need to do research into several of the formats (such as levels) as it seems the game wants the files inside the packfile in a certain order, seemingly the same order they are referenced inside the packfile's level. So, I need to parse the level and allow "manual" packfiles, or packfiles that do not contain a level and instead a group of random files (e.g., the language files or the Lua scripts).
## Post #4
- Username: TKFRvision
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 28, 2021 6:07 am
- Post datetime: 2023-02-03T08:01:34+00:00
- Post Title: Epic Mickey Language Files (*.dct) [Tool Release]

Hey AbsoulteZero,

Cars 2 is using the same file format for localization as epic Mickey. Now it doesn't work exactly because there are small changes between those formats probably. I cannot modify or redistribute your code tho since it is not Foss. So I wanted to ask you if yiu would be willing to apply a foss license to it, which one is up to you and I would be happy to help you making a decision,  but you would help us a lot since us devs don't have the time anymore to research formats from the ground up.

Thanks,
Klemens
## Post #5
- Username: AbsoluteZero
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 04, 2021 6:05 am
- Post datetime: 2023-02-03T21:10:53+00:00
- Post Title: Epic Mickey Language Files (*.dct) [Tool Release]

> Reply from TKFRvision ↑Fri Feb 03, 2023 4:01 pm at Fri Feb 03, 2023 4:01 pm
>
> 
Hey AbsoulteZero,

Cars 2 is using the same file format for localization as epic Mickey. Now it doesn't work exactly because there are small changes between those formats probably. I cannot modify or redistribute your code tho since it is not Foss. So I wanted to ask you if yiu would be willing to apply a foss license to it, which one is up to you and I would be happy to help you making a decision,  but you would help us a lot since us devs don't have the time anymore to research formats from the ground up.

Thanks,
Klemens

Updated the zip file to include the GPL 3.0 license. Good luck with the modifications!
## Post #6
- Username: heraldino
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 01, 2023 1:54 am
- Post datetime: 2023-02-05T20:04:06+00:00
- Post Title: Epic Mickey Language Files (*.dct) [Tool Release]

@AbsoluteZero The real problem is moving this one. PAK that the bms script won't let you apply a file larger than the original, I'm hoping you do something related to this .PAK, good luck you're a monster congratulations.
## Post #7
- Username: AbsoluteZero
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 04, 2021 6:05 am
- Post datetime: 2023-02-07T04:56:59+00:00
- Post Title: Epic Mickey Language Files (*.dct) [Tool Release]

> Reply from heraldino ↑Mon Feb 06, 2023 4:04 am at Mon Feb 06, 2023 4:04 am
>
> 
@AbsoluteZero The real problem is moving this one. PAK that the bms script won't let you apply a file larger than the original, I'm hoping you do something related to this .PAK, good luck you're a monster congratulations.

I put something quick together for packfile creation using some of the code from my work in progress tool.

Here you go! -- [viewtopic.php?t=26442](https://forum.xentax.com/viewtopic.php?t=26442)

If you are having trouble with it, post any problems on that post, and I will try my best to help you.
## Post #8
- Username: TKFRvision
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 28, 2021 6:07 am
- Post datetime: 2023-02-12T13:26:42+00:00
- Post Title: Epic Mickey Language Files (*.dct) [Tool Release]

Hey AbsoluteZero,

I would like to thank you for adding the license. I also noticed something weird. You said that your ordering was scrambled, but you can just disable the sorting of keys that the JSON library does by adding `sort_keys=False` to your call to json.dump. As for the tool, we will probably rewrite the whole thing, but it is still amazing that you shared this with us. Especially the great code comments and the good readability is great. Have a good one.

Thanks,
Klemens
## Post #9
- Username: AbsoluteZero
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 04, 2021 6:05 am
- Post datetime: 2023-02-12T22:45:21+00:00
- Post Title: Epic Mickey Language Files (*.dct) [Tool Release]

> Reply from TKFRvision ↑Sun Feb 12, 2023 9:26 pm at Sun Feb 12, 2023 9:26 pm
>
> 
Hey AbsoluteZero,

I would like to thank you for adding the license. I also noticed something weird. You said that your ordering was scrambled, but you can just disable the sorting of keys that the JSON library does by adding `sort_keys=False` to your call to json.dump. As for the tool, we will probably rewrite the whole thing, but it is still amazing that you shared this with us. Especially the great code comments and the good readability is great. Have a good one.

Thanks,
Klemens

No problem, but when I said the ordering was scrambled, I was referring to the ordering of the dialog lines in the DCT file. They aren't sorted by level or character or anything so you have to look around for the line you want to edit. As far as I know, the ordering of the lines in the DCT file doesn't really matter since they all have IDs, meaning they are identified by that and the ordering has no hold on anything. Good luck with the tool!
## Post #10
- Username: Techttv
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 23, 2022 8:48 pm
- Post datetime: 2023-03-06T09:31:15+00:00
- Post Title: Epic Mickey Language Files (*.dct) [Tool Release]

Did anyone try this tool with Epic Mickey 2?
