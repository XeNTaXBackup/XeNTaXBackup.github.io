## Post #1
- Username: neoen
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Oct 15, 2008 6:34 pm
- Post datetime: 2008-12-17T11:26:18+00:00
- Post Title: Telltale and Gametap - extract to translate

Hello,

do you know about any tool which could manage to translate text in following adventure series:

[http://www.gametap.com/grimm/](http://www.gametap.com/grimm/)

[http://www.telltalegames.com/](http://www.telltalegames.com/) (Strong Bad, Sam and Max)

Or is there anybody who could try to find text in these games?

Thank you very much.
## Post #2
- Username: Xino
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Dec 21, 2008 1:26 am
- Post datetime: 2008-12-25T13:27:15+00:00
- Post Title: Telltale and Gametap - extract to translate

Post the games filelists
## Post #3
- Username: neoen
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Oct 15, 2008 6:34 pm
- Post datetime: 2009-05-07T21:21:15+00:00
- Post Title: Telltale and Gametap - extract to translate

There is new game from TellTale. Any chance that anybody could extract it (and find translation)?

Thank you very much...

Demo: [http://www.telltalegames.com/wallaceandgromit](http://www.telltalegames.com/wallaceandgromit)
## Post #4
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-05-08T08:20:12+00:00
- Post Title: Telltale and Gametap - extract to translate

GameTap data is encrypted filesystem of original game data, I wouldn't bother. For non-GameTap data, I'll take a look within a week or two (I have a few TellTale games on Steam).
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-08T16:27:46+00:00
- Post Title: Telltale and Gametap - extract to translate

I have figured the algorithm and partially the file format (the folder names exist but don't seem used, mah).
practically it works like an encrypted and compressed file system composed by chunks of 65536 bytes encrypted with blowfish and the key "\x96\xCA\x99\xA0\x85\xCF\x98\x8A\xE4\xDB\xE2\xCD\xA6\xA9\xB8\xC4\xD8\x81\x8E\xE3\xA9\xD6\x99\xD4\xAC\x93\xDE\xC2\xA2\xE0\xA5\x99\xCC\xB4\x89\xB0\xCD\xCF\x9A\xCF\xDA\xBB\xEA\xDB\xA4\x9B\xC6\xB3\xAA\xD0\x95\x8A\xD1\xDE\xAB".

although it's not a so nice format to handle with a script (the best solution in this case is a stand-alone extractor) I have found a way for using QuickBMS with it, I will release the script tomorrow with a new version of the tool.
anyway it's necessary to test other games for making the script compatible with any other game which supports the TTARCH format (I guess that the first thing which changes is the blowfish key)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-09T15:20:53+00:00
- Post Title: Telltale and Gametap - extract to translate

released script and new version of QuickBMS (necessary):
[http://aluigi.org/papers/bms/ttarch.bms](http://aluigi.org/papers/bms/ttarch.bms)
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)

each game uses a different key for the blowfish encryption so the script must be edited manually for specifying the correct key.
I downloaded some demos and collected their keys (don't worry it's just a matter of some seconds):
. Episode 4 - Daneresque 3
. Wallace & Gromit: Grand Adventure
. Out From Boneville
. Telltale Texas Hold'em
. Sam & Max: Episode 205 - What's New, Beelzebub
. Sam & Max: Episode 101 - Culture Shock
. Episode 2 - Strong Badia the Free
. Sam & Max: Episode 103 - The Mole, The Mob, and the Meatball
. Homestar: Episode 5 - 8-Bit Is Enough
. Sam & Max: Episode 201 - Ice Station Santa
. CSI-Hard Evidence

the script supports various versions and types of name tables and files.
hope it helps.
## Post #7
- Username: neoen
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Oct 15, 2008 6:34 pm
- Post datetime: 2009-05-09T16:26:17+00:00
- Post Title: Telltale and Gametap - extract to translate

Great. Thank you very much! I will test it and try to find files with text...
## Post #8
- Username: neoen
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Oct 15, 2008 6:34 pm
- Post datetime: 2009-05-09T20:30:17+00:00
- Post Title: Telltale and Gametap - extract to translate

BMS script works perfectly!

I tried Sam and Max 101 and found some files which could contain text for translation.
But these files are probably compiled or encrypted. I did not find the way to handle them.

I know that it is not probably problem of extraction, but there were tools to translate these games. Do you have anybody any ideas?

There is old Telltale LangDB Editor (does not work with this game) - [http://quick.mixnmojo.com/readmes/Tellt ... ditor.html](http://quick.mixnmojo.com/readmes/TelltaleLangDBEditor.html)

And is it possible to re-create .ttarch file? There was also old tool - [http://quick.mixnmojo.com/readmes/Tellt ... eator.html](http://quick.mixnmojo.com/readmes/TelltaleTtarchCreator.html)

Thank you very much for your help...
[english.zip](https://xentaxbackup.github.io/file/2019_english.zip)
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-09T20:50:30+00:00
- Post Title: Telltale and Gametap - extract to translate

eh no, unfortunately was an error of mine in the script.
I have updated the [script](http://aluigi.org/papers/bms/ttarch.bms) immediately (note the version 0.1.1 in it), sorry
## Post #10
- Username: neoen
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Oct 15, 2008 6:34 pm
- Post datetime: 2009-05-10T08:55:38+00:00
- Post Title: Telltale and Gametap - extract to translate

Thank you very much, now I can see text strings in .langdb file.

Is it possible to simply edit .langdb file?
Is it possible to re-create .ttarch archive?

There were old tools, but they do not support newest games. I think that there is problem with different key for the blowfish encryption.

Also after extraction, maybe different extracted files should be stored in different subdirectories (I thought it in some files), like "include", etc?

Thank you very much for you help...
[english.zip](https://xentaxbackup.github.io/file/2023_english.zip)
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-10T10:37:51+00:00
- Post Title: Telltale and Gametap - extract to translate

I can't help with the rebuilding or the editing of the extracted files

*EDIT*: note that the ttarch.bms script is still a work-in-progress so are needed beta testers who report ANY error!
## Post #12
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2009-07-08T13:28:02+00:00
- Post Title: Telltale and Gametap - extract to translate

cool thx for the bms script any key for  Tales Of Monkey Island - Chapter 1 : Launch Of The Screaming Narwhal, the demo (189Mo) is out, any lucky for a update of bms script ?
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-08T16:36:20+00:00
- Post Title: Telltale and Gametap - extract to translate

that bms script was only a beta experiment, now the complete project is called ttarchext:

[http://aluigi.org/papers.htm#ttarchext](http://aluigi.org/papers.htm#ttarchext)

in the new 0.1.2 version I have added support for the new format used in Tales of Monkey Island (version 7, a customized blowfish encryption) just after its release this night :)
## Post #14
- Username: neoen
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Oct 15, 2008 6:34 pm
- Post datetime: 2009-07-08T20:21:46+00:00
- Post Title: Telltale and Gametap - extract to translate

Did you somebody manage to make a translation?

When you extract any game, there is english.langdb file. I can see english sentences in this file, but I was not successfull in preparing any tool to translate and use these texts. There were LangDB Editor, but it is outdated for new games. And it should not be hard task, because texts are visible for example in TC...

Could you please test it somebody?
## Post #15
- Username: oiakiller
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2009 8:36 am
- Post datetime: 2009-07-17T23:32:55+00:00
- Post Title: Telltale and Gametap - extract to translate

Sorry reborn this topic


Hi, I am from a group that is translating the Season 1 and 2 of Sam & Max. We already make the translation but we don't know how to recreate the .TTARCH with the translation. I tried with the TTARCH CREATOR but doesn't work. Can somebody help us? We have a lot of work, just need to do only one thing to release the translation. 

Sorry about the english

Thanks...(From Brazil)
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-18T22:10:45+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

released version 0.1.3 which is able to rebuild the ttarch archives:

[http://aluigi.org/papers.htm#ttarchext](http://aluigi.org/papers.htm#ttarchext)

if I'm not in error sam&max use version 4 (you can verify it when you extract or list the original archive) so try the following example command-line:

  ttarchext.exe -b -V 4 6 c:\output.ttarch c:\input_folder

obviously 6 is the key of "Culture Shock" so use the one of the game you have modified.
let me know if everything it's ok, in my tests I have rebuilt completely all the archives of monkey island and the game worked perfectly.
## Post #17
- Username: neoen
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Oct 15, 2008 6:34 pm
- Post datetime: 2009-07-19T19:08:31+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Could you please look at attached .langdb file?
This file is for translation, but it is not simple text file. Do you have any idea to translate it in the best way. It reminds me some database file, but I am not sure... Any idea? Thank you very much...
[english.zip](https://xentaxbackup.github.io/file/2207_english.zip)
## Post #18
- Username: oiakiller
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2009 8:36 am
- Post datetime: 2009-07-19T19:31:38+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Thx, i'm going to test.

I will post the results

Edit: It's not working, when i click play the game, shows a message sayng thats a DLL error
[DLL.JPG](https://xentaxbackup.github.io/file/2209_DLL.JPG)
## Post #19
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-20T02:12:12+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

yeah this game crashes with the rebuilt archive.
I have already performed some tests in this moment without finding the cause so tomorrow I will take a look again to the info_table because there is additional data at its end
## Post #20
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-20T10:32:12+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

released version 0.1.4
this version is important also because there was a bug in the extraction where some rare files were corrupted in their last bytes, so remember to update.
## Post #21
- Username: oiakiller
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2009 8:36 am
- Post datetime: 2009-07-20T14:31:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Thanks, i will try and post the results
## Post #22
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-07-20T20:44:02+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

From Telltale Games I had only the new Monkey Island Part

And I try to extract an rebuilt it
and everything work perfect after the rebuilt

Now I try to edit the langdb ^^
Let see what can be done.

good work "Bugtest"

regards Shippuuden
## Post #23
- Username: oiakiller
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2009 8:36 am
- Post datetime: 2009-07-20T20:50:18+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Bugtest - The extract and rebuild works great! 

But I'm having problems when I moddified the .Langdb

Now I just need to find a program to moddifie. 

Thanks very much for the TTARCHEXT


THE TRANSLATIONS WORKS GOOD!!!!!!!!!!!!! TO TRANSLATE JUST NEED TO EDIT WITH A TEXT EDITO!!!

IMAGES: (PT-BR)






THANKS VERY VERY MUCH "BUGTEST"
## Post #24
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-07-21T00:05:36+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Ohh, thats good news "oiakiller"
I will try tomorrow a bit with the "langdb"

@Bugtest
Is it possible to convert the (with -m extracted) ".dds" graphic files back to ".D3DTX"
(Or other way round)
Maybe so,
Is it possible to convert the (with -o extracted) "D3DTX" graphic files to ".dds" and then back (after editing)

There just a few pics, I want to edit
(In the Menu from MI)
And of course, I want to tinker a bit ^^

Yours sincerely
Shippuuden
## Post #25
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-21T02:19:31+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

the problem of the files (d3dtx, aud and lenc) handled with the -m option is that doesn't "seem" to exist a relation between them and the format of the file or the version of the ttarch archive or other things (lenc excluded which are simply encrypted completely and ever).
practically in the same ttarch file you could find 2 d3dtx files of which one has the first 0x800 bytes encrypted and the other which is clear.
then the d3dtx/aud formats are not known so the -m option does only a simple "search&dump" job, which is the only solution for viewing these files.

obviously I'm talking about the classical and automatic usage of ttarchext because you can do what you want performing some manual operations.

if you have a d3dtx file which is called (for example) launchmenu.d3dtx and you want to modify it you can do the following:

extract only that file using the -m option in another folder
Code: Select allttarchext -f launchmenu.d3dtx -m 24 narwhal.ttarch c:\
now take the launchmenu.d3dtx you extracted the first time and cut all the data after the header.
for example if launchmenu.d3dtx is 14000 bytes and launchmenu.dds is 13500 you must remove the last 13500 bytes from the d3dtx one which will have a result size of 500 bytes
edit launchmenu.dds as you want with the only requirement of not modifying its size which must be the same of the original launchmenu.dds before your modifications because I don't know if it could give problems to the game
now append the content of launchmenu.dds to launchmenu.d3dtx using the following command:
Code: Select allcopy /b launchmenu.d3dtx + launchmenu.dds + launchmenu.d3dtx
now your d3dtx file is complete and ready for being reimported.
and don't worry, it looks more complex than how it is :)
## Post #26
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-21T08:27:00+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

oh, I forgot to say that if the d3dtx contains the dds with its first 0x800 bytes encrypted (you need a hex editor to verify it) you need to perform this additional cut+encrypt operation which could be boring.
## Post #27
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-07-21T15:13:11+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I got it ^^

Its possible to change some pics ^^
I try it first with the Menu of MI (text on the right "the game title")
and there it work perfect

With Charakter or Obkekt textures, (Ingame)
I doesn't try it yet

@Bugtest
Why actually the rebuilted ".ttrach" so huge ?
The original such one third of then
Its undisturbing, but why this happend ?

Yours sincerely
Shippuuden
## Post #28
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-21T16:19:27+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

the reason is simple.
in a couple of the MI ttarch archives it's used the compression and so they are smaller while in my rebuilder I supported only the clean method because it's retro-compatible with any older game and it's easier to implement.

if you have problems with the editing of the images just let me know it but I guess that the problems are only those with the 0x800 bytes encryption which are more boring to handle and, luckily, MI doesn't seem to use them :)
## Post #29
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-21T16:37:11+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

IMPORTANT good news :)

is NOT needed to rebuild the whole ttarch archive but is enough to build a new one called 0.ttarch containing ONLY the files which have been changed.

for example I have extracted button_launch_launchdemo.png (the "Launch free demo!" image) from 0_monkeyisland101_pc_launcheronly.ttarch, I have edited it, I have built a new 0.ttarch archive containing only this file and now the game shows my changed image when it runs instead of the original one.

I know that this thing was enough obvious but, in case someone didn't know it, I hope it's useful
## Post #30
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-07-21T17:34:02+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Thats cool and really helpful

I try it with an edited langdb and a edited d3dtx file at once "0.ttrach" archive

And it works perfect
Thats really cool ^^

Thanks "Bugtest"

Did you know why the game prefer the content from the "0.ttrach" ?


Yours sincerely
Shippuuden
## Post #31
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-21T18:04:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I "guess" the priority is given by the filename and so 0.ttarch is read before 0_monkeyisland101_pc_launcheronly.ttarch.
indeed initially I called it 5.ttarch and it didn't work
## Post #32
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-07-21T20:01:39+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Normally I would thought that the first readed files into the "0.ttrach" would be overwrite by the afterwards readed archive like "4_MonkeyIsland101_pc_tx.ttarch" !??!

But it works with "0.ttrach", so its indifferent for me ^^



Yours sincerely
Shippuuden
## Post #33
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-07-23T15:27:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

And how to edit weathered_sf_30.font?
## Post #34
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2009-07-23T16:05:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Normally in Telltale games, the font files are similar to the DXTC files, in that they are dds images with an additional header.
Assuming this is still the case for TMI (I haven't checked) you should be able to use a hex editor to extract the dds, edit it and put it back.
## Post #35
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-07-23T16:08:57+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from bgbennyboy
>
> Normally in Telltale games, the font files are similar to the DXTC files, in that they are dds images with an additional header.
Assuming this is still the case for TMI (I haven't checked) you should be able to use a hex editor to extract the dds, edit it and put it back.
I think its not dxtc file.
[weathered_sf_30.rar](https://xentaxbackup.github.io/file/2224_weathered_sf_30.rar)
## Post #36
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2009-07-23T16:50:09+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

The DDS header is at offset 5343 in that file.
## Post #37
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-07-23T17:01:57+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from bgbennyboy
>
> The DDS header is at offset 5343 in that file.
Thanks.
## Post #38
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-07-23T18:57:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

So,
I try it too

I'm German and we need seven letters more (Ä,Ü,Ö,ä,ü,ö.ß) 

To find out 	which symbol from the .dds would read for the german special letter I edit the ".dds" with collored signs
[](http://img403.imageshack.us/img403/3103/letterp.gif)

So far so good,
I convert it back to the ".ttrach" archive, but all german letters (of course different letter, that I changed at the langdb file) was ALL show like the edited 1 from the ".dds" file (Ingame)

Someone ne Idee ?

The Hex-Code for the letters are:
C4 = Ä (A with dots)
E4 = ä (a with dots)
DC = Ü (U with dots)
FC =ü (u with dots)
D6 =Ö (O with dots)
F6 = ö (o with dots)
DF = ß (spezial letter called "ES-ZET")

If someone know the HEX-Code for the other edited signs (place at the .dds graphic)
Please tell me ^^
Then I can use this place for the German letters

EDIT:
-----------------------------
I got it
remember to myself, first use your mind ^^

So, here is the Code
based on the edited pic

pic sign = hex-code

1 = shows ingame if a unknown Hex-Code at the langdb was found
2 = 5B
3 = 5C
4 = 5D
5 = 7B
6 = 7C
7 = 7D
8 = 7F
9 = 80
a = 81
b = 84
c = 85
d = 86
e = 87
f = 89
g = 8A
h = 8.D (No dot between, but else the forum make a smile out of then "  ")
i = 8E
j = 8F
k = 90
l = 95
m = 9A
n = 9D
o = 9E
p = A4
q = A6
r = A7

Yours sincerely
Shippuuden
## Post #39
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-07-24T21:32:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

NEXT Problem   

Its just a blemish but maybe someone had ne Idde 

So,
I changed the free signs fields at the font .dds
With the capitals letters, no ptobleme

but the lower case version make some probleme with the size
there to much free place on the sides.

(Ingame its look like its a half space infront and after the letter)

Here a example:


Now I search the file where the coordinates for this invisible border (in pic blue border) was saved.

I know, I can simple change the size of the letter but its look a bit weird Ingame

So I thought the coordinates where at the insulated header, but I doesn't found nothing thats look like coordinates for the letters.

Maybe someone of you guys find something


Yours sincerely
Shippuuden
## Post #40
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-07-31T13:25:04+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello, I need some help repacking a translated english.langdb of Monkey Island Episode 1

I have successfully unpacked 1_MonkeyIsland101_pc_data.ttarch and modified english.langdb with a text editor. I have tried to repack 1_MonkeyIsland101_pc_data.ttarch with the modified .langdb and the game crashes. I also tried to create a new 0.ttarch file and game stills crashing. If i put the original 1_MonkeyIsland101_pc_data.ttarch or remove new 0.ttarch game works fine. Any idea why or what I'm doing wrong?
## Post #41
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-31T15:11:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

have you tried something like the following?

```
ttarchext -b -V 7 24 c:\0.ttarch c:\folder_where_resides_langddb
```
## Post #42
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-07-31T17:01:31+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

@TavoT

Did you change the textlength controll number too ? (at the langdb)
!!! Important !!!

If you don't did this ToMI crash on gamestart or doesn't show any ingame text (If the Game start).

Exception, your translated text has the same textlength like the original English Text !

To which language do you want translate the game ?


Yours sincerely
shippuuden
## Post #43
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-07-31T18:16:13+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Thanks for the replys...

@Bugcode: Yes, that's exactly the command I've used. I've been following all of your instructions, you really know what you are doing 

@Shippuden: I have a group of friends making a spanish translation. Where in the langdb file is the textlenght control and how do I change it? I'm sure this is the cause of the crashing... I didn't change it.

EDIT: I've just tried to change just one word, same lenght, repacked a new 0.ttarch file and game crashes. But then i've repacked the full file 1_MonkeyIsland101_pc_data.ttarch and worked!

Just need to know how to change the textlenght control
## Post #44
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-07-31T19:27:09+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Whats kind of editor did you use ?
With a normal Editor or notepad++ I had some problems.
I am work with the German version of this tool.

Its are the small freeware Hex-Editor called "HxD"
Here are the spanish version [http://mh-nexus.de/downloads/HxDSetupES.zip](http://mh-nexus.de/downloads/HxDSetupES.zip)

Use the original langdb (without changes)
And than,
at first try to edit just one letter at the game menu like "Save & Load" on line 22 at the "HxD"
For example, change the " & " to nen " a " (just first try)

Nen other question, did the rebuild work with the original langdb or did it crash there too ?
Did you rebuild all data from the "1_MonkeyIsland101_pc_data.ttarch" or such the "english.langdb" ?
If the test where possible (and the Game start with the small menu change)
I explain (next time) where the new textlength must be write

At the first try this ^^

Sorry for my awful english gramma
But my spanish is even worse ^^

EDIT:
---------------------------------------------------------
Ups ^^
You had successful change a word with the same textlength ^^

Ok I try to make a screenshoot that explain where you must change the textlength ^^

One moment ......
Here is it...

So, that should explain all^^

Have fun ^^
Its a lot of work
The German Version is also at the beginning 
Its to much Text

2461 dialogs or menu/objekt lettering
TO MUCH.....   

Yours sincerely
shippuuden
## Post #45
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-07-31T19:43:21+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I've used EditPlus for editing the .langdb

Changed "New Game" for "Nuevo..." (dots used to leave it same lenght) as you can see here



Worked when I unpacked 1_MonkeyIsland101_pc_data.ttarch, replaced english.langdb with the modified one and then repacked the full file again.

Thanks for your help!
## Post #46
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-07-31T19:52:43+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I had some problems with Notepad++
and its not so easy/comfortable to edit the hex Code for the textlength 

But its your choice ^^

Yours sincerely
shippuuden
## Post #47
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-31T19:57:37+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

editing binary data with a text editor is ever a bad idea.
luckily notepad++ handles enough well also the binary data (from 0x00 to 0xff) but obviuosly remains the problem of carriage return (0x0d) and line feed (0x0a) due to the usual window and unix mode.
so in any case a hex editor is not only suggested but even required.
## Post #48
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-07-31T20:15:08+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Yes, I see that using a Text Editor nothing works 

Now, i've started using the Hex Editor, modified a few words, repacked ttarch and... game crashes... Do I have to change textlenght of every word I change? How do I know where the textlenght begins and ends for each line of text?

This will not be easy
## Post #49
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-07-31T20:21:32+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

At Menu or Objekt text ever the 4byte in front of the main text.
You musst for each dialog or Menutext count the letter and write it back at a hexnumber

I post a example in few minutes......
## Post #50
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-07-31T20:25:19+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

The contents of this post was deleted because of possible forum rules violation.
## Post #51
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-07-31T20:44:34+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

@johntus

Ohh, great work.

Then you are faster then I ^^

I worked the last days on a online php based editor for the langdb.
So that a few people can work together at the same file
It almost workable but you guy where faster ^^
Such the write funktion doesn't work correct.... YET^^.

Good work,
such a english inteface is missing ^^
But with a bit trying its good workable ^^


Yours sincerely
shippuuden
## Post #52
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-07-31T21:09:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

@shippuden: Got it... Everything understood... But i've translated the main menu texts, corrected the textlenght control and now texts have dissapear. You gonna end hating me 

@johntus: Excellent tool, unfortunately it doesn't work on mi computer, I execute it, shows error message and closes. Bad luck for me.
## Post #53
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-07-31T21:14:02+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

@johntus

!!! IMPORTANT !!!
I found a small mistake at your editor

Three sentences wouldn't read in your programm


Thats the three sentences in front of the three ".anm/.wav" breaks

"....107684864.anm....107684864.wav000"


The three misssing sentences are probably used at the multiple choice interface

This are the three missing sentences:

{Confused}What was it I was supposed to be doing?
and twice this one
{Whiney}I haven't got a crew to take me to Lucre Island.

always in front of the ".anm/.wav" break

(yes, of course the sentences are twice existent at the file)
One for the speach (sub) and the other one for the multiple choice interface


EDIT:
And the long Menu text after the points "Periodic" and "Frequent" missing too

"Thanks for playing the Tales of Monkey Island demo! This is just the beginning - play the full series to join Guybrush on his exciting piratey quest!..You can also extend your pirate experience by joining Guybrush's Treasure Hunt..This additional mini-game is separate from the Tales of Monkey Island story"

So, than
"have fun to fix this"

I work meantime on my Online PHP based langdb editor ^^


@TavoT
No.... I dont hate you
hmmm but right now, I dont know what you make wrong on your side ?!?!

But now you have nen first editor from johntus
And without that tree dont editable sentences his tool work fine
His tool work at you file OR ?


Yours sincerely
shippuuden
## Post #54
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-07-31T21:41:39+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I now tried johntus program in other PC and worked.. I don't know what is wrong with mine... anyway my part of the job is repacking the file, i will not translate so that tool will be a great help. 

Thank you all for your help!

EDIT: Fixed it... It Requires Microsoft .Net Framework 2 to work... I didn't have it installed, but donwloaded and installed it and everithing is working fine now

EDIT 2: How do I save changes with the Langdb Translator? I can view and edit texts but it's not saving any changes

EDIT 3 and final: Found the button to save changes... all set!
## Post #55
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-08-01T07:30:39+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

@shippuuden
It's just beta version, so it will be updated.
## Post #56
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-01T13:44:14+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Guess what... using the Langdb translator I changed all menu texts, packed the ttarch and game has crashed... first thing I thinked is that the program does not correct the textlenght control, but I've checked the langdb file with the hex editor and all textlenght controls were corrected. Could it be the filesize of english.langdb? After the modifications its bigger than it was originally
## Post #57
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-01T16:31:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

@TavoT
for my curiosity, are you using Vista?
because in some cases this operating system has some problem scanning the directories with my code (used in rebuild mode).

remember that you can ever recheck the ttarch archive you have just rebuilt simply re-extracting its content in a new folder and comparing the files contained in them
## Post #58
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-01T20:26:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

@Bugtest, no i'm using XP. Anyway it wasn't a problem of the rebuild. I already have done modifications and rebuilded several ttarch files that worked, and some others that crashed the game. I'm using the Langdb Editor johntus posted here and after translate the Main menu texts and rebuild the ttarch the game crashes... I tried to translate just a word with the same lenght and the game worked, that's why I think it could be a filesize problem
## Post #59
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-01T20:35:47+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

in these cases the only problem is when the string you want to add is longer than the existent one.
if it's shorter it's enough to put the bytes 0x00 or 0x20 (space) covering the remaining chars of the previous string
## Post #60
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-01T21:25:08+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I supossed that, because with shorter texts the game works fine... Langdb Editor automatically corrects the textlength control.

Now the question is how can I do to insert longer lines?
## Post #61
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-08-03T07:53:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I'm sorry, it looks like previous version of Langdb Editor have some bug, and it saves file with errors.

Here's a new version 1.1, i have tested it, works fine. [http://multi-up.com/124838](http://multi-up.com/124838)
ps: abc.txt file is used for transliteration.
## Post #62
- Username: neoen
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Oct 15, 2008 6:34 pm
- Post datetime: 2009-08-03T09:02:36+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Great!

Will be editor expanded also to older TellTale games and not only latest MI?
Does editor handle with longer translated sentences than original ones?
## Post #63
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-08-03T10:07:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

No support for older Telltale Games.
It handles longer sentences, up to 255 symbols.
PS: Anyway, do backups often, who knows what can happen.
## Post #64
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-03T12:10:14+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Excellent Johntus! Is there somebody who can translate the interface from russian to english?... The program is easy to use, but I would like to understand what buttons say to have an idea of what they do.

EDIT: Game crashed with this new Langdb Editor again... I'm trying to use only shorter texts now to see what happens

EDIT 2: See what happened with shorter texts, and with texts with the same length
## Post #65
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2009-08-03T13:17:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

russian is a 2 bytes language, they probably modify something else to make it work. You need a brand new editor or dumper/reinserter i think
## Post #66
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-08-03T13:27:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Tavot
Upload ur modified english2.langdb
## Post #67
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-03T13:42:33+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Here you are... first 15 lines translated.

EDIT: With this one the game worked fine and shows all texts... I don't understand... hold on... I'm gonna translate a few lines more

EDIT 2: Well, crashing issue solved... I was moving the english.langdb file for repacking without closing LangDB Editor. Closing LangDB Editor before moving the file for repacking solved it 

Its working fine with longer lines too... It only remain one problem.... Game doesn't show some texts... Here you are the last translated langdb file


 english.rar
(74.09 KiB) Downloaded 53 times



EDIT 3: Never mind... i got it working now
## Post #68
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-04T20:26:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi there... I already have almost every text translated and now I'm attempting to insert them into the english.langdb with the Langdb Editor.

After serevarl tests, everything works fine (game runs, texts are visible and translated) until I get to line 75, 80 or 90 (aprox. each time was different), the game runs but texts start to dissapear. Any idea why? Is there something that I have todo do and I'm not doing it?

I wan't to be sure that everything works before going on... I don't want to get to the last lines with a non-working game
## Post #69
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-08-11T04:01:13+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Here's the new version of Langdb Editor 2.0 [http://multi-up.com/127793](http://multi-up.com/127793)
## Post #70
- Username: Luk
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 11, 2009 3:01 pm
- Post datetime: 2009-08-11T09:17:27+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from shippuuden
>
> NEXT Problem   

Its just a blemish but maybe someone had ne Idde 

So,
I changed the free signs fields at the font .dds
With the capitals letters, no ptobleme

but the lower case version make some probleme with the size
there to much free place on the sides.

(Ingame its look like its a half space infront and after the letter)

Here a example:


Now I search the file where the coordinates for this invisible border (in pic blue border) was saved.

I know, I can simple change the size of the letter but its look a bit weird Ingame

So I thought the coordinates where at the insulated header, but I doesn't found nothing thats look like coordinates for the letters.

Maybe someone of you guys find something


Yours sincerely
Shippuuden

Same problem here.

The coordinates are specified in the header but I can't find out how is the structure of the data so you can change the values properly. It seems to be 4bytes-8bytes-8bytes but this doesn't make sense to me... I was expecting something like x-y-width-height.

Apparently [these guys](http://www.zoneofgames.ru/forum/index.php?showtopic=17969) figured out how to do it, maybe we could contact them to ask them how they do it but we'll need someone to translate our request to russian
## Post #71
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-08-11T13:09:42+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Luk
Well, i am one of these guys, and we also cant find coordinates of letters.
I just redrawed english letters to russian.
## Post #72
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-11T13:22:07+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Right, but our problem (Luk is working with me in the spanish translation) is that we need to add some symbols to the existent ones... spanish and english have the same alphabet, but we also need a few symbols more:

á é í ó ú ñ ¿ !

The question is how to add them to the charmap

Here is that topic translated to English:

[http://translate.google.com.ar/translat ... s&ie=UTF-8](http://translate.google.com.ar/translate?u=http%3A%2F%2Fwww.zoneofgames.ru%2Fforum%2Findex.php%3Fshowtopic%3D17969&sl=ru&tl=en&hl=es&ie=UTF-8)
## Post #73
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2009-08-11T13:29:45+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Luk
Hi.
I am one of this guys too.   
"LangBD Editor for Tales of Monkey Island" is my work.
## Post #74
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-11T13:35:30+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

@Den Em: I'm using it to translate the game, the program is just excellent! I will never thank you enough for it.

Have an idea of when it will be ready the "Import" feature?
## Post #75
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-08-11T13:51:37+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Tavot
We also needed more letters for russian alphabet, so we used some special symbols like њџўҐ
Here's original font:
[http://img6.imageshack.us/img6/624/weatheredsf30.jpg](http://img6.imageshack.us/img6/624/weatheredsf30.jpg)
And here's russian font:
[http://img39.imageshack.us/img39/9132/w ... dsf30a.jpg](http://img39.imageshack.us/img39/9132/weatheredsf30a.jpg)

Den Em
Hi there!
## Post #76
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-11T16:43:11+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Yes, it's me, with another question 

Luk told me he already added the extra symbols, but he doesn't know how to change the size of the seleccion for those symbols... For example, he placed the simbol á (10 px width) in a place of 15 px widht, so when you read it, the word looks like "cu á ndo" . It leaves too much free space between letters... Is there some way to change the selection size?
## Post #77
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2009-08-11T16:43:51+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from TavoT
>
> @Den Em: I'm using it to translate the game, the program is just excellent! I will never thank you enough for it.

Have an idea of when it will be ready the "Import" feature?

Maybe... Now?  
[http://multi-up.com/128028](http://multi-up.com/128028)
See my import.txt in archive and test.

Format of input(import) string = Format export string 

Number of input string) Name(But not necessarily)
text of input string

If you crash your .langdb file, see the import.txt and write to me. 
That is all.   

P.S. Sorry for my bad english... maybe.
## Post #78
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-11T17:14:05+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Tested it and working perfectly!! Thanks a lot! that's gonna make the work much easy
## Post #79
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2009-08-11T17:24:04+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from TavoT
>
> Tested it and working perfectly!! Thanks a lot! that's gonna make the work much easy
=)
And...
Remember. In LangDB Editor 2.0 are found new string (more 255 characters). That in some places numeration of lines was displaced.
Be careful.
## Post #80
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-11T17:25:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I saw that, so I exported the original LangDB with 2.1 version and now i'm working with those texts 

Thanks again!
## Post #81
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2009-08-11T17:30:38+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

TavoT
Always please.

Good Luck!
## Post #82
- Username: Luk
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 11, 2009 3:01 pm
- Post datetime: 2009-08-12T06:03:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Den Em
>
> Luk
Hi.
I am one of this guys too.   
"LangBD Editor for Tales of Monkey Island" is my work.

Nice work 

Finally I figure out how to change the offset/width/height of the chars in charmap. If you are interested let me know.
## Post #83
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2009-08-12T09:50:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Luk
>
> 
Finally I figure out how to change the offset/width/height of the chars in charmap. If you are interested let me know.
Yes, of course. Tell us please.
## Post #84
- Username: Luk
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 11, 2009 3:01 pm
- Post datetime: 2009-08-12T11:57:59+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

PM sent =)
## Post #85
- Username: habit
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 12, 2009 6:20 pm
- Post datetime: 2009-08-13T02:35:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Luk
>
> 
Finally I figure out how to change the offset/width/height of the chars in charmap. If you are interested let me know.
I'm interested in the offset/width/height too. Would you please also PM me? Thanks.
## Post #86
- Username: habit
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 12, 2009 6:20 pm
- Post datetime: 2009-08-13T03:14:03+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

@Bugtest
Thanks for your ttarchext. I have a few problem here.
1 
E:\ttarchext>ttarchext 25 1_WallaceGromit104_pc_data.ttarch 111
E:\ttarchext>ttarchext -b -V 7 25 1.ttarch 111
I extract and then rebuilt a ttarch of Wallace & Gromit: Episode 4: The Bogey Man, without any change. After I replaced the ttarch, the game crashed. I found following information:

file / size / first 4 bytes
1_WallaceGromit104_pc_data.ttarch / 71,744,476 bytes / 06 00 00 00
1.ttarch / 71,744,488 bytes / 07 00 00 00

2 
In game "Wallace And Gromit Ep1 - Fright Of The Bumblebees", there are five ttarch packages:
1_wallacegromit101_pc_data.ttarch
2_wallacegromit101_pc_voice.ttarch
3_wallacegromit101_pc_ms.ttarch
Z_wallacegromit101_gm_data.ttarch
Z_WallaceGromit101_pc_core_launcherOnly.ttarch

But I can only extract one package successful with ttarchext 0.1.5. It's Z_wallacegromit101_gm_data.ttarch. What's wrong?

E:\ttarchext>ttarchext 0 pack\2_wallacegromit101_pc_voice.ttarch pack\voice

Telltale TTARCH files extractor/rebuilder 0.1.5
by Luigi Auriemma
e-mail: [aluigi@autistici.org](mailto:aluigi@autistici.org)
web:    aluigi.org

- open file pack\2_wallacegromit101_pc_voice.ttarch
- set output folder pack\voice
- set the blowfish key of "Wallace & Gromit: Episode 1: Fright of the Bumblebees
"
- version    4
- info_mode  1
- type3      2
- files_mode 1
- info_table has a size of 58219 bytes
- decrypt info_table
- set files base offset 0x0000e38f
- filesystem compression: off
- filesystem encryption:  off
- retrieve folders:
Error: No error
## Post #87
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-13T07:32:21+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

1)
bogey man uses -V 8
anyway it's strange that the first 4 bytes of the original packet contain the number 6 (which means version 6) because here I have the number 8.
in any case you must use the same version number of pack reported during the extraction so if ttarchext says version 6 then you must use -V 6 in rebuild mode

2)
ops the key I used was the one of wallacegromit_demo (as you know telltale has made a big chaos linking that demo for any of the 4 episodes) so I have corrected it immediately in version 0.1.5a.
thanx
## Post #88
- Username: habit
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 12, 2009 6:20 pm
- Post datetime: 2009-08-14T06:45:10+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Bugtest
>
> 1)
bogey man uses -V 8
anyway it's strange that the first 4 bytes of the original packet contain the number 6 (which means version 6) because here I have the number 8.
in any case you must use the same version number of pack reported during the extraction so if ttarchext says version 6 then you must use -V 6 in rebuild mode
Thanks for the reply.
Sorry, I made a mistake. You're right, it used v8. 
But the game still crashed after I extract and rebuilt the pack using following cmd:
E:\ttarchext>ttarchext 25 1_WallaceGromit104_pc_data.ttarch 111
E:\ttarchext>ttarchext -b -V 8 25 111.ttarch 111

original pack  71,746,665 bytes
new pack      71,744,489 bytes
## Post #89
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-14T10:44:25+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

uhmmm I can't help with the tests made on the starting of the game because here it doesn't work as demo so requires login and serial.

anyway there are some tests you can do in sequential order:
- temporary moving the original 1_WallaceGromit104_pc_data.ttarch in another location (so that it will be not loaded)
- renaming 111.ttarch as 0.ttarch
- using a hex editor and substituiting the two 0x01s at offset 0x20 and 0x24 with two 0x00s
- placing the following 8 bytes at offset 0x18: 20 79 00 00 6D 0D 00 00

tell me if one of these tests solves the problem
## Post #90
- Username: habit
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 12, 2009 6:20 pm
- Post datetime: 2009-08-15T01:41:06+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Thanx.
I just tested all of the steps. 
1) The new pack must be named as the original name but not 0.attarch, else the game crash. 
2) Substituiting the two 0x01s at offset 0x20 and 0x24 with two 0x00s solved the problem and the game running fine.
3) The 8 bytes at offset 0x18 seems have nothing to do with the problem. The problem still appear while I just changed them but didn't change the bytes at offset 0x20 and 0x24. And the problem didn't appear after I replaced all of the bytes at offset  0x20, 0x24 and 0x18.
## Post #91
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-15T14:09:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Substituiting the two 0x01s at offset 0x20 and 0x24 with two 0x00s solved the problem and the game running fine.
eh eh eh exactly as I guessed :)
in the next version (which will be released after the 20th of this month) I will add an additional option for controlling those two boolean values for avoiding the manual hex editing if it's necessary to specify zero values.
## Post #92
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2009-08-16T14:21:50+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

LangBD for Tales of Monkey Island v.2.2
- ASCII-1252, but not 1251.
+ Аdd File Dialog
- English language =)
[http://multi-up.com/129933](http://multi-up.com/129933)
## Post #93
- Username: oiakiller
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2009 8:36 am
- Post datetime: 2009-08-16T16:26:38+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hey everyone, i was helping a little in this topic at the beggining, but I stoped posting because my computer wasn't open this forum   

I and my team are translating the 1st and 2nd season of Sam & Max. Look the screenshots! Its great! We are translating and using Hex to remove the characters limits. Each member is translating a episode. I am at the 2nd of the season 2 and I am at the half (line 200 of 400)

The problem is that only one guy knows how to use Hex (I suck in this), and we need a Langdb editor. Someone knows one that works with Sam&Max?

Oh, and congratulations for the editor of Tales of Monkey Island!


SORRY FOR BAD ENGLISH
[Novo(a) Imagem de bitmap 5.JPG](https://xentaxbackup.github.io/file/2286_Novo(a) Imagem de bitmap 5.JPG)
## Post #94
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2009-08-17T15:29:09+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

oiakiller
[http://quick.mixnmojo.com/telltale-langdb-editor](http://quick.mixnmojo.com/telltale-langdb-editor)
This editor is not work?
## Post #95
- Username: oiakiller
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2009 8:36 am
- Post datetime: 2009-08-17T16:07:31+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

No, dont work...
## Post #96
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-18T02:11:41+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello everybody... Just want to let you know that spanish transaltion is completed, and that we couldn't have done it without all your help.

So, in behalf of all spanish talking people... THANK YOU VERY MUCH!
## Post #97
- Username: oiakiller
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2009 8:36 am
- Post datetime: 2009-08-19T16:35:45+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Congratulatios! or... Parabiens (I'm brazilian, so its easy to learn Español)


Can somebody please help me? I realy need a editor. Does anyone knows how to modiffy the Langdb editor for ToMI and makes it works on Sam & Max 1st and 2nd season?

Its SO hard to translate with Notepad++
## Post #98
- Username: NicotineLL
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 19, 2009 12:04 pm
- Post datetime: 2009-08-19T17:50:47+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello to everyone,

I've been reading the topic and I've tried some things here, but it seems that it doesn't work for me. I want to translate ToMI on bulgarian but I need some hints on how to do it.

I already know that the langdb is inside "1_MonkeyIsland101_pc_data.ttarch", but how am I supposed to extract it?
And/if I'm able to translate it, how to put it back in to test it and stuff?

Thanks
## Post #99
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-19T18:15:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

ttarchext.exe -f "*.langdb" 24 "C:\Program Files\Telltale Games\Tales of Monkey Island\Launch of the Screaming Narwhal\Pack\1_MonkeyIsland101_pc_data.ttarch" c:\output_folder

... edit the langdb file and then ...

ttarchext.exe -b -V 7 24 "C:\Program Files\Telltale Games\Tales of Monkey Island\Launch of the Screaming Narwhal\Pack\0.ttarch" c:\output_folder
## Post #100
- Username: NicotineLL
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 19, 2009 12:04 pm
- Post datetime: 2009-08-19T20:33:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

It gave me an error when I lauched the game. Then I've changed "-b -V 8 24" with "-b -V 7 24" and it works fine, but I see no translation happening.

Am I supposed to leave 0.ttarch file like this (only langdb inside) or should I extraxt the whole 1_MonkeyIsland101_pc_data.ttarch and rebuild it again with the changed langdb?
## Post #101
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-19T20:35:29+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

It works in both ways... check if you are creating the new ttarch with the translated LangDB and remember to place de new ttarch in the "Pack" folder of the game
## Post #102
- Username: NicotineLL
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 19, 2009 12:04 pm
- Post datetime: 2009-08-19T21:15:48+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

What I've noticed was that the ttarchext.exe use no files to create the 0.ttarch file   

What I do is, I extract the english.langdb file in c:\output_folder with this command:
ttarchext.exe -f "*.langdb" 24 "D:\Tales of Monkey Island Chapter 1\Launch of the Screaming Narwhal\Pack\1_MonkeyIsland101_pc_data.ttarch" c:\output_folder

So far so good.
I do some editing in the file and I try to rebuild it with this command:
ttarchext.exe -b -V 7 24 "d:\Tales of Monkey Island Chapter 1\Launch of the Screaming Narwhal\Pack\0.ttarch" c:\output_folder

But this is what ttarchext.exe shows me:

```
Narwhal\Pack\0.ttarch
- the file "d:\Tales of Monkey Island Chapter 1\Launch of the Screaming Narwhal\
Pack\0.ttarch" already exists
  do you want to overwrite it (y/N/all)? y
- set output folder c:\output_folder
- set the blowfish key of "Tales of Monkey Island: Launch of the Screaming Narwh
al"
- start recursive scanning
- collected 0 files
- start building of the file

- 0 files found
- done

```


0 files found... I just can't seem to be able to crack this one...
## Post #103
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-19T23:29:59+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I guess you use Vista or Windows7 right?
at the moment there are problems with the function which scans the folder and these operating systems, I should fix them one day maybe but it's not clear what these OS want
## Post #104
- Username: NicotineLL
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 19, 2009 12:04 pm
- Post datetime: 2009-08-20T09:30:38+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Yes, I'm on Vista. I also have XP, but it's quite unpleasant to change OSs all the time.
I hope you can fix this soon  

edit:

Can anybody tell me how to edit "weathered_sf_30.font" so can insert cyrillic letters (something like the russian guys did), becouse if I try to use letters from my language, ingame there are showing like "?".

As I found weathered_sf_30.font is not a font file, so I can't just set it in some font editor to do it. I red something about Hex editor but I've no clue what to do with it...
## Post #105
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2009-08-20T13:19:25+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

LangdbEditor for Tales Of Monkey Island
and 
LangdbEditor for Wallace & Gromit's Grand Adventures
Work with TOMI - Episode 2
[http://multi-up.com/131436](http://multi-up.com/131436)

oiakiller
Test LangdbEditor for W&GGA
Maybe it's work.
## Post #106
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-20T17:03:55+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

new version of [ttarchext](http://aluigi.org/papers.htm#ttarchext) which adds:
- support for Vista and Win7
- support for the new Monkey Island released some hours ago
- the -x option so that the hex editing of the bytes at offset 0x20 and 0x24 is no longer needed, add -x and it will do the job automatically
## Post #107
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-20T18:02:08+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Great Bugtest! Thanks a lot!
## Post #108
- Username: oiakiller
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2009 8:36 am
- Post datetime: 2009-08-20T19:45:21+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Den Em, I downloaded the LangDB editor, but i'm havin problems at the extration of the .rar

Can you re-up the editor?
## Post #109
- Username: Zipslow
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 07, 2009 7:25 pm
- Post datetime: 2009-08-20T22:47:45+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Bugtest
>
> new version of ttarchext which adds:
- support for the new Monkey Island released some hours ago

Thanks for the fast update but is it just me or does ttarchext -m 26 4_MonkeyIsland102_pc_tx.ttarch TEXTURES not work properly? All textures files are still D3DTX or corrupt DDS..
## Post #110
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-20T23:09:00+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I have already deleted the game but I guess I have understood about what you refer.
it's probably the same thing which has been made in the latest wallace&gromit, practically all the DDS files are now headerless so the scanning functions implemented with -m is totally useless because can't find the DDS header and even if you have a DDS file it's headerless and so you need to add a header to it or to read it in raw mode.
## Post #111
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2009-08-21T12:54:13+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

re-up
1) LangDB for Tales Of Monkey Island - 1
2) LangdbEditor for Wallace & Gromit's Grand Adventures
and Tales Of Monkey Island - 2
[http://multi-up.com/131817](http://multi-up.com/131817)
## Post #112
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-08-21T13:49:55+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Bugtest
>
> I have already deleted the game but I guess I have understood about what you refer.
it's probably the same thing which has been made in the latest wallace&gromit, practically all the DDS files are now headerless so the scanning functions implemented with -m is totally useless because can't find the DDS header and even if you have a DDS file it's headerless and so you need to add a header to it or to read it in raw mode.
Something wrong with unpacking textures, even without -m option, some d3dtx files have 2-3 dds headers.
## Post #113
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-21T14:10:37+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

it's not a problem of extraction, that's exactly how are the original files in the archive.
## Post #114
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-08-21T14:57:07+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Bugtest
>
> it's not a problem of extraction, that's exactly how are the original files in the archive.
Why then, for example: file ui_chapterscreen_title102.d3dtx have such header?
## Post #115
- Username: oiakiller
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2009 8:36 am
- Post datetime: 2009-08-21T16:12:39+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Den Em
>
> re-up
1) LangDB for Tales Of Monkey Island - 1
2) LangdbEditor for Wallace & Gromit's Grand Adventures
and Tales Of Monkey Island - 2
http://multi-up.com/131817

The extraction works fine, but the tool doesnt work for Sam & Max.... Can you make a version for Sam & Max Season 2 episode 2? And for all Season 1 and 2? 

Please I really need this tool
## Post #116
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2009-08-21T16:25:54+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from oiakiller
>
> Den Em wrote:re-up
1) LangDB for Tales Of Monkey Island - 1
2) LangdbEditor for Wallace & Gromit's Grand Adventures
and Tales Of Monkey Island - 2
http://multi-up.com/131817

The extraction works fine, but the tool doesnt work for Sam & Max.... Can you make a version for Sam & Max Season 2 episode 2? And for all Season 1 and 2? 

Please I really need this tool
Sent me in PM *.langdb files of all episodes.
## Post #117
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-21T16:52:18+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from johntus
>
> Why then, for example: file ui_chapterscreen_title102.d3dtx have such header?
all the files in the 4_MonkeyIsland102_pc_tx.ttarch archive are headerless.
only in some of them you can see some headers in the middle but this doesn't change that they are headerless dds images (if I'm not in error a dds file can contain multiple dds image but that's not my field so I don't know).

that's simple to verify because all the d3dtx file which contain dds images with header have the ERTM type, all the others are juse raw/headerless.
so I can do nothing.
## Post #118
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-21T17:01:57+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

oh I have also another hypothesis which could explain why the first file is ok and the others aren't.
Now I'm evaluating it but it's enough strange and senseless because would corrupt the whole format of the archive... I will keep you update.
## Post #119
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-21T17:41:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

problem found and solved in the new [0.1.7 version](http://aluigi.org/papers.htm#ttarchext).

it was caused by a field introduced from the archives version 7 (the first monkey island) which specifies the size of the chunks divided by 1024.
so the bug affected ONLY the "tx" archives of the 2 games Bogeyman and Spinner Cay.
thanx for the feedback
## Post #120
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-08-21T17:46:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Bugtest
>
> problem found and solved in the new 0.1.7 version.

it was caused by a field introduced from the archives version 7 (the first monkey island) which specifies the size of the chunks divided by 1024.
so the bug affected ONLY the "tx" archives of the 2 games Bogeyman and Spinner Cay.
thanx for the feedback
Thank you very much for quick response.
## Post #121
- Username: NicotineLL
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 19, 2009 12:04 pm
- Post datetime: 2009-08-21T20:28:40+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

For 2 straight days I try to resolve a problem with the font file (dds) but it seems impossible...

For editing I use nVidia plug-in for Photoshop (although I downloaded 5-6 other programs) but when I save the file it's either with a background or it doesn't show in-game.

What I do is, I hex the original font file to leave only the dds headers. Then I load it into PS and in alpha channel I put my edited font (black background with white letters). Then I save it in DXT5, I put the header back in and import it into the ttarch file.

I do something wrong, but I can't figure out what. May be I should change something in the saving options or I don't know...

Does anybody have a clue how to fix this  

Edit:
By the law of Murphy "I HAD TO post to find the answer..."

Apparently I should have used the option "No MIP maps" rather than "Generate MIP maps"...
## Post #122
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-08-22T03:46:03+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

@NicotineLL
I do everything like you, but i use Gimp 2 for editing dds files.
## Post #123
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-08-28T12:02:16+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi,

I try to rebuilt the ttrach from spinner cay but without success

If  I try to start the Game with the rebuilted 0.ttrach but it crash after the small window.


I use a linkage thats look like this.

"C:\ttrach017a\ttarchext.exe" -b -V 7 26 c:\0.ttarch c:\spinnercay

Whats wrong ???


Yours sincerely,
Shippuuden
## Post #124
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2009-08-28T12:33:52+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

You need to use the version 8 and the new parámeter x to correct an error, if you don't then you have to do it manually with a hex editor... The correct syntax is the following:

ttarchext -b -V 8 -x 26 C:\0.ttarch C:\Spinnercay

We already have spanish translation ready for this chapter, and that's how I packed the new ttarch
## Post #125
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-09-02T20:21:59+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi everyone, again.
We want to translate Sam&Max: Season 2
But I can't get dds from *.font files.
Maybe someone could help me with this?
Here is one of fonts - [http://multi-up.com/136603](http://multi-up.com/136603)
Thx in advance.
## Post #126
- Username: hjchen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 17, 2009 11:22 am
- Post datetime: 2009-09-17T14:17:02+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Den Em
>
> re-up
1) LangDB for Tales Of Monkey Island - 1
2) LangdbEditor for Wallace & Gromit's Grand Adventures
and Tales Of Monkey Island - 2
http://multi-up.com/131817

Dear gamers: 
                   I have successfully extract the subtitles of Tales of monkey island 1 and 2 and the first episode of Wallace&Gromit with the help of the tool provided by Den Em.
can Den Em help with the other titles of  Wallace&Gromit..  It seems other langdb editors are needed. many thanks.

howard
## Post #127
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2009-09-19T11:38:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from hjchen
>
> 
Dear gamers: 
I have successfully extract the subtitles of Tales of monkey island 1 and 2 and the first episode of Wallace&Gromit with the help of the tool provided by Den Em.
can Den Em help with the other titles of  Wallace&Gromit..  It seems other langdb editors are needed. many thanks.

howard
Universal Langdb Editor - alpha version
Warning
- Settings... now not saved =)

[http://multi-up.com/143656](http://multi-up.com/143656)

Support langdb (maybe work with other games... or don't work with this games =D)
Tales of Monkey Island - Chapter 1-2
Wallace & Gromits Grand Adventures - Episode 1-2
Sam & Max: Season 2 - Episode 1-2
Strong Bad - Episode 1

Open "Опции" -> "Настройки" and set "1252"
Click "Ok". Start the work.
## Post #128
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2009-09-19T11:59:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from johntus
>
> Hi everyone, again.
We want to translate Sam&Max: Season 2
But I can't get dds from *.font files.
Maybe someone could help me with this?
Here is one of fonts - http://multi-up.com/136603
Thx in advance.

I'm not 100% certain, but I think its because the Sam and Max games  use a slightly different meta file encryption for the dds and font files. That's why the files appear to be decoded correctly, with correct headers but are missing the 'font' and 'dds' headers later in the file.

There are two (speculative) possibilities: either the meta encryption is tweaked slightly for these files (possibly with different blowfish/block sizes) or a further pass of the file with some other action is needed to fully decode it.

If you compare the dds files with those from other games (eg the small colorxxx files) you can see how Sam and Max (and Texas Holdem) dds files are decoded differently. I've never managed to fix this, perhaps someone else will be able to help you though
## Post #129
- Username: damnor
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 21, 2009 6:40 pm
- Post datetime: 2009-09-21T16:14:03+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi all,

I've just added letters (à è ì ò ù) to the weathered_sf_30.font dds image, in the empty spaces (those with the block char). 
Now, how do i map these letters in the image to the letters in the langdb editor?
Should I edit the abc.txt file? How?
## Post #130
- Username: damnor
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 21, 2009 6:40 pm
- Post datetime: 2009-09-22T16:56:04+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Well, the langdb editor didn't work well, so I went to edit the file directly and now the chars are visible, finally.

Now I need to know how to reduce the space between the new chars (àèìòù) and the normal ones.... 

Pleeeeeeease   I won't tell anybody you told me!
## Post #131
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2009-09-30T14:57:29+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Universal LangDB Editor 
Version 1.0.b with save settings.
[http://multi-up.com/148657](http://multi-up.com/148657)
## Post #132
- Username: shippuuden
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jul 19, 2009 8:54 am
- Post datetime: 2009-10-01T17:01:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

How looks like guys,

Its now possible to extract the 3rd TOMI Capture ^^

We just in the middle of capture tow (at the translation) but
I'am so happy .... 

MURRY MURRY MURRY ^^


Yours sincerely,
Shippuuden
## Post #133
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-05-27T13:57:18+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi!
Sorry for posting in old topic, but can someone add support for last three episodes of S&M to Den Em's editor? I can send langdb files
## Post #134
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-05-30T15:59:17+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Did you use the -m option when you extracted the files? Because in the instructions say you have not to use this option if you think rebuild the file.

Anyway, you only have to write:

ttarchext.exe -b 6 output.ttarch c:\your folder (for culture shock, for example).

Have you tried this and the game doesn't work? What is the fail? Doesn't start? Crash?

Regards.
## Post #135
- Username: RafaelGC
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 03, 2010 6:41 am
- Post datetime: 2010-05-30T21:23:47+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hey guys, I finally been able to extract the .dds file from weathered_sf_30.font.

I edited the dds fine, but does anyone know how to import it back inside the .font file?

I just need that, I don't know how to do it. Any tips?


@damnor, did you make it?

@johntus, I did using a program called Dragon UnPACKer. Hope it helps you.
## Post #136
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-01T15:05:08+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

the following is a "real-life" example for editing a font file.
note that it's necessary ttarchext 0.1.11.

```
- go in the c:\temp folder and open berlin_sans_fb_demi_40_bold.FONT with a hex editor
- now you must dump all the data till offset 0x1517 in a new file that you will call header.dat
- and dump the rest (everything from 0x1517 till the end) in a file called file.dds
- modify file.dds as you want
- reconcatenate the header and the dds launching the following command (yes the + is necessary!):
- copy /b c:\temp\header.dat + c:\temp\file.dds c:\temp\newfont.font
- ttarchext -E 0x1517 0x800 12 c:\temp\newfont.font c:\
- rename c:\newfont.font as berlin_sans_fb_demi_40_bold.FONT
```
the example is plus or less like the one I posted various posts ago but should be simpler and even made "automatizable" if someone wants

*edit*
0x1517 is the starting of the DDS font (of Sam & Max: Episode 201 - Ice Station Santa) that CHANGES in each game so you must find it by yourself with a hex editor.
it's really a joke to do because you will notice the clear DDS data somewhat near the beginning of the file preceeded by exactly 0x800 bytes of garbage/strange data.
let me know if you have doubts about a particular font file
## Post #137
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-07T09:34:26+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Okashu from what Season?

aluigi Your algorithm for S&M. =)

That for ToMI, W&G:GA

```
- now you must dump all the data till "DDS" in a new file that you will call header.dat
- and dump the rest (everything from "DDS" till the end) in a file called file.dds
- modify file.dds as you want (not change the size of dds, if you want this, I tell.)
- reconcatenate the header and the dds launching the following command (yes the + is necessary!):
- copy /b c:\temp\header.dat + c:\temp\file.dds c:\temp\newfont.font (or make this in hex editor)
- rename newfont.font as original FONT-file name
```
## Post #138
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-07T15:16:05+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

From season two. There is only support for episode 1 and 2.

Also, did someone find out how to save the font? I tried editing it with Photoshop (nvidia plugin) and GIMP. But if i try to use that font, game crashes. I know I'm doing everything right in ttarchext and hex, because unpacked and packed original font works.
## Post #139
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-07T19:09:32+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Okashu

With this I'd open & export text from a 203 and 204 episodes without a problem.
Maybe you download old version? In last version on this forum I don't check support for all episodes, but I don't changes something in base algorithm in my program later.

Maybe did you change size of dds in font-file? Did you save dds with "generation MIP-maps"? Did you forget encrypt new font-file? 
I don't know what are you doing. >> I don't tell you what you doing wrong.
[ULE (last_version).rar](https://xentaxbackup.github.io/file/3118_ULE (last_version).rar)
## Post #140
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-08T12:39:16+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I save in DXT5, as a 2D texture, without MIP maps.
## Post #141
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-08T12:56:07+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Okashu
Very simple question: Did you change the size of dds-file?
Maybe you attach original font-file and new dds?
## Post #142
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-08T13:56:12+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

No. Not consciously, if I did ^^
I only use white brush to add dots
## Post #143
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-08T14:27:11+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Telepathists on vacation.
## Post #144
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-08T17:08:12+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Do you mean the size in bytes, or resolution, like 250x320?

Den Em, did you succeed in running edited font?
## Post #145
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-08T18:41:19+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

No difference. 

[Of course.](http://radikal.ru/F/s61.radikal.ru/i172/0909/1f/21bc5d1a9192.jpg.html)
## Post #146
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-08T18:58:38+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

No way!

You just motivated me to work. But you must tell me - what tool dd you use, and what settings did you use?
## Post #147
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-09T12:39:18+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

HxD, Photoshop (+ nvidia dds plagin), ttarchext.
## Post #148
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-09T12:44:27+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

What settings did you use to save the file?
## Post #149
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-09T12:55:17+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

You used a correct settings for saving dds.
Don't know about packing and encrypting.

It's difficult to write algoritm of this work.

Can you wait some time? I need two-tree day (max - one week).
Now I making a autopacker file for S&M S2... and I teach exams.
(Now I can pack d3dtx-file automaticaly.)
## Post #150
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-09T12:57:33+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Ok. It will help a lot, but I think I don't make a mistake.
## Post #151
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-09T13:08:33+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

extract font.
decrypt 2048(0x800) bytes from start of dds.
redraw dds.
paste new dds in font.
encrypt 2048(0x800) bytes from start of dds
pack font.
delete header ((packed font)-(unpacked font)) bytes
Copy encrypted, packed and cut file in game. Enjoy! 

Read post from aluigi for find some facts like start of dds and options for decrypt/encrypt start of dds.
And... good luck.
## Post #152
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-09T14:32:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Two last steps weren't in my list. Why delete the header?

I noticed something. When I open the original font and my font in hex editor, they're completly different. Only header is the same.

Maybe I'll attach a file, and you'll do it? (Only if you have too much free time) 

Here is how I want it to look like - [http://img708.imageshack.us/img708/7010/beztytuuvte.jpg](http://img708.imageshack.us/img708/7010/beztytuuvte.jpg). In attachment there is this file from screen, I just want you to make correct .font from it. (Remember - you don't have to do it)
[Desktop.rar](https://xentaxbackup.github.io/file/3128_Desktop.rar)
## Post #153
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-10T12:44:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Why delete the header?Don't know. It's worked, and I don't think about this.

> Maybe I'll attach a file, and you'll do it? I wrote about this.

Maybe attached file work.
But if you want use a transliteration... open file "dialog.lua" and delete function "ToUpper" (Save and put this file where you put font)
Becouse all dilaog-text game-engine convert from "Abc" in "ABC", and you don't see a changing in your redrawed font.
If you want make normal font, I can give you a one tool for changing a coordinat in font-file. (Universal Font Editor ) But it unfinished project and now I make this and write from non-my computer (I not can give it you.).
P.S. Sorry for my bad english.
[Making_font.rar](https://xentaxbackup.github.io/file/3129_Making_font.rar)
## Post #154
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-10T13:36:42+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

It's ok ^^ Polish talking with Russian in English 

Why is a bak file in step 6?

When I open my dialog.lua, I can't find function ToUpper in it.
## Post #155
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-10T13:52:42+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Oh, sorry. HxD automaticaly doing backup in bak.

Can you attach a dialog.lua?
Maybe I forget a name of function. =)
## Post #156
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-10T14:08:50+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

sure
[dialog.rar](https://xentaxbackup.github.io/file/3130_dialog.rar)
## Post #157
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-10T14:19:21+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Oh sh...
dialogbox.lua!
[dialogbox.rar](https://xentaxbackup.github.io/file/3131_dialogbox.rar)
## Post #158
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-10T14:22:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

You mean the line "	mText.mProps[kText] = string.upper( text );"?

Oh, I see. You sent me edited dialogbox
## Post #159
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-10T14:25:19+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Yes. =)

dialogbox - not dialog
upper - not ToUpper

My memory is completely full of holes.
## Post #160
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-10T14:58:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

When I paste the font into "data" folder, it doesn't show in-game. Am I supposed to do "ttarchext -b -V 2 12 0.ttarch "output_folder""?
## Post #161
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-10T15:29:52+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I did it wrong. 
Name of file is ccchatterbox_12.font, not - chatterbox_12.font. (Thanks for renamed file)
It's a first mistake.
Second... I don't know why you original font bigger then our font.
Test ccchatterbox_12.font & ccchatterbox_12_ver2.font(rename) and write about your bugs =)

You don't need pack all resource in 0.ttarch.

font - step 1-7
langdb - step 5-7
d3dtx - step 1-7
lua - don't need in packing
txt - don't need in packing
[Step_6.rar](https://xentaxbackup.github.io/file/3132_Step_6.rar)
## Post #162
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-10T16:14:38+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

now game freezes when I try to use the font.
## Post #163
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-10T18:39:39+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Ok. I make(program) and test all himself later.
P.S. File what we used 0x1157F, you sent 0x1158C. What the episode and version you translate? From steam?
## Post #164
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-10T19:32:41+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

It's demo version with crack. I know, weird. Episode 201. (When can I expect a program?)
## Post #165
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-12T18:49:41+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Test it.

Read "About" and think. In "Input" you can find yours unpacked decrypted font (with our old coordinates =) I'm lazy.). 
Open AutoPacker, select "S&M 201" and press "Go!". Wait. Yours new font you find in "Output".


Now you can start translating all 5 episodes, draw normal fonts like that (you can resize a dds of font):

And wait, I add all of my tools later.

P.S. When I write something — read it please.
P.P.S. Copy ttarchext.exe in directory of this tool!
[TTGTv.0.1.rar](https://xentaxbackup.github.io/file/3135_TTGTv.0.1.rar)
## Post #166
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-12T19:35:11+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Can't find "'C:\Users\vobis\Desktop\ttarchext\temp\encrypt.me".

Ok now. I had old version of ttarchext in that folder

Fonts work in-game. Thank you very very much.

Can you upload older Langdb editor somewhere? (1.0.b) The new version can't open langdb from Ice Station Santa, and I accidentally overwrote old version.
## Post #167
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-13T08:57:59+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hmm... very strange.
I fixed it (and test on 201-203 episodes).
[ULE (last_version).rar](https://xentaxbackup.github.io/file/3138_ULE (last_version).rar)
## Post #168
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-06-13T11:27:00+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Thank you one more time. I think from now on I can do everything. I will write to you on zoneofgames.ru If I had a problem.
## Post #169
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-06-13T12:03:51+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> I think from now on I can do everything.But you can not to change coordinates of characters now.

Upd.
TTG Tools v.0.2.1
## Post #170
- Username: qerqer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 16, 2010 7:59 pm
- Post datetime: 2010-07-16T15:42:17+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi, Den Em. Do you have tools for Puzzle Agent? For landb files?
## Post #171
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-07-23T19:36:29+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from qerqer
>
> Hi, Den Em. Do you have tools for Puzzle Agent? For landb files?
Yes. =)
[TTG Tools v.050.rar](https://xentaxbackup.github.io/file/3264_TTG Tools v.050.rar)
## Post #172
- Username: SileniusLegard
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jul 25, 2010 7:00 am
- Post datetime: 2010-07-25T12:46:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Puzzle Agent's text files are "*.landb" instead "*.langdb", LangDB Editor doesn't works.
Any idea?
## Post #173
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-07-26T08:31:42+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from SileniusLegard
>
> Puzzle Agent's text files are "*.landb" instead "*.langdb", LangDB Editor doesn't works.
Any idea?
Of course. Don't be a silly and use TTG Tools v.0.5.0 from my last post.
## Post #174
- Username: SileniusLegard
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jul 25, 2010 7:00 am
- Post datetime: 2010-07-26T15:34:02+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Well, thanks.
I extract, edit and compile game menu, and results its...
[](http://a.imageshack.us/img185/2945/grickle1012010072617314.png)
blank...

So, I extract and compile original ui_menu_english.landb with ttarchext with no edit, and same, blanks...
Bad luck, something wrong, : /

PD: I can edit with -x option in ttarchext.
But when I modify one line with more or less characters and run the game, show me an error.
Well, maybe too much for me...

PDD: Ok, I'm already knows, it must be text length, how can I modify that?
## Post #175
- Username: Wootman
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 27, 2010 12:40 pm
- Post datetime: 2010-07-28T17:14:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Whats the game key for Puzzle Agent?
## Post #176
- Username: SileniusLegard
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jul 25, 2010 7:00 am
- Post datetime: 2010-07-28T17:29:33+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

36

Well, at last I could edit text, not all, but almost.
I trying to edit textures now, with surprising success, haha
I don't know why some text, like "Solve it!" doesn't exists, I don't found it, damn it, : (
## Post #177
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-07-28T17:35:54+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

the game key of PA is already supported in the latest version of ttarchext, so is better if you [redownload it](http://aluigi.org/papers.htm#ttarchext)
## Post #178
- Username: Wootman
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 27, 2010 12:40 pm
- Post datetime: 2010-07-28T17:46:57+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

and Sam and Max 304?
## Post #179
- Username: qerqer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 16, 2010 7:59 pm
- Post datetime: 2010-08-01T10:25:51+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Den Em
>
> qerqer wrote:Hi, Den Em. Do you have tools for Puzzle Agent? For landb files?
Yes. =)
Thanks very, very much.
## Post #180
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-08-03T10:14:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

SileniusLegard

> I extract, edit and compile game menu, and results its... blank...
Sorry. I fixed it later. Maybe today.

> So, I extract and compile original ui_menu_english.landb with ttarchext with no edit, and same, blanks...Don't know, but when I did this is works.

> I don't know why some text, like "Solve it!" doesn't exists, I don't found it, damn it, : (
Because some text you can find in *.scene or other files.
I don't translate this game, but I find "BACK" in ui_backbutton.scene (offset 0xA77). Maybe this text used somewhere in game, but maybe not.
Use hex-editor for this.

===
UPD

New version. Open config.txt and fix way for work.
## Post #181
- Username: SileniusLegard
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jul 25, 2010 7:00 am
- Post datetime: 2010-08-03T20:17:40+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Yes, thank you very much.

I'm trying to edit that *.scene files with relative success, but if I add more characters to the file, game crash.
Even editing "text length" for the modified line, there is another "text counter" for the all file or something?
Thanks.
## Post #182
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2010-08-04T18:59:48+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I'd love a "search" function in Langdb Editor. Searching through thousands of lines if you want to correct something can be annoying.
## Post #183
- Username: Keeperv85
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 06, 2010 8:41 am
- Post datetime: 2010-08-08T07:16:58+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

OFF: Sorry my bad english. A friend of mine translates the game. (Puzzle Agent). Can would be our need which font types are in him. NOT in the "font" files, but in the graphics. 

Example this:

[http://imagerz.com/QEJEWktvAwJSXwhOFAVR](http://imagerz.com/QEJEWktvAwJSXwhOFAVR)

You can tell it what kind of font type this? /OFF
## Post #184
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-08-08T07:53:53+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

SileniusLegard
In Sam & Max Season 3 we translate one scene-file, but there lenght of new and old text is same.
In dlog and landb files on each string you can find three lenghts and two for all text. But scene isn't text-file, and it contains hex-code of game, I don't know how edit this files.

Now I edit "BACK" and lenght (04 00 00 00 42 41 43 4B = . . . . BACK) and game start (05 00 00 00 42 41 43 4B 4B = . . . . BACKK). But i don't know were this "BACKK". =)


Okashu
I think about "search"-function in "Somthing" Editor. But we translate and edit game text in txt-files.
Later I add support for langdb-files in TTG Tools, and about "Somthing" Editor you can forget.

Keeperv85
Don't know. Maybe should use this: [http://new.myfonts.com/WhatTheFont/](http://new.myfonts.com/WhatTheFont/)?
But this sample have very bad quality.
## Post #185
- Username: Keeperv85
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 06, 2010 8:41 am
- Post datetime: 2010-08-08T08:06:40+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Thanks the fast answer! I tried it on already unfortunately. He did not find an good.  The picture figures in the game in this quality. From there I extract it.
## Post #186
- Username: Keeperv85
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 06, 2010 8:41 am
- Post datetime: 2010-08-14T12:34:12+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I edit the *.scene files:

This original code:

```
09, 00, 00, 00, 53, 6F, 6C, 76, 65, 20, 69, 74, 21 = 09, 00, 00, 00 Solve it!  
```


This works...

```
0A, 00, 00, 00, 53, 6F, 6C, 76, 65, 20, 69, 74, 21, 21 = 09, 00, 00, 00 Solve it!! 
```


...but, this not anymore:

```
08, 00, 00, 00, 53, 6F, 6C, 76, 65, 20, 69, 74 = 09, 00, 00, 00 Solve it 
```


It I think it as me it is necessary to reduce the size with a hand in the header, but I do not find it which one offset. 

Can somebody help me?
## Post #187
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-08-16T09:14:59+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Keeperv85
Can you say what the scene-file you need to edit?
## Post #188
- Username: SileniusLegard
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jul 25, 2010 7:00 am
- Post datetime: 2010-08-16T09:23:28+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Well, finally I could translate the game.
Thanks for all, Den Em, ; )
## Post #189
- Username: Keeperv85
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 06, 2010 8:41 am
- Post datetime: 2010-08-17T07:52:06+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Den Em
>
> Keeperv85
Can you say what the scene-file you need to edit?

Sure. This file the "ui_puzzlebase_info.scene" file.
## Post #190
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-08-25T19:22:45+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Keeperv85
>
> Den Em wrote:Keeperv85
Can you say what the scene-file you need to edit?

Sure. This file the "ui_puzzlebase_info.scene" file.
I make string shorter, and this work.
I write symbol with hex-code 0x00 in place of unnecessary char.
[Solve it!.JPG](https://xentaxbackup.github.io/file/3375_Solve it!.JPG)
## Post #191
- Username: Keeperv85
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 06, 2010 8:41 am
- Post datetime: 2010-09-01T02:13:53+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Thank you for the help. I will try it.
## Post #192
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-11-02T14:50:08+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

The contents of this post was deleted because of possible forum rules violation.
## Post #193
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2010-11-02T18:04:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

CSI: Fatal Conspiracy demo:
82BC766A549C7696BBA2A59475B89C8D995A70CA86AB669FA874B88B699CA487A87B627FA4B682A2A5A4BBBF8068829F88B66F69A0A282
## Post #194
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-11-03T16:26:58+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from bgbennyboy
>
> CSI: Fatal Conspiracy demo:
82BC766A549C7696BBA2A59475B89C8D995A70CA86AB669FA874B88B699CA487A87B627FA4B682A2A5A4BBBF8068829F88B66F69A0A282
Thanks a lot! Can you explain to me how to get such a key? I want to retrieve it myself for the full version when it's released.
## Post #195
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2010-11-03T19:33:59+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

see pm
## Post #196
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-11-04T05:27:19+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Alright.
## Post #197
- Username: kurt28
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Sep 08, 2010 1:00 am
- Post datetime: 2010-11-19T02:10:42+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Please, I need help with Sam & Max 3x01.

I translate english.langdb and build 0.ttarch, but the game start always in english.

Any text in another place?

Thanks.
## Post #198
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-11-22T07:47:13+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

In 3 season you need to translate *.dlog files.
## Post #199
- Username: CuberToy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 01, 2010 4:05 am
- Post datetime: 2010-11-23T01:42:54+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

So I give up on the translation of Puzzle Agent (why do they had to change !)
But now, I'm interested in Poker Night... Hope it will be possible.
## Post #200
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-11-23T11:46:31+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Key for Poker Night at the Inventory:

```
\x82\xCE\x99\x99\x86\xDE\x9C\xB7\xEB\xBC\xE4\xCF\x97\xD7\x96\xBC\xD5\x8F\x8F\xE9\xA6\xE9\xAF\xBF\xD4\x8C\xD4\xC7\x7C\xD1\xCD\x99\xC1\xB7\x9B\xC3\xDA\xB3\xA8\xD7\xDA\xE6\xBB\xD1\xA3\x97\xB4\xE1\xAE\xD7\x9F\x83\xDF\xDD\xA4
```
## Post #201
- Username: CuberToy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 01, 2010 4:05 am
- Post datetime: 2010-11-24T22:43:59+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Can someone explain step by step how to translate and repack a telltale game.
I was trying to translate Puzzle Agent, but I give up. Now, I really want to work on Poker Night. 
When I tried to translate Puzzle Agent, I manage to do some (like depack, but not translate, neither as repack though)
## Post #202
- Username: kurt28
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Sep 08, 2010 1:00 am
- Post datetime: 2010-11-25T08:53:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Den Em
>
> In 3 season you need to translate *.dlog files.

Ok, thanks. I use your tool, TTGTools, and I can extract texts but I cannot pack it. Or I don't know how.
## Post #203
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-11-25T20:15:01+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from kurt28
>
> Ok, thanks. I use your tool, TTGTools, and I can extract texts but I cannot pack it. Or I don't know how.
Put in Input Folder dlog/langdb/landb-files and txt-files and click "Export".
[TTG TOOLS.rar](https://xentaxbackup.github.io/file/3641_TTG TOOLS.rar)
## Post #204
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-12-24T15:57:53+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I wanna translate the BTTF game.
Can someone make a tool for .landb? (It's not "langdb", its "landb")
## Post #205
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2010-12-24T21:08:34+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Try changing the extention of the file to .langdb a see if it works. How did you unpacked the .ttarch file?
## Post #206
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2010-12-25T12:47:29+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from TavoT
>
> Try changing the extention of the file to .langdb a see if it works. How did you unpacked the .ttarch file?

I think aluigi needs to update the script with the correct blowfish encryption key for Back To The Future to work. (He mentioned this game on his site for this tool so probably just a matter of time) I dont know which files he needs to get the encryption key but I can provide the file(s) if needed. Really looking forward to getting some models from this one
## Post #207
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-12-25T16:12:40+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Allright, we began the translation...
Now the question is, how can I edit the font?
Can somebody tell me about this detailed way?
Edit:
We cannot translate the menu?! Whats wrong?
And, in hex editor, text is like that;
Game PausedPress Spacebar to Resume
But, when I copy it to here, its like;

Game Paused
Press Spacebar to Resume
## Post #208
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2010-12-25T21:58:31+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello everyone!!

I'm translating "Back to the Future the Game" in ITALIAN.. if there's someone (italian eheh) that wants to help me, he can contact me on my e-mail address!! Thank you very much to all!!
## Post #209
- Username: venomtrk
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 28, 2009 5:36 am
- Post datetime: 2010-12-25T23:45:53+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Crybio
>
> Hello everyone!!

I'm translating "Back to the Future the Game" in ITALIAN.. if there's someone (italian eheh) that wants to help me, he can contact me on my e-mail address!! Thank you very much to all!!

Hi Crybio, we are translating this game to Turkish language. We can edit in-game dialogs but we couldn't edit in game menus. Can you help me about this problem ?
## Post #210
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2010-12-26T09:32:37+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

What method are you using?

I'm working directly on "0_dlog.ttarch" file, this is an example of Main Menu

[http://img63.imageshack.us/img63/218/sc ... a19280.png](http://img63.imageshack.us/img63/218/schermata20101225a19280.png)

Anyway, can you tell me what is your working method? So I can help in some way
## Post #211
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2010-12-26T11:12:32+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Am I to understand the current tool opens BTTF ttarch files (like 1_BackToTheFuture101_pc_data, 4_BackToTheFuture101_pc_tx) etc?

What "game number" are you choosing in the command line to make this work? (there are 40 of them!)

Thanks!
## Post #212
- Username: venomtrk
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 28, 2009 5:36 am
- Post datetime: 2010-12-26T13:56:51+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Crybio
>
> What method are you using?

I'm working directly on "0_dlog.ttarch" file, this is an example of Main Menu

http://img63.imageshack.us/img63/218/sc ... a19280.png

Anyway, can you tell me what is your working method? So I can help in some way

We extract landb files with ttarchext program. And than we use tt tools to extract txt files from landb files. There are 27 files (english) in the 0_dlog.ttarch and we translate these text files and put them back. Maybe tt tools program needs to be updated.

We can see translated in-game dialogs. We also translate in-game menus but it is still in English, I couldn't understand that.

Are you using hex editors or something for  "0_dlog.ttarch" file?  We really need some help for that, maybe we need to change the method
## Post #213
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2010-12-26T17:57:28+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Are you using hex editors or something for "0_dlog.ttarch" file? We really need some help for that, maybe we need to change the method

Yes, I open the "0_dlog.ttarch" file with an Hex editor (in my case it is "0xED" for Mac) and replace the text  that i found during the game.. It's a very very slow method because i need to play the game and write down all the text, then I must search them inside the file and finally replace in other language.. it's the only method I know but i can change everything i need to change, including  menu text.. 

Where can I download the "ttarchext program" and the "tt tools"? So I take a test.. Thanks!
## Post #214
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2010-12-27T12:40:33+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Could someone tell me the blowfish key used to unpack BTTF .ttarch files?

Thank you!
## Post #215
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-12-27T19:10:50+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

How can I edit the font of BTTF game?
## Post #216
- Username: tsl16b
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Dec 27, 2010 8:16 pm
- Post datetime: 2010-12-28T12:00:07+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from qabRieL
>
> How can I edit the font of BTTF game?  :)

Here's my solution:
- Extract .font files
- Open a .font file in hex editor
- Find 'DDS' string (that's the font DDS texture header)
- Select all bytes to the end of file
- Write selected block to disk as <somefont>.dds
- Edit .dds file to your needs in a suitable bitmap editor (font's in the alpha channel of the image), don't change its format in any way (DXT5 - Interpolated Alpha)
- Replace block (in the hex editor) to the new file. Or alternatively, truncate the .font file at the 'DDS' byte position and append the new .dds file to its end.
## Post #217
- Username: venomtrk
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 28, 2009 5:36 am
- Post datetime: 2010-12-29T02:44:31+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from TavoT
>
> Could someone tell me the blowfish key used to unpack BTTF .ttarch files?

Thank you!

New ttarch program has been released.

[http://aluigi.org/papers.htm#ttarchext](http://aluigi.org/papers.htm#ttarchext)
## Post #218
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2010-12-29T11:45:49+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from venomtrk
>
> TavoT wrote:Could someone tell me the blowfish key used to unpack BTTF .ttarch files?

Thank you!

New ttarch program has been released.

http://aluigi.org/papers.htm#ttarchext

Awesome! Thanks!
## Post #219
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2010-12-29T14:46:47+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Here's my solution for edit *.FONT.
1) Open TTG Tools.
2) Click "Font Editor". 
3) Open file
4) Click on row with need texture in first table and choose "Export"
5) Edit dds. (You can change size of dds)
6) Step 1-4 
7) Click on row with need texture in table and choose "Import"
8 ) edit in second table coordinates of char. If you need.
9) Save your font.
Have fun.
[TTG Tools.rar](https://xentaxbackup.github.io/file/3735_TTG Tools.rar)
## Post #220
- Username: nofear
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 29, 2010 3:23 am
- Post datetime: 2010-12-29T16:34:43+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

which program i can use to edit landb and dlog files?!?
## Post #221
- Username: StarWarsFan786
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 09, 2010 6:03 pm
- Post datetime: 2010-12-30T19:43:33+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I'm sorry, i can't figure out how to extract a ttarch file from the back to the future game. I need to extract the archive that contains the music. Could an experienced user please extract the "3_BackToTheFuture_ms_pc.ttarch" file for me? I know you guys all want to translate the game but could someone please help me? Also, if you're extracting the file with ttarchext, could you please use the option to automatically convert the music to .ogg files? Any help would be greatly appreciated.
## Post #222
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2010-12-30T19:48:17+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Try this

```
ttarchext -m 41 "C:\Program Files\Telltale Games\Back to the Future The Game\Episode 1\Pack\3_BackToTheFuture101_pc_ms.ttarch" C:\Output
```
## Post #223
- Username: StarWarsFan786
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 09, 2010 6:03 pm
- Post datetime: 2010-12-30T20:22:03+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from TavoT
>
> Try this
Code: Select allttarchext -m 41 "C:\Program Files\Telltale Games\Back to the Future The Game\Episode 1\Pack\3_BackToTheFuture101_pc_ms.ttarch" C:\Output
Thanks alot!!! I'm listening to the music right now
## Post #224
- Username: LordVoland
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 25, 2010 5:19 am
- Post datetime: 2011-01-04T19:29:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi. Could any body help. I`ve alredy unpack ttarch files, but I can`t translate whem. TTG Tools no helps. Не получается автопакером распаковать файлы. Ни импорт, ни экспорт не срабатывают
## Post #225
- Username: LordVoland
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 25, 2010 5:19 am
- Post datetime: 2011-01-04T19:35:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I foget it`s - Back to the future The game
## Post #226
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2011-01-04T20:06:06+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Check out a couple of messages above, Den Em has posted the updated version of TTG Tools to work with BTTF Game
## Post #227
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2011-01-06T09:25:28+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

LordVoland
Oh dear, another one. О г-споди, ещё один.
## Post #228
- Username: hjchen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 17, 2009 11:22 am
- Post datetime: 2011-01-12T14:57:58+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from qerqer
>
> Den Em wrote:qerqer wrote:Hi, Den Em. Do you have tools for Puzzle Agent? For landb files?
Yes. =)
Thanks very, very much.

Dear Dem Em:
                           I have dlog files how can i use your new tool to get the text file?  many thanks for help.   I am working on the "back to the future" episode one.  


Howard
## Post #229
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2011-01-12T15:02:26+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Unpack the file 0_dlog.ttarch with ttarchext tool, then put the files you get in "input" folder of TTG Tools. Use auto depacker to get the txt files
## Post #230
- Username: hjchen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 17, 2009 11:22 am
- Post datetime: 2011-01-13T14:53:18+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from TavoT
>
> Unpack the file 0_dlog.ttarch with ttarchext tool, then put the files you get in "input" folder of TTG Tools. Use auto depacker to get the txt files
Many thanks for very kind help.      I can use TTG to decode the *.dlog files but in the output folder i got all the text files with empty content.  Can you help?
[some files.rar](https://xentaxbackup.github.io/file/3795_some files.rar)
## Post #231
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2011-01-13T18:40:05+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

You have to put the *_english.landb files in the "Input" to get the game texts , like this:
## Post #232
- Username: hjchen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 17, 2009 11:22 am
- Post datetime: 2011-01-15T16:08:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I have difficulties in using the TTG tools v061 to extract BTTF english subtitles? I wonder if anyone can provide a short guide.  I do not follow the config part.  Many thanks for help.   

howard chen
## Post #233
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-02-15T20:46:58+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello guys, I'm new in here

Well, first I wanna thank all of you, you helped so much
I've done everything so great until now, and I have all the programs I need to translate
only one little problem..
I do NOT have an Arabic font.dds =\ (btw I wanna translate Tales Of Monkey Island to Arabic language)

So I'll need to replace the dds file in weathered_sf_30.font with an Arabic dds file
so the only thing I need is that Arabic dds file lol...
Or else I'll have to "draw" every letter using GIMP or any other .dds editor xD
## Post #234
- Username: venomtrk
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 28, 2009 5:36 am
- Post datetime: 2011-02-17T17:18:16+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

We're translating Bttf EP2 , we already translated EP1.

But we need importing tool. Waiting for it...

[http://aluigi.org/papers.htm#ttarchext](http://aluigi.org/papers.htm#ttarchext)
## Post #235
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-21T22:59:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

released the new version just now.
anyway please send me a mail when a new game of Telltale is released so that I can update the tool or publish directly the key on the fly
## Post #236
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2011-02-22T01:08:36+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I was waiting for it, thanks!

I'll let you know when the next episodes are launched
## Post #237
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-02-23T20:03:37+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I've downloaded the Langdb Editor which was released in this thread
It only has (1251 Russian and 1252 Latin encoding)
I need to make it 1256 Arabic encoding...is there anyway I can do that?
And how to use that "Change way to ABC of Transliteration" thing? I don't understand it
PLZ help me
## Post #238
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2011-02-28T05:55:58+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

error
Use a TTG Tools for it.
## Post #239
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-03-01T18:56:16+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Den Em
>
> error
Use a TTG Tools for it.

Honestly I didn't figure out how to use the TTG Tools except for the Font Editor
other functions...idk about em lol
Is there a way to edit the english.langdb file using it?
## Post #240
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2011-03-01T19:17:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

You have to put english.landb files in the INPUT folder, and then open TTG Tools, Click "Auto (De) Packer" button, and then in the screen that shows up, click the button "Decrypt, Export", then in the OUTPUT folder you will have the TXT files, ready for edit them
## Post #241
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-03-01T21:08:39+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from TavoT
>
> You have to put english.landb files in the INPUT folder, and then open TTG Tools, Click "Auto (De) Packer" button, and then in the screen that shows up, click the button "Decrypt, Export", then in the OUTPUT folder you will have the TXT files, ready for edit them

Already tried that...didn't work, first it gave me an error saying (can't find the path F:\BttF-TG\ïهًهâîن)

So I changed the Config.txt file to the Input, Output, Temp and ttarchext.exe right locations
and tried to decrypt again...but nothing happened, didn't give me an error , but didn't decrypt either...the english.langdb is still in the input folder and nothing is in the output
## Post #242
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2011-03-01T22:05:09+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Well, I remember having the same problem, and after a couple of times touching the config file started to work... You gonna have to wait for Den Em for more advice, this is all I can tell you
## Post #243
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-03-01T22:09:41+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

do I have to put a .ttarch or a .langdb file in the INPUT folder?

I'm wondering since it says I have to locate the ttarchext.exe....

anyways I tried both ttarch and langdb and none worked :S
## Post #244
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2011-03-01T22:12:51+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

i've used .landb files

Also, make sure you have .Net Framework 3.5 installed, TTG Tools doesn't work without it
## Post #245
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-03-01T22:16:28+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I believe I do have it installed...how to check tho?
## Post #246
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-03-01T22:18:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

nvm found it..it's installed...I've got aa..
Microsoft .NET Framework 2.0 Service Pack 2
Microsoft .NET Framework 3.0 Service Pack 2
Microsoft .NET Framework 3.5 SP1

I have these 3
## Post #247
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2011-03-01T22:19:53+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Then that's not your problem... Beats me... wait for Den Em to answer, he's the author of TTG Tools, he will be of more help than me
## Post #248
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-03-02T23:35:10+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hey Dem Em, can u help me? I've got a problem..I can't use ur TTG tools to decrypt english.langdb
## Post #249
- Username: harpseal
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:48 am
- Post datetime: 2011-03-03T23:57:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Thank you guys.Ttg tools & ttarchext work's correctly.
## Post #250
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2011-03-06T14:32:07+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from error
>
> F:\BttF-TG\ïهًهâîن
Use only a latin text in path for folder.
P.S. I answered on you letter. Any progress?
## Post #251
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-03-06T21:36:06+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

okay, I give up >.< I tried everything with that Auto(De)Packer..but it doesn't work
I even tried it in 2 different computers, none worked
when I click on the Export button, NOTHING happens, totally NOTHING
I tried all choices: (others, Sam & Max 201, Sam & Max 202.....etc) nothing happens

Here's my TTG tools in the attachment, can u plz check it out? see if it has something wrong?
P.S: My TTG Tools folder is located in E:\

EDIT:
owh, I've just tried it on a landb file, and it worked, but langdb doesn't work 
[TTG-Tools.rar](https://xentaxbackup.github.io/file/4018_TTG-Tools.rar)
## Post #252
- Username: Den Em
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Aug 11, 2009 12:23 am
- Post datetime: 2011-03-07T11:53:55+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from error
>
> Here's my TTG tools in the attachment, can u plz check it out? see if it has something wrong?

Okey. This version don't work with LANGDB. =)
Attached will be work (I hope.).
[Debug.rar](https://xentaxbackup.github.io/file/4023_Debug.rar)
## Post #253
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-03-07T17:25:04+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Den Em
>
> error wrote:Here's my TTG tools in the attachment, can u plz check it out? see if it has something wrong?

Okey. This version don't work with LANGDB. =)
Attached will be work (I hope.).

Yep it works  TY TY TY :}
## Post #254
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-03-07T20:25:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Well, one more problem, Arabic is a RIGHT TO LEFT language..
so when I change (Save & Load) to (سجل و حمل) in the english.txt file, then pack it to langdb
I open the packed english.langdb using HxD  and that's what I get

D3 CC E1 20 E6 20 CD E3 E1      ل م ح  و  ل ج س

So when I run the game it appears flipped, if u know what I mean
the character ل is supposed to be the last letter (From right to left) but it appears as the first letter..and same with other letters

so is there anyway to flip the text in the english.txt file? so that it's double flipped in the game and it returns to normal lol

EDIT:
never mind, my sister helped me with that using NetBeans, but I didn't test it yet, gotta go to bed 

There's something else I wonder if u can help me with

[http://www.youtube.com/watch?v=I4PrNenvcIU](http://www.youtube.com/watch?v=I4PrNenvcIU)

See in this video, the subtitles appear from left to right, so if it's in arabic, it'll appear from left to right, which means from  last to first, so is there anyway to change the way the subtitles appear? even if they'll just appear all words at the same time
## Post #255
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-03-08T21:49:05+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

See in the Hex editor, before every line there some bytes, around 31 bytes, sometimes more sometimes fewer
What are these bytes for? Do they have anything to do with how the word appears?
For example, a subtitle line said by SOMEONE appears from left to right, they appear one letter by the other, but an ITEM name just appears all at the same time, and so is the Main Menu options (New Game, Save & Load....etc)

so do these bytes control that? And if they do...can someone tell me how to make all subtitles said by SOMEONE just appears all at the same time like ITEM names?

see the pics ...may help


Main Menu -> Settings

By [gogelolo](http://profile.imageshack.us/user/gogelolo) at 2011-03-08

Main Menu -> Save & Load

By [gogelolo](http://profile.imageshack.us/user/gogelolo) at 2011-03-08

Guybrush speaking

By [gogelolo](http://profile.imageshack.us/user/gogelolo) at 2011-03-08

CrimpDigit speaking

By [gogelolo](http://profile.imageshack.us/user/gogelolo) at 2011-03-08

Interact-able Item

By [gogelolo](http://profile.imageshack.us/user/gogelolo) at 2011-03-08

Carry-able Item

By [gogelolo](http://profile.imageshack.us/user/gogelolo) at 2011-03-08
## Post #256
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2011-03-09T18:10:28+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I keep facing problems one after one >.<
There's only one thing that will fix all these problems: make the game typings go from right to left
(which means, if I type "Happy..." in the english.langdb file, it appears ingame like this "...yppaH")

I've tried the flipping thing...but it led to more troubles:

1- The typings go from bottom to top, like this 

(is Guybrush)
(Hi my name)  but in arabic lol

2- The 2nd line doesn't start from the very right, but it ends at the very left...like this:


3- If a sentence has 3 line for example, it'll first show the 1st and 2nd (which are the 2nd and 3rd of arabic translation) then it'll show the 3rd (which is the 1st in arabic translation


and maybe I'll face more troubles..
But they all can be fixed if I could somehow make the game type from RIGHT TO LEFT
anyone got an idea?

I've found some files who has the word "text" in their names but I couldn't even open them lol...see them in attachment, see if they can help
[Some files.rar](https://xentaxbackup.github.io/file/4028_Some files.rar)
## Post #257
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2011-03-16T02:50:07+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi everybody, i'm trying to translate  Sam & Max 104: Abe Lincoln Must Die to brazillian portuguese, and i used the [Telltale Explorer](http://quick.mixnmojo.com/telltale-explorer) to open the .ttarch file, extracted the english.langdb and used the Notepad++ to translate some strings. i need help to rebuild the ttarch and edit the font files; I read the whole thread, but i'm kinda noob with the tools. i'm begginer in game translations. thanks everyone.
## Post #258
- Username: REM1X
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 06, 2011 10:58 pm
- Post datetime: 2011-04-28T13:00:49+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Helo World!
How about extracting files new game from Telltale: Hector: Badge of Carnage - Episode 1?
## Post #259
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-29T09:19:16+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I will add support for Hector when will be released the upcoming BTTF episode
## Post #260
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-29T17:14:04+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

released ttarchext 0.1.12:
[http://aluigi.org/papers.htm#ttarchext](http://aluigi.org/papers.htm#ttarchext)
## Post #261
- Username: TavoT
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jul 31, 2009 9:04 pm
- Post datetime: 2011-05-06T12:53:26+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Use TTG Tools, Den Em posted it a few messages above, it can pack and unpack langdb files to txt and back to langdb
## Post #262
- Username: soring123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 07, 2011 11:35 am
- Post datetime: 2011-06-13T04:08:14+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Sorry to open the old topic. Telltale game is really famous.

We are a group of Chinese fans. We would like to translate ToMI into Chinese.
We got learn to unpack and rebuild the ttarch file. But we have a problem about the subtitle display now.

But Chinese is 2 bytes language. English is a 1 byte language. We think that might be the problem. 

Anybody know how to make this game to run with 2 bytes language? Assemble?

Thx!
## Post #263
- Username: REM1X
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 06, 2011 10:58 pm
- Post datetime: 2011-07-02T14:44:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Helo World!
Puzzle Agent 2 released!
but ttarchext.exe dont support version 9
## Post #264
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2011-07-02T15:36:42+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

As far as I'm aware - it does:

```
    if((version < 1) || (version > 9)) {
        printf("\nError: version %d is not supported yet\n", version);
        exit(1);
    }
```
## Post #265
- Username: REM1X
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 06, 2011 10:58 pm
- Post datetime: 2011-07-02T15:54:03+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

oh, sorry, my bad)
it was old version)
thx for answer)
## Post #266
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2011-07-11T23:52:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

That's strange but I still have problem with Sam and Max 201.

I extracted english.langdb file, edited it and then I wanted rebuild it to SamMax201_english.ttarch. But when I do this, SamMax201_english.ttarch is now only 335 kb instead of 210MB. When I try to launch game, there is black screen. It really gest my nerve.

Could somone check it and step by step explain it to me?

Thanks in advance.
## Post #267
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2011-08-05T00:32:40+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Anyone? I need comennds for S&M 201. Alugi only posted in ttarch program commends to TOMI. I have tried everything and it doesn't work.

ttarchext.exe -b -V 7 12 "C:\0.ttarch" c:\input_folder

NOTHING! Please, answer me!
## Post #268
- Username: Okashu
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 18, 2010 1:03 am
- Post datetime: 2011-08-27T13:19:48+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi, can anyone tell me how to use ttg tools with dlogs from sam & max season 3?

Here's what I do
1. paste original dlog in "Input" folder
2. Decrypt
3. Translate txt file
4. Put translated txt in "Input" folder
5. Encrypt
6. Paste translated .dlog in "Pack" folder

Unfortunatelly, when i test it, texts are still in english. What did I do wrong?
(strangely, I managed ui_mainmenu.dlog to work, but i dont know how)

EDIT: nevermind. I was editing wrong dlog. But i have another question. What's the font used in game? ttarch has 20 font files, but it containts all fonts used in all seasons
## Post #269
- Username: MeteoraMan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jul 08, 2010 4:39 am
- Post datetime: 2011-11-16T18:29:16+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

How about the encryption key for Jurassic Park ?

exe file: [http://www.multiupload.com/VOPZT5WQ4X](http://www.multiupload.com/VOPZT5WQ4X)
## Post #270
- Username: MAXVIDSTUDIO
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 17, 2011 9:03 am
- Post datetime: 2011-11-17T12:24:26+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

MeteoraMan
Go to ZOG =) I found it - 89DE9F9597DF9CA6C2CDE7CF639583A1DE9C8EEAB0DE99BFC693DA86699CABA9D1A6A5C2CAC689CDE7DFA99C677CC7E1A6D6999CD3C2A0
## Post #271
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-20T16:51:32+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

*edit (my fault, the key is correct)*
## Post #272
- Username: MAXVIDSTUDIO
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 17, 2011 9:03 am
- Post datetime: 2011-11-20T23:32:08+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

aluigi
You think? This is weird. Because with your key - not extracted at all.
But with this key - 89DE9F9597DF9CA6C2CDE7CF639583A1DE9C8EEAB0DE99BFC693DA86699CABA9D1A6A5C2CAC689CDE7DFA99C677CC7E1A6D6999CD3C2A0 - everything extracted.
Look, your key is from original exe, right?
[](http://fastpic.ru/view/32/2011/1121/679553eb52a4f931286bcf4f8595638c.jpg.html)
But my key from cracked exe (FLT)
[](http://fastpic.ru/view/28/2011/1121/42823d5e2c148f66014def4f85c00be4.jpg.html)
And works fine
## Post #273
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-22T18:44:18+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

yeah sorry, my fault.
lately I'm loosing my mind so don't worry if I release wrong posts like the previous one :)

the important thing is that everything works perfectly.
## Post #274
- Username: newbie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 23, 2011 10:36 pm
- Post datetime: 2011-11-23T14:38:51+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

how do you insert the key for decryption of Jurassic Park?
## Post #275
- Username: MAXVIDSTUDIO
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 17, 2011 9:03 am
- Post datetime: 2011-11-23T14:53:08+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from newbie
>
> how do you insert the key for decryption of Jurassic Park?
For example:

```
ttarchext.exe -k 89DE9F9597DF9CA6C2CDE7CF639583A1DE9C8EEAB0DE99BFC693DA86699CABA9D1A6A5C2CAC689CDE7DFA99C677CC7E1A6D6999CD3C2A0 "C:\1_JurassicPark101_english_pc_data.ttarch" "C:\output_folder"
```
## Post #276
- Username: k0sty4n
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 02, 2011 5:08 am
- Post datetime: 2011-11-24T09:05:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

aluigi, please create a GUI for your program
## Post #277
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-11-24T14:49:38+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from k0sty4n
>
> aluigi, please create a GUI for your program
Well said.
## Post #278
- Username: nahuel36
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 31, 2012 6:50 pm
- Post datetime: 2012-03-31T11:16:41+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

how about translating an iphone version?
i tried, i decrypted the file with langdb file (tomi 4, file 0_7_patch.ttarch), but i cant encript the file. Even encrypting with the original files, the game crashes. 
there is a way to find the encryption key? (there isn't exe file)


PD: sorry for my english
## Post #279
- Username: MAXVIDSTUDIO
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 17, 2011 9:03 am
- Post datetime: 2012-04-24T19:51:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

The key for The Walking Dead ep. 1 is:

```
96CA999F8DDA9A87D7CDD9956295AAB8D59596E5A4B99BD0C9529F8590CDCD9FC8B39993C6C49D9DA5A4CFCDA39DBBDDACA78B94D4A36F
```
## Post #280
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-04-25T10:51:04+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from MAXVIDSTUDIO
>
> The key for The Walking Dead ep. 1 is:
Code: Select all96CA999F8DDA9A87D7CDD9956295AAB8D59596E5A4B99BD0C9529F8590CDCD9FC8B39993C6C49D9DA5A4CFCDA39DBBDDACA78B94D4A36F

Any idea where are all texts and Fonts please ?
## Post #281
- Username: MAXVIDSTUDIO
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 17, 2011 9:03 am
- Post datetime: 2012-04-25T11:35:17+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from michalss
>
> Any idea where are all texts and Fonts please ?
in 2_WalkingDead101_english_pc_data.ttarch
## Post #282
- Username: sylar07
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 25, 2012 9:20 pm
- Post datetime: 2012-04-25T13:38:09+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Dude thanks for the code of The Walking Dead I needed a lot!
 now I have a different problem ... when I re-compile the file "2_WalkingDead101_english_pc_data.ttarch" he gets to about 19 Mb if I'm not mistaken, and then replace the original and the game does not open.

 Please give me a hint or help, What is the correct way to compile this program since it does not have The walking dead? and as if I run the file without errors?

Thank's
## Post #283
- Username: Fenris93
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Jul 20, 2010 6:51 am
- Post datetime: 2012-04-25T15:18:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Thanks for the key  But i can't repack .txt to .landb with TTG Tools :S Anyone knows how to? Thanks.
## Post #284
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-04-25T16:04:18+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Fenris93
>
> Thanks for the key  But i can't repack .txt to .landb with TTG Tools :S Anyone knows how to? Thanks.

same here does not work:(
## Post #285
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-25T16:36:54+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

So aluigi updated Telltale TTARCH files extractor/rebuilder 0.1.13a
added Walking Dead: A New Day

[http://aluigi.org/papers/ttarchext.zip](http://aluigi.org/papers/ttarchext.zip)

What is encrypted .lenc? the same as .ttarch - blowfish key?
## Post #286
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-04-25T17:33:43+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Ekey
>
> So aluigi updated Telltale TTARCH files extractor/rebuilder 0.1.13a
added Walking Dead: A New Day

http://aluigi.org/papers/ttarchext.zip

What is encrypted .lenc? the same as .ttarch - blowfish key?

new tool does not work some library is missing!
## Post #287
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-25T18:09:33+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Here dll
[libssp-0.rar](https://xentaxbackup.github.io/file/5365_libssp-0.rar)
## Post #288
- Username: Smash15195
- Rank: beginner
- Number of posts: 24
- Joined date: Fri Apr 08, 2011 4:35 am
- Post datetime: 2012-04-25T19:56:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from michalss
>
> Fenris93 wrote:Thanks for the key  But i can't repack .txt to .landb with TTG Tools :S Anyone knows how to? Thanks.

same here does not work:(

Same thing for me, decrypt works fine, encrypt not.
## Post #289
- Username: darkblackeye
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 26, 2012 1:51 am
- Post datetime: 2012-04-26T09:46:03+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Well, I get the encoded *.landb, by putting the edited txt into the input folder, but it seems corrupt in any way. The Game doesen't continue from the "connecting" window but it doesn't freeze, crash or anything like this, either. Just changing single letters without TTG works..
I use this command Line for ttarch encoding:

```
ttarchext -b -x -V 8 52 c:\output-file "c:\input-folder
```

Tried -V 9, but resulted just in an Appcrash at start, V 8 seems to work.
## Post #290
- Username: wicktor
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 26, 2012 1:07 am
- Post datetime: 2012-04-26T11:24:29+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from darkblackeye
>
> Well, I get the encoded *.landb, by putting the edited txt into the input folder, but it seems corrupt in any way. The Game doesen't continue from the "connecting" window but it doesn't freeze, crash or anything like this, either. Just changing single letters without TTG works..
I use this command Line for ttarch encoding:
Code: Select allttarchext -b -x -V 8 52 c:\output-file "c:\input-folder
Tried -V 9, but resulted just in an Appcrash at start, V 8 seems to work.

with -V 9 the game crashes here too, but with -V 8 works fine, let's try it with a cracked exe
## Post #291
- Username: mikaelN7
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 25, 2012 11:16 pm
- Post datetime: 2012-04-26T14:54:15+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Don't mean to hijack this thread, I have a question about the audio. I was trying to extract the dialogue using aluigi's tool and the .vox files sound distorted/corrupt. Can anyone see if you get the same result? I was extracting from 
```
3_WalkingDead101_english_pc_voice.ttarch
```

I tried extracting the sound effects from 4_WalkingDead101_english_pc_ms.ttarch which are .aud and those sound fine.
## Post #292
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-26T19:58:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

the libssp problem has been fixed this morning, so if you redownload the tool now it works as usual.

remember to send me a mail when you see a problem in one of my tools so I will not miss it
## Post #293
- Username: sylar07
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 25, 2012 9:20 pm
- Post datetime: 2012-04-27T01:00:05+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

You know some program to edit .landb? and how can I write more characters in a word for example:

 "New Game"
 "Nuevo Juego"
## Post #294
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-04-27T08:01:01+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

sylar07
[viewtopic.php?p=72306#p72306](http://forum.xentax.com/viewtopic.php?p=72306#p72306)
## Post #295
- Username: sylar07
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 25, 2012 9:20 pm
- Post datetime: 2012-04-27T13:26:17+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Haoose
>
> sylar07
viewtopic.php?p=72306#p72306

I love you man lol
i will try it, thank you.
## Post #296
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-04-27T18:40:24+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Haoose
>
> sylar07
viewtopic.php?p=72306#p72306
I could not find online link that tool...
Thank you man.
## Post #297
- Username: kamiyoru
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 27, 2012 1:47 am
- Post datetime: 2012-04-29T18:03:50+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Someone know how to change the font in "The Walking Dead" to accept all characters with accents like "ç" or "ê" ?
## Post #298
- Username: Johnny
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 17, 2010 1:21 am
- Post datetime: 2012-04-29T18:53:45+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

It actually does support the characters you mentioned. At least the main dialog font cheapsignage_50.font. Although TTG Tools don't allow you to edit them, they allow you to export the DDS files, so you can see what I'm talking about. Just open the font in font editor, click yes on the error and use the right mouse button on the upper table. You should see the options.

But it would be nice to get TTG Tools to fully work with The Walking Dead fonts.
## Post #299
- Username: kamiyoru
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 27, 2012 1:47 am
- Post datetime: 2012-04-29T19:33:03+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

In fact, the font support the accent in all notifications and all messages are here (not in uppercase) but, in dialogs options, the accents are displayed as square ...
## Post #300
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-05-07T07:21:10+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

any luck about Fonts pls ?
## Post #301
- Username: Goldenboy22
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 16, 2012 2:16 pm
- Post datetime: 2012-05-16T06:35:16+00:00
- Post Title: 

Hi guys !!! I'm trying to translate PS3 version of TALES of MONKEY ISLAND (ep1).But ttarchext can't extract/rebuild ttarch's correctly from .pkg . I'm working on this file:

0_2patch.ttarch
0_patch.ttarch
1_MonkeyIsland101_ps3_data.ttarch <- This contain langdb
2_MonkeyIsland101_ps3_voice.ttarch
3_MonkeyIsland101_ps3_ms.ttarch
4_MonkeyIsland101_ps3_tx.ttarch

I tried only to extract and rebuild with ttarchext 0.1.13a without modify anything and it gives me black screen. So i suppose that they have changed the blowfishkey/encryption for the console version.

Someone have experience with the translation of CONSOLE VERSION of TELLTALEGAMES??
Or someone can help me the structure of this file??

PS: After some other research i found that 0_2patch.ttarch e 0_patch are unencrypted. So i think i will create a 0_3patch.ttarch with the translated .langdb .The only problem  
      is:" can ttarchext be able to create an unencrypted patch file??? UNENCRIPTED


THANKS for you answers.
## Post #302
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-08-10T17:59:09+00:00
- Post Title: 

michalss -- until the next update of TTG Tools which may or may not happen, the fonts have to be edited... err... well, the 'hacky' way.

1. Rename all .font to .d3dtx and move'em to Input.
2. Decrypt to .dds with TTG Tools.
3. Open .dds in Photoshop. You'll see white squares. In Layers, switch to Alpha Channel. You'll see the font.
4. Here's the tricky part. Replace the characters your language does not use with the characters it uses and note the changes somewhere. Save your files and encrypt them back to d3dtx and rename to .font.
5. In text files, replace your localized chars with the symbols you changed to your chars.

Done.
## Post #303
- Username: Ton4o
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 01, 2012 4:11 am
- Post datetime: 2012-09-01T09:42:39+00:00
- Post Title: 

I am not sure if this problem has already been discussed but I've got an issue with the ttrachext program. When I try to rebuild a .ttarch archive I get Error: wrong argument (24). I'm using ttarchext.exe -b -V 7 24 and the game is BTTF 1. Maybe I am doing something wrong?

EDIT: Solved. It turned out that I was trying to build a 0.ttarch file out of everything in the original ttarch but not just out of the edited stuff.
## Post #304
- Username: Keeperv85
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 06, 2010 8:41 am
- Post datetime: 2012-10-16T17:34:41+00:00
- Post Title: 

Hi all, can anyone tell me how can i translate Puzzle Agent 2?

Here's what I do:
1. Extract 1_Grickle102_english_pc_data.ttarch with this command: 
ttarchext.exe -f "*.langdb" 36 "d:\TTARCH\1_Grickle102_english_pc_data.ttarch" D:\TTARCH\out
2. Decrypt the ui_menu_english.landb with TTG Tools
3. Translate "old" txt file 
4. Put translated txt in "Input" folder
5. Encrypt 
6. Paste translated landb in "out" folder, and repack with this:
ttarchext.exe -b -V 9 36 ""d:\TTARCH\0.ttarch" D:\TTARCH\out
7, Copy new patch file in "Pack" folder

Unfortunatelly, when i test it, texts are still in english. What did I do wrong?
## Post #305
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-01-12T13:38:44+00:00
- Post Title: 

> Reply from Delacroix
>
> michalss -- until the next update of TTG Tools which may or may not happen, the fonts have to be edited... err... well, the 'hacky' way.

1. Rename all .font to .d3dtx and move'em to Input.
2. Decrypt to .dds with TTG Tools.
3. Open .dds in Photoshop. You'll see white squares. In Layers, switch to Alpha Channel. You'll see the font.
4. Here's the tricky part. Replace the characters your language does not use with the characters it uses and note the changes somewhere. Save your files and encrypt them back to d3dtx and rename to .font.
5. In text files, replace your localized chars with the symbols you changed to your chars.

Done.

About step 4, what if there are too many characters I uses, so there aren't enough characters?
Could you please kindly tell me how to add new characters into the .font?
## Post #306
- Username: SileniusLegard
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jul 25, 2010 7:00 am
- Post datetime: 2013-01-13T11:14:13+00:00
- Post Title: 

I translated Puzzle Agent 1 long time ago, and worked, but now that I've translated Puzzle Agent 2, I'd wanted replay PA1, but my patch doesn't work, : S
I've realize PA1 was updated, so I'm looking for changes but the actual TTG Tools doesn't encrypt after editing, I don't understand it, and the TTG version that I used then doesn't work now probably for that's incompatible with new ttarchext.
Then PA1 is unedited now? : (((
Any tip?

Keeperv85, PA2 is 47 in ttarchext.
## Post #307
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2013-03-23T17:30:27+00:00
- Post Title: 

hi ttg tools can't decrypt puzzle agent 1 here the update file from steam ( 1_Grickle101_pc_data.ttarch ) : [http://uptobox.com/xld6rbb3p963](http://uptobox.com/xld6rbb3p963)
## Post #308
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2013-04-27T18:56:17+00:00
- Post Title: 

anyone got blowfish key for Poker Night 2? TIA
## Post #309
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-04-28T09:34:16+00:00
- Post Title: 

Aluigi already updated his ttarchext tool to support Poker Night 2.

BTW Thanks Aluigi
## Post #310
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2013-04-28T20:09:56+00:00
- Post Title: 

yes he did. but TG also made some changes and now files in ttarch are compressed or something. at least d3dtx and font files. -m option does not export dds, and TTG Tools don't open font files.
## Post #311
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-04-29T06:49:12+00:00
- Post Title: 

Yeah, d3dtx are now headerless DDS (sometimes normal PNGs). And header section has different length, from file to file :/
## Post #312
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2013-04-29T08:35:39+00:00
- Post Title: 

PNG usage explain different texture size vs PN1 - both games share some resources. grrr, i've hoped for fast and easy translation.
## Post #313
- Username: Smash15195
- Rank: beginner
- Number of posts: 24
- Joined date: Fri Apr 08, 2011 4:35 am
- Post datetime: 2013-06-01T11:00:20+00:00
- Post Title: 

For Puzzle Agent (extract langdb) Telltale Explorer works great : [http://quickandeasysoftware.net/softwar ... e-explorer](http://quickandeasysoftware.net/software/telltale-explorer)
## Post #314
- Username: SileniusLegard
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jul 25, 2010 7:00 am
- Post datetime: 2013-08-12T18:28:25+00:00
- Post Title: 

> Reply from Smash15195
>
> For Puzzle Agent (extract langdb) Telltale Explorer works great : http://quickandeasysoftware.net/softwar ... e-explorer
Extract is not the problem, the problem is to recompile... and as far as I know, doesn't work for that...
## Post #315
- Username: error
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Feb 15, 2011 7:42 am
- Post datetime: 2013-08-22T01:05:38+00:00
- Post Title: 

I have a question...

Is there anyway to change the game's coding from ASCII to Unicode? I hope I haven't gone too far

The reason is I'm trying to translate it to Arabic, and ASCII doesn't support Arabic characters, plus the Arabic letters' shape changes depending on their position in the word (in the first, middle, or end), and ASCII doesn't support all that.

Any ideas?
## Post #316
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-10-11T18:24:24+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

The Wolf Among Us - Episode 1
New format

```
_resourcedescriptions_500_Boot.lenc
_resourcedescriptions_500_Engine_Lua.lenc
_resourcedescriptions_500_Fables101.lenc
_resourcedescriptions_500_Menu.lenc
_resourcedescriptions_500_Project.lenc
_resourcedescriptions_500_Shaders.lenc
Fables_pc_Boot_anichore.ttarch2
Fables_pc_Boot_data.ttarch2
Fables_pc_Boot_ms.ttarch2
Fables_pc_Boot_txmesh.ttarch2
Fables_pc_Engine Lua_data.ttarch2
Fables_pc_Fables101_anichore.ttarch2
Fables_pc_Fables101_data.ttarch2
Fables_pc_Fables101_ms.ttarch2
Fables_pc_Fables101_txmesh.ttarch2
Fables_pc_Menu_anichore.ttarch2
Fables_pc_Menu_data.ttarch2
Fables_pc_Menu_ms.ttarch2
Fables_pc_Menu_txmesh.ttarch2
Fables_pc_Project_all.ttarch2
```

Screen: [http://3.firepic.org/3/images/2013-10/1 ... ez2c96.png](http://3.firepic.org/3/images/2013-10/11/cx84vxez2c96.png)
## Post #317
- Username: Smash15195
- Rank: beginner
- Number of posts: 24
- Joined date: Fri Apr 08, 2011 4:35 am
- Post datetime: 2013-10-11T19:01:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Is a big problem ?
## Post #318
- Username: MAXVIDSTUDIO
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 17, 2011 9:03 am
- Post datetime: 2013-10-11T23:33:55+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

It seems a brand new engine. Received a major update, at least.
## Post #319
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2013-10-12T09:06:33+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I really hope there is a way to extract this new format...!
## Post #320
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2013-10-12T15:47:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Just had a quick look, I haven't looked at the encrypted/compressed ones yet (files with ZCTT header).

NCTT header ttarch layout:
Header
File info table
Filename table (with many blank bytes at the end)
File data


4 bytes = "NCTT"
4 bytes = size of 3ATT file
4 bytes = 0
4 bytes = "3ATT"
4 bytes = 2 ??
4 bytes = size of filename table
4 bytes = number of files

File info table - 28 bytes per file:
8 bytes = unknown
4 bytes = File offset (relative to data offset)
4 bytes = 0 ?
4 bytes = File size
4 bytes = 0?
2 bytes = unknown
2 bytes = Offset of filename in filename table

Data offset = Start of filename table + length of filename table
## Post #321
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-10-12T17:05:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

NCTT maybe means NonCompressed and ZCTT is ZipCompressed.

My lame & buggy try to write a QBMS script  

In some of the unpacked files there are 3ATT headers visible, texts and so on, but they are splitted into 64kB parts. So it's on a good way. File names are probably in that _resourcedescriptions_500_*.lenc (encrypted?) files.

```

idstring "ZCTT"
get UNK1 long		# always 65535, chunk size?
get FILES long		# num of files

for i = 0 < FILES
 get OFFSET_A longlong
 savepos POS
 get OFFSET_B longlong
 math ZSIZE = OFFSET_B - OFFSET_A
 clog "" OFFSET_A ZSIZE ZSIZE
 goto POS
next i

get EOFOFF longlong	# end of file offset

```
## Post #322
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-12T17:42:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Encryption key

```
{ 0, "\x85\xCA\x8F\xA0\x89\xDF\x64\x73\xA2\xB2\xD6\xC6\x9E\xCA\xC6\x88\x99\x5A\x73\xD8\x9F\xE1\x9B\xE2\x96\x51\x9F\x9B\x9A\xCE\xCD\x99\xD2\x76\x62\x7F\xA7\xC4\x9B\xD8\xDA\xE7\xA9\x9C\x67\x78\xB3\xD1\xB1\xC8\x99\x64\xA0\xA2\x85", "The Wolf Among Us - Episode 1" },
```
## Post #323
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-10-12T18:36:10+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

[http://aluigi.altervista.org/papers.htm#ttarchext](http://aluigi.altervista.org/papers.htm#ttarchext)
## Post #324
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2013-10-12T19:14:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Haoose
>
> http://aluigi.altervista.org/papers.htm#ttarchext

It works fine!

I've got only a problem with ".landb to .txt" transformation with my version TTG Tools... It doesn't work when i choose "Decrypt" option... is there anyone who have tried to decrypt a .landb from "The Wolf Among Us"?
## Post #325
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-10-12T19:19:18+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Crybio
>
> Haoose wrote:http://aluigi.altervista.org/papers.htm#ttarchext
I've got only a problem with ".landb to .txt" transformation with my version TTG Tools... It doesn't work when i choose "Decrypt" option...
This again new format
## Post #326
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2013-10-12T20:23:34+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Haoose
>
> Crybio wrote:Haoose wrote:http://aluigi.altervista.org/papers.htm#ttarchext
I've got only a problem with ".landb to .txt" transformation with my version TTG Tools... It doesn't work when i choose "Decrypt" option...
This again new format
## Post #327
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2013-10-13T03:39:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

anyone know what is version of Wolf Among Us ttarch2 files. It did not show up when I extracted. Can't get the game run with the rebuilt archives
## Post #328
- Username: survfate
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 13, 2012 1:43 pm
- Post datetime: 2013-10-13T03:53:47+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from namquang93
>
> anyone know what is version of Wolf Among Us ttarch2 files. It did not show up when I extracted. Can't get the game run with the rebuilt archives

The ID to use in ttarchext is 54.
## Post #329
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-10-13T08:43:08+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hey guys !

Same problem here, ttg tool is not able to convert .landb to txt... Any solutions ?
## Post #330
- Username: MertKilic
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 27, 2012 1:26 am
- Post datetime: 2013-10-13T14:52:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

New TTG Tool please?
## Post #331
- Username: sch0t3
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Apr 22, 2012 12:04 am
- Post datetime: 2013-10-13T15:38:53+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

There are many people interested in editing the subs and i know there are coder working hard to get the new encrypten.
Well waiting is always hard but im sure the new ttg will be released soon.
The tools on [http://quickandeasysoftware.net](http://quickandeasysoftware.net) will not be updated because of telltales request a couple of years ago.
So i hope for a new version of ttg, too!
## Post #332
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2013-10-13T19:16:18+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from sch0t3
>
> There are many people interested in editing the subs and i know there are coder working hard to get the new encrypten.
Well waiting is always hard but im sure the new ttg will be released soon.
The tools on http://quickandeasysoftware.net will not be updated because of telltales request a couple of years ago.
So i hope for a new version of ttg, too!

The music extractor and speech extractor will be updated.
## Post #333
- Username: sch0t3
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Apr 22, 2012 12:04 am
- Post datetime: 2013-10-13T19:43:49+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from bgbennyboy
>
> sch0t3 wrote:There are many people interested in editing the subs and i know there are coder working hard to get the new encrypten.
Well waiting is always hard but im sure the new ttg will be released soon.
The tools on http://quickandeasysoftware.net will not be updated because of telltales request a couple of years ago.
So i hope for a new version of ttg, too! 

The music extractor and speech extractor will be updated.

Sry my mistake. Im only interested in the explorer and the landb Editor and that were the tools i was refer to. Didnt mean to badmouth your work dude =)
## Post #334
- Username: MertKilic
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 27, 2012 1:26 am
- Post datetime: 2013-10-14T08:26:43+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Still waiting new TTG Tool.
## Post #335
- Username: kamuline
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Sep 02, 2009 2:11 am
- Post datetime: 2013-10-14T08:41:55+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from MertKilic
>
> Still waiting new TTG Tool.
And you think if you write down every day it will help?!
## Post #336
- Username: MertKilic
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-10-14T09:04:40+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from MertKilic
>
> Still waiting new TTG Tool.
Author (DenEm) knows about issue and is working on a new version of the program. But when it is available here - I Don't Know. I think that after translation of game (The Wolf Among Us - Episode 1) on the Russian language by Tolma4 Team.
Text for translation easily extract (format TTG Tools). Maybe soon it will load here. To allow you to translate the game, before a new version TTG Tools =)
## Post #337
- Username: MertKilic
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 27, 2012 1:26 am
- Post datetime: 2013-10-14T09:58:54+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Okay. Thanks for reply.
## Post #338
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-10-15T16:39:31+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Well, any news ?
## Post #339
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-10-18T19:31:43+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Anyone here speak this language ? [http://grajpopolsku.pl/forum/viewtopic. ... d&start=20](http://grajpopolsku.pl/forum/viewtopic.php?f=9&t=1906&sid=d87e22efd3089070ae6fb71077e4796d&start=20)

It seem that this team found a way to convert landb to txt.
## Post #340
- Username: kamuline
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Sep 02, 2009 2:11 am
- Post datetime: 2013-10-18T21:28:13+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from tikuf
>
> Anyone here speak this language ? http://grajpopolsku.pl/forum/viewtopic. ... d&start=20

It seem that this team found away to convert landb to txt.
Its polish. Also the brazil team start the translation.
## Post #341
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2013-10-18T21:46:50+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from kamuline
>
> tikuf wrote:Anyone here speak this language ? http://grajpopolsku.pl/forum/viewtopic. ... d&start=20

It seem that this team found away to convert landb to txt.
Its polish. Also the brazil team start the translation.

...how do the brazilian team rebuild the .landb from the .txt???
## Post #342
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-10-19T07:26:36+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from kamuline
>
> Its polish. Also the brazil team start the translation.
And [russian team (Tolma4 team)](http://www.zoneofgames.ru/forum/index.php?showtopic=29938&view=getnewpost) start the translation.
## Post #343
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-10-19T09:27:06+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Brazil team : Contacted ! Now just have to wait and see
## Post #344
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2013-10-19T09:28:13+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from tikuf
>
> Brazil team : Contacted ! Now just have to wait and see

Me too!
## Post #345
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-10-20T08:57:47+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Well I don't really understand what the fuck happenned O_O, i asked the russian team and they answer me with "Hello, yes we have solution, but now we don't plan to give public access to the updated utility. Maybe later. "
## Post #346
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-10-20T09:09:16+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

```
string fname + ".txt"
log MEMORY_FILE 0 0
goto 0x4
get stringsize long
get idsize long
goto 0x94
get strings long 
goto 0x8c

for i = 0 < strings
getdstring dummy 0x4c
get str1size long
if str1size = 0 
get size1 long
get size2 long
getdstring str size2
putdstring str size2 MEMORY_FILE
put 0x0a0d short MEMORY_FILE
else
getdstring str2 str1size
putdstring str2 str1size MEMORY_FILE
put 0x203a short MEMORY_FILE
get size1 long
get size2 long
getdstring str size2
putdstring str size2 MEMORY_FILE
put 0x0a0d short MEMORY_FILE
endif
next i

get size asize MEMORY_FILE
log fname 0x00 size MEMORY_FILE
```

Script for quickbms. It's a very lame script, just for unpack landb to txt. For repack need fully research format. Maybe i do it later.
## Post #347
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-10-20T09:27:08+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Oh man thank you  I'll try 

EDIT:*
Here's what I get  :
Now it's time to see how to rebuild !
[Temp.rar](https://xentaxbackup.github.io/file/6716_Temp.rar)
## Post #348
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-10-20T10:24:14+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Haoose
>
> kamuline wrote:Its polish. Also the brazil team start the translation.
And russian team (Tolma4 team) start the translation.
Also Turkish Team (OyunÇeviri) started the translation.
## Post #349
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2013-10-20T12:01:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from tikuf
>
> Well I don't really understand what the fuck happenned O_O, i asked the russian team and they answer me with "Hello, yes we have solution, but now we don't plan to give public access to the updated utility. Maybe later. "

Ahahah ridiculous....

Thanks to Thief1987 and tikuf! And now, waiting for rebuild!
## Post #350
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-10-20T14:30:12+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hey guy's ! ready to extract YOUR landb ! 

Brazilian team gave me a software 
([http://dl.free.fr/mlyiGBB9A](http://dl.free.fr/mlyiGBB9A) )
I created a readme.txt, all is explained in. However the quickbms script seem to be better at some point like : the name of the character are shown.... So Thief, your script rock anyway, and a way to rebuild the .landb files would be great, I'll PM you 

Quickbms script :
TOAD: [pickup1] BLABLABLA

Brezilian team script:
[pickup1] BLABLABLA


ALL THANKS for the soft GOES TO Herdell Alves Tribo Gamer Brasil and squallzell8 (for sharing the method)
## Post #351
- Username: sch0t3
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Apr 22, 2012 12:04 am
- Post datetime: 2013-10-20T15:32:25+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from tikuf
>
> .... So Thief, your script rock anyway, and a way to rebuild the .landb files would be great, I'll PM you

Hey guys,
thx for the script! Isnt it important for the rebuilt to left the end of the orginal landb unchanged.
I mean if i look at the end of the original there are plenty of strings like "357191700.lang" "357191699.lang" and so on.
After the convertion these strings arent in the txt-Files?!

Just my opinion
## Post #352
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2013-10-20T16:23:30+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from tikuf
>
> Hey guy's ! ready to extract YOUR landb ! 

Brazilian team gave me a software 
(http://dl.free.fr/mlyiGBB9A )
I created a readme.txt, all is explained in. However the quickbms script seem to be better at some point like : the name of the character are shown.... So Thief, your script rock anyway, and a way to rebuild the .landb files would be great, I'll PM you 

Quickbms script :
TOAD: [pickup1] BLABLABLA

Brezilian team script:
[pickup1] BLABLABLA


ALL THANKS for the soft GOES TO Herdell Alves Tribo Gamer Brasil and squallzell8 (for sharing the method)

You are my hero! Thanks to TRIBO and squallzell8 too!!!
## Post #353
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-10-21T16:34:13+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

So, while we are waiting for QuickBMS script for re-importation, I worked all the day to find a solution to re-import.
You will wonder why I want to use QuickBMS version instead of the brazilian team solution, because it contain the names and the text is not reverted, just these things will help you to make a better translation 

First for this surgery , I mean for this solution, you'll need these programms :
-notpad ++ 5.5 [http://sourceforge.net/projects/notepad ... e/download](http://sourceforge.net/projects/notepad-plus/files/notepad%2B%2B%20releases%20binary/npp%205.5%20bin/npp.5.5.Installer.exe/download)
-Brazilian team solution: [http://dl.free.fr/mlyiGBB9A](http://dl.free.fr/mlyiGBB9A)
-Quickbms script by Thief: (see at the top) and the software by luigi auriemma for using it: [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

Now we are ready !

1)Use quickbms and convert landb to .txt
2)use brazilian team solution and convert landb to .txt
3) With notpad ++ version 5.5 (this version and not an other, cause you have textfx plugin on it), 
  -you open the text created by quick bms and you translat it. 
  -Once you finish, open it and then open the brazilian version in notpad++ 
(example, open ui_menu_english-quickbms.txt and ui_menu_english-brazilian team.txt)  
Now take a look at the number of lines :
/!\YOU MUST HAVE the same number of lines, for example if you have 165 (for brazilian version) and 178 (for quickbms) That NOT gonna work. Note: Never modify the original Brazilian text, consider it as the original text.

So, first, select all your quickbms text (not the brazilian text) and follow this :
1)Go in textFX --> TextFX tools --> Insert lines numbers
2)Go in textFX --> sort lines case senstives (at column)
3)Go in textFX --> Delete lines numbers or first word
Congralutations, your text is now reverted  and is readable in the same direction as the brazilian team text file.

Second:
Remove all spaces between lines :
Example : 
bigby: [pickup1]blablablabla 

bigby: [pickup1]blablablabla

BECOME
bigby: [pickup2]blabablablad
bigby: [pickup2]blabablablad

If you still don't have the correct number of lines, that mean there are "shortcut"

Example from ui_menu_english :
BEFORE
Brazilian version :
Best Value - save on all |remaining episodes !|(Episodes 2-5) and play |them as they become available!

QuickBMS version :
Best Value - save on all remaining episodes !
(Episodes 2-5) and play
them as they become available!

AFTER
Brazilian version :
Best Value - save on all |remaining episodes !|(Episodes 2-5) and play |them as they become available!

QuickBMS version :
Best Value - save on all |remaining episodes !|(Episodes 2-5) and play |them as they become available!


And then you have the same file as the brazilian version except you got the characters names, to delete these names. Press ctrl+F, and go to "overwrite", write for example : "BIGBY: " or "TOAD: " (with the spaces it's important)(WARNING: with "TOAD: " you can have "KIDTOAD: " To delete it, search for "KID")
Now you have the same file as the brazilian, but your translation will be better because you had the text not revert and with the names when you translated it .

Hope it was clear enough !  And remember it's a temporary solution.

Here are the .txt that need to be edited :
env_andersenwoodsmanapt_english
env_businessoffice_english
env_fabletownandersen_cleanup_english
env_fabletownwoodlandbuilding_english
env_faithapartment_english
fabletownandersen_cop_english

And here are the files you can directly translate from brazilian
ui_menu_english
fablespedia_english
ui_credits_english
ui_achievements_english

Have fun
## Post #354
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-10-22T21:07:25+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

```
get fname FILENAME
string fname + "_MOD"
open FDDE "landb" 0
open FDDE "txt" 1
goto 0x94 
get strings long
goto 0x00
getdstring head 0x8c
putdstring head 0x8c MEMORY_FILE
for i = 0 < strings
getdstring data 0x44
putdstring data 0x44 MEMORY_FILE
#savepos totalblocksizeoffset
get totalblocksize long
savepos TMP 1
getct str string 0x0d 1
strlen str_size str 
#math totalblocksize = str_size
#math totalblocksize + 0x1c
get nameblocksize long
if nameblocksize = 8
math totalblocksize = str_size
math totalblocksize + 0x1c
put totalblocksize long MEMORY_FILE
put nameblocksize long MEMORY_FILE
put 0x00 long MEMORY_FILE
goto TMP 1
get dummy long
else
math totalblocksize = str_size
math totalblocksize + 0x1a
put totalblocksize long MEMORY_FILE
put nameblocksize long MEMORY_FILE
get nameblocksize2 long
put nameblocksize2 long MEMORY_FILE
getdstring name nameblocksize2
putdstring name nameblocksize2 MEMORY_FILE
goto TMP 1
getdstring nametxt nameblocksize2 1
get dummy short 1
endif
get textblocksize long 
getct str2 string 0x0d 1
get dummy byte 1
strlen str_size2 str2
math  textblocksize = str_size2
math  textblocksize + 0x8
put textblocksize long MEMORY_FILE
put str_size2 long MEMORY_FILE
get textblocksize2 long
getdstring oldstr textblocksize2
putdstring str2 str_size2 MEMORY_FILE
next i
savepos endstringoffset
get origsize asize
math origsizeTMP = origsize
math origsize - endstringoffset
getdstring footer origsize 
putdstring footer origsize MEMORY_FILE
get size asize MEMORY_FILE
math origsizeTMP - size
if origsizeTMP >= 0
goto 0x90 MEMORY_FILE
get alltextblocksize long MEMORY_FILE
math alltextblocksize - origsizeTMP
goto 0x90 MEMORY_FILE
put alltextblocksize long MEMORY_FILE
else
math origsizeTMP ^ 0xffffffffffffffff
math  origsizeTMP + 1
goto 0x90 MEMORY_FILE
get alltextblocksize long MEMORY_FILE
math alltextblocksize + origsizeTMP
goto 0x90 MEMORY_FILE
put alltextblocksize long MEMORY_FILE
endif
log fname 0x00 size MEMORY_FILE

```

This is my script for repack landb, maybe it useful for somebody
## Post #355
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-10-22T21:48:12+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Thnak you man !
I'll try it !
## Post #356
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-10-23T10:53:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Work but gave .mod file, just delete the .mod and it should work.
## Post #357
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-10-24T08:50:45+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

If you don't need files with landb_MOD extension, just delete third string of the script "string fname + "_MOD""
## Post #358
- Username: survfate
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 13, 2012 1:43 pm
- Post datetime: 2013-10-24T12:58:14+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Any way to decrypt the .font file to use with Den Em TTG Tool? Last time this worked:

> Reply from merlinsvk
>
> I don't know why that "key" (or what it is) did not worked, but if you change values to these...



...font will be editable.
(btw that values are from Back To The Future font files)

Thank in advance.
## Post #359
- Username: survfate
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 13, 2012 1:43 pm
- Post datetime: 2013-10-27T14:45:28+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Well, it seem after the way to crack the new file is available, no one visit here anymore...
## Post #360
- Username: sch0t3
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Apr 22, 2012 12:04 am
- Post datetime: 2013-10-27T15:42:08+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

German team start the translation...
We are looking for a way to edit the font Files. too.
Hopefully someone comes up with a solution for the font file problem.
## Post #361
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-10-28T12:48:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I qill try to find a solution, but first, I need to find the .font X) Anyone knows where to find it ?
## Post #362
- Username: survfate
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 13, 2012 1:43 pm
- Post datetime: 2013-10-28T13:36:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from tikuf
>
> I qill try to find a solution, but first, I need to find the .font X) Anyone knows where to find it ?

Extract Fables_pc_Project_all.ttarch2 with ttarchext and you got these .font files (along with several other files):

```
AvantGarde_LT_Book_14.font
AvantGarde_LT_Book_40.font
Cantoria_MT.font
CCLegendaryLegerdemain_34.font
default.font
ITC_Kabel_Book.font
ITC_Kabel_Medium.font
ManlyMen_BB_60.font
Rockwell_Std_48_bold.font
Rockwell_Std_Condensed_48_bold.font

```

[http://grajpopolsku.pl/forum/viewtopic. ... =20#p21258](http://grajpopolsku.pl/forum/viewtopic.php?f=9&t=1906&sid=d87e22efd3089070ae6fb71077e4796d&start=20#p21258) - Here is the Link to the .font editor from a guy (I found this in some of the pages previous). The tool work exactly the same as TTG Tool Font Editor, but I haven't test it enough to see it actually working perfectly. I just extract the DDS to check the content of the .font and seem like the CCLegendaryLegerdemain_34.font (the one that use for the subtitles and choices in game) got an DDS that not having all the alphabet character - which worried me. Please check this out. Thanks.
## Post #363
- Username: survfate
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 13, 2012 1:43 pm
- Post datetime: 2013-11-07T17:07:27+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

The Thread is abandon... again.

Anyway, if anyone with experience come here please give me the correct comand to rebuild the ttarch2 file with ttarchext. I having problem running the game after rebuild my file.
## Post #364
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-11-08T12:12:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

It's not necessary rebuild ttarch, just put your changed files (landb, font, etc.) in one folder with .ttarch files, and game will use them.
## Post #365
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-11-11T14:20:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hey !
"I'm back ! " ^^
But not for a so big news, just for people who have problem with the re-pack of the .lanbd and get character like "Ãc" or "Ã{" verify that your texts are encoded as Ansi, I'm still in touch with the Brazilian team, they may have a solution for the font, keeping you in touch (if there is still someone ther ^^" ) Anyway, I know this will help someone, maybe you, who are reading this messsage
## Post #366
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-11-12T21:32:29+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hey !

Have a cool news for you all 

What you'll need :
-Photoshop
-the software attached to this message and the fonts edited by the Brazilian team tribogamer
-time

To edit the font, you'll need this software (it come from a russian forum, and it seem that he have a virus... So be carefull and launch it in a "securebox" with your antivirus)

Found the font named : "Cantoria MT.font" and "CCLegendaryLegerdemain_34.font"
then open it in the software previously downloaded.
Now you see a hundrends of line.
Click on the little box at the top where there are informations like : Width :512 ;Nr DDS : 0
And export as .DDS.

Open photoshop and open the .dds in it (if you are not able to do this, see this page : [https://developer.nvidia.com/nvidia-tex ... -photoshop](https://developer.nvidia.com/nvidia-texture-tools-adobe-photoshop))

You can see this : (all pictures and illustrations are in the .rar)
This is such a problem, because you don't see anything: LOL
Click on the "alpha" option : 
WOW ! This is so magic ^^
Press ctrl+r to make the gird appear and right click on it --> pixel

The following part will be a little bit harder.
So first, here's a draw of how it work
(all pictures and illustrations are in the .rar)
Now you just have to draw your characters and save the .dds.
Reimport it in the soft and found the one wich match in the software.
Exemple, if you have draw the "è" , you must found the "è" in the software
Hope it was enough clear 
A big thank to tribo gamer and the russian forum !
Come back tomorrow to put more details and my font containing "û" "è" 

Files : [http://paf.im/8h9L2](http://paf.im/8h9L2)
## Post #367
- Username: survfate
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 13, 2012 1:43 pm
- Post datetime: 2013-11-13T04:46:41+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from tikuf
>
> Hey !
"I'm back ! " ^^
But not for a so big news, just for people who have problem with the re-pack of the .lanbd and get character like "Ãc" or "Ã{" verify that your texts are encoded as Ansi, I'm still in touch with the Brazilian team, they may have a solution for the font, keeping you in touch (if there is still someone ther ^^" ) Anyway, I know this will help someone, maybe you, who are reading this messsage

Hmm this is exactly what happen to my Menu texts in TWD (the rest of the texts such as Subtitles and Choices is fine), I'll give it a try in my free time and let you know.

Edit: Oh and about the .font editor, it appear that the editor is the same one I posted above . I edited the font just fine, but the problem is the game won't run after repack everything). BTW @Thief1987: Correct me if I'm wrong, but TWAU don't have the same way to make a manual patch by making new .ttarch(2) like TWD (tried both, TWD having those number before a file which made they are a patch version, yet TWAU don't have any of that).
## Post #368
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-11-13T06:34:39+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Survfate : You'll have to download a software like kaboom to convert your text, notepad++ won't be able to convert utf8 to ansi
(i'm not a pro but that what i've done) ^^
and my command for ttarchext :

extraction:
\ttarchext.exe 54 "G:\path\yourpatch.ttarch2" G:\path\extract

rebuilding: 
ttarchext\ttarchext.exe -b -x -V 7 54 "G:\path\Fables_pc_Boot_data.ttarch2" G:\path\Rebuildboot

It seem that ttarchext don't like space 
exemple
G:\path   2\Fables_pc_Boot_data.ttarch2 <---- don't work

If you are still not able to repack, tell me, I make a quick software giveing you a ready-to-use key
## Post #369
- Username: survfate
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 13, 2012 1:43 pm
- Post datetime: 2013-11-13T09:26:42+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

TED Notepad is the one I used, it don't have many feature to mess with, but it get the job done nicely. And yes, change to ANSI and everything worked fine.

Oh and many thank, I have no idea TWAU was using "V 7" I thought it was "V 8" like TWD.  

> Reply from tikuf
>
> rebuilding: 
ttarchext\ttarchext.exe -b -x -V 7 54 "G:\path\Fables_pc_Boot_data.ttarch2" G:\path\Rebuildboot

It seem that ttarchext don't like space 
exemple
G:\path   2\Fables_pc_Boot_data.ttarch2 <---- don't work

BTW to solved the problem with the space just use " " for example: ttarchext\ttarchext.exe -b -x -V 7 54 "G:\path\Fables_pc_Boot_data.ttarch2" "G:\path   2\Fables_pc_Boot_data.ttarch2"
## Post #370
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-13T09:26:59+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from tikuf
>
> Hey !
"I'm back ! " ^^
But not for a so big news, just for people who have problem with the re-pack of the .lanbd and get character like "Ãc" or "Ã{" verify that your texts are encoded as Ansi, I'm still in touch with the Brazilian team, they may have a solution for the font, keeping you in touch (if there is still someone ther ^^" ) Anyway, I know this will help someone, maybe you, who are reading this messsage

I've done fonts for Brazilian team.

CCLegendaryLegerdemain_34 - Main text
ITC_Kabel_Medium_0 - Information, "use" and others
ITC_Kabel_Book - Copyrights, Click to run, a lot of menu strings, characters descriptions, things in game
ManlyMen_BB_60 - Previous Menu, Saving... etc
Cantoria_MT - Introduction and names in menu

ITC_Kabel_Book have a lot of chars, just copy chars table from this font to others, It will work fine.
Remeber, game is using Windows Code Page! So for Central Europe you must use CP-1250.
## Post #371
- Username: tikuf
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 22, 2012 2:21 am
- Post datetime: 2013-11-13T10:54:14+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hey ! 
Do you know how to had character in the wolf among us tool ?
For example: the "û" is not in it, do you know a way to had character to the editor ? 
Thanks ! 

P.S : I'll post the font CC_legendermain_34 this afternoon containing these chararcters : û è ù <-- Wich i had
é ê à ã ä â and a lot more <-- had by Brezilian team
## Post #372
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-13T11:40:25+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Windows Coding Page 1252:
DB	Û
FB	û

Replace with not used character in chars table using Hex Editor.
Search for 0F in Hex Editor, you will see char 8 bytes before it.

Guys, you still need tools for American McGee's Grimm?
## Post #373
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-12-17T18:36:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Need key for TWD Season 2 =)
## Post #374
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-12-18T08:02:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Haoose
>
> Need key for TWD Season 2 =)

```
\x96\xCA\x99\x9F\x8D\xDA\x9A\x87\xD7\xCD\xD9\x96\x62\x95\xAA\xB8\xD5\x95\x96\xE5\xA4\xB9\x9B\xD0\xC9\x53\x9F\x85\x90\xCD\xCD\x9F\xC8\xB3\x99\x93\xC6\xC4\x9D\x9E\xA5\xA4\xCF\xCD\xA3\x9D\xBB\xDD\xAC\xA7\x8B\x94\xD4\xA4\x6F
```
## Post #375
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-12-18T10:55:14+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Ekey
>
> Haoose wrote:Need key for TWD Season 2 =)
Code: Select all\x96\xCA\x99\x9F\x8D\xDA\x9A\x87\xD7\xCD\xD9\x96\x62\x95\xAA\xB8\xD5\x95\x96\xE5\xA4\xB9\x9B\xD0\xC9\x53\x9F\x85\x90\xCD\xCD\x9F\xC8\xB3\x99\x93\xC6\xC4\x9D\x9E\xA5\xA4\xCF\xCD\xA3\x9D\xBB\xDD\xAC\xA7\x8B\x94\xD4\xA4\x6F
Not work =(
## Post #376
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-12-18T12:15:49+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Haoose
>
> Ekey wrote:Haoose wrote:Need key for TWD Season 2 =)
Code: Select all\x96\xCA\x99\x9F\x8D\xDA\x9A\x87\xD7\xCD\xD9\x96\x62\x95\xAA\xB8\xD5\x95\x96\xE5\xA4\xB9\x9B\xD0\xC9\x53\x9F\x85\x90\xCD\xCD\x9F\xC8\xB3\x99\x93\xC6\xC4\x9D\x9E\xA5\xA4\xCF\xCD\xA3\x9D\xBB\xDD\xAC\xA7\x8B\x94\xD4\xA4\x6F
Not work =(
Format changed. Wait Luigi.
## Post #377
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-12-18T12:20:04+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Ekey
Разве формат не как в Волке? Я ключик поменял в ttarchext, и поменял там 3ATT на то что есть в TWD2 - выдало ошибку, как я понял не правильно расшифровалось имя файла. Наверно ключ не правильный. В скайпе обсудим подробнее
## Post #378
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-12-18T12:51:40+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Haoose
>
> 
поменял там 3ATT на то что есть в TWD2 - выдало ошибку, как я понял не правильно расшифровалось имя файла.
Я больше чем уверен что формат изменился и подмена заголовка занятие бесполезное 

> Reply from Haoose
>
> 
Наверно ключ не правильный.
Ключ валидный. Даже проверил - занопил его и игра не запускается вообще
## Post #379
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-12-18T13:01:05+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

In console version format same with wolf among us, not encrypted.
## Post #380
- Username: squallzell8
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 12, 2012 12:20 pm
- Post datetime: 2013-12-18T21:50:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

The Russian team has already managed to extract the texts? Could share the files with us.

I'm from Brazil and we want translate this game.


Please send the files for us. squallzell8@hotmail.com
## Post #381
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-12-19T07:08:14+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from squallzell8
>
> The Russian team has already managed to extract the texts? Could share the files with us.

I'm from Brazil and we want translate this game.


Please send the files for us. squallzell8@hotmail.com
Texts from console version (Thx Thief1987) =)
For PC need new version of ttarchext
## Post #382
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-12-19T07:34:17+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Ekey
>
> Format changed. Wait Luigi.

lol is the amazing Luigi still around? or alive for that matter (i'm sure he's on several government hit lists by now he he he). hope he's doing alright .
## Post #383
- Username: squallzell8
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 12, 2012 12:20 pm
- Post datetime: 2013-12-19T13:01:39+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Haoose
>
> squallzell8 wrote:The Russian team has already managed to extract the texts? Could share the files with us.

I'm from Brazil and we want translate this game.


Please send the files for us. squallzell8@hotmail.com
Texts from console version (Thx Thief1987) =)
For PC need new version of ttarchext

Ok, but could you send us the text console to go start the translation. Then we convert it to PC later.
## Post #384
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-12-19T14:27:03+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Eh, If you want it so much, here: [https://www.dropbox.com/sh/rf0v3t5lk5ahxmg/yOHkYFEU-D](https://www.dropbox.com/sh/rf0v3t5lk5ahxmg/yOHkYFEU-D)

New eof string!
\x48\x00\x00\x00\x14\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x02\x00\x00\x00\xAB
and
\x40\x00\x00\x00\x14\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x02\x00\x00\x00\xAB
## Post #385
- Username: squallzell8
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 12, 2012 12:20 pm
- Post datetime: 2013-12-19T16:39:10+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from GimmyBreaker
>
> Eh, If you want it so much, here: https://www.dropbox.com/sh/rf0v3t5lk5ahxmg/yOHkYFEU-D

New eof string!
\x48\x00\x00\x00\x14\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x02\x00\x00\x00\xAB
and
\x40\x00\x00\x00\x14\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x02\x00\x00\x00\xAB
Yes, thaks a lot.
## Post #386
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-12-19T23:12:07+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

@Ekey
thanks for the key

Luckily the update was quite simple and didn't require debugging, just added the new key and ttarch_chunks_b set to 1:

[http://aluigi.org/papers.htm#ttarchext](http://aluigi.org/papers.htm#ttarchext)
## Post #387
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-12-20T15:48:55+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Fonts from The Walking Dead Season 2:
CheapSignage.font - menu, only A-Z, a-z, 0-9 and some chars, original name (CheapSignage_800)
Univers_BoldExtened.font - Copyrights, "Previous menu etc.", Intro and main text; a lot of other chars for other countries. 
Univers_Bold.font - choices; Save notes (about Season 1)


Guys, you only need font for menu, very good news
## Post #388
- Username: Starnova
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Feb 10, 2014 10:19 am
- Post datetime: 2014-04-14T17:49:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello, could anybody tell me how to extract de dds from the d3dtx files??? Thanks

PD: I am from the spanish team
## Post #389
- Username: FireWolf
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 14, 2014 8:43 pm
- Post datetime: 2014-04-22T13:08:25+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi everyone, I am trying to make update with only my translate files in ttarch2 archive and nothing works. Translate all three episodes has around 200 MB in ttarch2, but if there will be only translate landb, then it should have around 10 MB. I guess there are important files with .lenc extension (which can be with ttarchext converted to .lua, and this format is readable in notepad++). Can anyone help me? I can upload some files, if you want it. Btw. sorry for my bad english
## Post #390
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-05-11T18:20:49+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from merlinsvk
>
> NCTT maybe means NonCompressed and ZCTT is ZipCompressed.

And how to pack ttarch2 using compression?
## Post #391
- Username: Starnova
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Feb 10, 2014 10:19 am
- Post datetime: 2014-05-26T18:24:00+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Its a shame that no one answer your questions, where is everyone? haha
## Post #392
- Username: Starnova
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Feb 10, 2014 10:19 am
- Post datetime: 2014-05-26T18:25:07+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from FireWolf
>
> Hi everyone, I am trying to make update with only my translate files in ttarch2 archive and nothing works. Translate all three episodes has around 200 MB in ttarch2, but if there will be only translate landb, then it should have around 10 MB. I guess there are important files with .lenc extension (which can be with ttarchext converted to .lua, and this format is readable in notepad++). Can anyone help me? I can upload some files, if you want it. Btw. sorry for my bad english

Hi, you can update the texts using only the landb files. Just droping the landbs and the font in Pack should work. Im from the spanish translation and my installer is 5MB size. If you wanna check it i could attach it.
## Post #393
- Username: Starnova
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Feb 10, 2014 10:19 am
- Post datetime: 2014-05-26T18:30:37+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Kaltan
>
> merlinsvk wrote:NCTT maybe means NonCompressed and ZCTT is ZipCompressed.

And how to pack ttarch2 using compression?

Is not posible, i talked with Aluigi, and he told me that it needs a lot of time of work and testing.
## Post #394
- Username: FireWolf
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 14, 2014 8:43 pm
- Post datetime: 2014-05-27T10:46:52+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Starnova
>
> FireWolf wrote:Hi everyone, I am trying to make update with only my translate files in ttarch2 archive and nothing works. Translate all three episodes has around 200 MB in ttarch2, but if there will be only translate landb, then it should have around 10 MB. I guess there are important files with .lenc extension (which can be with ttarchext converted to .lua, and this format is readable in notepad++). Can anyone help me? I can upload some files, if you want it. Btw. sorry for my bad english 

Hi, you can update the texts using only the landb files. Just droping the landbs and the font in Pack should work. Im from the spanish translation and my installer is 5MB size. If you wanna check it i could attach it.

Oh, I love you  Many thanks to you
## Post #395
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2014-07-14T06:44:27+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Ive been trying to extract from TWAU, successfully with most things except from the d3dtx files. I can't seem to get them to convert to dds, the option that was supposed to work in the ttarchext didnt work D:
## Post #396
- Username: 7dami77
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 19, 2012 11:12 pm
- Post datetime: 2014-09-12T18:31:40+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

How do I open this file? This is a file from TWD on Android. Files .font I was able to open using The Wolf Among Us Font Tool.
[obj_pileSelectionBoardA.d3dtx.zip](https://xentaxbackup.github.io/file/7801_obj_pileSelectionBoardA.d3dtx.zip)
## Post #397
- Username: pashok6798
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Sep 06, 2014 2:45 am
- Post datetime: 2014-09-22T14:08:51+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from 7dami77
>
> How do I open this file? This is a file from TWD on Android. Files .font I was able to open using The Wolf Among Us Font Tool.
If I don't mistake, it's an A8 compression with 10 mip-maps. I'm sure. I know, that on PC textures have 3 methods of compressions (maybe, it's more, but generally new games use 3 methods): DXT1, DXT5 and A8. Also, some textures can have mip-maps. But about Android and iOS compression methods could know Dhampir.


P.S. Poker Night almost has this structure (DXT1, DXT5 and A8 with mip-maps or without mip-maps), like TWAU and WD S2.
P.P.S. Sorry for bad English.

---------------------------------------------------------------------------------------
Somebody tried to decompile and compile lua scripts? We tried to decompile .lenc files in Pack folder, but some people had problems (our archives on some PCs just don't loading, but on another PCs could load).



Example on one texture Безымянный.png (159.35 KiB) Viewed 488 times
## Post #398
- Username: jediyoshi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 11, 2014 3:15 pm
- Post datetime: 2014-11-26T00:59:11+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Tales from the Borderlands released today

```
Borderlands_pc_Borderlands101_ms.ttarch2        157,053.170 KB
Borderlands_pc_Borderlands101_txmesh.ttarch2    799,630.320 KB
Borderlands_pc_Borderlands101_voice.ttarch2     115,901.520 KB
Borderlands_pc_Engine_Lua_data.ttarch2              162.131 KB
Borderlands_pc_Menu_anichore.ttarch2                162.671 KB
Borderlands_pc_Menu_data.ttarch2                    828.960 KB
Borderlands_pc_Menu_ms.ttarch2                    6,675.668 KB
Borderlands_pc_Menu_txmesh.ttarch2               85,546.271 KB
Borderlands_pc_Project_anichore.ttarch2               1.610 KB
Borderlands_pc_Project_data.ttarch2               2,088.682 KB
Borderlands_pc_Project_txmesh.ttarch2                48.637 KB
Borderlands_pc_Shaders_shader.ttarch2           165,574.850 KB
Borderlands_pc_UI_anichore.ttarch2                  265.400 KB
Borderlands_pc_UI_data.ttarch2                      244.121 KB
Borderlands_pc_UI_ms.ttarch2                      3,202.996 KB
Borderlands_pc_UI_txmesh.ttarch2                240,825.560 KB
_resdesc_50_Boot.lua                                  1.164 KB
_resdesc_50_Borderlands101.lua                        1.313 KB
_resdesc_50_Engine_Lua.lua                            0.994 KB
_resdesc_50_Menu.lua                                  1.164 KB
_resdesc_50_PC.lua                                    0.838 KB
_resdesc_50_Project.lua                               1.112 KB
_resdesc_50_Shaders.lua                               0.986 KB
_resdesc_50_UI.lua                                    1.148 KB
Borderlands_pc_Boot_anichore.ttarch2                  7.508 KB
Borderlands_pc_Boot_data.ttarch2                     49.242 KB
Borderlands_pc_Boot_ms.ttarch2                    2,051.207 KB
Borderlands_pc_Boot_txmesh.ttarch2               31,215.946 KB
Borderlands_pc_Borderlands101_anichore.ttarch2   79,024.049 KB
```
## Post #399
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2014-11-26T12:39:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from jediyoshi
>
> Tales from the Borderlands released today
Code: Select allBorderlands_pc_Borderlands101_data.ttarch2       16,877.211 KB
Borderlands_pc_Borderlands101_ms.ttarch2        157,053.170 KB
Borderlands_pc_Borderlands101_txmesh.ttarch2    799,630.320 KB
Borderlands_pc_Borderlands101_voice.ttarch2     115,901.520 KB
Borderlands_pc_Engine_Lua_data.ttarch2              162.131 KB
Borderlands_pc_Menu_anichore.ttarch2                162.671 KB
Borderlands_pc_Menu_data.ttarch2                    828.960 KB
Borderlands_pc_Menu_ms.ttarch2                    6,675.668 KB
Borderlands_pc_Menu_txmesh.ttarch2               85,546.271 KB
Borderlands_pc_Project_anichore.ttarch2               1.610 KB
Borderlands_pc_Project_data.ttarch2               2,088.682 KB
Borderlands_pc_Project_txmesh.ttarch2                48.637 KB
Borderlands_pc_Shaders_shader.ttarch2           165,574.850 KB
Borderlands_pc_UI_anichore.ttarch2                  265.400 KB
Borderlands_pc_UI_data.ttarch2                      244.121 KB
Borderlands_pc_UI_ms.ttarch2                      3,202.996 KB
Borderlands_pc_UI_txmesh.ttarch2                240,825.560 KB
_resdesc_50_Boot.lua                                  1.164 KB
_resdesc_50_Borderlands101.lua                        1.313 KB
_resdesc_50_Engine_Lua.lua                            0.994 KB
_resdesc_50_Menu.lua                                  1.164 KB
_resdesc_50_PC.lua                                    0.838 KB
_resdesc_50_Project.lua                               1.112 KB
_resdesc_50_Shaders.lua                               0.986 KB
_resdesc_50_UI.lua                                    1.148 KB
Borderlands_pc_Boot_anichore.ttarch2                  7.508 KB
Borderlands_pc_Boot_data.ttarch2                     49.242 KB
Borderlands_pc_Boot_ms.ttarch2                    2,051.207 KB
Borderlands_pc_Boot_txmesh.ttarch2               31,215.946 KB
Borderlands_pc_Borderlands101_anichore.ttarch2   79,024.049 KB

Great!! Wich key you used for ttarchext? Thanks!
## Post #400
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2014-11-26T14:24:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Great!! Wich key you used for ttarchext? Thanks!

I'm waiting for key to TftB too, guys 
Hope you get it soon.
## Post #401
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2014-11-26T15:22:54+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Key for TFTB:
ttarchext.exe -k 81D89F9889DE9FA4E0D0E895629595C6DB8E92E9A9D6A4D3D8529F857BDBD398C4B79EB0CFC7AC9DA5A4BADBA996B7E1B1C49497E3A36F
## Post #402
- Username: Tomas2886Cz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 16, 2013 8:15 am
- Post datetime: 2014-11-26T16:23:54+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Is it just me or does the current QuickBMS script for unpacking .landb's [(this one)](http://pastebin.com/zcBZskpZ) not work with Tales from the Borderlands? It leaves me with the following error:


- error in src/xalloc.c line 617: xdbg_malloc()

Error: memory allocation problem
              Not enough storage is available to process this command.
## Post #403
- Username: squallzell8
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 12, 2012 12:20 pm
- Post datetime: 2014-11-27T03:41:41+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Someone managed to successfully convert files landb to txt?
## Post #404
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2014-11-27T13:04:17+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Tomas2886Cz
>
> Is it just me or does the current QuickBMS script for unpacking .landb's (this one) not work with Tales from the Borderlands? It leaves me with the following error:


- error in src/xalloc.c line 617: xdbg_malloc()

Error: memory allocation problem
              Not enough storage is available to process this command.


Same problem here...
## Post #405
- Username: nurik040404
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 28, 2014 1:09 am
- Post datetime: 2014-11-27T17:31:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Guys, i tryed all ways to landb to txt, but Tales from the Borderland, have another crypting, what i should to do?
## Post #406
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-11-27T21:50:58+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

nurik040404	
It's no crypting =)
## Post #407
- Username: Starnova
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Feb 10, 2014 10:19 am
- Post datetime: 2014-11-29T00:40:34+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Any news, guys?
## Post #408
- Username: nicky rhys
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 30, 2014 8:32 pm
- Post datetime: 2014-11-30T13:01:30+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> Key for TFTB:
ttarchext.exe -k 81D89F9889DE9FA4E0D0E895629595C6DB8E92E9A9D6A4D3D8529F857BDBD398C4B79EB0CFC7AC9DA5A4BADBA996B7E1B1C49497E3A36F

Okay thanks, but what's the code key for import to .ttarch2 ?
## Post #409
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2014-11-30T15:10:58+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from nicky rhys
>
> Okay thanks, but what's the code key for import to .ttarch2 ?

You don't have to import files to ttarch2. Just put edited files (font,landb,d3dtx) in "archives" directory next to the ttarch2 files.
## Post #410
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2014-11-30T16:14:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Is there a script for quickbms .landb TO .txt that works for TFTB? Anything?
## Post #411
- Username: squallzell8
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 12, 2012 12:20 pm
- Post datetime: 2014-11-30T16:59:02+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Den Em and Haoose shared all texts in English.


Still missing the file ui_achievements_english.



Currently, the repack is not possible.

If anyone can enter the texts please share the method.


[All english texts](https://drive.google.com/file/d/0B0xqP9hD7BZCODdnQ0Y3a3p6cms/view?usp=sharing)
## Post #412
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2014-11-30T17:25:33+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

ui_achievements_english.txt: [http://pastebin.com/f0B73Cmv](http://pastebin.com/f0B73Cmv)
## Post #413
- Username: squallzell8
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 12, 2012 12:20 pm
- Post datetime: 2014-12-02T07:53:14+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

The Russian team managed to insert the texts.

Tolma4team, please share the method with us.

http://vk.com/tolma4team?w=wall-6860521 ... 33b1a74c46
## Post #414
- Username: squallzell8
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-12-02T11:43:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

squallzell8
May be after the release of the translation...
## Post #415
- Username: squallzell8
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-12-02T18:25:34+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Game of Thrones (Telltale Games)

Key

```
86CA9A9973D287ABE4DBE3C9A5968387B08B9ADC8CDB8AD7D790DDBAAC9D9164A6A69FB4B0C98DD4E7E3E6D1AA63829F8CC49398BFD893
```

Unpack example:

```
ttarchext.exe -k 86CA9A9973D287ABE4DBE3C9A5968387B08B9ADC8CDB8AD7D790DDBAAC9D9164A6A69FB4B0C98DD4E7E3E6D1AA63829F8CC49398BFD893 0 "C:\Games\Game of Thrones\archives\GameOfThrones_pc_GameOfThrones101_data.ttarch2" unpack\
```

English texts for example
[http://rghost.ru/private/59390100/5bbf9 ... 3a74285c19](http://rghost.ru/private/59390100/5bbf9bde5ad8a9671805c03a74285c19)
## Post #416
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-12-03T02:32:55+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Haoose
>
> Game of Thrones (Telltale Games)

Key
Code: Select all86CA9A9973D287ABE4DBE3C9A5968387B08B9ADC8CDB8AD7D790DDBAAC9D9164A6A69FB4B0C98DD4E7E3E6D1AA63829F8CC49398BFD893
Unpack example:
Code: Select allttarchext.exe -k 86CA9A9973D287ABE4DBE3C9A5968387B08B9ADC8CDB8AD7D790DDBAAC9D9164A6A69FB4B0C98DD4E7E3E6D1AA63829F8CC49398BFD893 0 "C:\Games\Game of Thrones\archives\GameOfThrones_pc_GameOfThrones101_data.ttarch2" unpack\
English texts for example
http://rghost.ru/private/59390100/5bbf9 ... 3a74285c19

Nice! How to edit .font file's Game of Thrones? Thanks!
## Post #417
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2014-12-04T15:42:38+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from namquang93
>
> 
Nice! How to edit .font file's Game of Thrones? Thanks!
As TWAU/TWDS2 .font, but header of FONT increased by 4 bytes. Header of DDS increased by (4*4+1*4) bytes, and additional 1 byte after headers of dds.
## Post #418
- Username: mahakar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 05, 2014 1:15 am
- Post datetime: 2014-12-04T17:18:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> namquang93 wrote:
Nice! How to edit .font file's Game of Thrones? Thanks!
As TFTB/TWDS2 .font

Well, that's some help but how to edit TFTB/TWDS2 .font?
## Post #419
- Username: ojeda
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 05, 2014 2:46 am
- Post datetime: 2014-12-04T18:51:42+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Haoose
>
> Game of Thrones (Telltale Games)

Key
Code: Select all86CA9A9973D287ABE4DBE3C9A5968387B08B9ADC8CDB8AD7D790DDBAAC9D9164A6A69FB4B0C98DD4E7E3E6D1AA63829F8CC49398BFD893
Unpack example:
Code: Select allttarchext.exe -k 86CA9A9973D287ABE4DBE3C9A5968387B08B9ADC8CDB8AD7D790DDBAAC9D9164A6A69FB4B0C98DD4E7E3E6D1AA63829F8CC49398BFD893 0 "C:\Games\Game of Thrones\archives\GameOfThrones_pc_GameOfThrones101_data.ttarch2" unpack\
English texts for example
http://rghost.ru/private/59390100/5bbf9 ... 3a74285c19
How did you get the key number, like whats the procedure to generate or find it?
## Post #420
- Username: Tomas2886Cz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 16, 2013 8:15 am
- Post datetime: 2014-12-05T13:00:28+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> namquang93 wrote:
Nice! How to edit .font file's Game of Thrones? Thanks!
As TFTB/TWDS2 .font, but header of FONT increased by 4 bytes. Header of DDS increased by (4*4+1*4) bytes, and additional 1 byte after headers of dds.

How exactly is that done? Through Hex editing?
## Post #421
- Username: inter9429
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 06, 2014 1:14 am
- Post datetime: 2014-12-05T21:38:04+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello everyone, how can I convert the files landb of games of thrones in txt?
## Post #422
- Username: mahakar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 05, 2014 1:15 am
- Post datetime: 2014-12-06T02:10:50+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Okay, guys. I know that 'a font file job' should be done in HEX editor. I did such a thing in past. That's not a problem. But maybe some details? Someone wrote:

> As TFTB/TWDS2 .font, but header of FONT increased by 4 bytes. Header of DDS increased by (4*4+1*4) bytes, and additional 1 byte after headers of dds.

But I dunno what positions were in Tales from the Borderlands and The Walking Dead 2 

NOTE: I'm from China. I've written a tool for unpacking/packing a text. I can share it with person who can help me with the font/textures files for Tales from the Borderlands and Game of Thrones.
## Post #423
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2014-12-06T16:23:19+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from mahakar
>
> Okay, guys. I know that 'a font file job' should be done in HEX editor. I did such a thing in past. That's not a problem. But maybe some details? Someone wrote:
As TFTB/TWDS2 .font, but header of FONT increased by 4 bytes. Header of DDS increased by (4*4+1*4) bytes, and additional 1 byte after headers of dds.

But I dunno what positions were in Tales from the Borderlands and The Walking Dead 2 

NOTE: I'm from China. I've written a tool for unpacking/packing a text. I can share it with person who can help me with the font/textures files for Tales from the Borderlands and Game of Thrones.
I was wrong. 
As TWAU/TWDS2 .font
I will release a program the other day.
## Post #424
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2014-12-10T00:42:18+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Here is the tool I coded for both Game of Thrones and Tales of Borderlands landb files. Requires .NET 4 Redist.
Put 3 files into folder with .landb files.
Then run 'extractAll.cmd' and it will extract all landb files in current folder to txt files.
Do not delete empty lines or add a new line in text files. Also do not delete | char, since it is used as line separator.
After editing  text files, run 'repackAll.cmd' to create new .landb2 files with your texts.

> Reply from Usage
>
> To extract: Code: Select alllandb5.exe <landb_file>
Extracts <landb_file>.txt 
Structure of text file:
<speaker>
<line of speaker>
<speaker>
<line of speaker>
...
Some speaker lines are empty. Do not delete those lines.
To repack: Code: Select alllandb5.exe  <landb_file>   gom 
Repack requires both <landb_file> and <landb_file>.txt and create <landb_file>2 file

EDIT: I added tool to extract fonts from dds files. Requires 010Editor v5. Just put into the folder with .font files, and run extractAll.cmd to extract all font files.
I will not do dds injector. You may do it.

```
http://www44.zippyshare.com/v/46137225/file.html
```

[landb5_program.7z](https://xentaxbackup.github.io/file/8236_landb5_program.7z)
## Post #425
- Username: Tomas2886Cz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 16, 2013 8:15 am
- Post datetime: 2014-12-13T00:19:45+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from rengareng
>
> Here is the tool I coded for both Game of Thrones and Tales of Borderlands landb files...

That is amazing, thank you so much for that.
Would you also happen to have a quick advice on how to reimport the edited .dds fonts back into a .font file, please?
## Post #426
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2014-12-13T00:56:28+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Tomas2886Cz
>
> rengareng wrote:Here is the tool I coded for both Game of Thrones and Tales of Borderlands landb files...

That is amazing, thank you so much for that.
Would you also happen to have a quick advice on how to reimport the edited .dds fonts back into a .font file, please?

You may use a hex-editor. Just copy DDS file without header, replace with the previous one. Sizes should be same.
 DDS data in the end of the file. Some files may have more than 1 DDS data.
## Post #427
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2014-12-13T19:16:36+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

My modification of TTG Tools by Den Em:

I do not have time to describe all the features of the program and how to use it, so the summary:

Features:
 Work with Hector/Puzzle Agent/TWD (Not test)/TWDS2/TWAU and newer games
 Work: Land/Font/Textures Import/Export
 Landb: Export to TTG Tools original format (Landb), "NAME_OF_SPEAKER: TEXT" format (Notabenoid), and like .SRT format (Line number, Author, Text, Empty line). Import from TTG Original (In GUI with select "Landb"), .SRT (In GUI and console)
 To import landb in .SRT format into .LANDB from *.txt files you can use TTG Tools from console: ""TTG Tools.exe" -import landb input output", input/output - you folders.
 To import/export textures, select you game in the list of games in Auto Depacker.

Font Editor: It's using Unicode to represent characters. And is designed for Cyrillic characters.
Landb export and import worked only with UTF-8 txt exported files.
Transfer unicode to CP* change local encoding character in UTF8 format to ansi (< 256 places)(need to select your [https://en.wikipedia.org/wiki/Windows_code_pages](https://en.wikipedia.org/wiki/Windows_code_pages)) for games with UTF8 support (Borderlands+).

If you have any questions, ask them here, or contact me.

New TTG Version support all games in font editor. Walking Dead: A New Frontier landb.
Download: [http://file.quckly.ru/5k2galA276O4TUS](http://file.quckly.ru/5k2galA276O4TUS)

FontStudio 4.2 for creation fonts png with xml that will be parsed by TTG Tools:
[http://file.quckly.ru/q7scmSNVzC5nox8](http://file.quckly.ru/q7scmSNVzC5nox8)

Old versions:
With font editor for GoT/TFTB:
Download: [http://file.quckly.ru/2eZmbBKY8mo3H0G](http://file.quckly.ru/2eZmbBKY8mo3H0G)
Few newer version: [http://file.quckly.ru/f5G88DR7S8WDrAu](http://file.quckly.ru/f5G88DR7S8WDrAu)
## Post #428
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2014-12-14T01:32:16+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

hi.
so, how ttarch2 rebuilding? (Game Of Thrones EP1)
## Post #429
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-12-16T22:36:11+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Taner038
>
> hi.
so, how ttarch2 rebuilding? (Game Of Thrones EP1)
It's no need
## Post #430
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2014-12-16T22:43:58+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Haoose
>
> Taner038 wrote:hi.
so, how ttarch2 rebuilding? (Game Of Thrones EP1)
It's no need

how? 
I opened the file, but does not see the game for not close
## Post #431
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2014-12-23T21:02:19+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Anybody ? How do I close .ttarch2 files.
## Post #432
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-23T21:27:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Close? In what meaning? You can only extract the content of .ttarch2 archive.
## Post #433
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2014-12-24T07:37:45+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from merlinsvk
>
> Close? In what meaning? You can only extract the content of .ttarch2 archive.

how packed the .ttarch2 archive
## Post #434
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-24T09:25:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

You can't, and as Ekey said, it's not needed.
## Post #435
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2014-12-24T11:07:32+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from merlinsvk
>
> You can't, and as Ekey said, it's not needed.

I tried the method also fails to ekey.
## Post #436
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-24T11:30:26+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Place changed (.font, .landb, etc) files in "archives" folder.
## Post #437
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2014-12-25T00:06:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from merlinsvk
>
> Place changed (.font, .landb, etc) files in "archives" folder.

I don't understand. giving examples ?
## Post #438
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2014-12-25T20:17:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi everyone, I'm trying to use a d3dtx/dds file from german version of Sam&Max 301 to use it for english version of the game for a few days now without success. . I know the game is obsolete, but I hope anyone experienced can help anyway. 

When I extract .d3dtx from .ttarch archive of english version from S&M, ttarchext from Luigi A. shows me that the ttarch archive is V 8, is encrypted and compressed. 
The other .d3dtx from german .ttarch archive of the game shows V 9 when I extract the .d3dtx file with ttarchext.

The .d3dtx file of english version is 257kb and the german .d3dtx file is 342kb. If I replace english .d3dtx file with german .d3dtx, it only shows me a black boundary texture instead of the "new game"-texture in the game options.

I opened both versions of .d3dtx files with hexeditor. The first bytes of english version of .d3dtx starts with "ERTM", but german not. The header of german .d3dtx is a bit different..

I've read the whole topic here over and over again, but I can't inject the german .d3dtx file into the english version of the game and having the desired success. Instead of the "New Game"-texture in game Options in the title screen, the texture is shown always filled in black when I replace english .d3dtx with german .d3dtx.

Maybe it's because the .ttarch archive from english version was built vith -V 8, and .ttarch archive from german version was built with -V 9 ? I don't know.. I could really need some help..
[_d3dtx_compare.jpg](https://xentaxbackup.github.io/file/8373__d3dtx_compare.jpg)
## Post #439
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2014-12-29T15:40:33+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

goldenboy78,
Have you tried to put .d3dtx in a Pack in game folder?
## Post #440
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2014-12-29T17:24:26+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Yeah I tried to repack it back to ttarch, and put the ttarch archive back in pack folder. 
I tried with ttarchext -b -V 8 33 c:\1_output.ttarch c:\1_input_folder and with ttarchext -b -V 9 33 c:\1_output.ttarch c:\1_input_folder

But as far as I know, there's no need to pack .d3dtx back to ttarch. 
It's just enough to put .d3dtx file back to Pack folder without packing it back to ttarch.

EDIT: 
Problem solved. I substituted original .dds with edited .dds and it appears correctly now in the title screen of the game.
## Post #441
- Username: Tomas2886Cz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 16, 2013 8:15 am
- Post datetime: 2015-02-27T02:34:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Any idea if it's somehow possible to extract the .obb archives from Android versions of Telltale's games? I'd like to try and make our translations compatible with those.
## Post #442
- Username: ricky12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 24, 2014 6:47 pm
- Post datetime: 2015-03-01T07:15:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

how do i extract d3dtx files? its not work
## Post #443
- Username: ricky12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 24, 2014 6:47 pm
- Post datetime: 2015-03-01T07:16:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

nvm i think i figured it out
## Post #444
- Username: ricky12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 24, 2014 6:47 pm
- Post datetime: 2015-03-01T07:17:26+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Taner038
>
> merlinsvk wrote:Place changed (.font, .landb, etc) files in "archives" folder.

I don't understand. giving examples ?

translate landb filesa and put those files in your game folder thats it
## Post #445
- Username: Ssencall
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 14, 2015 11:06 am
- Post datetime: 2015-04-14T03:36:37+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Greetings, I'm trying to figure out how the game actually refers to the files it uses, especially *.chore files, each of which contains a segment of a whole chapter, to let translators know which line goes first and which one follows more clearly. (just going through all the line presented without contexts could be a pain in the ass, you know.) 

Through trying times I somehow managed to find out these relations between some of of the game files and the hex code that the game uses to locate them, but that's all I've got. It seems to be a kind of hash algorithm to shorten the file names (for the purpose of efficiency, perhaps,) but reversing them is above my ability and that's where I need your help.

```
previouslyon_episode4_cs_Enter_2.chore   9A 76 23 2F 2D 5E 3B BF
previouslyon_episode4_cs_Enter_3.chore   96 35 75 DA B0 CE F7 78
env_twinsEncampment_cs_Enter_2.chore     8A 9A AA 47 79 75 6C 37
```


note: All the Telltale Games product recently released seems to use the same hash code, at least The Wolf among Us, The Walking Dead, Tales from the Borderlands, and Game of Thrones.


It would be really appreciated if you could suggest what kind of algorithm it is using.
## Post #446
- Username: HieiTF76
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 01, 2015 4:31 am
- Post datetime: 2015-12-01T09:18:04+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Okashu
>
> Hi, can anyone tell me how to use ttg tools with dlogs from sam & max season 3?

Here's what I do
1. paste original dlog in "Input" folder
2. Decrypt
3. Translate txt file
4. Put translated txt in "Input" folder
5. Encrypt
6. Paste translated .dlog in "Pack" folder

Unfortunatelly, when i test it, texts are still in english. What did I do wrong?
(strangely, I managed ui_mainmenu.dlog to work, but i dont know how)

EDIT: nevermind. I was editing wrong dlog. But i have another question. What's the font used in game? ttarch has 20 font files, but it containts all fonts used in all seasons

Damn pretty old message, but well...

Hello. I'm actually trying to extract Sam & Max Season 3 french subs from the DVD version, to make them compatible with the Steam version I own.

I managed to did it for Season 2, with some little modifications to the files (minus the accentued letters, as Steam version doesn't seem to support them, so I replaced them with non-accentued equivalents. What is weird is the accentued letters works in the menu but not in the in-game subtitles ), noticed some headers from the langdb files of the Steam version had to be modified to work, but Season 2 use .langdb files when Season 3 use .dlog files (they are a langdb file, and some landb files on the DVD version, but they seem unused according to the contents of the script). I didn't even bothered to recompile the season 2 langdb files as the game handle them properly directly as langdb files.

I tried what the message I quoted says, the .dlog (env_skunkapeflagshipbridge.dlog) to .txt (env_skunkapeflagshipbridge.txt) conversion is working fine (I choose "other" in TTG Tools as other names in the list are for Season 2) then I modify a few words on the .txt file to be able to check in-game if it worked, but when I click on Encrypt to recreate the dlog file from the txt file, the dlog file is not recreated (I did put the edited .txt file in the "Input" folder) and there are no messages in TTG window (a message is displayed when I decrypt sucessfully the dlog file). 

I think I have the last TTG tools version (0.6.2, from 2011, seems old but don't think there's a new version?) so is there something I'm doing wrong? Is another tool needed to recreate the dlog file?

I saw that the DVD version of the season 3 use .landb files for the french translation, but this is not really a problem, as the contents seems to use the same format from what I saw. So I was planning to copy-paste the contexts of the french .landb files (replacing the accentued letters with non-accentues one with a find/replace in a text editor, as I did for the season 2) in the english dlog files, which is why I would need to be able to recreate them from the .txt source file, and then recompile them in a _0.ttarch file.

Edit : It seems recompiling the files in a ttarch archive is not necessary. I found a russian patch, I extracted the dlog files, put them in the game directory and the translation was still working.

Thanks a lot.

Edit 2 : I found the problem. I was deleting the dlog file from the input folder before creating the new one and it seems it was the problem. After reading a lot of pages from this forum, I found a message when someone was talking about leaving the original dlog file in the input folder and then it worked.

Also noticed that Season 3 on Steam already support accentued characters, maybe because the Season 3 use lower-case letters.

Edit 3 : Seems the accentued letters doesn't work in some "menus" (like in Sam's Notebook for example) but it's not a big problem, I'll edit those files and remove the accentued letters 

Edit 4 : Noticed something weird. Converted the french dvd .landb to .txt files. Converted the english steam .dlog to .txt files. Noticed the contents of the files was using the same template (except two ui_files that I had to modify manually) so I put the french .txt files along with the english steam .dlog in the input directory and rebuilt the .dlog. Those .dlog work fine and the game is now subtitled in french.

Did the same for the episode 2, but seems the files crash the game, so except if the template if different, it seems weird. I'll have to check each template manually, hoping it can be fixed.

Edit 5 : I confirm there is a problem but I don't know which one. I converted "env_boilerroom.dlog" to "env_boilerroom.txt" (steam english version) which contains the first subtitles of the game. I only modified one word in the .txt file, then rebuilt the "env_boilerroom.dlog" file. When I put it in the game directory, th game boot, and where the subtitles should be display, the game crash with an error. Maybe the episode 2 use another encryption, which TTG Tools can't handle?

I also tried to directly editing the original "env_boilerroom.dlog" file with an hexadecimal editor, replacing the ASCII string "city" with "TEST" and the game also crash. What is weird is that if I put the untouched "env_boilerroom.dlog", extracted from the Steam version in the game directory, the game also creash, which would make me think the problem wasn't my french modifications but rather how the game handle the file, so maybe creating a ttarch file will work, I will try that.

Edit 6 : Creating a ttarch file changed nothing, really weird.
## Post #447
- Username: HieiTF76
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 01, 2015 4:31 am
- Post datetime: 2015-12-03T11:25:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Still more weird, the subtitles replacement works fine on episode 3/4/5 of the season 3 xD (except one little menu file I had to tweak because the order of the texts wasn't the same).

I'll still take a little while to try to understand how the episode 2 works and if I don't find the problem, I'll use Xdelta to make patch from each file, to transform the Steam DVD into the DVD version, not the best way in my opinion but better than nothing if I don't find another method
## Post #448
- Username: Melkor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 04, 2015 2:51 am
- Post datetime: 2015-12-05T03:41:01+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello there!   

I was looking in the forum but couldn't find any post about how to change fonts of telltale games specifically TWOU.
My language is from right to left and it doesn't use any words from English alphabet so I have to change all the letters.

I have found some files with .font extension but I don't know what to do with them, from what I have gathered if I want to change the font it has something to do with .dds files, where I can find them and how I can edit .font/.dds files to solve my problem?

it would be nice if you lead me to a tutorial or something or just give me some clues about the process.

Thanks bros (and sis'z ? *_* )
## Post #449
- Username: Korkofilaki
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 19, 2015 2:04 pm
- Post datetime: 2015-12-15T18:06:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello, I am currently trying to translate the GOT subtitles to Greek.
Can someone please tell me where to find the font files and how to edit them to support greek letters?
## Post #450
- Username: stapheen
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 11, 2014 10:24 pm
- Post datetime: 2016-01-14T12:14:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

which fonts should I change to translate the game?
all I know is cheapsignage_50.font for subtitle
and which font are for menu ?
because when I'm chaning the menu language I get ???
## Post #451
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2016-01-16T13:51:00+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Korkofilaki
>
> Hello, I am currently trying to translate the GOT subtitles to Greek.
Can someone please tell me where to find the font files and how to edit them to support greek letters?
For edit fonts for GoT/TFTB use [viewtopic.php?p=101723#p101723](http://forum.xentax.com/viewtopic.php?p=101723#p101723)
## Post #452
- Username: badass
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 06, 2016 8:26 pm
- Post datetime: 2016-02-06T13:43:00+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

hi. i am new in translating tell tale games. i want to translate Tales From Borderlands. I extracted game archives using ttarchext but i cant convert .landb to .txt for translation. also i couldnt find the .dds or .font for changing the game's font.i also used TTG_Tools_by_quckly for converting but had no luck.I'd appreciate any help on this matter. thanks.
## Post #453
- Username: Melkor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 04, 2015 2:51 am
- Post datetime: 2016-02-07T22:26:13+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from badass
>
> hi. i am new in translating tell tale games. i want to translate Tales From Borderlands. I extracted game archives using ttarchext but i cant convert .landb to .txt for translation. also i couldnt find the .dds or .font for changing the game's font.i also used TTG_Tools_by_quckly for converting but had no luck.I'd appreciate any help on this matter. thanks.

What is your problem? Ill try to help you in anyway that i can, although my knowledge is not much.
## Post #454
- Username: Melkor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 04, 2015 2:51 am
- Post datetime: 2016-02-08T14:24:38+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I want to edit some texture in The Wolf Among Us and I need a bit of help:
I can extract/repack textures of the game with no problem with "quckly" TTG Tools but they show up completely in BLACK in the game. I guess I am saving them with wrong setting. could anyone please tell me with what setting should i save them?

Example: I should save .dds texture of fonts with "No MIP MAP" selected.

Should i use any particular setting?
## Post #455
- Username: badass
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 06, 2016 8:26 pm
- Post datetime: 2016-02-09T20:34:57+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Melkor
>
> badass wrote:hi. i am new in translating tell tale games. i want to translate Tales From Borderlands. I extracted game archives using ttarchext but i cant convert .landb to .txt for translation. also i couldnt find the .dds or .font for changing the game's font.i also used TTG_Tools_by_quckly for converting but had no luck.I'd appreciate any help on this matter. thanks.

What is your problem? Ill try to help you in anyway that i can, although my knowledge is not much.
i put my  .landb file inside input folder of TTG_Tools_by_quckly. then i open TTG_Tools_by_quckly and then going to auto Depacker ,on the drop box i choose TFTB then click Decrypt and nothing happens. i choose other options too. but nothing happens.
thanks for your help.
## Post #456
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2016-02-13T19:04:09+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from badass
>
> Melkor wrote:badass wrote:hi. i am new in translating tell tale games. i want to translate Tales From Borderlands. I extracted game archives using ttarchext but i cant convert .landb to .txt for translation. also i couldnt find the .dds or .font for changing the game's font.i also used TTG_Tools_by_quckly for converting but had no luck.I'd appreciate any help on this matter. thanks.

What is your problem? Ill try to help you in anyway that i can, although my knowledge is not much.
i put my  .landb file inside input folder of TTG_Tools_by_quckly. then i open TTG_Tools_by_quckly and then going to auto Depacker ,on the drop box i choose TFTB then click Decrypt and nothing happens. i choose other options too. but nothing happens.
thanks for your help.

Choose Landb notabenoid or .SRT Export for extract "txt" from "landb".
For extract textures from d3dtx choose TFTB.
## Post #457
- Username: badass
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 06, 2016 8:26 pm
- Post datetime: 2016-02-14T13:09:11+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> badass wrote:

What is your problem? Ill try to help you in anyway that i can, although my knowledge is not much.
i put my  .landb file inside input folder of TTG_Tools_by_quckly. then i open TTG_Tools_by_quckly and then going to auto Depacker ,on the drop box i choose TFTB then click Decrypt and nothing happens. i choose other options too. but nothing happens.
thanks for your help.

Choose Landb notabenoid or .SRT Export for extract "txt" from "landb".
For extract textures from d3dtx choose TFTB.[/quote]

thanks. that worked. but how can i convert .txt to .landb after my translation fiished? also where are the fonts? (in Tales from Borderlands)
## Post #458
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-24T11:52:04+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

The Walking Dead Michonne Episode 1 

How can we open .ttarch2 files.What is the key guys?
## Post #459
- Username: pashok6798
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Sep 06, 2014 2:45 am
- Post datetime: 2016-02-24T15:46:16+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from MitiSen
>
> The Walking Dead Michonne Episode 1 

How can we open .ttarch2 files.What is the key guys?

Here ya go: 96CA999F8DDA9A87D7CDD9B1639583AECA9698E0ABDC7AD4C685BC86699CB895CBB09BBDC8A79ECDD9C1A99C6789B3DBB0CC949AB4D7A0

Extract files (example):
C:\ttarchext.exe -o -k 96CA999F8DDA9A87D7CDD9B1639583AECA9698E0ABDC7AD4C685BC86699CB895CBB09BBDC8A79ECDD9C1A99C6789B3DBB0CC949AB4D7A0 WDM_pc_UI_data.ttarch2 C:\src_folder
## Post #460
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-02-24T23:40:24+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from pashok6798
>
> MitiSen wrote:The Walking Dead Michonne Episode 1 

How can we open .ttarch2 files.What is the key guys?



Here ya go: 96CA999F8DDA9A87D7CDD9B1639583AECA9698E0ABDC7AD4C685BC86699CB895CBB09BBDC8A79ECDD9C1A99C6789B3DBB0CC949AB4D7A0

Extract files (example):
C:\ttarchext.exe -o -k 96CA999F8DDA9A87D7CDD9B1639583AECA9698E0ABDC7AD4C685BC86699CB895CBB09BBDC8A79ECDD9C1A99C6789B3DBB0CC949AB4D7A0 WDM_pc_UI_data.ttarch2 C:\src_folder
Thx man
## Post #461
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2016-02-26T20:07:21+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

TTG Tools with font editor worked only with The Walking Dead: Michonne
Download: [http://file.quckly.ru/5k2galA276O4TUS](http://file.quckly.ru/5k2galA276O4TUS)
## Post #462
- Username: FEARka
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 22, 2011 2:10 am
- Post datetime: 2016-02-27T21:21:42+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> TTG Tools with font editor worked only with The Walking Dead: Michonne
Download: http://file.quckly.ru/5k2galA276O4TUS

This is normal? [http://www.kephost.com/image/cBC0](http://www.kephost.com/image/cBC0)  DCCSharpDistress(0).dds
## Post #463
- Username: Sajjad Rahim
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 07, 2015 5:04 pm
- Post datetime: 2016-02-28T08:51:39+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from FEARka
>
> quckly wrote:TTG Tools with font editor worked only with The Walking Dead: Michonne
Download: http://file.quckly.ru/5k2galA276O4TUS

This is normal? http://www.kephost.com/image/cBC0  DCCSharpDistress(0).dds
same to me. Any help? @quckly
## Post #464
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2016-02-28T09:07:41+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Replaced saving dds from DXT5 to DXGI_FORMAT_B5G5R5A1_UNORM
Same link: [http://file.quckly.ru/5k2galA276O4TUS](http://file.quckly.ru/5k2galA276O4TUS)

Send me all fonts.
## Post #465
- Username: Sajjad Rahim
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 07, 2015 5:04 pm
- Post datetime: 2016-02-28T17:22:00+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> Replaced saving dds from DXT5 to DXGI_FORMAT_B5G5R5A1_UNORM
Same link: http://file.quckly.ru/5k2galA276O4TUS

Send me all fonts.

export dds works fine but the problem with import dds
## Post #466
- Username: Melkor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 04, 2015 2:51 am
- Post datetime: 2016-02-28T21:53:37+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> Replaced saving dds from DXT5 to DXGI_FORMAT_B5G5R5A1_UNORM

As quckly said Save .dds files with this setting "DXGI_FORMAT_B5G5R5A1_UNORM"
What program u use? Use paint.net and select "A1R5B5G5" in the setting menu that comes up when u are saving the file.
## Post #467
- Username: supernova26
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 09, 2015 6:23 am
- Post datetime: 2016-03-09T13:07:47+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello, I'm trying to translate Tales From The Borderlands. Subtitle parts are fine, font is working but I also want to translate character intro screens. I don't know how but I think those are texture files? How can I open game texture files so I can look for those?

For example, finding "company man (you)" image and changing that in this ss:

[http://vignette3.wikia.nocookie.net/bor ... 0316191642](http://vignette3.wikia.nocookie.net/borderlands/images/1/12/Rhys_Intro.png/revision/latest?cb=20150316191642)

Is it possible?
## Post #468
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2016-03-13T06:26:40+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from supernova26
>
> Hello, I'm trying to translate Tales From The Borderlands. Subtitle parts are fine, font is working but I also want to translate character intro screens. I don't know how but I think those are texture files? How can I open game texture files so I can look for those?

For example, finding "company man (you)" image and changing that in this ss:

http://vignette3.wikia.nocookie.net/bor ... 0316191642

Is it possible?

Extract all "ui_smashcard_*Name.d3dtx" files from ttarch2 texture archives.
Use TTG Tools by quckly.
Put .d3dtx files to Import folder.
In Import/Export select TFTB and click "Export".
In photoshop or something translate dds textures.
Put translated dds files to input folder.
In Import/Export select TFTB and click "Import".
d3dtx files from output folder place in game folder.
## Post #469
- Username: stapheen
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 11, 2014 10:24 pm
- Post datetime: 2016-03-16T07:19:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Where I can find fonts in walking dead michonne?
## Post #470
- Username: FEARka
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 22, 2011 2:10 am
- Post datetime: 2016-03-18T23:05:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from stapheen
>
> Where I can find fonts in walking dead michonne?

WDM_pc_Project_txmesh.ttarch2
## Post #471
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2016-03-26T17:15:15+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> supernova26 wrote:Hello, I'm trying to translate Tales From The Borderlands. Subtitle parts are fine, font is working but I also want to translate character intro screens. I don't know how but I think those are texture files? How can I open game texture files so I can look for those?

For example, finding "company man (you)" image and changing that in this ss:

http://vignette3.wikia.nocookie.net/bor ... 0316191642

Is it possible?

Extract all "ui_smashcard_*Name.d3dtx" files from ttarch2 texture archives.
Use TTG Tools by quckly.
Put .d3dtx files to Import folder.
In Import/Export select TFTB and click "Export".
In photoshop or something translate dds textures.
Put translated dds files to input folder.
In Import/Export select TFTB and click "Import".
d3dtx files from output folder place in game folder.

Any idea how to extract .dds from .d3dtx files for this game from xbox360 ?


 Samples.rar
(156.97 KiB) Downloaded 24 times
## Post #472
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2016-03-27T23:22:26+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Tomas2886Cz
>
> Any idea if it's somehow possible to extract the .obb archives from Android versions of Telltale's games? I'd like to try and make our translations compatible with those.

Just rename .obb to ttarch2 and you should be able to extract with ttg tools or ttarchext.
## Post #473
- Username: bekir007
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 02, 2012 8:52 pm
- Post datetime: 2016-04-03T11:14:01+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

How can i convert this font to dds? For minecraft ep5.
[font.rar](https://xentaxbackup.github.io/file/10723_font.rar)
## Post #474
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2016-05-04T14:35:31+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello, can please someone on this forum tell me how to edit(Encrypt,Decrypt) The Wolf Among Us .dlog files i really need so bad    but i only find .dlog decryptor-encrypter for Sam&Max Season 3   . I Would Really Appreciate it.  
PS: For example i can give u that file: [https://yadi.sk/d/e3JAtgYDrUoWx](https://yadi.sk/d/e3JAtgYDrUoWx)
## Post #475
- Username: pashok6798
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Sep 06, 2014 2:45 am
- Post datetime: 2016-06-02T14:14:42+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Maximmum
>
> Hello, can please someone on this forum tell me how to edit(Encrypt,Decrypt) The Wolf Among Us .dlog files i really need so bad    but i only find .dlog decryptor-encrypter for Sam&Max Season 3   . I Would Really Appreciate it.  
PS: For example i can give u that file: https://yadi.sk/d/e3JAtgYDrUoWx
Why you need to "decrypt" dlog files? Text in landb files. Find somewhere TTG Tools.
## Post #476
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2016-06-07T17:38:39+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from pashok6798
>
> Maximmum wrote:Hello, can please someone on this forum tell me how to edit(Encrypt,Decrypt) The Wolf Among Us .dlog files i really need so bad    but i only find .dlog decryptor-encrypter for Sam&Max Season 3   . I Would Really Appreciate it.  
PS: For example i can give u that file: https://yadi.sk/d/e3JAtgYDrUoWx
Why you need to "decrypt" dlog files? Text in landb files. Find somewhere TTG Tools.

Well i don't need a text i need a Lua code in dlog files because i want to make a little modification

P:S TTG Tools doesn't decrypt dlog files
## Post #477
- Username: LagunaFAN
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 10, 2014 8:55 am
- Post datetime: 2016-07-06T23:49:26+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi guys!

I've got a question about the "Game of Thrones". How can I edit or re-create LUA to use different ttarch2? I have not found the answer to this question.  

I would be glad of any help!
## Post #478
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2016-07-07T13:23:08+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from LagunaFAN
>
> Hi guys!

I've got a question about the "Game of Thrones". How can I edit or re-create LUA to use different ttarch2? I have not found the answer to this question.  

I would be glad of any help!

Use existing .lua file. Encode/Decode by ttarchext. Change path to ttarch2 file in hex editor.
## Post #479
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2016-07-07T13:24:24+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Maximmum
>
> pashok6798 wrote:Maximmum wrote:Hello, can please someone on this forum tell me how to edit(Encrypt,Decrypt) The Wolf Among Us .dlog files i really need so bad    but i only find .dlog decryptor-encrypter for Sam&Max Season 3   . I Would Really Appreciate it.  
PS: For example i can give u that file: https://yadi.sk/d/e3JAtgYDrUoWx
Why you need to "decrypt" dlog files? Text in landb files. Find somewhere TTG Tools.

Well i don't need a text i need a Lua code in dlog files because i want to make a little modification

P:S TTG Tools doesn't decrypt dlog files

Are you sure that dlog files contains Lua code?
## Post #480
- Username: LagunaFAN
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 10, 2014 8:55 am
- Post datetime: 2016-07-07T17:43:10+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> Use existing .lua file. Encode/Decode by ttarchext. Change path to ttarch2 file in hex editor.
My fault... Initially, I tried to decrypt through ttarchext with option -d (ttarchext -d 0 <gamenum> <.lua> <output>) and the result was wrong, but not looked example where decrypt Lenc without options (ttarchext <gamenum> <.lua> <output>).

Thanks for your help!
## Post #481
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2016-07-10T08:52:34+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Yes mostly thanks to file swapping and partly by my research with hex editor i'm definitely sure they contain code that i need!
## Post #482
- Username: Sajjad Rahim
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 07, 2015 5:04 pm
- Post datetime: 2016-08-03T05:02:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

any key for "Batman - The Telltale Series" ep1 out now
## Post #483
- Username: batuzama
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 24, 2014 3:20 am
- Post datetime: 2016-08-03T11:39:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi Everyone! I don't know how to unpack the Batman:The Telltale Series files to get the LANDB files, and get the TXT files. Can you help me 
[](http://hizliresim.com/kvq7A9)
## Post #484
- Username: pashok6798
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Sep 06, 2014 2:45 am
- Post datetime: 2016-08-04T11:30:37+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from batuzama
>
> Hi Everyone! I don't know how to unpack the Batman:The Telltale Series files to get the LANDB files, and get the TXT files. Can you help me

Here's the key of descryption: 81CAA1A185DA6473A2AED6D89FC6C188995A6FD8B1E297DD96519F979AE0CE95CD76627FA3C4ADD9D6E2A99C6774B3E3B2C49464A0A281

But it won't work on compressed archives, because Telltale compressing now another compress method. auigi is researching now. In landb files I found differents only in header: instead 5VSM they write 6VSM.

UPD: Added txt files of Batman.
[Batman.7z](https://xentaxbackup.github.io/file/11498_Batman.7z)
## Post #485
- Username: dufresne
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 17, 2015 2:34 am
- Post datetime: 2016-08-07T18:12:17+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from pashok6798
>
> batuzama wrote:Hi Everyone! I don't know how to unpack the Batman:The Telltale Series files to get the LANDB files, and get the TXT files. Can you help me 


Here's the key of descryption: 81CAA1A185DA6473A2AED6D89FC6C188995A6FD8B1E297DD96519F979AE0CE95CD76627FA3C4ADD9D6E2A99C6774B3E3B2C49464A0A281

But it won't work on compressed archives, because Telltale compressing now another compress method. auigi is researching now. In landb files I found differents only in header: instead 5VSM they write 6VSM.

UPD: Added txt files of Batman.

Well, how did you unpack these files @pashok6798 and how do we repack them?
## Post #486
- Username: dante h3
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 28, 2015 6:11 am
- Post datetime: 2016-08-09T04:12:38+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

anyone know how I can edit batman fonts?
when I change 6VSM to 5VSM some of fonts open with ttg tool (With font editor for TWD Michonne),
but tool can't recognize texture.


and when I import a new dds, don't work correctly in game.


I guess I use wrong dds type for import.
anyone know what kind of dds I should use?
or where I can find a new tool for batman fonts?

ps: sorry for my bad English.
[Batman-Fonts.rar](https://xentaxbackup.github.io/file/11518_Batman-Fonts.rar)
## Post #487
- Username: pashok6798
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Sep 06, 2014 2:45 am
- Post datetime: 2016-08-09T08:33:37+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from dante h3
>
> anyone know how I can edit batman fonts?
when I change 6VSM to 5VSM some of fonts open with ttg tool (With font editor for TWD Michonne),
but tool can't recognize texture.


and when I import a new dds, don't work correctly in game.


I guess I use wrong dds type for import.
anyone know what kind of dds I should use?
or where I can find a new tool for batman fonts?

ps: sorry for my bad English.
Wait... Why you tried to change header? Which version did you use? In Michonne and Batman texture format differents.
## Post #488
- Username: dante h3
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 28, 2015 6:11 am
- Post datetime: 2016-08-09T08:52:50+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from pashok6798
>
> 
Wait... Why you tried to change header?
because tool didn't worked with that header, and i needed to change coordinates.

> Reply from pashok6798
>
> 
Which version did you use?
[http://file.quckly.ru/5k2galA276O4TUS](http://file.quckly.ru/5k2galA276O4TUS)

> Reply from pashok6798
>
> 
In Michonne and Batman texture format differents.
i know. but don't know how i can solve texture problem.
## Post #489
- Username: pashok6798
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Sep 06, 2014 2:45 am
- Post datetime: 2016-08-09T09:09:38+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Here's test font.



Batman_win7 2016-08-09 12-08-00-047.jpg (133.62 KiB) Viewed 227 times


[http://s000.tinyupload.com/index.php?fi ... 5950442618](http://s000.tinyupload.com/index.php?file_id=37402596755950442618)
## Post #490
- Username: Sajjad Rahim
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 07, 2015 5:04 pm
- Post datetime: 2016-08-10T06:41:38+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from pashok6798
>
> Here's test font.
Batman_win7 2016-08-09 12-08-00-047.jpg
http://s000.tinyupload.com/index.php?fi ... 5950442618

hey
how did you put .fnt (xml) in .font?
I know you can put xml if it from fontstudie
## Post #491
- Username: rico555
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 14, 2016 2:59 am
- Post datetime: 2016-08-13T19:33:53+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

quckly: If you have a new TTG Tools, can you share with us?
## Post #492
- Username: falta
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Aug 16, 2016 8:38 am
- Post datetime: 2016-08-16T01:09:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from pashok6798
>
> batuzama wrote:Hi Everyone! I don't know how to unpack the Batman:The Telltale Series files to get the LANDB files, and get the TXT files. Can you help me 


Here's the key of descryption: 81CAA1A185DA6473A2AED6D89FC6C188995A6FD8B1E297DD96519F979AE0CE95CD76627FA3C4ADD9D6E2A99C6774B3E3B2C49464A0A281

But it won't work on compressed archives, because Telltale compressing now another compress method. auigi is researching now. In landb files I found differents only in header: instead 5VSM they write 6VSM.

UPD: Added txt files of Batman.

how will I do repack ?
## Post #493
- Username: falta
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Aug 16, 2016 8:38 am
- Post datetime: 2016-08-31T12:16:47+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

how can i  txt to landb repack.  ttg tools auto(De)packer Encrypt don't work.  help?
## Post #494
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2016-08-31T14:06:09+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from falta
>
> how can i  txt to landb repack.  ttg tools auto(De)packer Encrypt don't work.  help?
Try this:
[https://mega.nz/#!nFcBgZTB!U2zFlokwme1s ... 7Mldcod-No](https://mega.nz/#!nFcBgZTB!U2zFlokwme1shVWOlpivUUvlC3ue6M4a87Mldcod-No)

I am translating with it Batman and it works properly.
## Post #495
- Username: falta
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Aug 16, 2016 8:38 am
- Post datetime: 2016-08-31T14:19:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Godxon1
>
> falta wrote:how can i  txt to landb repack.  ttg tools auto(De)packer Encrypt don't work.  help?
Try this:
https://mega.nz/#!nFcBgZTB!U2zFlokwme1s ... 7Mldcod-No

I am translating with it Batman and it works properly.

thank you but how can i repack?  landb and txt files put input +  Encrypt. isn't it ? Where am I doing wrong?
## Post #496
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2016-08-31T14:43:30+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from falta
>
> Godxon1 wrote:falta wrote:how can i  txt to landb repack.  ttg tools auto(De)packer Encrypt don't work.  help?
Try this:
https://mega.nz/#!nFcBgZTB!U2zFlokwme1s ... 7Mldcod-No

I am translating with it Batman and it works properly.

thank you but how can i repack?  landb and txt files put input +  Encrypt. isn't it ? Where am I doing wrong?

You must copy translated files + original landb to input folder, than encrypt. In output you will have translated landb. Than move it to game directory/archives and you will have game translated.
## Post #497
- Username: falta
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Aug 16, 2016 8:38 am
- Post datetime: 2016-08-31T14:52:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

quote]


thank you but how can i repack?  landb and txt files put input +  Encrypt. isn't it ? Where am I doing wrong?[/quote]

You must copy translated files + original landb to input folder, than encrypt. In output you will have translated landb. Than move it to game directory/archives and you will have game translated.[/quote]

Look.   

[](http://hizliresim.com/pEzDNN)

[](http://hizliresim.com/kEBD87)
## Post #498
- Username: falta
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Aug 16, 2016 8:38 am
- Post datetime: 2016-09-06T15:21:37+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

[](http://hizliresim.com/J3q0jE)


Where am I doing wrong? Is there no one to help?
## Post #499
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2016-09-08T09:50:42+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from falta
>
> 


Where am I doing wrong? Is there no one to help?
Download the tool, that I posted on previous page.
## Post #500
- Username: falta
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Aug 16, 2016 8:38 am
- Post datetime: 2016-09-08T10:56:02+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Godxon1
>
> falta wrote:


Where am I doing wrong? Is there no one to help?
Download the tool, that I posted on previous page.


[](http://hizliresim.com/pEzDNN)

[](http://hizliresim.com/kEBD87)

i am trying you tool but it is not repack.
## Post #501
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2016-09-08T14:51:32+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from falta
>
> Godxon1 wrote:falta wrote:


Where am I doing wrong? Is there no one to help?
Download the tool, that I posted on previous page.






i am trying you tool but it is not repack.
Huh, have you tried reinstall game and unpack *.landb files FROM *.TTARCH2 files again?
## Post #502
- Username: falta
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Aug 16, 2016 8:38 am
- Post datetime: 2016-09-09T07:54:12+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

yes i tried. Do you want to try? 


landb and txt files down
## Post #503
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2016-09-10T17:58:54+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from falta
>
> yes i tried. Do you want to try? 


landb and txt files down
It works for me, here's a little tutorial:
1) Copy all *.landb files to INPUT folder, delete all other files, that are in INPUT
2) Start TTGtool, click yes, start "Auto(De)Packer
3) Choose Minecraft
4) Click "Decrypt, Export"
5) Edit text files, that are in OUTPUT folder and copy them to INPUT folder
6) Start TTGtool, click yes, start "Auto(De)Packer
7) Choose Minecraft
 Click "Encrypt, Pack, Import"
9) *.landb files, that are in OUPUT folder move to game directory/archives and you have translated game!
## Post #504
- Username: falta
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Aug 16, 2016 8:38 am
- Post datetime: 2016-09-10T21:03:53+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Godxon1
>
> falta wrote:yes i tried. Do you want to try? 


landb and txt files down
It works for me, here's a little tutorial:
1) Copy all *.landb files to INPUT folder, delete all other files, that are in INPUT
2) Start TTGtool, click yes, start "Auto(De)Packer
3) Choose Minecraft
4) Click "Decrypt, Export"
5) Edit text files, that are in OUTPUT folder and copy them to INPUT folder
6) Start TTGtool, click yes, start "Auto(De)Packer
7) Choose Minecraft
 Click "Encrypt, Pack, Import"
9) *.landb files, that are in OUPUT folder move to game directory/archives and you have translated game!


Okeeyy my friend  i understand. look 


[](http://hizliresim.com/QQpZJk)


i will make arrangement again   very very thank you
## Post #505
- Username: benladen
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 14, 2016 8:31 am
- Post datetime: 2016-11-18T07:41:18+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Need help for the key of PSVita TWD1.
## Post #506
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-12-03T05:40:08+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> My modification of TTG Tools by Den Em:

I do not have time to describe all the features of the program and how to use it, so the summary:

Features:
 Work with Hector/Puzzle Agent/TWD (Not test)/TWDS2/TWAU/TFTB/GoT
 Work: Land/Font/Textures Import/Export
 Landb: Export to TTG Tools original format (Landb), "NAME_OF_SPEAKER: TEXT" format (Notabenoid), and like .SRT format (Line number, Author, Text, Empty line). Import from TTG Original (In GUI with select "Landb"), .SRT (In GUI and console)
 To import landb in .SRT format into .LANDB from *.txt files you can use TTG Tools from console: ""TTG Tools.exe" -import landb input output", input/output - you folders.
 To import/export textures, select you game in the list of games in Auto Depacker.

The current version of Font Editor correctly works only with TFTB/GoT. It's using Unicode to represent characters. And is designed for Cyrillic characters.
Landb TFTB/GoT export and import in CP-125*, and save strings in landb as UTF-8.

If you have any questions, ask them here, or contact me.

With font editor for GoT/TFTB:
Download: http://file.quckly.ru/2eZmbBKY8mo3H0G
Few newer version: http://file.quckly.ru/f5G88DR7S8WDrAu

With font editor for TWD Michonne:
Download: http://file.quckly.ru/5k2galA276O4TUS

Hi! I am starting with Walking Dead, how to use utf8 string with this game, please. Could you help me?
## Post #507
- Username: Smexhy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 05, 2016 8:13 pm
- Post datetime: 2016-12-05T22:37:52+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Boys, I am tottaly new at this  How can I translate TWD: Michonne? There are too many programs, topics, but there is nothing for that who are starting with this or I am just idiot and dodn'f find it  
I beg you, is there anyone who know explain me this method of translation or just post me some link with tutorial? 
Love ya
## Post #508
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-12-21T08:48:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi, is there any code for twd season 3 landb file ?
## Post #509
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2017-01-01T06:30:34+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Taner038
>
> Hi, is there any code for twd season 3 landb file ?

It's same as Michonne but only header magic is different to 6VSM.
## Post #510
- Username: The Spyker
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 28, 2016 7:07 pm
- Post datetime: 2017-01-03T18:58:26+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello, My name is The Spyker and I´am translating a TWD: A New Frontier in Czech.

I have a problem with my C:/ Disc and all my data was erased.. (My Translate data was in Cloud)
I have my TTG Tools there. So, I have a .txt files, What i translating and i cant convert in .landb files

Can someone post here New version of TTG Tools with TWD: A New Frontier ?

Or Help me fix problem with JIT something

Details:



Error with decrypting Decrypt error.png (193.71 KiB) Viewed 44 times



Thanks for help,
The Spyker
## Post #511
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2017-01-08T17:49:39+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Updated version of TTG Tools worked with 6VSM landb from TWD S3.
Download: [http://file.quckly.ru/5k2galA276O4TUS](http://file.quckly.ru/5k2galA276O4TUS)
## Post #512
- Username: The Spyker
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 28, 2016 7:07 pm
- Post datetime: 2017-01-08T18:56:36+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> Updated version of TTG Tools worked with 6VSM landb from TWD S3.
Download: http://file.quckly.ru/5k2galA276O4TUS


Thanks
## Post #513
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-01-09T03:24:11+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hey guys
I have a problem about translation for walking dead season 1
I cant open ui-subtitles_text.prop and subtitles.secne
How i can edit this files?
## Post #514
- Username: AIC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 09, 2016 10:05 pm
- Post datetime: 2017-01-11T07:42:29+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Can you create a landb convert tool that corresponds to "WDS1"?

Also, please attach the new extension geurigo file template, so please make a tool for it if possible.

Sorry to Bad English.. 


Ps. Please use the attached " landb template " if necessary.Someone else tuned it into the 010 Editor.

WDS1 Landb Templet :
[https://www.dropbox.com/s/pzantnhbq55tw ... nd.bt?dl=0](https://www.dropbox.com/s/pzantnhbq55twdr/landb_wdand.bt?dl=0)

WDS1 Mobile Font Templet:
[https://www.dropbox.com/s/vb9498fxlt9q0 ... s2.bt?dl=0](https://www.dropbox.com/s/vb9498fxlt9q0o2/font_wds2.bt?dl=0)
## Post #515
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-01-11T08:41:36+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

thank bun this cant help
i mean do you have a tool about this
this is about pc version>not about mobile games
how i can edit subtitles_text.secne
becuse i want change size and postion of subtitles and text line in the walking dead season 1 &2
edit size and postion
## Post #516
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-01-11T08:48:08+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> Updated version of TTG Tools worked with 6VSM landb from TWD S3.
Download: http://file.quckly.ru/5k2galA276O4TUS
good    
thats was so good  
but font editor ahve a uh-ertm\a.m problem! in sam and max and game of throns
anyway... that was good
and this tool dont have utf-16,just have a binary ance type for landb
## Post #517
- Username: xanger94
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 09, 2017 5:34 am
- Post datetime: 2017-01-13T13:29:45+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> Updated version of TTG Tools worked with 6VSM landb from TWD S3.
Download: http://file.quckly.ru/5k2galA276O4TUS

Hello, the program does not generate me the txt file from landb. I'm trying to translate the New Frontier.
I put the file ui_episode_english.landb in "input" but when I Auto(De)Packer: "Error. Please write me about this!"
## Post #518
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2017-01-14T09:57:00+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

AIC, just use last version from the my post and select "Landb .srt export". That works with all games.
GHOST DEAD, you may try find and change hex values in the .scene file.
GHOST DEAD, download last version of TTG Tools, i added support of all TTG games in one font editor.
xanger94, try select "Landb .srt export".
## Post #519
- Username: xanger94
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 09, 2017 5:34 am
- Post datetime: 2017-01-14T21:10:17+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> AIC, just use last version from the my post and select "Landb .srt export". That works with all games.
GHOST DEAD, you may try find and change hex values in the .scene file.
GHOST DEAD, download last version of TTG Tools, i added support of all TTG games in one font editor.
xanger94, try select "Landb .srt export".

Hi, thanks for the reply.

I translated the first episode of "A New Frontier" but the game does not find the new language in the settings. These were my steps:

```
ttarchext 61 "C:\Program Files (x86)\Steam\steamapps\common\The Walking Dead - A New Frontier (Season 3)\archives\WD3_pc_WalkingDead301_data.ttarch2" "C:\Users\Daniele\Desktop\TTG Tools\input"
```


with TTG Tools I extracted files txt from landb and I translated the env_*.txt file.
I put the txt file in to the TTG Tools input folder, I put in the input folder landb file renamed as English in Italian and I created new landb output file

Now I recreated a ttarch files, not ttarch2. I created the file with the command:

```
ttarchext -b -x -V 8 61 c:\Users\Daniele\Desktop\0.ttarch "c:\Users\Daniele\Desktop\TTG TOOLS\output"
```


I copied the 0.ttarch files in archives but can not find my language, where am I wrong?
## Post #520
- Username: AIC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 09, 2016 10:05 pm
- Post datetime: 2017-01-15T08:30:13+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> AIC, just use last version from the my post and select "Landb .srt export". That works with all games.
GHOST DEAD, you may try find and change hex values in the .scene file.
GHOST DEAD, download last version of TTG Tools, i added support of all TTG games in one font editor.
xanger94, try select "Landb .srt export".

I can't find a "a landb srt export". :{
## Post #521
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2017-01-15T08:44:37+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

For compile ttarch2 files use: 

```
ttarchext.exe -o -b -V 8 61 ep1.ttarch2 ".\output"
```


Create file _resdesc_50_WalkingDead301.lua with content:

```
set.name = "WalkingDead301"
set.setName = "WalkingDead301"
set.descriptionFilenameOverride = ""
set.logicalName = "<WalkingDead301>"
set.logicalDestination = "<>"
set.priority = 101
set.localDir = _currentDirectory
set.enableMode = "bootable"
set.version = "trunk"
set.descriptionPriority = 0
set.gameDataName = "WalkingDead301 Game Data"
set.gameDataPriority = 0
set.gameDataEnableMode = "constant"
set.localDirIncludeBase = true
set.localDirRecurse = false
set.localDirIncludeOnly = nil
set.localDirExclude = 
{
    "Packaging/",
    "_dev/"
}
set.gameDataArchives = 
{
    _currentDirectory .. "ep1.ttarch2",
    _currentDirectory .. "WD3_pc_WalkingDead301_anichore.ttarch2",
    _currentDirectory .. "WD3_pc_WalkingDead301_data.ttarch2",
    _currentDirectory .. "WD3_pc_WalkingDead301_ms.ttarch2",
    _currentDirectory .. "WD3_pc_WalkingDead301_txmesh.ttarch2",
    _currentDirectory .. "WD3_pc_WalkingDead301_voice.ttarch2"
}
RegisterSetDescription(set)

```

and compile them: 
```
ttarchext -o -e 0 61 _resdesc_50_WalkingDead301.lua .\
```


Copy both files to game folder.
## Post #522
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2017-01-15T08:50:06+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from AIC
>
> quckly wrote:AIC, just use last version from the my post and select "Landb .srt export". That works with all games.
GHOST DEAD, you may try find and change hex values in the .scene file.
GHOST DEAD, download last version of TTG Tools, i added support of all TTG games in one font editor.
xanger94, try select "Landb .srt export".

I can't find a "a landb srt export". :{
This is default option in import/export dialog.



Снимок.PNG (38.35 KiB) Viewed 154 times
## Post #523
- Username: AIC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 09, 2016 10:05 pm
- Post datetime: 2017-01-15T09:51:16+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> AIC wrote:quckly wrote:AIC, just use last version from the my post and select "Landb .srt export". That works with all games.
GHOST DEAD, you may try find and change hex values in the .scene file.
GHOST DEAD, download last version of TTG Tools, i added support of all TTG games in one font editor.
xanger94, try select "Landb .srt export".

I can't find a "a landb srt export". :{
This is default option in import/export dialog.
example

"lua" as a "ttarchext" tool can be modified?

Sorry to bad English
## Post #524
- Username: xanger94
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 09, 2017 5:34 am
- Post datetime: 2017-01-15T15:35:05+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> For compile ttarch2 files use: 
Code: Select allttarchext.exe -o -b -V 8 61 ep1.ttarch2 ".\output"

...

Copy both files to game folder.

I tried it and I did not find the language, I'm pretty sure That I'm wrong in the creation of landb files...
Once the txt files are extracted and translated, how I recreate the landb archive?

Thanks
## Post #525
- Username: rico555
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 14, 2016 2:59 am
- Post datetime: 2017-01-15T21:41:00+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

xanger94: Don't rename the .landb files!!! Test: put the translated .landb files to the game archives folder.


quckly: Do you plan to upgrade the TTG Tols for Batman and TWD S3 .d3dtx files?
## Post #526
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2017-01-16T17:32:36+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

xanger94, rename landb files to language that you see in the game.
rico555, i think that version works with landb files from batman. Did you try to extract d3dtx? Probably you just need to change dds header to correct.
## Post #527
- Username: rico555
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 14, 2016 2:59 am
- Post datetime: 2017-01-16T21:18:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> xanger94, rename landb files to language that you see in the game.
rico555, i think that version works with landb files from batman. Did you try to extract d3dtx? Probably you just need to change dds header to correct.

Hm? TFTB .d3dtx extract work with AutoDepacker -> GoT/TFTB -> export

What should I do with the Batman .d3dtx?
## Post #528
- Username: AIC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 09, 2016 10:05 pm
- Post datetime: 2017-01-17T09:35:26+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

How do I solve this?
An annual figure. the file lua...
[asd.png](https://xentaxbackup.github.io/file/12242_asd.png)
## Post #529
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2017-01-17T15:57:17+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

rico555, firstly upload a considered d3dtx file.
AIC, edit hex values in the file. Thats compiled lua file. 
Here is [http://4pda.ru/forum/index.php?showtopi ... ry38362576](http://4pda.ru/forum/index.php?showtopic=573198&st=1480#entry38362576) example modification to android version.
## Post #530
- Username: rico555
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 14, 2016 2:59 am
- Post datetime: 2017-01-20T10:49:45+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> rico555, firstly upload a considered d3dtx file.
AIC, edit hex values in the file. Thats compiled lua file. 
Here is http://4pda.ru/forum/index.php?showtopi ... ry38362576 example modification to android version.

d3dtx files: [http://www59.zippyshare.com/v/f9UuwmMh/file.html](http://www59.zippyshare.com/v/f9UuwmMh/file.html)
## Post #531
- Username: tice17
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 04, 2015 1:20 am
- Post datetime: 2017-01-21T16:21:40+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi, I'm currently trying to translate twd a new frontier to my local language but having problems with landb-txt/srt conversion

here's the error,

[http://prntscr.com/dyifuw](http://prntscr.com/dyifuw)

I have solved my problem. Thx to slayer983.

But now, ihave another problem  i couldn't find the font file.    Does anybody know which ttarch files contain the fonts?

All right... its solved too

But now the ttg tools cannot open the font file   
[http://prntscr.com/dylxsy](http://prntscr.com/dylxsy)
## Post #532
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2017-02-01T19:35:27+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I updated TTG Tools with support TWD Season 3 fonts.
Download: [http://file.quckly.ru/5k2galA276O4TUS](http://file.quckly.ru/5k2galA276O4TUS)
## Post #533
- Username: tice17
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 04, 2015 1:20 am
- Post datetime: 2017-02-01T23:27:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> I updated TTG Tools with support TWD Season 3 fonts.
Download: http://file.quckly.ru/5k2galA276O4TUS
Thx!!
## Post #534
- Username: slayer983
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 30, 2012 4:26 am
- Post datetime: 2017-02-02T08:41:09+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from tice17
>
> 
Thx!!

well, you're in luck
## Post #535
- Username: gokhan935
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 06, 2016 11:50 am
- Post datetime: 2017-02-14T02:16:39+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from quckly
>
> I updated TTG Tools with support TWD Season 3 fonts.
Download: http://file.quckly.ru/5k2galA276O4TUS

thank you so much but when i try to use font editor i get following error.
[http://prnt.sc/e8g0bd](http://prnt.sc/e8g0bd)
## Post #536
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-02-22T15:04:19+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from gokhan935
>
> quckly wrote:I updated TTG Tools with support TWD Season 3 fonts.
Download: http://file.quckly.ru/5k2galA276O4TUS

thank you so much but when i try to use font editor i get following error.
http://prnt.sc/e8g0bd
I made a font and translated wakling dead season3!
Mayby your tool have problem or somthing like that
Anyway... Try ttg tool for version of batman telltale. I think this version can work on font of walking dead season3.
## Post #537
- Username: bero
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Dec 27, 2010 1:05 am
- Post datetime: 2017-03-08T01:01:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

TTG Tools Font Editor looks work with no-header  (extract with ttarchext -m, no "6VSM" header)
after edit font,
how do I add "6VSM" header?
## Post #538
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-03-09T06:41:21+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from bero
>
> TTG Tools Font Editor looks work with no-header  (extract with ttarchext -m, no "6VSM" header)
after edit font,
how do I add "6VSM" header?
Use telltale eplorer to extract files... Becuse ttarchext have a bg problem in header of new games
Find telltale explorer in internet
I think you can find this tool in quickandeasysoftwars.net or in searching in internet.. 
Use telltale explorer
## Post #539
- Username: bero
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Dec 27, 2010 1:05 am
- Post datetime: 2017-03-09T18:11:49+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from GHOST DEAD
>
> bero wrote:TTG Tools Font Editor looks work with no-header  (extract with ttarchext -m, no "6VSM" header)
after edit font,
how do I add "6VSM" header?
Use telltale eplorer to extract files... Becuse ttarchext have a bg problem in header of new games
Find telltale explorer in internet
I think you can find this tool in quickandeasysoftwars.net or in searching in internet.. 
Use telltale explorer

thanks but it looks not support new games such as batman
## Post #540
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-03-10T03:19:54+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from bero
>
> GHOST DEAD wrote:bero wrote:TTG Tools Font Editor looks work with no-header  (extract with ttarchext -m, no "6VSM" header)
after edit font,
how do I add "6VSM" header?
Use telltale eplorer to extract files... Becuse ttarchext have a bg problem in header of new games
Find telltale explorer in internet
I think you can find this tool in quickandeasysoftwars.net or in searching in internet.. 
Use telltale explorer

thanks but it looks not support new games such as batman

Download new versoin (2016) telltale explorer
New version can support all ttarch files
## Post #541
- Username: maltek
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 09, 2015 7:40 pm
- Post datetime: 2017-03-12T15:21:06+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Android
There was no problem in episode 1 but the other sections are unfortunately not working.
## Post #542
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-04-12T00:39:53+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

We are half through the translation of TWD S3.
I extracted/translated/repacked all the *.landb files in the game but there are still some text that i cannot find to translate.
I can see there are some texts in the *.prop files but i cannot edit them.
And there are also this *.dlog files that i feel like i need to open and translate some texts in it.

How can i open those files? Or what are those files? Some help/explanation would be greatly appreciated !@_@!
## Post #543
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-04-12T02:57:04+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I can not decrypt. please! TWD S3

PS: I am Vietnamese. My english is poor :p
## Post #544
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-04-12T04:37:10+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from binlv
>
> 
I can not decrypt. please! TWD S3

PS: I am Vietnamese. My english is poor :p

OK... Try This version of TTG TOOL, this vesion can edit all font and text from .font & .landb or langb files
Link: [http://www.mediafire.com/file/4aa7e8gi8 ... edition.7z](http://www.mediafire.com/file/4aa7e8gi84f2kub/ttg_tool+original+compelet+edition.7z)
## Post #545
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-04-12T05:41:32+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from GHOST DEAD
>
> binlv wrote:
I can not decrypt. please! TWD S3

PS: I am Vietnamese. My english is poor :p

OK... Try This version of TTG TOOL, this vesion can edit all font and text from .font & .landb or langb files
Link: http://www.mediafire.com/file/4aa7e8gi8 ... edition.7z

thank you. But I still get errors, apparently this tool does not support TWD S3

Obviously I copied all .landb files to INPUT, but I still can not decrypt
## Post #546
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-04-12T16:14:25+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

What should I do to edit this .font file and repack it. I need to translate it to Vietnamese language. help!
## Post #547
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-04-13T04:56:24+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from binlv
>
> What should I do to edit this .font file and repack it. I need to translate it to Vietnamese language. help!
i know! you cant work with ttg tool... right? maybe your windows have a problem  
and if you dont have any font for your language... so, give me all characters in your language and give me your .ttf (font file). ok?
## Post #548
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-04-14T16:59:54+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from GHOST DEAD
>
> binlv wrote:What should I do to edit this .font file and repack it. I need to translate it to Vietnamese language. help! 
i know! you cant work with ttg tool... right? maybe your windows have a problem  
and if you dont have any font for your language... so, give me all characters in your language and give me your .ttf (font file). ok?

If so, then I thank you very much 
These are the characters of my language:

```
!"#$%&'()*+,-./0123456789:;<=>?@AÁÀẢÃẠĂẮẶBCDĐEÉÈẺẼẸÊẾỀỂỄỆFGHIÍÌỈĨỊJKLMNOÓÒỎÕỌÔỐỒỔỖỘƠỚỜỞỠỢPQRSTUÚÙỦŨỤƯỨỪỬỮỰVWXYÝỲỶỸỴZ[\]^_`aáàảãạăắặbcdđeéèẻẽẹêếềểễệfghiíìỉĩịjklmnoóòỏõọôốồổỗộơớờởỡợpqrstuúùủũụưứừửữựvwxyýỳỷỹỵz{|}~
```

[http://www.mediafire.com/file/2s9lbtdha ... nicode.zip](http://www.mediafire.com/file/2s9lbtdha2b5s29/Unicode.zip)

 You can took file font any, but  easy reading^^
 If you have the free time, you can say how to edit this *.font file?
## Post #549
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-04-21T16:14:37+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from binlv
>
> GHOST DEAD wrote:binlv wrote:What should I do to edit this .font file and repack it. I need to translate it to Vietnamese language. help! 
i know! you cant work with ttg tool... right? maybe your windows have a problem  
and if you dont have any font for your language... so, give me all characters in your language and give me your .ttf (font file). ok?

If so, then I thank you very much 
These are the characters of my language:
Code: Select all!"#$%&'()*+,-./0123456789:;<=>?@AÁÀẢÃẠĂẮẶBCDĐEÉÈẺẼẸÊẾỀỂỄỆFGHIÍÌỈĨỊJKLMNOÓÒỎÕỌÔỐỒỔỖỘƠỚỜỞỠỢPQRSTUÚÙỦŨỤƯỨỪỬỮỰVWXYÝỲỶỸỴZ[\]^_`aáàảãạăắặbcdđeéèẻẽẹêếềểễệfghiíìỉĩịjklmnoóòỏõọôốồổỗộơớờởỡợpqrstuúùủũụưứừửữựvwxyýỳỷỹỵz{|}~
http://www.mediafire.com/file/2s9lbtdha ... nicode.zip

 You can took file font any, but  easy reading^^
 If you have the free time, you can say how to edit this *.font file?
I will make a font. But tell me your subtitles size ana family font (name font)
## Post #550
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-04-21T16:26:54+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hey guys... I translated the wolf among us and i translated every text in this game...
But i cant edit (your choice) in end of any episode. But i fount this text. Choice texts in choice.prop
I can see this text in hex editor and i want edit  them in text files. I want edit this texts in hex editor but my text is beggrer and i cant edit in text... Plus, hex cant support my characters in real type.
 Who can help me? For edit choice.prop(convert to text and repack)
## Post #551
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-04-21T17:28:11+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from GHOST DEAD
>
> binlv wrote:What should I do to edit this .font file and repack it. I need to translate it to Vietnamese language. help! 
i know! you cant work with ttg tool... right? maybe your windows have a problem  
and if you dont have any font for your language... so, give me all characters in your language and give me your .ttf (font file). ok?

thank u, I think the subtitle size may be slightly larger than English for easy to read, and Font name is fontvietnam
Another question i can used fonts make by you for all fonts telltale like the wolf among us, ...?
## Post #552
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-04-22T02:18:12+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

thank u, I think the subtitle size may be slightly larger than English for easy to read, and Font name is fontvietnam
Another question i can used fonts make by you for all fonts telltale like the wolf among us, ...?[/quote]

no! just for newer games. like Marvel's Guardians of the Galaxy The Telltale Series or other newer games... i send your font 1 day latar. ok?
and this font can use no the wolf among us or old games.
## Post #553
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-04-22T08:02:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from GHOST DEAD
>
> thank u, I think the subtitle size may be slightly larger than English for easy to read, and Font name is fontvietnam
Another question i can used fonts make by you for all fonts telltale like the wolf among us, ...?

ok thank u, later day I will download

but that font as TWD S1, TWD S2 .. not used??
## Post #554
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-04-23T02:55:51+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from binlv
>
> GHOST DEAD wrote:thank u, I think the subtitle size may be slightly larger than English for easy to read, and Font name is fontvietnam
Another question i can used fonts make by you for all fonts telltale like the wolf among us, ...?

ok thank u, later day I will download

but that font as TWD S1, TWD S2 .. not used??
no. not working on old games.
i upload your font today. font is done
## Post #555
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-04-23T06:03:02+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from GHOST DEAD
>
> binlv wrote:GHOST DEAD wrote:thank u, I think the subtitle size may be slightly larger than English for easy to read, and Font name is fontvietnam
Another question i can used fonts make by you for all fonts telltale like the wolf among us, ...?

ok thank u, later day I will download

but that font as TWD S1, TWD S2 .. not used??
no. not working on old games.
i upload your font today. font is done
I want to create font old game!
Can you do a tutorial for me to create that font?
## Post #556
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-04-23T07:04:33+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from binlv
>
> I want to create font old game!
Can you do a tutorial for me to create that font?
sorry but nobody cant import new characters in old games. like wolf among us and other games...(sam and max, The Walking Dead Season 2 and...)
## Post #557
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-04-23T07:21:06+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

hey guys... I need Font Studio and I cant find this app...
please someone share this tool to me! (Font Studio Bitmap Font Generator)
## Post #558
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-04-23T07:37:13+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from GHOST DEAD
>
> hey guys... I need Font Studio and I cant find this app...
please someone share this tool to me! (Font Studio Bitmap Font Generator)
Is bitmap font generator?

[http://www.programmingmoney.com/custom- ... or-libgdx/](http://www.programmingmoney.com/custom-bitmap-font-for-libgdx/)
## Post #559
- Username: sergop
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Apr 21, 2017 8:47 pm
- Post datetime: 2017-04-23T17:46:45+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

hi guys i am from bulgaria and i am trying to translate game of thrones but i cant edit fonts i dont know how to do it so can someone help me
## Post #560
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-04-24T02:31:01+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from binlv
>
> GHOST DEAD wrote:hey guys... I need Font Studio and I cant find this app...
please someone share this tool to me! (Font Studio Bitmap Font Generator)
Is bitmap font generator?

http://www.programmingmoney.com/custom- ... or-libgdx/
No man... I need font studio for this work
Who can share this app?
## Post #561
- Username: sergop
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Apr 21, 2017 8:47 pm
- Post datetime: 2017-04-24T11:34:50+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

hi i managed to find Fontlab Studio 5.0 its cracked version and i think is old check it if u want install and then use patch.exe to register it if u have trouble with installer try switching to win 7 support in compatibility menu
[https://files.fm/u/22xxuhw6](https://files.fm/u/22xxuhw6)#_

can someone help me with fonts on game of thrones i have no idea how to make them support bulgarian language
## Post #562
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-04-26T04:14:38+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from sergop
>
> hi i managed to find Fontlab Studio 5.0 its cracked version and i think is old check it if u want install and then use patch.exe to register it if u have trouble with installer try switching to win 7 support in compatibility menu
https://files.fm/u/22xxuhw6#_

can someone help me with fonts on game of thrones i have no idea how to make them support bulgarian language

no no no! guys... we need (font studio)
## Post #563
- Username: Sajjad Rahim
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 07, 2015 5:04 pm
- Post datetime: 2017-04-26T09:04:05+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from GHOST DEAD
>
> sergop wrote:hi i managed to find Fontlab Studio 5.0 its cracked version and i think is old check it if u want install and then use patch.exe to register it if u have trouble with installer try switching to win 7 support in compatibility menu
https://files.fm/u/22xxuhw6#_

can someone help me with fonts on game of thrones i have no idea how to make them support bulgarian language

no no no! guys... we need (font studio)

here font studio

[https://mega.nz/#!2AEQmZ7b!0cvTm3mBYDrn ... AdPp5uLRB4](https://mega.nz/#!2AEQmZ7b!0cvTm3mBYDrnnEUSJIpZRPN7p7a-81ePsAdPp5uLRB4)
## Post #564
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-04-26T17:16:59+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Sajjad Rahim
>
> GHOST DEAD wrote:sergop wrote:hi i managed to find Fontlab Studio 5.0 its cracked version and i think is old check it if u want install and then use patch.exe to register it if u have trouble with installer try switching to win 7 support in compatibility menu
https://files.fm/u/22xxuhw6#_

can someone help me with fonts on game of thrones i have no idea how to make them support bulgarian language

no no no! guys... we need (font studio)

here font studio

https://mega.nz/#!2AEQmZ7b!0cvTm3mBYDrn ... AdPp5uLRB4

Thanks...
## Post #565
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-04-30T00:40:19+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Why am i getting this error on TWD s3??
## Post #566
- Username: Zhilian
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 27, 2011 1:15 am
- Post datetime: 2017-05-25T08:40:04+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from sergop
>
> hi i managed to find Fontlab Studio 5.0 its cracked version and i think is old check it if u want install and then use patch.exe to register it if u have trouble with installer try switching to win 7 support in compatibility menu
https://files.fm/u/22xxuhw6#_

can someone help me with fonts on game of thrones i have no idea how to make them support bulgarian language

Hi Sergop. Send me the font files and characters you want to have in the fonts. I will create new fonts for your language.

BTW, doesn´t it same like russian characters?
## Post #567
- Username: sergop
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Apr 21, 2017 8:47 pm
- Post datetime: 2017-05-27T12:11:03+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

thx for doing it
here are all fonts i could find [https://files.fm/u/82phj89d](https://files.fm/u/82phj89d)#_
how to send u all characters from font studio or to write them here 
btw they are similar but russian fonts miss 1 character and have 2 extra that we dont use
## Post #568
- Username: Zhilian
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 27, 2011 1:15 am
- Post datetime: 2017-05-28T16:54:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from sergop
>
> thx for doing it
here are all fonts i could find https://files.fm/u/82phj89d#_
how to send u all characters from font studio or to write them here 
btw they are similar but russian fonts miss 1 character and have 2 extra that we dont use

OK.
I´ll let you know when I create these fonts.

Which character the russian font missing? Maybe I can only redraw it and change some letter.
## Post #569
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-07-04T01:26:42+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I want to know " you are dead" where file, because I want to edit it
## Post #570
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-07-06T04:02:51+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from binlv
>
> I want to know " you are dead" where file, because I want to edit it
in ui_death_english.landb
## Post #571
- Username: rico555
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 14, 2016 2:59 am
- Post datetime: 2017-07-07T08:49:53+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from binlv
>
> I want to know " you are dead" where file, because I want to edit it

TWDS3? WD3_pc_UI_txmesh.ttarch2 -> ui_death_splat2.d3dtx
## Post #572
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-07-09T11:02:57+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from rico555
>
> binlv wrote:I want to know " you are dead" where file, because I want to edit it


TWDS3? WD3_pc_UI_txmesh.ttarch2 -> ui_death_splat2.d3dtx

thank Rico555
My want to add my language characters to TWDS1?
can you help my?
## Post #573
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-07-10T03:05:54+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

just repalece your character texture with all postion in .font... then make a character replacer to type in your landb. and rememer, all landb files in old telltale games cant support UTF8 & UTF 16
use ttg tool complete edition
## Post #574
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-07-13T06:05:23+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from GHOST DEAD
>
> just repalece your character texture with all postion in .font... then make a character replacer to type in your landb. and rememer, all landb files in old telltale games cant support UTF8 & UTF 16
use ttg tool complete edition
replace character how?
use can not ttg tool!
## Post #575
- Username: sergop
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Apr 21, 2017 8:47 pm
- Post datetime: 2017-07-19T12:17:21+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

hi guys so i understand that if i want to translate GoT i need to create a new ttarch2 archive with all fonts and text is this true and how to make it with ttarchext im new in this so i dont know what i should write in that file can someone send me the text or make the file
## Post #576
- Username: sergop
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Apr 21, 2017 8:47 pm
- Post datetime: 2017-07-19T13:54:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

guys i made it no need to make bulgarian fonts i figured it out thx for the help
## Post #577
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-07-20T03:46:51+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from sergop
>
> guys i made it no need to make bulgarian fonts i figured it out thx for the help
you dont have to do that
just put your files (font & landb) between ttrach packages... all telltale game can read external files!
## Post #578
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2017-08-09T18:54:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

I want to translation Batman The Enemy Within 
but, ttarch.exe is not working.
Does anyone know the code for Batman?
## Post #579
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2017-08-10T01:31:51+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello, I want to convert landb file to txt using TTG Tool, but this error keep popping up. 

Error. Please write me about this.

I tried different versions etc... Nothing works, still the same error.



error.jpg (129.77 KiB) Viewed 98 times
## Post #580
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-08-10T02:57:53+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

this version of ttg tool cant support this landb file or your landb is not intact... becuse some time ttarch extractor (ttarchext.exe) can not read the header... check your file with hex editor and make sure your header file is in there (6vsm & 5vsm)
## Post #581
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2017-08-10T11:07:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Oh, okay. It looks like my file is without header. I read about that somewhere here, that ttarchext have a big problem with extracting files from TTARCH archives of new games. My game is Walking Dead Michonne, the archive extension is TTARCH2 then. But what else do I have to use instead of ttarchext.exe to extract TTARCH2 archives?

PS: TTG Tool show this error even when I want to encrypt txt file into landb file.

Again somewhere here is that they used Telltale Explorer but it is out of date, the newest version seems to be from 2016 and it don't support Walking Dead Michonne or Walking Dead New Frontier. When I try to open TTARCH2 file from Michonne folder, it shows error "Decompression Error".

EDIT:

Solved it! In TTARCH I was extracting using the -m option and that way the whole archive was extracted WITHOUT headers. So I simply used just game ID, input and output folder and files have HEADERS!

ttarchext.exe <ID> C:\Input\something.ttarch2 "C:\Output"

instead of

ttarchext.exe -m <ID> C:\Input\something.ttarch2 "C:\Output"

But now when I try to pack the txt file, it says Import in file: something.landb is incorrect. 
And nothing is in output folder.

Well, I solved it again. I just unchecked the "Use a real ID of text in LANDB/LANGDB" option.
## Post #582
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2017-08-10T16:48:51+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Taner038
>
> I want to translation Batman The Enemy Within 
but, ttarch.exe is not working.
Does anyone know the code for Batman?

up.
## Post #583
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-08-10T17:17:20+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Taner038
>
> Taner038 wrote:I want to translation Batman The Enemy Within 
but, ttarch.exe is not working.
Does anyone know the code for Batman?

up.
give me a small file
## Post #584
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2017-08-10T17:29:59+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from GHOST DEAD
>
> give me a small file

file:
[http://www.mediafire.com/file/oa7o2wa6o ... ichore.rar](http://www.mediafire.com/file/oa7o2wa6o4h0koe/BAT2_pc_Menu_anichore.rar)

106,97 kb.
## Post #585
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2017-08-11T00:40:51+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello, I would like to test my translation and I know how to put translated text into game using ttarchext and TTG Tools, but some of the characters are... blank? Because some of characters in my language are different from the english characters so I need to change in-game font to be able to properly show them.

Please, where do I find fonts and how to change them?

There is this archive WDM_pc_Project_txmesh.ttarch2 and inside of that are some files with .font extension, but I cant find anything about .font extension on google and I dont know how to change it.
I downloaded font with characters of my language, but it is in .ttf. Is it possible to convert it into .font ?

Thank you.
## Post #586
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-08-11T03:48:42+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Taner038
>
> 
file:
http://www.mediafire.com/file/oa7o2wa6o ... ichore.rar

106,97 kb.
sorry... i tested this files with all scripts but its doent work with my stuff
## Post #587
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2017-08-11T15:23:49+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Here's the Batman Season 2 key, thank vivec for getting it  

```
ttarchext -k 81CAA1A185DA6573A2AED6D89FC6C189995A6FD8B1E297DD97519F979AE0CE95CD77627FA3C4ADD9D6E2AA9C6774B3E3B2C49465A0A281 0
```
## Post #588
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2017-08-11T17:18:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Maximmum
>
> Here's the Batman Season 2 key, thank vivec for getting it  
Code: Select allttarchext -k 81CAA1A185DA6573A2AED6D89FC6C189995A6FD8B1E297DD97519F979AE0CE95CD77627FA3C4ADD9D6E2AA9C6774B3E3B2C49465A0A281 0

Thank you so much. I owe you
## Post #589
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-08-12T04:19:00+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

thanks a lot!
## Post #590
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2017-08-12T15:24:50+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi, please, how do I dcerypt this .LUA file? Looks like that if I want to change charset or add new characters (for example characters like ř Ř ě Ě etc... are not there at all). I edited .font file so it have these characters there including coordinates, but it take no effect in-game.



decrypt1.jpg (221.66 KiB) Viewed 203 times
## Post #591
- Username: quckly
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Oct 22, 2014 1:13 pm
- Post datetime: 2017-10-01T16:05:17+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

In addition to [viewtopic.php?p=101723#p101723](http://forum.xentax.com/viewtopic.php?p=101723#p101723)

FontStudio 4.2 for creation fonts png with xml that may will be parsed by TTG Tools:
[http://file.quckly.ru/q7scmSNVzC5nox8](http://file.quckly.ru/q7scmSNVzC5nox8)
## Post #592
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2017-10-06T14:51:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

hello guys...
how can i change align subtitle text to center?
for walking dead season 1 and walking dead season 2 games
## Post #593
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2017-10-06T19:30:56+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello, could someone please make me fonts for Tales from the Borderlands game? I've been trying to do it, but seems like I can't add a new character in Font Editor in TTG Tools. Just view and copy coordinates from one to another etc...
## Post #594
- Username: wasabi65
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 18, 2017 10:18 pm
- Post datetime: 2017-10-18T14:24:46+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hi, i'm new in here. Anyone can tell me where is tutorial (step by step) for translating a Telltale game.
I have no glue to do it and just found a tool called Telltale Explorer. That tool can find and extract to text landb file.
Then i have no idea to do next. So anyone help me please.
## Post #595
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2017-10-25T14:43:47+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Please, how to decrypt .DLOG files from Tales from the Borderlands? I need to know which lines of text is the game actually using.

Thanks.
## Post #596
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-10-27T04:51:40+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from martanius
>
> Please, how to decrypt .DLOG files from Tales from the Borderlands? I need to know which lines of text is the game actually using.

Thanks.

Try With WAV EXPORT in landb of Langb converter... [in ttg tool]
you can see adress and dialog number[fsb name and character name] in txt file
for rdit and translating... you dont need to edit Dlog files
## Post #597
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2017-12-01T00:09:44+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Which version of ttg tools do you use to edit Minecraft Story Mode's FONT files? It either show an error upon opening the file in font editor there or it export bitmap with non-transparent background.
## Post #598
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-12-01T05:59:29+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from martanius
>
> Which version of ttg tools do you use to edit Minecraft Story Mode's FONT files? It either show an error upon opening the file in font editor there or it export bitmap with non-transparent background.
Try this Version
Link: [http://www.mediafire.com/file/4aa7e8gi8 ... edition.7z](http://www.mediafire.com/file/4aa7e8gi84f2kub/ttg_tool+original+compelet+edition.7z)

You can edit all version of font in this version
this tool has a some problem with unicode in landb files, so edit landb files in older version
and if you'll get a problem in every time, just text a massage.
## Post #599
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2017-12-01T13:25:52+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from GHOST DEAD
>
> martanius wrote:Which version of ttg tools do you use to edit Minecraft Story Mode's FONT files? It either show an error upon opening the file in font editor there or it export bitmap with non-transparent background.
Try this Version
Link: http://www.mediafire.com/file/4aa7e8gi8 ... edition.7z

You can edit all version of font in this version
this tool has a some problem with unicode in landb files, so edit landb files in older version
and if you'll get a problem in every time, just text a massage.

Thank you. But I was using this version of TTG tools.
It exports a texture of a font with turqouise background and some pixels are weirdly blurred.



pexico_medium(0).png (17 KiB) Viewed 63 times
## Post #600
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-12-02T04:21:29+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hmmm... i knew it! just give your characters in language... then i'll create a fix font to you
this problem?(blue color in texture)
blue color or same color in textures of games:
this problem is really bad! because some bit are missing in dds or some Byte are broken
ttg tool got a big problem in such work...
ttg tool has 2 problem

problem 1; dds injector in font editor (look's like in minecraft & walking dead season 2) so don't
 change DDS type in font {DXT1, DXT3, DXT5, DXTRGB, RAGABA}

 problem 2; unicode in landb files (in walking dead season 2 and some old games [but some other old games doesn't have UTF mode, and this is not a big deal(for asian characters)
## Post #601
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2017-12-07T02:29:10+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

No need, buddy  Thanks for the explanation and that offer.
I can create a plain new texture with needed characters. Font already done.

---------------

Btw. Can please someone tell me how to decrypt Tales from the Borderlands's _resdesc .lua files? Those defined for each archive. I need to create an installation of a localization, but it won't work for every versions of the game. I need to create plain new archive with edited files and new .lua file to tell the game I want it to primary use my ttarch2 archive.

I downloaded a russian localization by quckly for Tales from the Borderlands whre it is exatly how I'd want it to. But how to edit these .lua? I tried to decrypt it with ttarchext, but it won't decrypt all of it. Just partly.

This is what I get after ttarchext decryption using command (the ZIP archive contains both encrypted and decrypted files)
ttarchext.exe <gamenum> ...\source.lua "...\output"
_resdesc_50_PC_LOC_Menu_01.zip

How and what do I need to change?
Thank you.
## Post #602
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-12-13T14:11:02+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

give me a sample, maybe I can help
## Post #603
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2017-12-13T14:23:34+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Here is the sample file.


 sample tftb lua.zip
(1.43 KiB) Downloaded 37 times
## Post #604
- Username: roobin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 18, 2011 3:52 am
- Post datetime: 2017-12-16T15:56:17+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Here is decompiler and compiler Lua scripts in version 5.2.
[lua_5.2.7z](https://xentaxbackup.github.io/file/13692_lua_5.2.7z)
## Post #605
- Username: RedEye82
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 07, 2018 7:09 pm
- Post datetime: 2018-03-07T11:13:34+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

sorry for my bad english
iam trying to translate walking dead s1 to my language, i already unpack .ttarch with ttarchext, decrypt with ttg tool, got some .txt file, edit it, finish, try to encrypt, done. so i try on my game.
nope, still no change, why ? i already change everything on "2_WalkingDead101_english_pc_data.ttarch" i try to decrypt it again just to see, yep, it's in my language, why does this happen ?
## Post #606
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2018-03-07T13:34:55+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Try different archive.
## Post #607
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2018-03-07T19:05:07+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from GHOST DEAD
>
> martanius wrote:Which version of ttg tools do you use to edit Minecraft Story Mode's FONT files? It either show an error upon opening the file in font editor there or it export bitmap with non-transparent background.
Try this Version
Link: http://www.mediafire.com/file/4aa7e8gi8 ... edition.7z

You can edit all version of font in this version
this tool has a some problem with unicode in landb files, so edit landb files in older version
and if you'll get a problem in every time, just text a massage.

Hi. It seems like this version is unable to decrypt/encrypt TWD A New Frontier's d3dtx files (d3dtx>dds or the other way around) at all.
## Post #608
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2018-03-11T05:59:26+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from martanius
>
> GHOST DEAD wrote:martanius wrote:Which version of ttg tools do you use to edit Minecraft Story Mode's FONT files? It either show an error upon opening the file in font editor there or it export bitmap with non-transparent background.
Try this Version
Link: http://www.mediafire.com/file/4aa7e8gi8 ... edition.7z

You can edit all version of font in this version
this tool has a some problem with unicode in landb files, so edit landb files in older version
and if you'll get a problem in every time, just text a massage.

Hi. It seems like this version is unable to decrypt/encrypt TWD A New Frontier's d3dtx files (d3dtx>dds or the other way around) at all.

Add This Fix File With Other Texture in input Folder
[Fix.rar](https://xentaxbackup.github.io/file/14016_Fix.rar)
## Post #609
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2018-03-11T11:15:15+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Thank you. Now it encrypt, but all the .DDS textures are pitch black. In TTG Tools it seems like it can't recognize texture format.
## Post #610
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-03-13T09:52:05+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from martanius
>
> Thank you. Now it encrypt, but all the .DDS textures are pitch black. In TTG Tools it seems like it can't recognize texture format.

use this version of TTG tool
Link: [http://www.mediafire.com/file/4aa7e8gi8 ... edition.7z](http://www.mediafire.com/file/4aa7e8gi84f2kub/ttg_tool+original+compelet+edition.7z)
## Post #611
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2018-03-13T10:52:27+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Thank you for reply. I was using this version tho. Tried it again with this specific one of yours, but result is the same.

I unpack ttarch2 archive using ttarchext included in TTG Tools by quickly (the one in this TTG Tools compelet edition does not have TWD A New Frontier game number).

Put exported .d3dtx files in input folder in TTG Tools Compelet Edtion together with that Fix.d3dtx 'halfway' send me in previous reply.

And this is the result:



Am I doing something wrong?
## Post #612
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-03-15T07:42:57+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

find telltale Explorer...
halfway gave you a fix.d3dtx, Does'nt work?
I saw that problem in month's ago, maybe your header file is curapted or broken... ttarch has some bug and i never use this becuse header will removing in this tool,
search Telltale Explorer in google, in a website has named QuickAndEasy sofware...
## Post #613
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2018-03-15T09:09:22+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Ye, it does not work even with fix.d3dtx.

And Telltale explorer does not support The Walking Dead: A New Frontier. It's not in the list there and it says Decompression error upon trying to open The Walking Dead Season 3 ttarch2 file.
## Post #614
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-03-17T04:29:33+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Something is wrong on your platform... Because i test it, try on another PC
## Post #615
- Username: Raul
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 15, 2018 1:24 am
- Post datetime: 2018-04-18T18:14:26+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Any idea where i can find .font in Batman the enemy within or add special letters from my language ?
## Post #616
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2018-08-14T11:09:24+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

There is (originally posted by Maximmum):

```
96CA999F8DDA9A87D7CDD9986295AAB8D59596E5A4B99BD0C9559F8590CDCD9FC8B39993C6C49DA0A5A4CFCDA39DBBDDACA78B94D4A66F
```


I'd like to edit fonts, but alas I cannot. TTG Tools (the "complete edition" or TTG Tool made by quckly is not able to opet .FONT file from TWD The Final Season. It says "Texture header was encrypted, but I decrypted" message over and over again - I have to close the program via program manager
## Post #617
- Username: thisrock84
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 02, 2019 8:20 pm
- Post datetime: 2020-04-22T11:26:06+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Hello,
I am making localization for PS4. But I get errors in some games. For example, Batman: The Telltale Series, Tales from the Borderlands (all episodes). In these games, tool can extract the package but when I rebuild the package in to ttarch2, the game locks on the playstation or waiting loading screen or wait in black screen. 

Are the keys different for PS4? Is there a method you know? Because I downloaded the PC versions of these games and the tool works properly for the PC versions. It just crashes on PS4.

Thank you for your help in advance.

Note: I know that I can put the files with landb extension to the archive folder, but there are the files with the same name with landb extension for different episodes. I cannot put these files to the archive folder because it has same name. For this reason, I had to make changes to ttarch2 files.

I used;
ttarchext.exe -o -b -V 7 60 "BM_ps4_Boot_data.ttarch2" "BM_ps4_Boot_data"
ttarchext.exe -o -b 60 "BM_ps4_Boot_data.ttarch2" "BM_ps4_Boot_data"
ttarchext.exe -o -x -b 60 "BM_ps4_Boot_data.ttarch2" "BM_ps4_Boot_data"
ttarchext.exe -o -b -x -V 7 60 "BM_ps4_Boot_data.ttarch2" "BM_ps4_Boot_data"

And I also used ttg_tool original compelete edition > TTG Tools.exe > Archive packer. 
I tried these all combinations in Archive packer: version of archive 1 or 2, or compress archive, or checked encrypt archive, or checked Encrytpt Lua for new games or checked  don't encrypt lua. (I have tried 32 combinations totally)
## Post #618
- Username: Vihanga101
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 28, 2022 1:55 am
- Post datetime: 2022-02-28T05:02:19+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

plz someone explain how to use font editor in TGG tools for TWD season 1.
## Post #619
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-28T17:19:35+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

> Reply from Vihanga101 ↑Mon Feb 28, 2022 1:02 pm at Mon Feb 28, 2022 1:02 pm
>
> 
plz someone explain how to use font editor in TGG tools for TWD season 1.

What's the issue? 

You click on "Font Editor", you load your font file and then you edit what you need in the font.
It's not any different from editing font for other Telltale games.
## Post #620
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-08T14:56:10+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

File format specification for FONT files from Telltale Games
[http://wiki.xentax.com/index.php/Telltale_Games_FONT](http://wiki.xentax.com/index.php/Telltale_Games_FONT)
## Post #621
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-02-08T21:47:04+00:00
- Post Title: Re: Telltale and Gametap - extract to translate

Short tutorial on editing FONT files ---> [viewtopic.php?p=189939#p189939](https://forum.xentax.com/viewtopic.php?p=189939#p189939)

OLD tutorial (polish only) --> [https://ikskoks.pl/poradnik-4-edycja-gier-telltale/](https://ikskoks.pl/poradnik-4-edycja-gier-telltale/)

FONT samples from Batman game ---> [download/file.php?id=11518](https://forum.xentax.com/download/file.php?id=11518)

TTG Tools (tool for translating and font editing) --> [https://github.com/pashok6798/TTG_Tools](https://github.com/pashok6798/TTG_Tools)
