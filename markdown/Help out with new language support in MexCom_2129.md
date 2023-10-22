## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-05T14:01:05+00:00
- Post Title: Help out with new language support in MexCom

Dear all, 

Those of you who have already downloaded the new version of MultiEx Commander will have noticed that users can now choose between an English and Dutch user-interface. 

The implementation is a simple one, one that requires only editing of text files. 

I have attached here the two text files that come with MexCom 4.3. 

Any of you willing to participate in creating support for other languages (not specifically needing other non-Western characters) in MexCom, please post here! 

If more than one of you wish to translate into the same language, the better of course, as the work load can be divided! 

Here's an example from the text file:

```
File 
[File Menu|2]
New...
[File Menu|3]
Open archive
[File Menu|4]
Table of contents
[File Menu|5]
Exit
[Table of contents|6]
Save the table of contents
[Edit |7]
Edit 
[Edit Menu|8]
Find...
[Find|9]
Search and select
[Find|FrameCaption|10]
Search criterium
[Log|11]
Log

```


Each word or sentence is preceded by an identifier in brackets []. The number is the most important one, as that determines where to use what sentence/word. This number always needs to be the last entry in a list of |-delimited entries. For instance, in [Log|11] there are two parts, delimited by the "|": Log and 11. The number is important, and you could fill in anything before that, but keep in mind that the text that's already there is informative of what type of senctence/word is expected. 

The next line then is the actual text that will be used in the program! *THIS SHOULD BE TRANSLATED*!  

Allright, Dinoguy has already volunteered for Spanish, but perhaps some of you can assist him with that. All that help out will be acknowledged in the About screen of the next MultiEx Commander AND earn a serial key for the next release 

To experiment yourself, copy an existing file, such as Nederlands.txt under a new name in the languages directory in the data folder of MexCom. Then you can choose that one in MexCom (Options). Then make alteration to the new text file and restart MexCom each time to test the results.
[English.zip](https://xentaxbackup.github.io/file/884_English.zip)

[Nederlands.zip](https://xentaxbackup.github.io/file/883_Nederlands.zip)
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-05T14:30:16+00:00
- Post Title: Help out with new language support in MexCom

Il give it a go with JAPANESE text.
It shouldnt be hard ot do.
BUT i dont know IF MEXCOM will even read it, as its UNICODE and not normal text.
If you KNOW its not gonna work then say and i wont do it lol.
THo id like soem help with JAPANESE as I am a busy man lately lol.
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-05T14:35:19+00:00
- Post Title: Help out with new language support in MexCom

> Reply from lionheartuk
>
> Il give it a go with JAPANESE text.
It shouldnt be hard ot do.
BUT i dont know IF MEXCOM will even read it, as its UNICODE and not normal text.
If you KNOW its not gonna work then say and i wont do it lol.
THo id like soem help with JAPANESE as I am a busy man lately lol.

That will be possible in a future version of MexCom only. I first have to see what I can do to support those languages. So for now, we are left with Western languages-based characters. But you will be the first to be contacted when I do get the support for other characters in there.
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-05T15:09:14+00:00
- Post Title: Help out with new language support in MexCom

> Reply from Mr.Mouse
>
> lionheartuk wrote:Il give it a go with JAPANESE text.
It shouldnt be hard ot do.
BUT i dont know IF MEXCOM will even read it, as its UNICODE and not normal text.
If you KNOW its not gonna work then say and i wont do it lol.
THo id like soem help with JAPANESE as I am a busy man lately lol.

That will be possible in a future version of MexCom only. I first have to see what I can do to support those languages. So for now, we are left with Western languages-based characters. But you will be the first to be contacted when I do get the support for other characters in there.
Yes ok then.
Thats god to hear.
BTW the Plugin for Brea of fire .EMI files works BUT it doesnt matter as the fiels INSIDE the archives STILL cannot be used with anything lol.
## Post #5
- Username: BPh_Designs
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Apr 05, 2006 7:14 pm
- Post datetime: 2006-10-05T15:43:15+00:00
- Post Title: Help out with new language support in MexCom

I'll translate it in french, I'm belgian and my mother language is french, it's used in France, Switserland, Quebec, ~Africa, Luxemburg...
## Post #6
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-10-05T18:22:05+00:00
- Post Title: Help out with new language support in MexCom

I'll start translating into Swedish. 
Strobe, you wanna help me?
## Post #7
- Username: BPh_Designs
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Apr 05, 2006 7:14 pm
- Post datetime: 2006-10-05T18:50:37+00:00
- Post Title: Help out with new language support in MexCom

Here it is... in french. Let me know if it's ok.
[French.rar](https://xentaxbackup.github.io/file/885_French.rar)
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-05T19:03:21+00:00
- Post Title: Help out with new language support in MexCom

> Reply from BPh_Designs
>
> Here it is... in french. Let me know if it's ok.
 That's FAST!!! I do read a little French, so it looks okay to me. Perhaps another native speaker could beta-test it.  

There are a few problems with the spacing in which you can put text, I noticed. For instance, if you start Options, or MRF manager, you see that some text does not have enough space to fit in the Buttons etc. Do you think you could shorten that so it looks a little better? I will see what I can do in next releases to give more room for text. But would be nice if you could fit most of the text in the space provided at this time. 

Anyway, it's really awesome you've done this so far, at this rate we can already release the French language file this week!
## Post #9
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-10-05T20:40:20+00:00
- Post Title: Help out with new language support in MexCom

I'm going to translate to spanish as well
## Post #10
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-05T21:37:38+00:00
- Post Title: Help out with new language support in MexCom

Oh, why not ...

Here's a preliminary german translation. Some of the texts will probably be too long; I'll correct this tomorrow while doing the spelling and sanity checks.

Meanwhile, I have a few questions/comments on the English source.

- Some lines ended with blanks. I tried to preserve this, but was it intentional?
- Some lines contained just a "*". I didn't translate those.  
- line 10: "criterion", not "criterium". As least as far as my dictionary knows.
- line 45: There were brackets around this line. I removed them for the translation ...
- line 207: What does "selecteer" mean? I assumed "select".
- line 264: "analyzing", not "analizing". I really don't want to know what the latter means. 

Good night everybody.
[German.zip](https://xentaxbackup.github.io/file/886_German.zip)
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-05T21:46:53+00:00
- Post Title: Help out with new language support in MexCom

Excellent, and thanks for pointing out some errors in the original English script. I see some Dutch words slipped in there during the process. Might be an idea to have a native English speaker correct/change the English.txt. 

I eagerly await your final Deutsche version. You can save it as Deutsch.txt, just like the Nederlands.txt. I'll see about those other errors you mention.
## Post #12
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-05T21:59:25+00:00
- Post Title: Help out with new language support in MexCom

> Reply from Mr.Mouse
>
> Excellent, and thanks for pointing out some errors in the original English script. I see some Dutch words slipped in there during the process. Might be an idea to have a native English speaker correct/change the English.txt.
Ima NATIVE inelgish Speaker, Japanese is only my 2ND language so If anyone tells me what file im supposed to look at to correct then il do it INSTANTLY.
Fixed errors with TEXT in the original english one.

- Some lines ended with blanks. Im not sure if this was intentional so i have left it as it was (i see Deniz also noticed this)

- Certain lines contianed this ie line 153 "[Info for developers|DialogTitle|153]" contained *, Im not sure if those need to be translated or not so i left them sorry.

- line 10: "criterion", not "criterium". As least as far as my dictionary knows. 
-
> line 45: There were brackets around this line. I removed them for the translation ... Ditto my friend.

> - line 207: What does "selecteer" mean? I assumed "select".
I changed it to Selected
- line 264: "analyzing", not "analizing", the latter doesnt exist in my dictionary

- Line 39 correct en to "an"

- Line 334 "Naye" fixed to "No"

- Line 333 "Aye" foxed to "Yes"

- Line 332 Fixed "Aye" and "Naye" once again   

- Other lines I just added Capitals and stuff to make the formatting look nicer.


Those were all that needed changing, the lines with naye in STILL say naye as the COMMAND but not as the text, I simply chose to ignore the COMAND as i figured itd mess with the code.
[Fixed English.rar](https://xentaxbackup.github.io/file/887_Fixed English.rar)
## Post #13
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-05T22:43:35+00:00
- Post Title: Help out with new language support in MexCom

> Reply from Mr.Mouse
>
> I see some Dutch words slipped in there during the process.
Ah, that makes sense. In contrast to most Dutch people I know (who have quite a firm grip on the German language), my knowledge of the Dutch language relies heavily on guessing. 

> Reply from Mr.Mouse
>
> I eagerly await your final Deutsche version. You can save it as Deutsch.txt, just like the Nederlands.txt.
Good idea. The attached version is not yet final, but I couldn't sleep before at least fixing the worst bugs. 

By the way: Not all labels in the program seem to have an equivalent in the language file and are therefore not translated. Is this known or should I make up a list as I notice them?

> Reply from lionheartuk
>
> - Line 332 Fixed "Aye" and "Naye" once again
Let them be. They're funny; I stopped there to choose some fine translations. 

[Edit: New version attached.]
[Edit #2: Even newer version attached.]
[Deutsch.zip](https://xentaxbackup.github.io/file/888_Deutsch.zip)
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-10-06T00:22:50+00:00
- Post Title: Help out with new language support in MexCom

> Reply from Savage
>
> I'm going to translate to spanish as well
Alright, thanks for the help, Savage! Would you like to split it 50/50?

As to the English translation, I'll look through it myself, and (when I get the chance) also check into the lines that Deniz said don't have a language file equivalent.
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-06T07:12:17+00:00
- Post Title: Help out with new language support in MexCom

Answer to all:

- Please do note down those lines that are not in the text file, but still need to be translated. I can have missed some, so you're right to point them out. 

- Line 45: It has brackets around because it will be put in the textbox where people can enter a new folder name, so they'd notice that it is there that they should put the new text. But I guess its allright to remove them. 
- Line 10: "Criterium"is Dutch, so yeah, it should be criterion in English
- Line 207: "selecteer" is "select" in Dutch
- Line 264: WOOPS! Funny typo (Final analisis  ) 
- Lines with an asterix do not need to be translated at this time. 
- Lines that end with blanks : this was intentional as they represent snippets of a whole sentence and some value in the program will be inserted in the sentence, like "MexCom supports "<insert number> " archive formats".

"Aye" and"Naye" were intentional, like Deniz said: just a humorous note. 

In the next executable I will add more lines to make sure non-translated lines/commands in this version are also translated. Please point them out. 

The next step would be to have also the MexCom download site translated, and how about the manual? LOL That would take considerable time! Well, if you feel up to it, go ahead and I can send you a RTF file of the manual. If not, that's also okay.
## Post #16
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-10-06T08:33:37+00:00
- Post Title: 

> Alright, thanks for the help, Savage!
send me/attach  the 50% to translate
## Post #17
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-06T09:20:12+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Please do note down those lines that are not in the text file, but still need to be translated. I can have missed some, so you're right to point them out.

Here's what I have noticed "on the fly":

- Splash screen: status messages during startup (that's probably intentional ...?)
- Status bar: "AutoPreview = Off"
- Status bar, during load of editable game list: "Analysing BMS scripts..."
- "Open archive" dialogue, "MexScript source" group box: "Wiki (unofficial)"
- "Open archive" dialogue, "Filter" group box: "All", "Ext"
- "Open archive" dialogue, bottom right: "Type"
- "Tools" menu: "Scan file..."
- "Help" menu: "Help"
- Main window, context menu: "View <filename>"
- Main window, context menu: "Extract <filename>"
- Search box for multiple selection: basically all tooltips
- all of Jaeder Naub 

> Reply from Mr.Mouse
>
> Line 45: It has brackets around because it will be put in the textbox where people can enter a new folder name, so they'd notice that it is there that they should put the new text. But I guess its allright to remove them.
No, you're right, that's useful. Now I have seen where this line belongs.

> Reply from Mr.Mouse
>
> Lines that end with blanks : this was intentional as they represent snippets of a whole sentence and some value in the program will be inserted in the sentence, like "MexCom supports "<insert number> " archive formats".
I thought so. However, more often than not the program seems to add additional blanks on its own, so I removed some of them from the translation to make it look right. 
Shouldn't be a problem to fix the translation file if this changes in later versions.

> Reply from Mr.Mouse
>
> The next step would be to have also the MexCom download site translated, and how about the manual? LOL That would take considerable time!
The download page is not a problem. The translation of the manual, however, is indeed a hefty task. 

Concering the current translation status: I have updated the attachment to my last post.  I have fixed bugs as far as I could see them. For the rest, someone with a registered version will have to tell me which lines still need tweaking (especially regarding the length). A person speaking German would be great -- I don't know if all of my translations actually make sense in the program's context.

[Edit: Attached translated download page.]
[index_de.zip](https://xentaxbackup.github.io/file/889_index_de.zip)
## Post #18
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-10-06T10:51:17+00:00
- Post Title: 

Sorry for out of topic 

> Yes ok then. 
>
> Thats god to hear. 
>
> BTW the Plugin for Brea of fire .EMI files works BUT it doesnt matter as the fiels INSIDE the archives STILL cannot be used with anything lol.
So that mean Mexcom can rip the file, but the file is still unknown?
## Post #19
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-06T11:10:12+00:00
- Post Title: 

@ LustD : Yes

@ Deniz: Check it !  [http://multiex.xentax.com/index_de.html](http://multiex.xentax.com/index_de.html)
## Post #20
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-06T13:21:22+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Check it !  http://multiex.xentax.com/index_de.html
Great! 
If you change the alternate text for the German flag from "Nederlandse taal" to "Deutsche Sprache", it'll be perfect. 

Thanks to Mr.Mouse's generosity, I was now able to do the remaining checks myself ... so the attachment to the [above post](http://forum.xentax.com/viewtopic.php?p=17430#17430) has once again been updated with what could be considered a final version. However, everybody is invited to find bugs I might have missed ...

Some additional observations regarding untranslated lines:

- MultiEx Editor: Status messages during Add/Delete
- MultiEx Editor: "Directory based batch job" dialogue title
- general: error messages (download error, mrf add failure etc.)

Additionally, the monospaced font used in some smaller labels doesn't seem to use the standard ANSI charset, which causes incorrect display of "special" characters. But that's just a minor thing ...
## Post #21
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-06T13:34:46+00:00
- Post Title: 

> Reply from Deniz Oezmen
>
> 
Additionally, the monospaced font used in some smaller labels doesn't seem to use the standard ANSI charset, which causes incorrect display of "special" characters. But that's just a minor thing ...

Could you point out a few? So I can see if that can be fixed in-code for a future release.
## Post #22
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-10-06T14:18:50+00:00
- Post Title: 

Two examples:

- MultiEx Editor: the info labels that function as "mouse hover" triggers or display the file/ressource size
- MRF manager: the captions of the columns in the left list box

These are the cases I noticed. If you try to have them display, say, an "Ã¼", you will get a "Â³" instead. At least that happened on my system.

But perhaps not the application, but my fonts are the cause for this problem? Is the MRF manager list box on the left supposed to have a font different from the one on the right?
## Post #23
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-10-06T20:08:20+00:00
- Post Title: 

> Reply from Savage
>
> Alright, thanks for the help, Savage! 
send me/attach  the 50% to translate
Take your pick: first half or last half? (just pick one and tell me the item number you used as the 'cutoff'...)
## Post #24
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-10-06T22:12:13+00:00
- Post Title: 

I get the last 50% you start from the beginning, sendme the part of text to translate in zip file   

PS: i like this icon
## Post #25
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-10-06T22:46:13+00:00
- Post Title: 

LOL... Alright, I'll get it to you as soon as I can get what I've done off the other comp... (hopefully, that'll be tonight)
## Post #26
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-07T01:37:14+00:00
- Post Title: 

> Reply from lionheartuk
>
> Il give it a go with JAPANESE text.
It shouldnt be hard ot do.
BUT i dont know IF MEXCOM will even read it, as its UNICODE and not normal text.
If you KNOW its not gonna work then say and i wont do it lol.
THo id like soem help with JAPANESE as I am a busy man lately lol.
Just to let your know that althrough japanese is part of the unicode
standard, japanese is also one of the many ansi codepages so it will be
posible to have MultiEx display japanese as long as the users
computer is configured with the right ansi codepage

eg: ãƒ†ã‚¹ãƒˆ <-- japanese :P Codepage 932 - Shift jis

That is ofcourse if the program passes the text strings as-is to windows
with for eg Set??TextA(A for Ansi) winapi. I don't know if you can go
wrong there thought
## Post #27
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-10-07T12:40:24+00:00
- Post Title: 

Mexcom was created with VB5, all strings are in UTF-16 format and converted when needed to ansi if calling AAPI.  Code pages are the devil, asian scripts are still in multibyte format and its a big pain to program that in  UTF16 is the way to go.  But weither or not Mexcom will read it is another story, i'm not sure of the format of whatever hes using to read the languages in (resource/file/etc)
## Post #28
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-08T07:21:45+00:00
- Post Title: 

VB6
## Post #29
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-08T11:31:04+00:00
- Post Title: 

> Reply from Rahly
>
> i'm not sure of the format of whatever hes using to read the languages in (resource/file/etc)
By HE you mean ME right?
I actually have NO IDEA what unicode Japanese is lol, I just set the text documents to UTF8 when i save them.
As for WEBPAGES, well I have it set to UNICODE UTF8 all the time, BUT on the other hand i DO have the language bar and Japanese language support for all programs on my PC.
But to make CERTAIN JAPANESE ONLY programs work i do have to chane EVERYTHING to japanese, so they arnt just ANOYING squares that i cant read.
But yes as soon as MULTI EX supports UTF8 please feel free to contact me and I will translate the PROGRAM text into Japanese, though the MANUAL will take more PROFESIONAL japanese and seing as my sentance structure isnt all that good for LONG Sentances I will most likely need some help with that, though my japanese does get better on a DAILY basis.
Was THINKING of writing a translation program in VB6 to trnaslate english words into their ROMANJI counterparts, But i havent started it yet lol.

 ãƒ ãƒ«ãƒ
## Post #30
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-10-08T22:13:18+00:00
- Post Title: 

No, HE, that I was refering to is, Mr. Mouse.  UTF-8 is a Unicode encoding.  Since no OS i know of actually uses UTF-8 directly, and I highly doubt Mr.Mouse is doing any UTF-8<->UTF-16 transformation, it all depends on how hes reading the language data.  Windows and *nix machines that have unicode support, all use UTF-16 encodings when talking on an OS level.  If he has straight UTF-16 support, then you can do it.  Programs like Notepad and Wordpad for windows support these formats.
## Post #31
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-08T22:34:56+00:00
- Post Title: 

> Reply from Rahly
>
> No, HE, that I was refering to is, Mr. Mouse.  UTF-8 is a Unicode encoding.  Since no OS i know of actually uses UTF-8 directly, and I highly doubt Mr.Mouse is doing any UTF-8<->UTF-16 transformation, it all depends on how hes reading the language data.  Windows and *nix machines that have unicode support, all use UTF-16 encodings when talking on an OS level.  If he has straight UTF-16 support, then you can do it.  Programs like Notepad and Wordpad for windows support these formats.
Yes i guess this will all boil down to Mr Mouse lol.
Though I can imagien its gonna take a WHILE until MECOM supports Unicode letters.
## Post #32
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-10-10T22:27:21+00:00
- Post Title: 

> Reply from Savage
>
> Alright, thanks for the help, Savage! 
send me/attach  the 50% to translate
All right, here's your half (sorry it took so long)...
[Espanol_half_2.zip](https://xentaxbackup.github.io/file/907_Espanol_half_2.zip)
## Post #33
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-26T07:33:48+00:00
- Post Title: 

Okay, so we have a German version, an almost complete French version (I do not have the time yet to see which lines are wrong, Bhp_Design) and a half-way completed Spanish version? I would like to release those language files officially some time soon, if possible. Would it also be an option for someone to translate the webpage ([http://multiex.xentax.com](http://multiex.xentax.com)) like Deniz did for the German language and yours truly for the Dutch language?
## Post #34
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-11-03T06:19:14+00:00
- Post Title: 

Oops, I knew there was something I was forgetting to do... *blush* I'm sorry, but my Spanish isn't nearly good enough to translate a whole website.
## Post #35
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-11-13T15:38:23+00:00
- Post Title: 

Mr Mouse.
Do you have any idea when you plan to begin the conversion of Multi ex so that it supports unicode characters?
As im more free now so i gues id have the time to translate it soon enough.
I dont think id have the knowledge to translate and ENTIRE webpage though, as there will most likely be english words that arnt translatable into Japanese.
## Post #36
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-31T12:25:14+00:00
- Post Title: 

Now this is a neat idea:

[http://cestiny.idnes.cz/pm/multiexcommandercz.html](http://cestiny.idnes.cz/pm/multiexcommandercz.html)

This little program will install a custom language file making MultiEx Commander support the Czech language. 

It will let you choose the installation folder of MexCom and then add the text file in the appropriate data/languages folder! 

Now just how are those Spanish and French versions coming along?
## Post #37
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-07-31T17:30:27+00:00
- Post Title: 

Gaah, you remembered!

Erm, I mean, no speaka de Ingles... yeah...
## Post #38
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-08-02T08:34:54+00:00
- Post Title: 

MexCom Language Pack 1 

[http://www.xentax.com/uploads/author/mr ... Pack_1.zip](http://www.xentax.com/uploads/author/mrmouse/MexCom_Language_Pack_1.zip)

```
=================================
2nd of august 2007

Installation:
-------------
Browse to the installation directory of MultiEx Commander (e.g. c:\program files\multiex commander)
and start install! 

This contains the following files:

data\eul\English.txt	
data\eul\Magyar.txt	
data\eul\Nederlands.txt	
data\languages\Deutsch.txt	
data\languages\English.txt	
data\languages\Français.txt	
data\languages\Magyar.txt	
data\languages\Nederlands.txt	
data\languages\Èeština.txt

Please note that we need the French, German and Hungarian translations of the End User License!

If you feel up to it, contact me at the forum (http://forum.xentax.com) and I'll 
include it in the next Pack and MultiEx Commander. 

Warm thanks to: 

David Kramoliš ("kramla") for the Installer tip and Czech translation
Sziládi Zsolt for the Hungarian translation
Deniz Oezmen for the German translation 
Bhp_Designs for the French Translation


Should you think the translations need a bit of tweaking, don't hesitate to drop in 
and pose your suggestions at the forum as well. 

Have fun !

Mike Zuurman AKA Mr.Mouse
http://www.xentax.com 

```
## Post #39
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2007-08-02T09:48:50+00:00
- Post Title: 

nice work Mr Mouse.
Any news on support for unicode characters. As im still up for translating it to japanese.
Only a hour or so work really.
## Post #40
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-02T10:53:24+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Please note that we need the French, German and Hungarian translations of the End User License!
[You rang?](http://www.xentax.com/uploads/author/denizoezmen/eul_german.zip) 

Please note that I cannot guarantee that this translation is identical to the English version from a legal point of view (or legally valid in any respect); it might say something different than you originally intended.

Generally speaking, it might be a good idea to add a line to the translated licenses stating that the translations are merely presented as (not necessarily correct) conveniences for the user, but the English original (or whichever you choose) stays the legally binding document -- just like gnu.org does for their licenses.
## Post #41
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-08-02T11:42:48+00:00
- Post Title: 

GREAT! Updated the installer to 1.1 (and the readme too!  ) 

And you are right about just one be "legally" binding.
## Post #42
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-08-02T21:34:49+00:00
- Post Title: 

*sigh* I'm really gonna have to get back to work on the Spanish file... Don't expect a EULA from me, my translation would probably make any native speaker die laughing...
## Post #43
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-02T21:45:53+00:00
- Post Title: 

> Reply from Dinoguy1000
>
> Don't expect a EULA from me, my translation would probably make any native speaker die laughing...
I think that's a characteristic trait of legal texts anyway ...
## Post #44
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-08-02T22:42:09+00:00
- Post Title: 

I dunno, they usually just put me to sleep with a killer headache (anyone got an Aspirin?)...
## Post #45
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-08-03T05:40:35+00:00
- Post Title: 

LOL@both
## Post #46
- Username: Carlos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Aug 07, 2007 12:05 pm
- Post datetime: 2007-08-07T21:24:45+00:00
- Post Title: Spanish translate full

Hello, here is my version of Spanish translate.

Hope you can use it.

Grettings from Uruguay.

Carlos Arbizu
[Spanish.rar](https://xentaxbackup.github.io/file/1305_Spanish.rar)
## Post #47
- Username: Carlos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Aug 07, 2007 12:05 pm
- Post datetime: 2007-08-08T00:14:54+00:00
- Post Title: Spanish translate full

It's very dificult to translate in this way:

The size of the buttons is very small.

In english you say: Set Base (that's small)
In spanish we say: Configurar Base (almost the double).

Try to make the size of buttons variable depends its contents (it's no easy I know).

Other way is make the buttons bigger independent of the content.

Another thing, some words in the program has no translate for example in the tools menu the last item "Scan file" doesn't appear in the english text.

And the last, try to put all the text in one single file (aknowledgments, info for developers and eul), because it's more easy to edit all in one single file that three or four.

I want to offer my time as a crontibution to the project.
If you like, send me by mail the RTF Help file and I'll try to translate it.

Thanks.

Carlos Arbizu
## Post #48
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-08-08T06:26:58+00:00
- Post Title: Spanish translate full

Hey Carlos! Thank you very much !! I know some of the problems with the size of the buttons, and some things not translated. I will try to fix them in the current release. Content-dependent size is possible, but boring work  I will see if I can get the layout so that the buttons get a little larger overall. 

Do you have a registration key for MultiEx Commander? If not, I'll send you one. This will also enable you to see other options (that may need translation). 

Thanks again! Are you also doing the EUL?
## Post #49
- Username: Carlos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Aug 07, 2007 12:05 pm
- Post datetime: 2007-08-09T00:03:15+00:00
- Post Title: Spanish translate full

I know that make buttons variable it's a hard work, but the oher way it's so easy (make the buttons bigger) to acept all words large for others languages.

If you can send me the registration key, that's wonderfull.

Would you like I try to translate the others three files (eul, aknowdlegements, and info for developers)?

If you answer yes, I'll try to do these files. OK?

Oh, congratulations, it's an excelent software.

Carlos 

> Reply from Mr.Mouse
>
> Hey Carlos! Thank you very much !! I know some of the problems with the size of the buttons, and some things not translated. I will try to fix them in the current release. Content-dependent size is possible, but boring work  I will see if I can get the layout so that the buttons get a little larger overall. 

Do you have a registration key for MultiEx Commander? If not, I'll send you one. This will also enable you to see other options (that may need translation). 

Thanks again! Are you also doing the EUL?
## Post #50
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-08-09T16:23:17+00:00
- Post Title: Spanish translate full

Well, you seem to have beat me to the punch, Carlos! Excellent work.
## Post #51
- Username: Carlos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Aug 07, 2007 12:05 pm
- Post datetime: 2007-08-10T00:56:19+00:00
- Post Title: Spanish translate full

Here is the Spanish eul.

Hope you enjoy it.
[Spanish eul.rar](https://xentaxbackup.github.io/file/1311_Spanish eul.rar)
## Post #52
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-08-10T07:50:16+00:00
- Post Title: Spanish translate full

Allright, updated the MultiEx Commander language pack to 1.2 inlcuding now also the Spanish translation. 

[http://www.xentax.com/uploads/author/mr ... Pack_1.zip](http://www.xentax.com/uploads/author/mrmouse/MexCom_Language_Pack_1.zip)
## Post #53
- Username: Carlos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Aug 07, 2007 12:05 pm
- Post datetime: 2007-08-11T20:18:23+00:00
- Post Title: Spanish translate full

It's a great honor to be frind of Multiex.

Thanks a lot.

One question. How to translate the MexBinderPlus?
It hasn't a text file.

It's necessary to translate the strings inside the program?

Thanks again.

Carlos
## Post #54
- Username: kramla
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Jul 15, 2007 11:27 pm
- Post datetime: 2008-12-25T22:43:37+00:00
- Post Title: Spanish translate full

Hi guys,

I made new version of the Czech translation, i made same corrections and i added eula.
Here is install program

```
http://rapidshare.com/files/176777678/MultiEx_Commander_CZ.exe.html
```

and here are only translated files 

```
http://rapidshare.com/files/176778043/data.rar.html
```


Kramla
## Post #55
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-26T12:14:19+00:00
- Post Title: Spanish translate full

hm, on first page i read that someone was gonna translate to swedish. Has i been done? I can help if you haven't gotten any input.
## Post #56
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-12-26T14:12:56+00:00
- Post Title: Spanish translate full

No , there's no Swedish version as yet. That would be nice!
## Post #57
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-26T18:03:56+00:00
- Post Title: Spanish translate full

ok, i'll do it after new years celebrations are over
