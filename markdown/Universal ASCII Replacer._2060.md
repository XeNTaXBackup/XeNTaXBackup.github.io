## Post #1
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-27T13:48:50+00:00
- Post Title: Universal ASCII Replacer.

So. this was just a fun addition to jaeder naub.
(this is not released, im testing it further).

But it crossed my mind that it could actually be used
for translating or something 

The current screenshot is from the UARF file created from
Diablo.exe. (the uarf contains the Offset of the string, and length of it,
so they can be replaced later in the exe file by just loading the UARF into it).
[ascii2.gif](https://xentaxbackup.github.io/file/830_ascii2.gif)
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-08-27T14:02:49+00:00
- Post Title: Universal ASCII Replacer.

> Reply from Strobe
>
> So. this was just a fun addition to jaeder naub.
(this is not released, im testing it further).

But it crossed my mind that it could actually be used
for translating or something 

The current screenshot is from the UARF file created from
Diablo.exe. (the uarf contains the Offset of the string, and length of it,
so they can be replaced later in the exe file by just loading the UARF into it).
Well its its for TRANSLATING then its GREAT.
AS I KNOW A LOT of games that i need to translate.
Tho does it support Japanese Characters? Ie ã
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-27T14:04:54+00:00
- Post Title: Universal ASCII Replacer.

It DOES not support Japanses Chars yet, as those are Unicode,
(which is yet unsupported by the ascii string detection routine). 

yet...

And yes, the LionHeart UK folder contains the files you have sent me,
so i know what is what
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-08-27T14:16:30+00:00
- Post Title: Universal ASCII Replacer.

> Reply from Strobe
>
> It DOES not support Japanses Chars yet, as those are Unicode,
(which is yet unsupported by the ascii string detection routine). 

yet...

And yes, the LionHeart UK folder contains the files you have sent me,
so i know what is what
Ahh i got ya.
Yeah they are Unicode lol.
Tho if u can make that a supported feature that'd be kick ass cool.
## Post #5
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-08-27T15:45:55+00:00
- Post Title: Universal ASCII Replacer.

agree could be great to do translations instead using an hex tool and typing more chars than original 


greets!
## Post #6
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-08-27T20:00:20+00:00
- Post Title: Universal ASCII Replacer.

Well, I don't like to burst your bubble, but translation is far more complex than simple character replacement. This is seen, for example, between the English phrase 'Good morning.' and its Spanish translation 'Buena manana.' While a very simple example, it illustrates that the major obstacle in straight translation is the need of a dictionary of words. After that, though, you must also consider syntax and context. Translation is, in fact, so complex, that the world's best programmers have been working on it for more than a decade (IIRC), and yet it still doesn't work anywhere near perfectly.
## Post #7
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-08-27T21:21:32+00:00
- Post Title: Universal ASCII Replacer.

> Reply from Dinoguy1000
>
> Well, I don't like to burst your bubble, but translation is far more complex than simple character replacement. This is seen, for example, between the English phrase 'Good morning.' and its Spanish translation 'Buena manana.' While a very simple example, it illustrates that the major obstacle in straight translation is the need of a dictionary of words. After that, though, you must also consider syntax and context. Translation is, in fact, so complex, that the world's best programmers have been working on it for more than a decade (IIRC), and yet it still doesn't work anywhere near perfectly.
Yes of course translation is hard.
I know that.
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-28T04:52:46+00:00
- Post Title: Universal ASCII Replacer.

Dinoguy1000:
Hi there!  . Maybe you got a point there, but i can say that that would not be the most problematic part. the hard part is that you cannot change the length of the strings. (and make them longer than the original ones, that
would break the file, so the replacer dont allow it). But someone with fluent
language knowledge of the language he/she is translating to wouldnt
find it so hard. but for some games it would ofcourse take a hell of a long
time :X
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-28T08:36:54+00:00
- Post Title: Universal ASCII Replacer.

> Reply from Strobe
>
> Dinoguy1000:
Hi there!  . Maybe you got a point there, but i can say that that would not be the most problematic part. the hard part is that you cannot change the length of the strings. (and make them longer than the original ones, that
would break the file, so the replacer dont allow it). But someone with fluent
language knowledge of the language he/she is translating to wouldnt
find it so hard. but for some games it would ofcourse take a hell of a long
time :X

That's actually the biggest problem. You can't change the lenght of the strings this way, which would be an absolute must in translations, or even modding. Best is to detect the format of the archive file that contains the strings, so you can modify those while still keeping in line with the archive structure.
## Post #10
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-28T08:53:07+00:00
- Post Title: Universal ASCII Replacer.

So now i have to code an Universal Archive Detection too?
you guys dont ask for little !! ;((
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-28T11:07:28+00:00
- Post Title: Universal ASCII Replacer.

Well, check out this :

[viewtopic.php?t=851](http://forum.xentax.com/viewtopic.php?t=851)
## Post #12
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-08-28T22:14:58+00:00
- Post Title: Universal ASCII Replacer.

not to mention, what happens if its like an item name referer, but it looks like the item name itself, you change it, then the resource its applied to doesn't exist, then you are screwed.
## Post #13
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-08-28T22:37:17+00:00
- Post Title: Universal ASCII Replacer.

> Reply from Rahly
>
> not to mention, what happens if its like an item name referer, but it looks like the item name itself, you change it, then the resource its applied to doesn't exist, then you are screwed.
Yeah i thought of that too.
## Post #14
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-08-28T23:39:51+00:00
- Post Title: Universal ASCII Replacer.

> Reply from lionheartuk
>
> Dinoguy1000 wrote:Well, I don't like to burst your bubble, but translation is far more complex than simple character replacement. This is seen, for example, between the English phrase 'Good morning.' and its Spanish translation 'Buena manana.' While a very simple example, it illustrates that the major obstacle in straight translation is the need of a dictionary of words. After that, though, you must also consider syntax and context. Translation is, in fact, so complex, that the world's best programmers have been working on it for more than a decade (IIRC), and yet it still doesn't work anywhere near perfectly.
Yes of course translation is hard.
I know that.
But your speaking asthough im a N00b with NO knowlege of Japanese and im trying to translate a game.
Damn.
Ive spend TWO years of my life in tokyo, well 2 months living in Shimotsuma, but that doesnt really matter.
Il be abel to translate the files i need easy enuf.
I know the context of th efiles and games I wish to translate, Im not translating for me lol, thatd be Dumb, im doing it for my gf, she likes ot watch me play games (rarely) but cant rea/understnad anything from them.
I am FLUENT in japanese so il be abel to translate things in no time lol.
so....ã€€ã
## Post #15
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-29T12:35:18+00:00
- Post Title: Universal ASCII Replacer.

I have some explanations to do here 

The first thought of the UARF was mainly for exe files actually,
thats actually the whole intention i had from the start, but then realized
it "could" be used for other files aswell.

but ofcourse its totally dependent on how the files structure is, if its
going to be editable or not. the padding however if the string is too short
will be padded with char(32)[space] instead of Nulls.
## Post #16
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-08-29T14:23:15+00:00
- Post Title: 

> Reply from Dinoguy1000
>
> 
Well, hey, I didn't know that tidbit of you being fluent in Japanese... What I was talking about was, say, writing a program that does the translation itself. I wasn't trying to treat you as a n00b or anything of the sort, that's not my style, and if I rubbed you the wrong way, accidentally or otherwise, you have my sincerest apology. And in any case, I would much rather make myself look like a n00b than treat someone else like one.

As for string length, if strings are padded with nulls, you will of course come to the fortunate circumstances where the translated string is shorter than the original, in which case you an just pad with nuls the rest of the way. Unfortunately, this is just as often as not NOT the case, in that event you would want to find the structure of the file format.
lol do not worry, I understand EXACTLY what oyu mean, and yes i agree that string LENGTH will be the most difficult part, cos for instand the japanese word for YOU is only 1 kanji but in engilsh its 3 characters Y.O.U, so this will prove to be quite a difficult task tbh lol.
No do not worry i didn not take your comment the wrong way lol, sorry if i came across as angry lol.
Yes if only ALL games were LOADS OF ENDLESS NUL's, that way i can make the string longer, tho that may only work for certain things, I doubt that ext boxes with be filled with NUL's so I may be screwed there lol.
## Post #17
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-08-29T17:04:25+00:00
- Post Title: 

even more difficult, that a lot of games don't use unicode at all, and in that sense, you CAN'T add jap.  Now some games do use the locale, but then the user would have to set the code page of their system before its readable.  Most games in other languges do NOT use unicode, but a bastardized code page that supports their language.  Most apps also do not handle UTF8, so i doubt you'd be able to encode one and place it in there.  And you have to have specific support for UFT16 which OSes use by default.  Games have to have support for this or you'll just have limited Latin character set support.
## Post #18
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-08-29T19:25:37+00:00
- Post Title: 

> Reply from Rahly
>
> even more difficult, that a lot of games don't use unicode at all, and in that sense, you CAN'T add jap.  Now some games do use the locale, but then the user would have to set the code page of their system before its readable.  Most games in other languges do NOT use unicode, but a bastardized code page that supports their language.  Most apps also do not handle UTF8, so i doubt you'd be able to encode one and place it in there.  And you have to have specific support for UFT16 which OSes use by default.  Games have to have support for this or you'll just have limited Latin character set support.
Yeah lol.
Thatl prove difficult to overcome.
Tho a LOT of games are fan translated, wonder how they all do it lol.
I once had a nice tool for NES/SNES/meGA DRIVE (Genesis) games.
Tho its possible ot make MOST programs support japane fonts, just simply install the japanese language pack and set it so that unicode language suppot is added ot other programs that wont normally support it.
Tho i must admit that it didnt work to well with certain programs, so i had to turn it off lol.
Still have ot use media player Clasic to play most of my movies as the folder names are in japanese and most players just dont even open the files, not even VLC lol.
