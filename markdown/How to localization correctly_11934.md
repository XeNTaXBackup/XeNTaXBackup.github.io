## Post #1
- Username: MMM
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 11, 2014 8:09 pm
- Post datetime: 2014-09-11T13:00:03+00:00
- Post Title: How to localization correctly?

Hi

I want to localization a game called Lucius
so I just edit subtitles_en.xml with notepad++
unfortunately the localization didn't show up correctly, 
the localization show up as question marks
I tried to change the encoding from notepad++ but nothing changed.

what is the solution?

p.s it's my first time to try to localization a game   

thanks
## Post #2
- Username: basil
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Mar 29, 2010 3:00 am
- Post datetime: 2014-09-11T16:12:27+00:00
- Post Title: How to localization correctly?

What language are you translating to? And what Notepad encodings have you tried? If you replace text with English words, do the new English words appear correctly?

This is a complete shot in the dark, but you could try launching Lucius with [AppLocale](http://en.wikipedia.org/wiki/AppLocale), a free program by Microsoft. (You might have to search Google for help if you are running Applocale on Windows 7 or 8.)
## Post #3
- Username: MMM
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 11, 2014 8:09 pm
- Post datetime: 2014-09-12T07:13:21+00:00
- Post Title: How to localization correctly?

I'm trying to translate the game to Arabic,
I tried encode in ANSI, UTF-8, UCS-2 Little Endian 
and character sets > Arabic > (ISO, OEM & Windows)

Yes when I replace English word with new English word it appear correctly.

AppLocale didn't change anything,
the Arabic words still show up as question marks.

I also tried Wanted: Weapons of Fate and it has the same problem.

thanks
## Post #4
- Username: basil
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Mar 29, 2010 3:00 am
- Post datetime: 2014-09-12T08:17:33+00:00
- Post Title: How to localization correctly?

Here, try this. (I can't tell if you tried this specific combination yet.)

> 1. Encode your text with "code page 1256" or "windows 1256" or something similar. If it's not there, encode with Arabic -> Windows.
>
> 2. Run in Applocale with Arabic. If there is more than one Arabic choice, try all of them.

P.S. At the top of the XML file, does it mention encoding?
## Post #5
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-09-12T09:10:34+00:00
- Post Title: How to localization correctly?

The question is: Does that games contains arabic fonts? Probably not, so you have to make them.
## Post #6
- Username: ZORROSYR
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 02, 2014 9:35 pm
- Post datetime: 2014-09-12T09:15:48+00:00
- Post Title: How to localization correctly?

First at any game localize you have to find the system game font , i mean you have to find the game font and edit it with add your charecter . then easy to continue with your game .
## Post #7
- Username: basil
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Mar 29, 2010 3:00 am
- Post datetime: 2014-09-12T09:27:02+00:00
- Post Title: How to localization correctly?

Ah, that's right. If you want to see an example, [this person wants to translate Sniper Elite 3 to Arabic](http://forum.xentax.com/viewtopic.php?f=35&t=11924).

Can you post a screenshot of the game with text, any text? I want to see something...

(Hmm, I just realized... what about right-to-left reading order, how will that work?)
## Post #8
- Username: MMM
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 11, 2014 8:09 pm
- Post datetime: 2014-09-12T10:43:31+00:00
- Post Title: How to localization correctly?

do you mean character sets > Arabic > windows 1256 ?
because I already did that and I tried it now with Applocale as Arabic 
( there is only one option for Arabic ) nothing changed.

I know nothing about fonts, 
and no there is no option to change the font, 
but anyway those are the pics from Lucius in-game:

Lucius Options

[http://i.imgur.com/OgzqWN0.jpg](http://i.imgur.com/OgzqWN0.jpg)

English (default)

[http://i.imgur.com/MUyXNxj.jpg](http://i.imgur.com/MUyXNxj.jpg)

Arabic

[http://i.imgur.com/ixbglOt.jpg](http://i.imgur.com/ixbglOt.jpg)


Lucius XML file:

<?xml version="1.0"?>

I didn't change anything.

Wanted: Weapons of Fate XML file:

<?xml version='1.0' encoding='UTF-8'?>

I tried to change the encoding in Wanted XML file,
but when I change it the game crash at start up.

thanks
## Post #9
- Username: basil
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Mar 29, 2010 3:00 am
- Post datetime: 2014-09-12T12:04:49+00:00
- Post Title: How to localization correctly?

Okay... so we're done with Applocale now, and let's forget about "encoding=". Time for Plan B.

Basically you want to figure out in which file the font graphics are stored. Are you new to this part? Finding files like this is more of an art than a science. See if you can figure it out from the filenames and extensions. If you don't recognize a file extension, try doing a search on it.
## Post #10
- Username: MMM
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 11, 2014 8:09 pm
- Post datetime: 2014-09-14T12:33:49+00:00
- Post Title: How to localization correctly?

I found a folder called fonts:

[http://i.imgur.com/kAnCrkm.jpg](http://i.imgur.com/kAnCrkm.jpg)

what should I do ?

thanks
## Post #11
- Username: basil
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Mar 29, 2010 3:00 am
- Post datetime: 2014-09-15T00:18:33+00:00
- Post Title: How to localization correctly?

Yes, those looks like font files  Since you played this game, do you have any idea which fonts are used where, judging by the filenames alone?

Anyway, the way usually I do this is (1) open files with known extensions, (2) research unknown file extensions, and (3) try using a hex editor.

(1) I see a few .png files. Your computer should be able to open those. If you're lucky, they will contain letter graphics. Or maybe not...

(2) I also see .font files and .txds files. If you're lucky, there may be information out there about these file types. You can do an Internet search for ".???? file format" or ".???? file extension".
(If you're really lucky, you may find a program that can open and edit the file for you. But not always. Be careful so you don't download a virus program!)

(3) Did you ever use a hex editor before? There's a good, reliable hex editor called XVI32, you can download it for free. Here, let's try this: open a couple unknown files in XVI32 and take a screenshot of the very beginning.
## Post #12
- Username: MMM
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 11, 2014 8:09 pm
- Post datetime: 2014-09-17T10:33:45+00:00
- Post Title: How to localization correctly?

Arial32.font

[http://i.imgur.com/6AXqu7k.jpg](http://i.imgur.com/6AXqu7k.jpg)

Arial32.png

[http://i.imgur.com/u3EoGAF.png](http://i.imgur.com/u3EoGAF.png)

darylshort.txds

[http://i.imgur.com/8Llfbrw.jpg](http://i.imgur.com/8Llfbrw.jpg)
## Post #13
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-09-17T16:17:59+00:00
- Post Title: How to localization correctly?

I made a QBMS script which will separate font description (eh, I hope it's a description) and texture from .font files. 

```
# by MerlinSVK    	Sep 2014
# script for QuickBMS   http://aluigi.org/papers.htm#quickbms

set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\x00\x00\x80\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
get NAME basename
string DNAME = NAME
string TNAME = NAME
string DNAME += ".desc"
string TNAME += ".dds"

get FSIZE asize

findLoc OFFSET string "GFX"
if OFFSET == ""
 print "This file does not contain texture!"
 cleanexit
endif

log DNAME 0 OFFSET		# save description part of file

math OFFSET += 0x4
goto OFFSET
get UNK byte			# no idea

# ---- texture size calculation -----
math FSIZE -= OFFSET	# file size minus description part
if UNK == 0x2
	math FSIZE -= 0x12	# minus size of the custom texture header; result = size of texture
	get NULL byte
else
	math FSIZE -= 0x14
endif
# ---- texture size calculation -----

get WIDTH long
get HEIGHT long
savepos OFFSET
if UNK == 0x2
	math OFFSET += 0x8
else
	math OFFSET += 0x7
endif

putVarChr MEMORY_FILE 0xc HEIGHT long
putVarChr MEMORY_FILE 0x10 WIDTH long

append
log MEMORY_FILE OFFSET FSIZE
append

get TEXSZ asize MEMORY_FILE
log TNAME 0 TEXSZ MEMORY_FILE

```


Every .font file will be separated into .desc and .dds texture. 
I have only few .font files, so the script might not work for all of them.
