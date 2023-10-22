## Post #1
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-11-25T12:37:16+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

Hello there.
I wanna translate this beautiful game.
I can open the font file easily;

But, I don't know how can I open the text files...
I think they are in the zone folder...
Can somebody help?
## Post #2
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-12-20T20:14:45+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

I found a tutorial yesterday, but it's for CoD4. Can someone take a look at it?
[http://wiki.modsrepository.com/images/b/b4/Unpack.png](http://wiki.modsrepository.com/images/b/b4/Unpack.png)
## Post #3
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2011-01-11T11:48:24+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

what language?
## Post #4
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-01-11T15:23:26+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

To Turkish.
## Post #5
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-01-11T16:19:04+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

if it were possible I would like to translate to Portuguese-BR
## Post #6
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-01-28T23:06:19+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

Sorry for the bump, just wanted to note that translation is now possible.
I made a tiny tool that will take care of the .ff files, it allows for text extraction & injection.
Instructions in supplied read_me.txt, download:
[http://gljivolog.com/data/releases/bo_tex_fix.rar](http://gljivolog.com/data/releases/bo_tex_fix.rar)

Virus scan:
[http://www.virustotal.com/url-scan/repo ... 1296293444](http://www.virustotal.com/url-scan/report.html?id=9fc4836d75e40e732097b6a6cc5b6ccf-1296293444)
## Post #7
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-01-29T00:40:22+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

Great tool.
But, I want to translate the game completely.
Is there any other way to translate other texts? (like menu, objectives)
Or, can you update your tool?

Thanks.
qabRieL

...and never mind my pm. 
Its easy already.
## Post #8
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-01-29T08:26:27+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

UPDATE RELEASED:
Should work for all languages now and for all textual elements, not just dialogues, report bugs if it doesn't to [chronic@gljivolog.com](mailto:chronic@gljivolog.com)
Download: [http://gljivolog.com/data/releases/bo_tex_fix.rar](http://gljivolog.com/data/releases/bo_tex_fix.rar)
Virus check: [http://www.virustotal.com/url-scan/repo ... 1296293444](http://www.virustotal.com/url-scan/report.html?id=9fc4836d75e40e732097b6a6cc5b6ccf-1296293444)

@qabriel: Check your PM
## Post #9
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-01-29T14:32:11+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

When I edit en_code_post_gfx.ff, and, game crashes, says "FATAL ERROR".
Is there anyone else get this error?
## Post #10
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-01-29T14:36:25+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

Happened to me now, too. Of all the files I tested, I didn't test this one, sorry. I don't know why it happens, let me look into it, there may be an update soon.
Sorry for the inconvenience
P.S. play in windowed mode so you can exit those fatal errors (to avoid freezing which happens in FS mode)
## Post #11
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-01-29T16:49:42+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

No need to be sorry. 
Any news?
## Post #12
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-01-29T17:04:54+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

Well, there's one thing I'm sure about:
en_code_post_gfx.ff is the only file (talking about SP files) which uses this kind of approach. It seems Treyarch has for some reason decided to place static offsets for menu strings, so all strings in that .ff file are invalid if your length differs from the default string length.
In other words, if your text string length is equal to the length of the string extracted from the original en_code_post_gfx.ff, there will be no fatal error. This is only for en_code_post_gfx.ff, all others can work with different lengths!

Only solution that comes to mind is to push back the text that many bytes that your length overruns the default one, but that would interfere with other .ff data. I also have some other ideas I'm currently trying out, maybe I'll succeed in something. I'll keep you posted.
## Post #13
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-01-29T17:58:31+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

Here is polish code_post_gfx. For comparison

```
http://www.multiupload.com/29GEBXG25V
```
## Post #14
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-01-30T00:31:03+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

Thanks, Jurko! That helped me in additional researching of the files.

UPDATE RELEASED:
v1.2
Fixes: now should work with the notorious en_code_post_gfx.ff file (or any lang prefix)
NOTE: Injecting your own text into en_code_post_gfx.ff requires that your strings are the same or shorter length than the originals. This is an unfortunate limitation due to the fact menu-text offsets seem to be hardcoded within the game .exe for each specific language. Of course, all other files can have text of any length, you're not limited to anything.

Download: [http://gljivolog.com/data/releases/bo_tex_v12.rar](http://gljivolog.com/data/releases/bo_tex_v12.rar)
Virus check: [http://www.virustotal.com/url-scan/repo ... 1296343855](http://www.virustotal.com/url-scan/report.html?id=5b4f54a7d334cd7048ffd0d7c74a927f-1296343855)
## Post #15
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-01-30T12:51:10+00:00
- Post Title: Call of Duty: Black Ops - How to translate?

So, there is no way to translate code_post_gfx.ff without char limit?
## Post #16
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-01-30T15:38:35+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

I'm afraid so, yes. The offsets are hardcoded and there's just no way to tell the game "read at 0x2c, not 0x2e". So the only thing possible is to have shorter strings or of equal length, which the new version allows (because we can easily pad out the bytes not used by 0xff separators).
However, I have an idea how can we bypass that char limit. We need to find a language which has the longest possible strings. Then, we take a lang_code_post_gfx.ff file from that lang, extract strings from it, and inject all English or whatever strings in there. If all of that language's strings were longer than the English ones, maybe you will have enough space, but this is not really a solution as it depends on what language is the longest.

It also wouldn't be enough just to put in a lang_code_post_gfx.ff - you would also need to change the registry entry 'language' from ENG or whatever to that lang code and rename "localized_lang_x.iwd" files to the appropriate lang code, rename "en_outro.ff" to "lang_outro.ff" and all other .ff files too. Maybe that way you will be able to get a bit longer strings.
## Post #17
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-01-30T22:15:20+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

Here is the Spanish version of code_post_gfx.
[sp_code_post_gfx.rar](https://xentaxbackup.github.io/file/3854_sp_code_post_gfx.rar)
## Post #18
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-01-30T22:34:21+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

Right, it seems most strings are longer so maybe you should use that? Try editing the registry entry, renaming all .ff files to their Spanish lang codes etc and then try to inject some text; there shouldn't be any errors, but you are still limited to the length of the Spanish strings. I'm afraid there's no workaround except modifying the offsets the game has hardcoded somewhere...
## Post #19
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-01-31T09:27:27+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

Sorry for my bad english.
I compare polish, english and spanish code_post_gfx.
Look on 24 bit. There is "Second size" of .ff file.
I don´t know how to calculate this value.
Only this values are diferent
## Post #20
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-01-31T11:21:36+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

Well, I believe that there is no character limit on spanish file.
Can you take a look at it?
## Post #21
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-01-31T12:28:35+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

fatal error
## Post #22
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-02-01T01:05:19+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

Ok, I've been fiddling around with the .ff's and there is a way to remove the fatal error!
However, string positions (some of them, not all!) seem to be hardcoded so you'll get text blanks somewhere, probably.
Here's a test version of the injector:
[http://gljivolog.com/data/releases/test.rar](http://gljivolog.com/data/releases/test.rar)

There can be bugs, so please wait until next week when I get full time to explore some other options I have in mind.
## Post #23
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-02-01T12:19:50+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

Here the game crashes when I translate and use the file: "en_vorkuta.ff".
If I translate the file with same length, the game works.
## Post #24
- Username: harpseal
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:48 am
- Post datetime: 2011-02-01T12:27:47+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

Thank you for your effort Chronic.You cannot do something for mw2.Because they have the same file.
## Post #25
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-02-01T19:15:50+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

There will be a MW2 tool next week; the .ff structure is similar, but not identical, I just need to make some modifications.

@Herdell: Yes, I see this happens for all menu-related strings. There is a way around the fatal error, but it seems the string offsets (some of them) are hardcoded, at least for the code_post_gfx.ff. Try downloading from the link above, maybe that will work. If not, report back so I'll try one more thing.
## Post #26
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-02-01T21:48:43+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

Unfortunately, the game still crashing with translated files. Even with the test tool the fatal error still.
## Post #27
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-02-01T22:20:00+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

It seems that depends on how many you changed the original strings... I got fatal errors sometimes, but not at other times when changing only a couple of strings, which seems to be the result of the offset hardcoding. I'm sorry, but there is no direct cure to that. I'll try something else, but the hardcoded offsets are something that can't be changed that easily unless we find where they are located, and they're not in any .ff files.
## Post #28
- Username: harpseal
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:48 am
- Post datetime: 2011-02-01T22:23:03+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

Thank you Chronicle for Mw2. I am content.I am delighted by your answer.

Sorry, I am not good in English.
## Post #29
- Username: Gagarin
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 11, 2009 7:17 pm
- Post datetime: 2011-02-01T22:33:56+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

mw2 have deflate encryption algorithm. Without key we cant do anything with fast files.

About cod4/cod5/cod7 fast files. Except main file size (first 4 bytes after zlib decompression) they have "second size" which I didn't know how to calculates (offset 0x18-0x1B). Author of .FFviewer didn't know too. So I didn't see the way to translate game (or fix some localization errors like in our russian version) normaly (without any bugs, unreadeble strings or something else)
## Post #30
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-02-01T22:53:20+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

MW2 files are easily readable after inflation, already done it: the strings are in the same format as in BO so no problems.
Yes, the 'second size' is weird, but goes up the same as the normal size. For example, if 1 of your strings is by a char longer than the one in the original .ff, the size will increase by 1, but so will the 'second size'. Tried it out, no problems.
The 'second size' is not the problem; the hardcoded offsets for menu strings are.
## Post #31
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-03-21T19:18:48+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

any news ?
## Post #32
- Username: m7med
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 31, 2011 7:15 pm
- Post datetime: 2011-03-31T11:38:09+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

How can I find a font file ?
## Post #33
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-03-31T12:24:31+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

Font file is in C:\Program Files\Activision\Call of Duty - Black Ops\main\localized_English_iw00.iwd
file.
You can open .iwd with WinRar.
After that, go images, find "gamefonts_pc.iwi", then extract it somewhere.
Then download iwi to dds utility.
That's all I know. I don't know how can you edit it.

qabRieL
## Post #34
- Username: m7med
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 31, 2011 7:15 pm
- Post datetime: 2011-03-31T13:05:53+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

thanks   qabRieL 
if u want call of duty :black ops transalted to turkish its already there 

```
http://www.oyunceviri.com/forum/showthread.php?2176-Call-Of-Duty-Black-Ops-T%C3%BCrk%C3%A7e-Yama-v1.
```


If you discovered how it was translation please  tell me because I would like to translate this game  to Arabic
## Post #35
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-03-31T13:22:14+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

Thanks, that's our translation.   
To translate the game, you have to download the utility ([here](http://gljivolog.com/data/releases/bo_tex_fix.rar)).
There is already a guide in it, if you still couldn't make it, ask here again.

Good luck.
## Post #36
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-03-31T17:06:05+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

will it work with the files on PS3?
## Post #37
- Username: Dynamite Dan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 05, 2011 10:39 am
- Post datetime: 2011-04-05T02:43:24+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

hi! glad to found this thread in the world!
(sorry mi bad english, it is not my native language).

i want to put spanish subtitles with english voices (much better acting and fonetic   )

using this tool game hangs.
someone can do it? any news?
## Post #38
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-04-06T02:21:51+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

The contents of this post was deleted because of possible forum rules violation.
## Post #39
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2012-08-16T08:31:39+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

Can't seem to find the wav's for the strings in "en_code_post_gfx.ff".  So can get to everything except the loading screens... anyone have a clue where the wav's are hiding?
## Post #40
- Username: miryusifrahimov
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 23, 2023 4:31 am
- Post datetime: 2023-09-23T10:28:28+00:00
- Post Title: Re: Call of Duty: Black Ops - How to translate?

Links are not working. Please update the download link of the following files.

[http://gljivolog.com/data/releases/bo_tex_fix.rar](http://gljivolog.com/data/releases/bo_tex_fix.rar)
[http://gljivolog.com/data/releases/bo_tex_v12.rar](http://gljivolog.com/data/releases/bo_tex_v12.rar)
[http://gljivolog.com/data/releases/test.rar](http://gljivolog.com/data/releases/test.rar)

Please share with me programs to modify .ff and .iwi file.

My computer is Windows 11 Pro

Thanks....
