## Post #1
- Username: kiminru
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Nov 12, 2021 12:42 am
- Post datetime: 2022-01-18T10:58:41+00:00
- Post Title: PS2 GTA 3 & Vice City (HELP Font)

Hi, I currently have successfully output the language patch for PS2 GTA San Andreas
However, I don't know what to do with the font width (or coordinates) in GTA 3 and GTA Vice City
In the case of San Andreas, the font coordinates (or width) were set and output through the font.dat file
but PS2 GTA 3 and Vice City do not have font.dat
Where is it? Where do you adjust the coordinates (or width) of the font?
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-18T18:42:13+00:00
- Post Title: PS2 GTA 3 & Vice City (HELP Font)

For Vice City you have to edit "fonts.txd" file in 
/Rockstar Games/Grand Theft Auto Vice City/models/ directory

Then you can try to use this tool
[https://libertycity.net/files/gta-vice- ... -tool.html](https://libertycity.net/files/gta-vice-city/107999-vice-city-font-withts-correction-tool.html)
## Post #3
- Username: kiminru
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Nov 12, 2021 12:42 am
- Post datetime: 2022-01-19T02:50:19+00:00
- Post Title: PS2 GTA 3 & Vice City (HELP Font)

> Reply from ikskoks ↑Wed Jan 19, 2022 2:42 am at Wed Jan 19, 2022 2:42 am
>
> 
For Vice City you have to edit "fonts.txd" file in 
/Rockstar Games/Grand Theft Auto Vice City/models/ directory

Then you can try to use this tool
https://libertycity.net/files/gta-vice- ... -tool.html


First of all, as i'm Korean, we use 2byte word, unlike in English-speaking countries

and the language is '안녕하세요', such as 'ㅇㄴㅎㅅㅇ' and 'ㅏㅕㅏㅔㅛ' rather than 'abcde'.

So I replaced the font that were not used in the game with Korean and confirmed that Korean was output in the game.

But PS2 GTA 3 and Vice City don't have font.dat, so I can't do it, it seems impossible with that program you mentioned
## Post #4
- Username: kiminru
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-19T09:36:32+00:00
- Post Title: PS2 GTA 3 & Vice City (HELP Font)

Well, I can't help you more with this, but Vice City source code has been reverse engineered recently,
so it may give you some clues how font coordinates are stored in game.
## Post #5
- Username: kiminru
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Nov 12, 2021 12:42 am
- Post datetime: 2022-01-20T11:10:48+00:00
- Post Title: PS2 GTA 3 & Vice City (HELP Font)

> Reply from ikskoks ↑Wed Jan 19, 2022 5:36 pm at Wed Jan 19, 2022 5:36 pm
>
> 
Well, I can't help you more with this, but Vice City source code has been reverse engineered recently,
so it may give you some clues how font coordinates are stored in game.
Anyway, thank you so much for giving me this information! 
I'll try to find out if it's possible with a program once and if it's not possible, I'll try to find another way.
