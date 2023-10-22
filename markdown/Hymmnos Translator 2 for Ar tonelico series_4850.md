## Post #1
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2010-08-05T22:10:00+00:00
- Post Title: Hymmnos Translator 2 for Ar tonelico series

Hymmnos Translator 2
Hello again everyone. This will be my second major contribution here. About 1.25 years ago I worked on a program that could translate the Hymmnos language from the Ar tonelico series. My coding skills were somewhat limited, and the way I organized the database was just... silly. Anyway, I learned a lot coding the TMX explorer and I noticed that people are STILL downloading my WAY OUTDATED Hymmnos translator, and that my original post is the FIRST LINK on Google for the query "hymmnos translator" and the 5th for "hymmnos translation." Now I will readily admit that version that nearly 200 people have downloaded is OLD, and while the features are good, the code is bad, the database is epically outdated, etc. So, since people seem to want to use it, I decided to do it up and see what I could come up with.

Originally I had manually typed up a database based on the information at [http://conlang.wikia.com/wiki/Hymmnos](http://conlang.wikia.com/wiki/Hymmnos) and it took literally forever. Now, since their table that contains the translations of the Hymmnos language is far bigger than a year ago, I was dreading that. But then I wondered to myself if I could write a small bit of code to parse the wikisource of that page directly into a database, organizing as it goes. Obviously wikisource is parsable, and this turned out to be quite easy. So for anyone familiar with the old version, these are the changes:

-Hymmnos database is now ripped from the wikisource of [http://conlang.wikia.com/wiki/Hymmnos](http://conlang.wikia.com/wiki/Hymmnos) by opening the source to edit, pasting the table into a DAT, and running my parser. It is very easy to update this way.

-Database loading and updating routines are entirely rewritten to be more efficient and less sketchy.

-The screen will no longer "flash" randomly, and the cpu usage is greatly diminished, all because I moved a "SLEEP" command.    I was trying to figure that out forever.

-For anyone in the source, the variables are much more sanely named(mostly) and the commenting is updated.
Features:
All features and functionality of the original program are intact and the same:
Basically I changed the engine of the machine, not it's exterior.

This is the information from my original post a year ago, as it is still valid (slightly edited):

1- You can type in any single Hymmnos word in the database and receive an entry for it which contains the part of speech, possible English translations of the word, what dialect it is from, and the word printed in the Hymmnos TTF.

2- You can type in a Hymmnos phrase and the application will try to translate it. This is where most of the coolness lies:

a. The translated text is displayed in romanized Hymmnos, Hymmnos TTF and translated English.

b. There is basic syntax highlighting (more to come).

c. With your translation results on screen, you can cycle through the various possible translations for each word. Just pick the word with the left and right arrows, and cycle through the known translations with up or down.

d. You can modify the translation of any word, or add your own new translation for it. You can do this by highlighting the word, picking which translation definition you want to alter (or NEW to add a new result to the existing ones). Once you've got it highlighted just start typing. When you are finished press ENTER. Then when you exit the phrase with SPACE the new information will be saved in the "Hymmnos Database Override Rules.dat" file, which contains all your changes. This way the actual wiki database itself is not modified. If you don't like your changes you can exit the phrase with ESC, which will discard your changes.

e. Hymmnos "rules" are applied to the resultant English text. This part is not complete yet but the parts that are work well. For instance, the rule for "re" basically works by adding either "d" or "ed" to the word after "re" depending on the last letter of said word. Words that have special past tense forms would get funny of course, e.g. "re heighte" could translate "hurted", even though the past tense of the verb hurt is still hurt. E.g. "I will hurt him tomorrow." "I hurt him yesterday." In the future I may make a list of special cases so that won't happen. "Rre" is implemented by simply making an arrow pointing to the subject. In the future once full syntax highlighting is implemented, it will make the subject highlight in the appropriate color.

Updates to come:
I can speak and compose "broken" Hymmnos, I am not a master by any means but I do know that many of my machine translations are wrong. There is often problems in subject verb order and tenses etc. I am going to manually update the Override Rules database to correct some of this this.

I want the application to remember your choices, giving precedence to your custom entries and/or whichever translation you decided was "best" for a particular word. This is not hard to code, but I am very tired, I have been working on this 6 hours haha.

Big question(figuratively and literally:)
Does anyone here speak Hymmnos better than me?
I am looking for someone who can help me understand the Binasphere rules so I can incorporate that into the application.


Final notes:
Credits - This application was written in FreeBASIC by me, except for the Freetype header to implement the Hymmnos font. That was written by Thorham of the FreeBASIC forum.
zlib code Copyright (C) 1995-2005 Jean-loup Gailly and Mark Adler
Portions of this software are copyright © <2009> The FreeTypeProject ([http://www.freetype.org](http://www.freetype.org)).  All rights reserved.
All contributors to the Conlang: Hymmnos.
My good friend Xaio, for getting me into this series.

Disclaimer - This application is provided as is, without any warranty of any kind, including the implied ones of merchantability or fitness for a particular purpose. Use of this application is entirely at your own risk.

License -
[http://myriaddreams.com/index.php?optio ... 4&Itemid=9](http://myriaddreams.com/index.php?option=com_content&view=article&id=4&Itemid=9)

Screenshot:


Download
http://myriaddreams.com/projects/applic ... ator_2.zip


I guess my file is too big to be an attachment   

~Was yea erra haf revm innna mea
~Blyss
## Post #2
- Username: OverLordAyame
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 03, 2011 10:10 pm
- Post datetime: 2011-12-03T14:17:35+00:00
- Post Title: Hymmnos Translator 2 for Ar tonelico series

Thank you for making this!!!!

Ummm...the window when its not full screen is a bit big is it possible to adjust it?

and is it possible to translate Eng to Hymmos yet?
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-12-04T09:00:51+00:00
- Post Title: Hymmnos Translator 2 for Ar tonelico series

I have no idea what Hymmnos is, but it looks good.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-10-12T21:01:57+00:00
- Post Title: Hymmnos Translator 2 for Ar tonelico series

Does anyone still have this file? Blyss seems to have disappeared and his website is down.
## Post #5
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2013-07-08T02:50:31+00:00
- Post Title: Hymmnos Translator 2 for Ar tonelico series

Been a while and googled my signature text and found this. I lost a lot of data when I lost my website and my pc and laptop. This was part of it, I've been messaged a couple of times about the tmx explorer where people hunted nee down but as for this I'm afraid it's gone forever unless I ever pay for data recovery.
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2013-07-08T06:10:14+00:00
- Post Title: Hymmnos Translator 2 for Ar tonelico series

Ok, thanks for letting us know. Are you aware of any sites that used to offer it for download?
## Post #7
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2013-11-11T03:56:05+00:00
- Post Title: Hymmnos Translator 2 for Ar tonelico series

I actually discovered this in my mediafire folder!

[http://www.mediafire.com/download/msxqm ... ator+2.zip](http://www.mediafire.com/download/msxqmef3atdwstw/Hymmnos+Translator+2.zip)

So yay, it still exists!
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2013-11-11T21:51:49+00:00
- Post Title: Hymmnos Translator 2 for Ar tonelico series

> Reply from Blyss
>
> I actually discovered this in my mediafire folder!

http://www.mediafire.com/download/msxqm ... ator+2.zip

So yay, it still exists!

INCREDIBLE!

          
          


Then this is now complete! [blog/?p=177](http://forum.xentax.com/blog/?p=177)
