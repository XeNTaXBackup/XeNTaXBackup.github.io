## Post #1
- Username: NabilMo7amed
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 23, 2022 1:30 am
- Post datetime: 2022-07-23T20:58:21+00:00
- Post Title: Stray Game files (localization issue)

Hi Gamers

I want to ask a  question, I used quickbms in extracting game files But I can't edit the .uasset and .uexp files of language so anyone helps me in this
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-24T09:45:50+00:00
- Post Title: Stray Game files (localization issue)

Try this [http://wiki.xentax.com/index.php/List_o ... gine_Tools](http://wiki.xentax.com/index.php/List_of_Unreal_Engine_Tools)
## Post #3
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-07-24T20:41:58+00:00
- Post Title: Stray Game files (localization issue)

Have you looked in Game.locres for the game's language file?
## Post #4
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2022-07-25T02:56:26+00:00
- Post Title: Stray Game files (localization issue)

Can someone help?-How is it possible to unpack textures, change them, and implement them into the game?
## Post #5
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-07-25T19:48:33+00:00
- Post Title: Stray Game files (localization issue)

Just find the Game.locres file and replace it.
[1.jpg](https://xentaxbackup.github.io/file/22561_1.jpg)
## Post #6
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-07-26T20:26:13+00:00
- Post Title: Stray Game files (localization issue)

> Reply from DENver666 ↑Mon Jul 25, 2022 10:56 am at Mon Jul 25, 2022 10:56 am
>
> 
Can someone help?-How is it possible to unpack textures, change them, and implement them into the game?

Put your edited Game.locres file in this location ''Hk_project-WindowsNoEditor_P\Hk_project\Content\Localization\Game\en''
And drag the ''Hk_project-WindowsNoEditor_P'' folder onto the bat file and it will create a new pak file.

[https://www.mediafire.com/file/mifbname ... ealPak.rar](https://www.mediafire.com/file/mifbnamesqbzehf/UnrealPak.rar)
## Post #7
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2022-07-27T03:26:57+00:00
- Post Title: Stray Game files (localization issue)

Thank you very much
## Post #8
- Username: DENver666
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 20, 2020 11:26 pm
- Post datetime: 2022-07-27T05:50:51+00:00
- Post Title: Stray Game files (localization issue)

> Reply from Franco ↑Wed Jul 27, 2022 4:26 am at Wed Jul 27, 2022 4:26 am
>
> 
DENver666 wrote: ↑Mon Jul 25, 2022 10:56 am
Can someone help?-How is it possible to unpack textures, change them, and implement them into the game?


Put your edited Game.locres file in this location ''Hk_project-WindowsNoEditor_P\Hk_project\Content\Localization\Game\en''
And drag the ''Hk_project-WindowsNoEditor_P'' folder onto the bat file and it will create a new pak file.

https://www.mediafire.com/file/mifbname ... ealPak.rar

And somehow you can unpack Hk_project-Windows No Editor.apk so that all resources are unpacked
