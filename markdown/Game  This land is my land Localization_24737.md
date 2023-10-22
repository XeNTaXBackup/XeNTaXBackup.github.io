## Post #1
- Username: AMININE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 12, 2021 9:29 pm
- Post datetime: 2021-11-14T21:07:18+00:00
- Post Title: Game : This land is my land Localization

This land is my land. it's unity game i already edit localization game but the game supports my language(Thai languages) more than 60 - 70%, the rest it doesn't. it's a square like this :[https://prnt.sc/1zlb13m](https://prnt.sc/1zlb13m) [https://prnt.sc/1zlb40d](https://prnt.sc/1zlb40d) how i make it support 100%

i want to know it's about TTF and DDS or not
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-14T21:41:23+00:00
- Post Title: Game : This land is my land Localization

> how i make it support 100%

You need to find game's fonts and edit them to add characters from your language.
As it's Unity game you can use UnityEx or AssetStudio first.

> i want to know it's about TTF and DDS
Not always. Sometimes font can be completely custom.
## Post #3
- Username: AMININE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 12, 2021 9:29 pm
- Post datetime: 2021-11-15T17:34:06+00:00
- Post Title: Game : This land is my land Localization

> Reply from ikskoks ↑Mon Nov 15, 2021 5:41 am at Mon Nov 15, 2021 5:41 am
>
> 
how i make it support 100%

You need to find game's fonts and edit them to add characters from your language.
As it's Unity game you can use UnityEx or AssetStudio first.
i want to know it's about TTF and DDS
Not always. Sometimes font can be completely custom.

firstly thanks you for reply.

This is TTF i found in asset0 : [https://www.img.in.th/image/WXk3fc](https://www.img.in.th/image/WXk3fc) what is .ufnt
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-15T18:18:36+00:00
- Post Title: Game : This land is my land Localization

> This is TTF i found in asset0
You can edit it with High-Logic Font Creator or similar program.

> what is .ufnt
I don't know. It looks custom.
## Post #5
- Username: AMININE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 12, 2021 9:29 pm
- Post datetime: 2021-11-16T13:53:11+00:00
- Post Title: Game : This land is my land Localization

> Reply from ikskoks ↑Tue Nov 16, 2021 2:18 am at Tue Nov 16, 2021 2:18 am
>
> 
This is TTF i found in asset0
You can edit it with High-Logic Font Creator or similar program.
what is .ufnt
I don't know. It looks custom.

i use Unityex extract ttf and replace with my ttf and then import file and i get .raw  

This is Right way ?
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-16T22:27:43+00:00
- Post Title: Game : This land is my land Localization

> and i get .raw
What do you mean by "get .raw"?
## Post #7
- Username: AMININE
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Oct 12, 2021 9:29 pm
- Post datetime: 2021-11-17T14:54:29+00:00
- Post Title: Game : This land is my land Localization

> Reply from ikskoks ↑Wed Nov 17, 2021 6:27 am at Wed Nov 17, 2021 6:27 am
>
> 
and i get .raw 
What do you mean by "get .raw"?

This is file when i press import : [https://www.img.in.th/image/WApQbg](https://www.img.in.th/image/WApQbg)
## Post #8
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2021-12-03T12:25:23+00:00
- Post Title: Game : This land is my land Localization

That's just some file created by UnityEx. Don't mind that. Just export TTF, edit in some font editor (I use Glyphr Studio) and then import back and try it in the game.

You should try to edit the .ttf fonts tho. Don't mind the .ufnt one. If the edited .ttf fonts won't work in game, then the problem is elsewhere.
