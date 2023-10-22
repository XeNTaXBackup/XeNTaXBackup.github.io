## Post #1
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2011-11-15T19:21:55+00:00
- Post Title: Saints Row: The Third Translation {PC}

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2011-11-19T05:51:05+00:00
- Post Title: Saints Row: The Third Translation {PC}

You can use [Gibbed volition](http://svn.gib.me/builds/volition/volition-r52_b23.zip).
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-11-19T09:01:26+00:00
- Post Title: Saints Row: The Third Translation {PC}

> Reply from RedDeadRedemption
>
> You can use Gibbed volition.

Does it work for X360 as well pls ? Who made this tool Rick ?
## Post #4
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2011-11-19T13:18:10+00:00
- Post Title: Saints Row: The Third Translation {PC}

> Reply from michalss
>
> RedDeadRedemption wrote:You can use Gibbed volition.

Does it work for X360 as well pls ? Who made this tool Rick ?
Maybe.
Yes.
## Post #5
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2011-11-19T22:30:49+00:00
- Post Title: Saints Row: The Third Translation {PC}

> Reply from RedDeadRedemption
>
> You can use Gibbed volition.

Thanks for the link but it's not working or the file(s) are deleted -

Not Found

The requested URL /builds/volition/volition-r52_b23.zip was not found on this server.

.....
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-11-20T06:33:24+00:00
- Post Title: Saints Row: The Third Translation {PC}

btw it does not work on X360 ...
## Post #7
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2011-11-20T15:01:48+00:00
- Post Title: Saints Row: The Third Translation {PC}

> Reply from Sartr0n
>
> RedDeadRedemption wrote:You can use Gibbed volition.

Thanks for the link but it's not working or the file(s) are deleted -

Not Found

The requested URL /builds/volition/volition-r52_b23.zip was not found on this server.

.....
try [this](http://svn.gib.me/builds/volition/).
## Post #8
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2011-12-05T14:34:07+00:00
- Post Title: Saints Row: The Third Translation {PC}

editing the sound files ([http://forums.somethingawful.com/showth ... id=3449395](http://forums.somethingawful.com/showthread.php?threadid=3449395)) is a bit much for me.....anyone know how I can get at only the subtitles?

EDIT: ok using the gibbed violation tools i found the subtitles, they are packed in misc.vpp_pc, *.le_strings files.  The problem is now i need a way to edit them, opening them up with a hex editor shows me that i need a unpacker/repacker to feasibly search and edit.  Is there one for one of the previous SR games that might work?
## Post #9
- Username: evandro
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 21, 2011 4:37 am
- Post datetime: 2011-12-20T20:50:30+00:00
- Post Title: Saints Row: The Third Translation {PC}

I found a tool for extract/compact le_strings files:

[View](http://translate.google.com/translate?sl=pt&tl=en&js=n&prev=_t&hl=pt-BR&ie=UTF-8&layout=2&eotf=1&u=http%3A%2F%2Fwww.ultraduz.com.br%2Fartigo%2F81%2Fferramenta-lestrings-extraia-e-compacte-os-arquivos-de-texto-dos-jogos-saints-row.html&act=url)

Note: google translated (Brazilian site)

thx
## Post #10
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2011-12-21T07:59:00+00:00
- Post Title: Saints Row: The Third Translation {PC}

Thanks, I had given up hope

EDIT: extracting is easy enough but I cannot understand how to compress again, have tried various things.  Google translator gives "ferramenta.exe name> C-file with the file name> textos> le_strings original>"
wth does "C-file with the file name" mean?

EDIT2: I have tried "Ferramenta.exe -c subtitle_us.le_strings.txt subtitle_us.le_strings" as seems to make sense but instead of compressing it extracts

EDIT3: ok the -c must be -C, it's case sensitive.  The problem now is that misc.vpp_pc seems to only contain a few subtitles, most of the subtitles I have been unable to find in any of the vpp files
## Post #11
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2011-12-21T15:35:01+00:00
- Post Title: Saints Row: The Third Translation {PC}

EDIT3: ok the -c must be -C, it's case sensitive.  The problem now is that misc.vpp_pc seems to only contain a few subtitles, most of the subtitles I have been unable to find in any of the vpp files [/quote]

Indeed - most of telephone dialogs, and action dialogs are in the "voices.vpp_pc" file.

Method is the same like "custom radio" mod. So you have to unpacked the mentioned file - you'll get *.bnk files.
You have to extract them with bnk_extractor, and HEX edit files, and repack them, then repack all to 'voice.vpp_pc".
Yes, it will huge localization.
## Post #12
- Username: evandro
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 21, 2011 4:37 am
- Post datetime: 2011-12-21T16:46:26+00:00
- Post Title: Saints Row: The Third Translation {PC}

> EDIT: extracting is easy enough but I cannot understand how to compress again, have tried various things. Google translator gives "ferramenta.exe name> C-file with the file name> textos> le_strings original>"
>
> wth does "C-file with the file name" mean?

To extract:
ferramenta.exe -E <le_strings_file_name>

To compress:
ferramenta.exe -C <texts_file_name> <original_le_strings_file_name>

> Indeed - most of telephone dialogs, and action dialogs are in the "voices.vpp_pc" file.
>
> 
>
> Method is the same like "custom radio" mod. So you have to unpacked the mentioned file - you'll get *.bnk files.
>
> You have to extract them with bnk_extractor, and HEX edit files, and repack them, then repack all to 'voice.vpp_pc".
>
> Yes, it will huge localization.

bnk_extractor -> [View](http://www.saintsrowmods.com/forum/index.php?threads/bnk_pc_extractor-ripping-audio-files.55/)
## Post #13
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2011-12-22T06:34:44+00:00
- Post Title: Saints Row: The Third Translation {PC}

And now I need a tool for decoding dmav files....oh joy.
They make these games so difficult to mod and then they complain when people have to hack them to change anything.....idiot artistic youknowwhats.
## Post #14
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-12-24T18:13:13+00:00
- Post Title: Saints Row: The Third Translation {PC}

> Reply from evandro
>
> EDIT: extracting is easy enough but I cannot understand how to compress again, have tried various things. Google translator gives "ferramenta.exe name> C-file with the file name> textos> le_strings original>"
wth does "C-file with the file name" mean?

To extract:
ferramenta.exe -E <le_strings_file_name>

To compress:
ferramenta.exe -C <texts_file_name> <original_le_strings_file_name>
Indeed - most of telephone dialogs, and action dialogs are in the "voices.vpp_pc" file.

Method is the same like "custom radio" mod. So you have to unpacked the mentioned file - you'll get *.bnk files.
You have to extract them with bnk_extractor, and HEX edit files, and repack them, then repack all to 'voice.vpp_pc".
Yes, it will huge localization.

bnk_extractor -> View
Fazendo propaganda da sua própia tool heim Evandro...   
Parabéns!
## Post #15
- Username: Vagohid
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 29, 2011 12:10 am
- Post datetime: 2011-12-27T10:53:16+00:00
- Post Title: Saints Row: The Third Translation {PC}

Can someone help me out? I just don't understand the original tutorial so I guess it would be simple if one of you who succeeded would write a quick tutorial with one of the le_strings files as an example. Thank you.
## Post #16
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2011-12-29T05:42:26+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

> Open up cmd(command line console/prompt), a fast way is start>run>cmd
>
> Goto the location where the files are in cmd
>
> 
>
> To extract:
>
> ferramenta.exe -E subtitle_us.le_strings
>
> 
>
> edit the subtitle_us.le_strings.text that was created
>
> 
>
> To compress:
>
> ferramenta.exe -C subtitle_us.le_strings.text subtitle_us.le_strings
>
> 
>
> the -E and -C MUST be in upper case

That what you needed?
## Post #17
- Username: Vagohid
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 29, 2011 12:10 am
- Post datetime: 2011-12-29T06:17:59+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

Oh thanks, I was just too lame to figure out that I need to write the extension there. Thank you very much!

By the way what languages are you people trying to translate the game? Just to know if I have a fellow countryman already translating the game.
## Post #18
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2011-12-29T06:24:34+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

I just want to censor the rampant blasphemy.
## Post #19
- Username: Vagohid
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 29, 2011 12:10 am
- Post datetime: 2011-12-29T14:29:36+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

Haha, well good luck with that! I don't see the point but that's just me. But there will be a lot of work for you to do that's for sure.

I have just figured out that compiling fails if there's an 'ő' or an 'ű' in the text. Just saying.
## Post #20
- Username: rambo919
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Sep 19, 2011 11:32 pm
- Post datetime: 2011-12-30T08:09:24+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

Had a go at trying to manually edit the dmav files but.....loading almost 2000 files into a hex editor makes it crash.
Unless someone whips up dialogue editor i don't see how changes across the board can happen feasibly.  But dammit, if they seriously want to make it this hard to mod i say screw them, life is too short for badly made games.  I'm deleting this &*(&*^&
## Post #21
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-12-30T12:45:29+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

Why would you want to censor the game?
## Post #22
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2011-12-31T18:10:27+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

> Reply from Vagohid
>
> Haha, well good luck with that! I don't see the point but that's just me. But there will be a lot of work for you to do that's for sure.

I have just figured out that compiling fails if there's an 'ő' or an 'ű' in the text. Just saying.

Én már fordítom a játékot, és nem használom a 'ő'. 'Ő', 'ű', 'Ű' betűket. Emellett, az összes (telefonos is) szöveget tökéletesen tudom már honosítani.
## Post #23
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-12-31T22:33:20+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

Eh?
## Post #24
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-01-01T08:38:28+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

He already translating the game, include the telephone texts too, just not use őű accents.

> Reply from terminator
>
> Én már fordítom a játékot, és nem használom a 'ő'. 'Ő', 'ű', 'Ű' betűket. Emellett, az összes (telefonos is) szöveget tökéletesen tudom már honosítani.

Next time, English pls.
## Post #25
- Username: Vagohid
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 29, 2011 12:10 am
- Post datetime: 2012-01-01T16:35:23+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

> Reply from terminator
>
> Én már fordítom a játékot, és nem használom a 'ő'. 'Ő', 'ű', 'Ű' betűket. Emellett, az összes (telefonos is) szöveget tökéletesen tudom már honosítani.
 Az a gond, hogy már én is eléggé benne vagyok, úgyhogy most félúton már nem állok le vele. 
Ha hamarabb szólsz, bele sem kezdek.
De hát ha azt nézzük, az még nem katasztrófa, ha egy játéknak két fordítása készül el, nemde?
## Post #26
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-01-01T19:07:31+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

Ha magyarul akartok beszélni, akkor ott a PM. Ha a fórumba írtok, akkor meg tessék használni az angolt!
Csak megsúgom, hogy a tiéteken kívül már készül egy fordítás, és ha minden igaz, rendes őű is lesz benne.
## Post #27
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-01-01T21:51:45+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

English please.
## Post #28
- Username: Vagohid
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 29, 2011 12:10 am
- Post datetime: 2012-01-02T06:20:25+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

> Reply from evin
>
> Ha magyarul akartok beszélni, akkor ott a PM. Ha a fórumba írtok, akkor meg tessék használni az angolt!
Csak megsúgom, hogy a tiéteken kívül már készül egy fordítás, és ha minden igaz, rendes őű is lesz benne.

So why did you use Hungarian? Mine was just a response that I didn't want to PM. Anyway I feel quite awkward speaking to a Hungarian in English.

Then three will be the minimal amount of translation, right? Well we'll see the qualities of them.
## Post #29
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-01-02T06:31:29+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

Well, the main reason we insist on using English is because the vast majority of our visitors can speak it, even if only as a second (or third, or...) language. Personally, I wouldn't mind you using Hungarian when talking to a fellow Hungarian speaker, as long as you offer an English translation side-by-side with it (of course, that kind of defeats the purpose if you both speak English as well...), though Mr.Mouse might disagree... I dunno.
## Post #30
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-01-02T08:42:05+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

> Reply from Vagohid
>
> So why did you use Hungarian? Mine was just a response that I didn't want to PM. Anyway I feel quite awkward speaking to a Hungarian in English.
I thought, maybe I wasn't clear enough, when I said to terminator: "Next time, English pls." In PM you can use any language, but here is English the expected language, to we can help others.
## Post #31
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-01-02T08:59:32+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

What Evin says.
## Post #32
- Username: Vagohid
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 29, 2011 12:10 am
- Post datetime: 2012-01-02T16:49:03+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

Please don't treat me like an idiot. I used Hungarian, so what? Why the hell would anybody non-Hungarian care about Hungarian translations? And if they don't care about it then why shouldn't I use my native language? Yes, I could write a PM but why if it's just a short response? 
But if that makes you happy then from now I will use only English.
Seriously I'm sick of this 'Let's pick a quarrel' behaviour. 
Last time I came here it was a topic about the game and its translation and not about what languages do people use on the forum.
Now does any of you have something to say about the translation or do you want to continue this meaningless conversation? Please move on.
## Post #33
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-01-02T19:05:29+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

Just one more thing: If you don't use English language, the most people how the heck will know, what are you talking about? It could be an important information for them about compression/tool/etc. The Google Translator won't help too much to understand it.
## Post #34
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-01-02T21:03:07+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

@Vagohid: I'm not treating anyone like an idiot, neither is anyone else. The forum's language is English. I'm Dutch myself, but I refrain from using Dutch texts, because the language here is English. I'm not picking a quarrel, just stating the unwritten rule. Also, nobody is angry with anyone, we just ask to stick to English, so a lot of people can follow the discussion, and perhaps learn something new. So indeed, that said, let's move on.
## Post #35
- Username: Vagohid
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 29, 2011 12:10 am
- Post datetime: 2012-01-03T06:23:00+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

No, no, no... leave it. Seems like you didn't understand what I was trying to say, I won't continue it.

Now about the real subject - What do you think about the slangy parts in the texts? Some of them are pretty difficult to translate and figure out their meanings.
## Post #36
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2012-01-03T08:46:52+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

> Reply from Vagohid
>
> No, no, no... leave it. Seems like you didn't understand what I was trying to say, I won't continue it.

Now about the real subject - What do you think about the slangy parts in the texts? Some of them are pretty difficult to translate and figure out their meanings.

Most of them are really simple - my native language, as you know yet not english, but -, just use on of these sites:
* [Dictionary Reference](http://dictionary.reference.com/browse/node)
* [Urban Dictionary](http://www.urbandictionary.com/)

Last one helped me out so many times
## Post #37
- Username: Vagohid
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 29, 2011 12:10 am
- Post datetime: 2012-01-03T13:58:08+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

> Reply from terminator
>
> Most of them are really simple - my native language, as you know yet not english, but -, just use on of these sites:
* Dictionary Reference
* Urban Dictionary

Yes, I'm already using Urban Dictionary, I'll check out the other site, too, thanks.

There are also a few linguistic jokes which need a little creativity to be translated correctly while the joke remains understandable like "say sleaze" instead of "say cheese".
## Post #38
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-01-03T18:47:34+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

Just be glad you guys aren't trying to translate from Japanese. They seriously love their puns, and (especially in something like this) you end up with all sorts of (sometimes incredibly subtle) jokes that can be almost impossible to translate.
## Post #39
- Username: Vagohid
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 29, 2011 12:10 am
- Post datetime: 2012-01-04T06:33:35+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

The Simpsons is also full of puns and since I watch it dubbed the original joke disappears in the translation or I get another really weak joke instead.
I guess this situation is the nightmare of translators.
## Post #40
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2012-01-05T13:55:51+00:00
- Post Title: Re: Saints Row: The Third Translation {PC}

> Reply from Vagohid
>
> The Simpsons is also full of puns and since I watch it dubbed the original joke disappears in the translation or I get another really weak joke instead.
I guess this situation is the nightmare of translators.

Sometimes (!) the translated text or dub is more funny, or has finess, secondary meanings that makes them more funny - in local or/and worldwide comprehension...

A 'George W. Bush' jokes mostly funny (or shame) for american gamers, readers etc., but all over the world understandable, i suppose.
But there so many little-big jokes in games (like Borderlands, Saints Row-series etc.) that an european gamer none or just hardly can understand.
Those are the most/hardest things in localization
