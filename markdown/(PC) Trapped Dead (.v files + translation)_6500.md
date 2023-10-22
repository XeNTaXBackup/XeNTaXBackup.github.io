## Post #1
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-04-25T18:13:55+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

::[ Who am I? ]
First of all hello entire XeNTaX Community! I searched around but didn't find a "Presentation-thread" so I'll do it here. I'm a general knowledge fan of IT and like a lot to learn always new things. Newly, I discovered a person who would like to have the pc game Trapped Dead translated into Italian. So I decided to pick up this "personal challenge" and discovered the world of game-translators. I really found a lot of information and was impressed how much knowledge and dedication someone must spend into creating those "Unofficial (or Amateur) Language Patchers"! I don't want to be annoying so I stop here by saying that I think this Community could me further.

::[ What is my aim? ]
My intent is to create a language patcher (into Italian) for the game Trapped Dead ([http://www.trappeddead.com](http://www.trappeddead.com)). I know some ppl would like it. At the same time I learn more about file structures and such.

::[ Introduction + assumption of what I have already done ]
The game has an about 1GB _GameData.v file. Further after their official patch (1.0.71) another file was added _Patch0.v. Thanks to chrrox (viewtopic.php?p=35770#p35770) and to Aluigi for his xor 0.2 tool I managed to decrypt both files. Among the large amount of files inside them I managed to localize the 3 language files:

```
%ProgramFiles%\Trapped Dead\_GameData.v\language\en\Missions.xml
%ProgramFiles%\Trapped Dead\_GameData.v\language\en\Story.xml
```

Changing them happened nothing to the flow of the game (was in English, yet). I discovered in then the same files in the patch (which are few bytes larger):

```
%ProgramFiles%\Trapped Dead\_Patch0.v\language\en\Missions.xml
%ProgramFiles%\Trapped Dead\_Patch0.v\language\en\Story.xml
```

... ok. I translated then the entire GlobalStringTable.xml replaced in the extracted .zip file the original with the Italian-translated one. Then I xored (thx Aluigi) the entire _Patch0.zip file (with 0x55) back to _Patch0.v! Replaced the original one and then...

::[ Actual problem where i need help please ]
... and then the game works, but there are no the Italian strings and neither the English (obviously) ones. Just the kind-function-name strings see picture:


```
and
http://www.sendspace.com/file/ybvp2z/GlobalStringTable_TRANSLATED.xml
```


So my questions are... Does someone already experienced this situation? Have I overlooked something? Is my approach completely wrong?

Just in case you could need it, the entire original official patch file is here:

```
http://www.sendspace.com/file/kn4d6r/_Patch0.v
```

::[ Conclusion ]
I really do hope that I didn't break any rule (I read them!). Btw if this is the wrong section, sry didn't find anything which suites more (others are GFX, audio, etc.). Moreover thanks to you all who read this long post, but I wanted to be as detailed as possible. That's it. Waiting for kind responses I wish you all a good time 
Cheers
## Post #2
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-04-26T15:28:31+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

Hmmm... I see many posts in other threads. Just wondering if my request is "strange" or is it in a wrong section, or even wrong forum? Plesae let me know if I did something wrong, but I really would like to create such a translation patch.

Thanks once again
## Post #3
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-04-26T18:42:06+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

Try to save your translated xml as utf-8 with BOM.
## Post #4
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-04-26T20:02:02+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

> Reply from XRaptor
>
> Try to save your translated xml as utf-8 with BOM.
First of all thank you very much XRaptor for pointing to the "encoding-clue". You are right. I alway use NotePad++ for quite everything and since when opening the original .xml, it kept ANSI. So I tried the following options and the result is:
[*]ANSI -> does not work
[*]UTF-8 without BOM -> works! 
[*]UTF-8 (with BOM) -> does not work
So now we solved this part. I will translate everything and encode all files with the 2nd option. But now showed up another problem. Italian language has a lot of vouels accented (grave or acute) which will show in the game as an invalid char like ß? or such... Any idea or may I just use the ' sign, because the game-font does not support those chars probably?

Many thanks in advance one again for a reply... Btw thx again XRaptor  Works like a charm!
## Post #5
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-04-27T06:01:35+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

> Reply from KLseeker
>
> But now showed up another problem. Italian language has a lot of vouels accented (grave or acute) which will show in the game as an invalid char like ß? or such... Any idea or may I just use the ' sign, because the game-font does not support those chars probably?
It is simple, if game doesn't have all characters in font, you have to modify all font files and add missing chracters
## Post #6
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-04-27T22:18:09+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-04-28T06:24:31+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

Every xml must be saved with the same encoding as is entered in header. So it is just up to you what you choose. Default xml encoding (if encoding attribute is missing) is utf-8. Just set all encoding attributes to utf-8 and save all files in utf-8 format.

BTW you really found working font editor for this font version?? With working dds edit and info export?
## Post #8
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-04-28T13:21:44+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

Hi dear XRaptor and thank you for keeping helping me in my lonely job. Concerning the FNT Editor unfortunately it didn't work in my case. Its About says it all:

> Reply from FNT Editor
>
> Using this editor, you can edit C&C RA2's game.fnt file to change the in-game font. Please note that only the RA2/YR "fonT" format, which applies to "game.fnt" only, is supported by this tool.
So it is not working for Trapped Dead's font files. Their extension is .fnt and the first chars of the header are "BMF".

Regarding the encoding, he  I'll try do manage it. On first news I'll post again here  Btw thank your for taking your time for me. Sincerely.
## Post #9
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-04-28T14:57:07+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

Hi KLseeker, new fonts for that game can be created with [BMFont from AngelCode](http://www.angelcode.com/products/bmfont/). 
Just choose font you like (I was searching for orignal font used and it's Blambot Hometown Hero BB Regular, but it's not free), and set as output .dds texture without compression, and binary font descriptor (that is .fnt file).

I have not tested it in the game yet, but it looks exactly like the original fonts.
## Post #10
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-04-28T21:24:45+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

Hi there merlinsvk and thanks to you too for joining the thread  Helpful post, but unfortunately I'm completely new into "fonts" in *this* manner... I'm downloading right now 1.8GB compressed font files + an archive with 235 Bomblat fonts. Unfortunately in no one of these is the one you said. In this manner I would like to ask some things:
01) one of the .dds files IngameText_00.dds looks like that and we see the a-grave, e-grave, i-grave, (the vowels-accented). So why are they not in the .fnt file? Or at least usable?


02) I can't find the right approach to AngelCode's BMFont? Is there a simple/basic tutorial which explains what we are trying to do now? It seems I can't understand those proposed on its homepage.

By the way I managed to translate already the majority of system dialogs and the first 2 mission dialogs  I'm getting proud. But it's not enough, I would to share with you this final patch (whenever I'll finish it). For now the only problem are the encoding "things" and font "things". All your help is really appreciated.
## Post #11
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-04-29T11:45:46+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

Hmm it looks I was wrong. I tried BMFont to create a new IngameTitle font from Arial, but game can't run with it.
## Post #12
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-04-29T12:36:40+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

Well, it is not so hard. You have to check original fnt file to get setings like size, charset, padding etc. Then just in BMFont set the same values and generate a new font. Just make sure you set output dds size to fit all characters to one file. It will not work if more dds files per font are made.
## Post #13
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-04-29T12:51:12+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-04-29T20:29:34+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

Hey guys, look what I've got. [Tools](http://www.mediafire.com/?4h9c7ib8plq0vcl) from Vision Engine. And yes, Font Generator is there 

Now there is only one question. How to display correct characters? Because I tried other font (A.C.M.E. Secret Agent by Blambot), font was there, but chars like Á, É weren't.
## Post #15
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-04-29T20:42:06+00:00
- Post Title: (PC) Trapped Dead (.v files + translation):

All you need is ttf font with all characters. Use any unicode version or just edit any ttf and add missing characters. Then use BMFont
## Post #16
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-05-02T14:00:52+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

Hi there XRaptor and merlinsvk. Thank's for keeping helping me... Unfortunately it seems I'm not "getting it". I don't want to look ignorant, but apparently I am. I'm not understanding some things:

01) Why should I edit or create new BMF file (which is .fnt + .dds) if in the .dds files of the fonts folder of the game I see the characters I actually need? (á, é, í, ó and ú)? Doesn't it mean that those chars are already there if I see them? See picture some posts above.
02) When I try to open one of the .fnt files (in example the IngameText-00.fnt) AngelCode's BMFont says "Sorry can't open 230 chars..." So how should I get it?
03) Do you know of any good article, tutorial, essay, writing which shows a practical example of how to add a char in .fnt file and update the existing .dds file?
04) Do you know of any program, which tells you all possibile info from an BMF .fnt file? For example, the charset it has, the lenght and so on?

Sure for a kind reply I'm waiting  Thank you very much one again in advance. And remember: I'm not an expert in this IT-sector... I just want to make a language pack for all people who would like to play that game in Italian!
## Post #17
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-05-02T15:33:17+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

I don't know if Italian language have any special characters that are not in ANSI char table. If there is only áéíóú then all chars should be in dds files. Just check them. If there is any char missing, you have to regenerate fonts. You are asking why not to edit. It is simple. Generate new font file will take about 1 minute. Editing existing one should take hour and more  In other hand, there is no need to know all about bmf font format. All you need to know is font type and font size. Thats all. 
So for example:
Arial_18.fnt = Arial, 18px
Arial_18_TPL.fnt = Arial, 18px
CourierNew_18.fnt = Courier New, 18px
DebugFont.fnt = Tahoma, 14px
DebugFont_TPL.fnt = Tahoma, 14px
IngameSmall.fnt = HometownHero BB, 20px
IngameText.fnt = HometownHero BB, 24px
IngameTitle.fnt = HometownHero BB, 32px

So just open BMFont and check required sets on the right side. For example Latin + Supplement, maybe Latin Extended A. It depends where your characters are.

Then in Font Settings select like this:


Select export Options like this:

You can change texture width and height for 128*128, 256*128, 256*256 etc. Just set multiple 128. The best way is to set resolution to get only one dds per font. 

Because Trapped Death is using old version 1 bmf format, I hope there will be no problem.

Then select Save bitmap font as ... and select filename like Arial_18.fnt etc. That's all. Generate all fonts and test it in game.
## Post #18
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-05-03T17:52:44+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

The contents of this post was deleted because of possible forum rules violation.
## Post #19
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-05-03T18:17:12+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

Problem is you renamed new dds files  In fnt there is reference to texture (*.dds) and now it just doesn't exists. Just let all names as are generated. 
For example:
Save font as IngameText.fnt and IngameText_0.dds will be generated.
Save font as IngameTitle.fnt and IngameTitle_0.dds will be generated.
etc. Just delete original files and put there new ones. Don't  name fonts as test20, 24 and 32 like is referenced in your fnt files
## Post #20
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-05-03T20:37:26+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

The contents of this post was deleted because of possible forum rules violation.
## Post #21
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-05-03T20:45:47+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

One question - are you trying to put new files to original *.v archives or just extracted from them?

EDIT: Well I checked it on my sode and you are right. Game crashes. It should be because of newer version of fnt file. It is now version 3 but original file is 1. There are some new fields in version 2+. So try to do fonts the same way BUT with old version of BMFont tool. It is somewhere here posted by other user.
## Post #22
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-05-03T21:10:26+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

> Reply from XRaptor
>
> One question - are you trying to put new files to original *.v archives or just extracted from them?
Yes, I'm trying to put the 3 new Ingame*.fnt + relative .dds files into the original _GameData.v file/archive. Otherwise I would not know if it works or not? But in any case it seems that I have to buy the HometownHero BB font...


There are 2 main files: 1GB _GameData.v and _Patch0.v. Those are encrypted. Every time I modify a file i do exactly as follows (the xor tool is the one from great aluigi):

01) xor _GameData.v _GameData.zip 0x55
02) With WinRAR v3.90 I then extracted the fonts folder only.
03) Generated the new .fnt (+ .dds) files in a temporary folder and when all complete overwrited the existing .fnt and .dds.
04) In WinRAR directly deleted the fonts folder and after, added the new fonts folder.
05) I finally deleted the original _GameData.v and encrypted the _GameData.zip again into _GameData.v (xoring with 0x55).

Please tell me if it is not clear, I will try to be more detailed. Anyway I did this same procedure with the .xml files contained in the _Patch0.v (which contains the text) and works well.
## Post #23
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-05-04T06:30:49+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

Yes, I know how VEngine works. It is easy.

1) you can put fonts to original file or to patch file. Files from patch have higher priority
2) zip file is without compression (byt it is not important)
3) you don't have to buy that font. Just google it or select ANY similar of your choice. It is only font. Type doesn't matter. It will only just look different 
4) as I wrote before, problem should be in fnt version. Maybe just game can't load newer version (and it makes sense, because there are new fields in binary format v2+). so use font tool v1 from vtools archive on page 1
## Post #24
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-05-04T10:36:23+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

So this is what I tried.

1. I used original font editor for that engine (link is on first page), I chose Segoe UI font just for test, make a new IngameTitle.fnt + dds. 
2. I unxor and unpacked _Patch0.v
3. In unpacked Fonts delete, original one, and put there a new one
4. Translated .xml in Language\en\
5. Pack all these files to _Patch0.zip (with or without compression, it doesn't matter)
6. xor .zip to _Patch0.v

But in 4. step I had to convert .xml to ANSI coding and also rewrote utf-8 to windows-1250 on first row of file.

```
to
<?xml version="1.0" encoding="windows-1250"?>

```


And this is result
[](http://imghost.sk/image/358270-Obr0002.jpeg)
## Post #25
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-05-04T11:13:59+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

So as I said, game is looking for v1 font files
## Post #26
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-05-04T13:15:03+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

> Reply from XRaptor
>
> So as I said, game is looking for v1 font files

Yep   

So KLseeker, try [this](http://www.mediafire.com/?f6jsgfs81ia06f8).
It contains _Patch0.v, setting's screenshots of font editor that I used for creating new IngameTitle font, and also TTF font. Maybe you got it in that huge pack of Blambot fonts. It's called A.C.M.E Secret Agent (it looks similarly that original font).


[](http://imghost.sk/image/358293-Screenshot.jpeg)
## Post #27
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-05-04T22:26:11+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

First: thank you sooo much both for all info (2 pages of more knowledge I came through (we never learn enough)).

So let's go step-by-step what I did. After your (both) last posts I wanted to try myself if I get it working. So I searched for a similar font with accents. I found that one with all accents "Vigilante Notes Font" ([http://www.dafont.com/vigilante-notes.font](http://www.dafont.com/vigilante-notes.font)). Then I created the 3 Ingame* .fnt + .dds files with your recommended settings with the "old-bmf-version-tool". After successfully creating them, I updated the _GameData.v archive. Run the game and with great surprise it didn't work.

After I did 7 different tryies with different .xml encoding and changing several times the encoding-attribute inside the .xml file. Nothing worked, goddamn! (By the way, I spend my entire day only in modifying and updating and rerunning the game. 11 hours and 15 minutes NO JOKE!). I became suspicious and so updated the _GameData.v with the 2 files (IngameTitle.fnt and IngameTitle_00.dds) provided by merlinsvk and the _Patch0.v with (GlobalStringTable.xml) even provided by him... now good news:

Oh my god, unbelievable! It works... and it works like a charm! It displays áàÁÀ --> all four kinds! YESSS SuperHappyMan.

Myself is very curious, so I wanted to understand what makes appear those "magic chars". I then deleted and put there the original, completely, totally untouched _GameData.v file... Run the game and bet what happened?! The game run with original Hometown Hero BB font WITH accented chars.    And in fact all IngameTitle dialogs show them the right way. But not the IngameText dialogs.

With NotePad++ I convert to ANSI the Missions.xml file, save it but everytime I open it it shows "ANSI as UTF-8" encoding "UTF-8 without BOM". And this is making me nervous. Because everytime I hopen GlobalStringTable.xml edited by merlinsvk it remains ANSI??? Perhaps a bug of notepad++!!!

ROFL I'm really getting crazy with all these encoding-nonencoding-nonsens...
## Post #28
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-05-04T22:47:47+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

Yes it looks like a bug or something, because I also tried convert Missions.xml to ANSI and nothing happened. But try convert it firstly to UTF-8, and than to ANSI. It worked for me. Now I got Missions.xml in ANSI
## Post #29
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-05-04T23:09:46+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

Dear XRaptor and dear merlinsvk, with your wide-range knowledge and willing to help and with my "I want to get/understand it" we found the solution... finally  .


[](http://imgur.com/BchyH)


Solution: since the 3 original Ingame* .fnt files already incorporate many accented chars (we can see it from the original .dds files) we do not need (in this case, in another case, this thread comes DEFINITELY in handy  ) to integrate other fonts. The manner is the numerous encoding types. In our specific case (if you want to translate this in another language w/ special char you will need to pay attention) we needed to make sure that the 3 .xml files (GlobalStringTable, Missions, Story) are binary encoded in ANSI format and that the xml encoding-attribute is set to "windows-1252". ROFL now it sounds easy hehehe.

Conclusion: after a long and difficult troubleshooting we got  And we found a bug in a program too.
## Post #30
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-05-05T06:10:57+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

Think about it, if your xml files are saved in ANSI encoding, how should it work, if font is exported as Unicode?  If you need ANSI text, you will need ANSI font export, but in ANSI there is no extended font support. But yes, engine should be little buggy, because they don't test all characters sets.
## Post #31
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-05-05T10:12:23+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

Hi XRaptor. To satisfy my thirst of knowledge I've some little questions.

01) How (please list some tools) do you add a char to an existing .ttf file? For example: there is a example.ttf file which has all lowercase chars from a to z and I would like to add a "K".
02) Are there any REAL .fnt analysers? Please tell me I'm curious. For example: there exist .avi files. AVI is a container which has inside video + audio (thus 2 different formats). Is it the same with .fnt files? Some .fnt files start with ABC header some with DEF header and some as in our case with BMF. Are there tools which show you ALL possibile info about what's inside them?

Thanks once again
## Post #32
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-05-05T11:24:45+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

1) I'm using FontCreator Pro and FontLab Studio for ttf editing.
2) If you are talking about fnt from this game, then fnt is not standard, it is just custom format for bitmap fonts. So no, there is no analyzer. But check \doc\file_format.html, there is structure info, so you can make your own tool to parse it and write info
## Post #33
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-05-08T09:15:28+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

Hi XRaptor and merlinsvk, just wanted to show you with what I came up 

```
http://www.sendspace.com/file/xz3eks
```


... it's quite all in italian (obviously) but look at the bottom of the file "leggimi.txt"  .
## Post #34
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-05-10T14:43:12+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

I'm having the same problem, I can not add character to these fonts there, I need all the special characters of the game for the translation into Portuguese of Brazil.
If someone finds something, please let me know.
## Post #35
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-05-10T14:46:23+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

> Reply from delutto
>
> I'm having the same problem, I can not add character to these fonts there, I need all the special characters of the game for the translation into Portuguese of Brazil.
If someone finds something, please let me know.

Just read again this thread, threre is everything you need
## Post #36
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-05-10T14:51:41+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

delutto, does pt-BR use characters that are not in original game fonts? Because I think that it uses windows-1252 codepage, just like italian language.
## Post #37
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-05-10T18:12:09+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

Believe so. The Portuguese language uses characters: a, à, â, ã, is, ê, í, ó, ô, õ, ç, etc.. The problem is that I could not use the source editor, has almost no knowledge of this part. Someone managed to make the game accept these characters? If yes, could make the files available to me, please?

An example of the translated text in Portuguese:

```
      <CONTROLS>Controles</CONTROLS>
      <GRAPHIC>Gráficos</GRAPHIC>
      <GAME>Jogo</GAME>
      <SOUND>Som</SOUND>
      <RESTORE_DEFAULTS>Prédefinições</RESTORE_DEFAULTS>
      <CHANGE_RESOLUTION>Alterar a Resolução</CHANGE_RESOLUTION>
```
## Post #38
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-05-10T18:31:12+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

Original fonts should be OK. Try replace 

```

with

<?xml version="1.0" encoding="windows-1252"?>

```


in .xml files.
## Post #39
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-05-10T22:09:26+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

Thank you merlinsvk, it worked perfectly.
Thanks everyone!
## Post #40
- Username: KLseeker
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 25, 2011 11:01 pm
- Post datetime: 2011-05-20T18:23:10+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

Ups. Sorry for replying so late. Anyway delutto, I see you managed to solve the same problem I had.

By the way are there any portals where to upload translation files or patches? May we see your work delutto when done?
## Post #41
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-05-21T02:44:01+00:00
- Post Title: Re: (PC) Trapped Dead (.v files + translation):

> Reply from KLseeker
>
> Ups. Sorry for replying so late. Anyway delutto, I see you managed to solve the same problem I had.

By the way are there any portals where to upload translation files or patches? May we see your work delutto when done?
My problem was the encoding of the XML files. You can see my work in the translation list of the community that I serve:
[http://www.tribodosrenegados.com.br/](http://www.tribodosrenegados.com.br/)
