## Post #1
- Username: TheCreepy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 15, 2022 5:19 pm
- Post datetime: 2022-03-15T09:45:44+00:00
- Post Title: Help a newbie

Heyo! I want to learn about game localization but I dont know when where or how to start, I believe that I can actually translate -or rather localize- games but I dont know the necessary steps, for example lets say I want to localize Red Alert 3 (because it has already been translated so it shouldnt be that hard to find files) Which steps should I follow ?

edit: So my question is, to localize a game (in this case red alert3) 

1-Is there a standardized procedure to follow ? (find .big file open it  with a script tool etc.) 

2-Where do I start with the localization ? Where do I find the necessary strings/script files ? 

3-Do I need to use programs like MemoQ and TRADOS ?

4-I've heard MultiEx Commander can extract scripts and codes, is there any way to use Multiex commander to localize a game, if yes would it be eaiser or harder for a newbie to localize ? 


I'd appreciate any help I could get,
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-15T23:45:02+00:00
- Post Title: Help a newbie

> 1-Is there a standardized procedure to follow ? (find .big file open it with a script tool etc.)
No. That really depends on the game. For some games people have created custom tools to make translating easier
(for example to translate "Undertale" you should use "UndertaleModTool" [https://github.com/krzys-h/UndertaleModTool](https://github.com/krzys-h/UndertaleModTool) or any similar tool for dealing with GameMaker files).

Other example is Kuriimu which can be used to translate many different games 
[https://github.com/FanTranslatorsInternational/Kuriimu2](https://github.com/FanTranslatorsInternational/Kuriimu2)

If no custom tools were created, then things become complicated and someone needs to figure out file formats, write tools etc. etc.
If you want to learn that, you can start here [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)

If none of these methods work for you, then you can try translating in hex editor, but this method is very "old school" 
and I wouldn't recommend it for bigger projects.

> 2-Where do I start with the localization ? Where do I find the necessary strings/script files ?

You can use total commander method for that if text is uncompressed [https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)
If text is compressed or encrypted, then you need to reverse engineer file formats first or unpack data if the tools are available.

> 3-Do I need to use programs like MemoQ and TRADOS ?

No. You CAN use them if you want, but OmegaT is a free alternative and I can recommend it
for fan translations [https://omegat.org/](https://omegat.org/)
After you will gain some experience, you may switch to something else.

> 4-I've heard MultiEx Commander can extract scripts and codes, is there any way to use Multiex commander to localize a game, if yes would it be eaiser or harder for a newbie to localize ?

MultiEx seems may be a little outdated. You can try quickkBMS as alternative [http://aluigi.zenhax.com/quickbms.htm](http://aluigi.zenhax.com/quickbms.htm)
BMS scripts are not always best solution for translating (text length limitation etc.). Try to use custom programs if they are available.
