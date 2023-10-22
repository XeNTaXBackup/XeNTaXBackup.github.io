## Post #1
- Username: mami9x
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 10, 2017 5:29 pm
- Post datetime: 2017-09-17T01:12:21+00:00
- Post Title: Edit file FONT in Startup_INT.upk (Batman Arkham Asylum)?

Help! Edit file FONT in Startup_INT.upk (Batman Arkham Asylum)?
[https://www.dropbox.com/s/axr2cci5iafwx ... T.upk?dl=0](https://www.dropbox.com/s/axr2cci5iafwx8b/Startup_INT.upk?dl=0)
[12.PNG](https://xentaxbackup.github.io/file/13319_12.PNG)
## Post #2
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2017-09-17T04:34:43+00:00
- Post Title: Edit file FONT in Startup_INT.upk (Batman Arkham Asylum)?

can you give me your .int file (Localization files)?
and your characters in your language. too. and your ttf font (your favorite font for use on this game)
## Post #3
- Username: abuali
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Dec 13, 2010 12:48 am
- Post datetime: 2017-09-19T13:05:47+00:00
- Post Title: Edit file FONT in Startup_INT.upk (Batman Arkham Asylum)?

> Reply from halfway
>
> can you give me your .int file (Localization files)?
and your characters in your language. too. and your ttf font (your favorite font for use on this game)
Do you have any idea on how to mod this upk? 
please share it if you have... I'm interested
## Post #4
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-09-19T14:43:54+00:00
- Post Title: Edit file FONT in Startup_INT.upk (Batman Arkham Asylum)?

> Reply from abuali
>
> halfway wrote:can you give me your .int file (Localization files)?
and your characters in your language. too. and your ttf font (your favorite font for use on this game)
Do you have any idea on how to mod this upk? 
please share it if you have... I'm interested
i can do  that... like halfway said, give us int or localization files and your characters from your language
we do that with hex editor... i dont have any tool or something...
## Post #5
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-09-19T14:44:31+00:00
- Post Title: Edit file FONT in Startup_INT.upk (Batman Arkham Asylum)?

> Reply from abuali
>
> halfway wrote:can you give me your .int file (Localization files)?
and your characters in your language. too. and your ttf font (your favorite font for use on this game)
Do you have any idea on how to mod this upk? 
please share it if you have... I'm interested
i can do  that... like halfway said, give us all .int or localization files and your characters from your language
we do that with hex editor... i dont have any tool or something...
## Post #6
- Username: abuali
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Dec 13, 2010 12:48 am
- Post datetime: 2017-09-19T15:44:47+00:00
- Post Title: Edit file FONT in Startup_INT.upk (Batman Arkham Asylum)?

> Reply from GHOST DEAD
>
> abuali wrote:halfway wrote:can you give me your .int file (Localization files)?
and your characters in your language. too. and your ttf font (your favorite font for use on this game)
Do you have any idea on how to mod this upk? 
please share it if you have... I'm interested
i can do  that... like halfway said, give us all .int or localization files and your characters from your language
we do that with hex editor... i dont have any tool or something...
here is some attached...

but just FYI, I tried before to apply some modding to this file with hex editor and I made a success...

oh sorry I remembered now
Startup_INT.upk was meant to the font for UI fonts only, but the game has a separate file to use for in-game subtitles which was this CommonGame_LOC_INT.upk and that one I didn't succeeded to mod 

anyway, I attached all the files that we were talking about.

[https://mega.nz/#!PZ9BWLYC!4JEwRQ5kDdbo ... fljHy59b1s](https://mega.nz/#!PZ9BWLYC!4JEwRQ5kDdboOR6IN_VWVr04I_kfLGjSgfljHy59b1s)
## Post #7
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-09-20T03:51:39+00:00
- Post Title: Edit file FONT in Startup_INT.upk (Batman Arkham Asylum)?

done!
[https://ufile.io/7wzz1](https://ufile.io/7wzz1)
## Post #8
- Username: abuali
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Dec 13, 2010 12:48 am
- Post datetime: 2017-09-20T14:55:50+00:00
- Post Title: Edit file FONT in Startup_INT.upk (Batman Arkham Asylum)?

> Reply from GHOST DEAD
>
> done!
https://ufile.io/7wzz1
Thanks, I will check it and back with results.
## Post #9
- Username: abuali
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Dec 13, 2010 12:48 am
- Post datetime: 2017-09-20T16:21:14+00:00
- Post Title: Edit file FONT in Startup_INT.upk (Batman Arkham Asylum)?

From your files I see that:
First you modded Startup_INT.upk, in a wrong way, because this game requires a special way to deal with .swf fonts, look at what I did in modding this file which is working perfectly. 

[https://mega.nz/#!eRNGnbzY!ig2BLjx4iWJX ... xgxNrL1Z_U](https://mega.nz/#!eRNGnbzY!ig2BLjx4iWJXvC3gjplqY3FMYQVzYKVBZxgxNrL1Z_U)

Second, you use unreal engine to build a whole different package -font_set.upk- to bypass using CommonGame_LOC_INT.upk, but that is cannot be done in this game, it had some kind of protection to use it's own files, and when trying to do that the game will force close.

this is the error


and on the top of that, the upk must be cooked, while uncooked is causing the ran out of virtual memory issue in this game.

anyway, thanks for your help.
## Post #10
- Username: ramyzahran
- Rank: n00b
- Number of posts: 19
- Joined date: Tue May 23, 2017 7:41 am
- Post datetime: 2018-11-28T22:21:34+00:00
- Post Title: Edit file FONT in Startup_INT.upk (Batman Arkham Asylum)?

> Reply from abuali
>
> From your files I see that:
First you modded Startup_INT.upk, in a wrong way, because this game requires a special way to deal with .swf fonts, look at what I did in modding this file which is working perfectly. 

https://mega.nz/#!eRNGnbzY!ig2BLjx4iWJX ... xgxNrL1Z_U

Second, you use unreal engine to build a whole different package -font_set.upk- to bypass using CommonGame_LOC_INT.upk, but that is cannot be done in this game, it had some kind of protection to use it's own files, and when trying to do that the game will force close.

this is the error


and on the top of that, the upk must be cooked, while uncooked is causing the ran out of virtual memory issue in this game.

anyway, thanks for your help.
 OK.. how to do this?!!
i want to translate this game BATMAN AA into ARABIC .. and i have problems in editing and re-packing BOTH fonts files startup and in-game fonts .. 
How to do THIS?!!
THANKS!..
