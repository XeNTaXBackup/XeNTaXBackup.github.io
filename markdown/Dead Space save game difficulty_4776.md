## Post #1
- Username: thermite
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 26, 2010 3:55 am
- Post datetime: 2010-07-21T13:43:47+00:00
- Post Title: Dead Space save game difficulty

Hi

I need help in editing a save game: when I reached chapter 8 in Dead Space my save got corrupted so it changed my difficulty from impossible to medium. I tried to Google a fix but couldn't find anything so I opened the save with hex editor and found this line "44 00 69 00 66 00 66 00" (d i f f) and changed the value to 3 (for impossible) but in game it only changed the difficulty visible in save window to impossible. After I saved in game it showed the difficulty in medium.

Would anyone know how to change the difficulty properly?

I attached the save game unedited if someone would like to take a look at it. (Had to compress it as "The extension deadspacesaved is not allowed." error was thrown at me.)
[ds_slot_05.rar](https://xentaxbackup.github.io/file/3257_ds_slot_05.rar)
## Post #2
- Username: masterX244
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 17, 2010 12:48 am
- Post datetime: 2010-08-17T13:06:05+00:00
- Post Title: Dead Space save game difficulty

Try tomake a new savegame in impossible and another in medium. Then look for the differences between them. Maybe youfind the second one!
## Post #3
- Username: TigerNightmare
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 03, 2011 6:05 am
- Post datetime: 2011-07-03T02:48:27+00:00
- Post Title: Dead Space save game difficulty

I know this thread is ancient, but I've been looking for a solution and came across this page.  I have tried comparing two new game files, one on medium and one on impossible, with just the small health pack found inside the Kellion and saving at the first save point.  Besides changing M.e.d.i.u.m........ to I.m.p.o.s.s.i.b.l.e and the number following D.i.f.f from 1 to 3, there are hundreds if not thousands of differences between the two files.  Until someone can translate the code and make a save game editor, us amateurs are stuck playing impossible from scratch without the military suit.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-07-03T03:24:10+00:00
- Post Title: Dead Space save game difficulty

Does Dead Space save the game on creation, or does it not happen until you reach a savepoint and save yourself (it's been too long since I played it, so I don't remember, and my Xbox is down, so I can't check). If it saves on creation, start one game on Medium and one on Impossible, and immediately exit the game after starting them, then compare the save files. This should (hopefully) lead to far fewer differences to sort through.

It would also help to do the same for two games on the same difficulty; any differences between the two would not be related to the difficulty and so could be ignored in the comparison between difficulties.
## Post #5
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2012-08-17T17:24:52+00:00
- Post Title: Dead Space save game difficulty

Same issue here. I try comparing new game with differents difficulty levels and found this:
4400690066002E00200033
44 69 66 = D i f (From difficulty)

The last 33 means the difficulty; in that orden 32 will be Hard, 31 medium and 30 easy. (33 is impossible, very hard).

Also, game save has some text accord the difficulty. For example, if it on 33 on other strings it have "impossible". Changing that 2 values (The text and the 30/31/32/33) game recognize the difficulty as i set at least on the menu cause in game i didn't notice difficulty change. AND MORE IMPORTANT, if i save game with one modified difficulty, the difficulty of game saved will set to the original difficulty. For example, if i have a game under medium, and then modify the text to hard and the hex value to 32 game will recognyze it but if i continue with that modified save game and then try to save, the generated save game will be medium instead hard.

So, the save file has some other value attached to load the difficulty.
