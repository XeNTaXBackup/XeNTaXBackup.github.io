## Post #1
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-15T16:18:50+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

Hi, we are translate groupe called by "Oyunçeviri" and we want to translate Sniper Ghost Warrior 2. 
We need open .xml files. When i try open .xml files with notepad there are only codes  :



There is .xml Files : http://www.mediafire.com/?dd06wgqy0e6nqpn
Please someone help me!!!
## Post #2
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-15T20:12:47+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

Please someone help me!
## Post #3
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2013-03-15T21:45:20+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

The solution is simple.
1. - To unpack pak files, using WinRar
2. - To edit an XML can do it with a hex editor, Ultraedit example ""not notepad""
3. - After editing you must keep the original size of the file or edit the bytes 9 and 10
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-15T23:25:17+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

> Reply from vitoci
>
> The solution is simple.
1. - To unpack pak files, using WinRar
2. - To edit an XML can do it with a hex editor, Ultraedit example ""not notepad""
3. - After editing you must keep the original size of the file or edit the bytes 9 and 10

Indeed not good way of doing it, but possible, i was trying to figure it out, but still missing 1 piece. Thre are messy data before actual text, not sure exactly what they represent i guess this are offsets to text
## Post #5
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2013-03-16T00:05:44+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

So is Michalss, I see an XML file without an ordered structure.
In addition there are labels that contain no values, for example Clip_size in some weapons, despite this I can edit and the game runs
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-16T06:35:31+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

> Reply from vitoci
>
> So is Michalss, I see an XML file without an ordered structure.
In addition there are labels that contain no values, for example Clip_size in some weapons, despite this I can edit and the game runs

Sounds OK after investigation, but not sure how it will work if strings will be bigger then original, size for whole file is easy as u said there is size mark. But im gonna try will see
## Post #7
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-16T07:40:09+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

> Reply from vitoci
>
> The solution is simple.
1. - To unpack pak files, using WinRar
2. - To edit an XML can do it with a hex editor, Ultraedit example ""not notepad""
3. - After editing you must keep the original size of the file or edit the bytes 9 and 10

Dear vitoci, i don't know using hex editor. Can you send me tool for those files ? Plase, i need this.
## Post #8
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-16T10:57:58+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

> Reply from vitoci
>
> So is Michalss, I see an XML file without an ordered structure.
In addition there are labels that contain no values, for example Clip_size in some weapons, despite this I can edit and the game runs

This is all wrong xml contains offsets to texts/string of course, so your way it totally wrong until you keep the same size of strings you OK but this is pain not really good for localization! I just cannot figure it out damn i found start offset size and etc... but i cannot find offsets for actuall strings.... Hmm any idea ?
## Post #9
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-16T12:35:54+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

michalss, so can you create a tool/converter/editor for .xml files of Sniper ghost warrior 2 ?
## Post #10
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2013-03-16T15:35:10+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

> Reply from turkgamer
>
> vitoci wrote:The solution is simple.
1. - To unpack pak files, using WinRar
2. - To edit an XML can do it with a hex editor, Ultraedit example ""not notepad""
3. - After editing you must keep the original size of the file or edit the bytes 9 and 10

Dear vitoci, i don't know using hex editor. Can you send me tool for those files ? Plase, i need this.

Download HxD Editor, [http://mh-nexus.de/en/hxd/](http://mh-nexus.de/en/hxd/) 

Use this program to edit XML, remember to keep the bytes of the original file size, until we find the offset of the XML files in the archive Pak
## Post #11
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-03-16T20:37:19+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

Hey
I converted the Russian language version of the game from consoles to PC.
Here I am to you to convert the English files:

dialog_recording_list.xml
text_ui_menus.xml

[http://yadi.sk/d/7JAvKj0c3KB8q](http://yadi.sk/d/7JAvKj0c3KB8q)

Unpack to folder: SniperGhostWarrior2\Game\languages\ (create this folder)

Enjoy =)

P.S. For Editing - Open in Excel or Akelpad
## Post #12
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-16T23:18:44+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

> Reply from Haoose
>
> Hey
I converted the Russian language version of the game from consoles to PC.
Here I am to you to convert the English files:

dialog_recording_list.xml
text_ui_menus.xml

http://yadi.sk/d/7JAvKj0c3KB8q

Unpack to folder: SniperGhostWarrior2\Game\languages\ (create this folder)

Enjoy =)

P.S. For Editing - Open in Excel or Akelpad

Thank you so much bro.
## Post #13
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-17T07:27:46+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

> Reply from Haoose
>
> Hey
I converted the Russian language version of the game from consoles to PC.
Here I am to you to convert the English files:

dialog_recording_list.xml
text_ui_menus.xml

http://yadi.sk/d/7JAvKj0c3KB8q

Unpack to folder: SniperGhostWarrior2\Game\languages\ (create this folder)

Enjoy =)

P.S. For Editing - Open in Excel or Akelpad

Not sure if i got the point, how this gonna help to localize the game ?
## Post #14
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-03-17T08:20:30+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

> Reply from michalss
>
> Not sure if i got the point, how this gonna help to localize the game ?

> Reply from Haoose
>
> For Editing - Open in Excel or Akelpad
## Post #15
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-17T18:11:06+00:00
- Post Title: Sniper Ghost Warrior 2 .xml files

> Reply from Haoose
>
> michalss wrote:Not sure if i got the point, how this gonna help to localize the game ?
Haoose wrote:For Editing - Open in Excel or Akelpad

OK i got that you can open it excel but again how this goona help to localize this game pls ? I have text out for week, but repack is the problem not text extraction  So you saing that it gonna read it from xml files directly from Folders ? I have try this and it does not work on X360...... I guess we need repacker...
## Post #16
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-03-17T18:28:08+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from michalss
>
> So you saing that it gonna read it from xml files directly from Folders ?
Yes!
(PC version)
[](http://fastpic.ru/view/54/2013/0317/1a691518d64319a9858b4680cc3a7e9b.png.html) [](http://fastpic.ru/view/54/2013/0317/6bc7081bbba43a843b1d21549aed32d0.jpg.html)
## Post #17
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-17T19:31:39+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

hmm ok so far does not work on X360. But se file english_xml.pak does it need to be in localized folder as well or i can simple remove it ? Any chace to release repacker for original XML pls ?
## Post #18
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-03-17T19:54:44+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from michalss
>
> hmm ok so far does not work on X360. But se file english_xml.pak does it need to be in localized folder as well or i can simple remove it ? Any chace to release repacker for original XML pls ?
1. No. No need to delete the file. Or unpack it (english_xml.pak) in a folder "game" and then delete.
2. Try to pack the files (text_ui_menus.xml, dialog_recording_list.xml) in the file english_xml.pak
3. Try changing one or two letters in a source file (not the ones that I gave, and the source (original from first post) ) and pack the modified file in the file english_xml.pak
If all of this fails, then I can not help you =)
I do not know, what have you on the consoles. We have a PC, all works well. =)
## Post #19
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-17T20:07:31+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

ok then ill try can you please at least release tool for extraction of original xml to excel xml?
## Post #20
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-03-17T20:25:36+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from michalss
>
> ok then ill try can you please at least release tool for extraction of original xml to excel xml?
No =)

It's
Hex Editor +
AkelPad(Excel) +
Original files from CryEngine3SDK or Crysis 3 +
Hands +
Brain =))
## Post #21
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2013-03-18T23:21:32+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from Haoose
>
> Hey
I converted the Russian language version of the game from consoles to PC.
Here I am to you to convert the English files:

dialog_recording_list.xml
text_ui_menus.xml

http://yadi.sk/d/7JAvKj0c3KB8q

Unpack to folder: SniperGhostWarrior2\Game\languages\ (create this folder)

Enjoy =)

P.S. For Editing - Open in Excel or Akelpad
Good!
But, the PC version has 7 XML files:

```
text_ui_menus.xml
ai_dialog_recording_list.xml
credits.xml
loading.xml
pc_keyboard.xml
warnings_ui.xml
```

I have attached these files uncompressed, but in a slightly different format. Edit them using Notepad++.
Put the files in "SniperGhostWarrior2\Game\languages\" (Create this folder)
I have not tested it right, but the menu texts works perfectly.
Enjoy.[/b]


 English.7z
(140.93 KiB) Downloaded 126 times
## Post #22
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-03-23T18:15:28+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

It doesn't work on dialogues. We need xml2txt tool.
## Post #23
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2013-03-24T06:38:50+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from turkgamer
>
> It doesn't work on dialogues. We need xml2txt tool.
Sorry, but as I said, I haven't tested properly...
## Post #24
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-24T07:52:46+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

we found the c++ source for XML from SDK but i'm c++ noob can anyone please have alook ? 

```
 public:
  uint32 nTagStringOffset;         // offset in CBinaryXmlData::pStringData
  uint32 nContentStringOffset;     // offset in CBinaryXmlData::pStringData
  uint16 nAttributeCount;
  uint16 nChildCount;
  NodeIndex nParentIndex;
  NodeIndex nFirstAttributeIndex;
  NodeIndex nFirstChildIndex;
  Pad<sizeof(uint32) - sizeof(NodeIndex)> reserved_for_alignment;
 };

 class Attribute
 {
 public:
  uint32 nKeyStringOffset;         // offset in CBinaryXmlData::pStringData
  uint32 nValueStringOffset;       // offset in CBinaryXmlData::pStringData
 };

 class BinaryFileHeader
 {
 public:
  static const char* sk_szCorrectSignature;
  char szSignature[8];
  uint32 nXMLSize;
  uint32 nNodeTablePosition;
  uint32 nNodeCount;
  uint32 nAttributeTablePosition;
  uint32 nAttributeCount;
  uint32 nChildTablePosition;
  uint32 nChildCount;
  uint32 nStringDataPosition;
  uint32 nStringDataSize;
 };

```
## Post #25
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-31T18:22:48+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

anyone please ?
## Post #26
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-04-04T07:42:18+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

Anyone?
## Post #27
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-04-22T16:27:21+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

bump.... I was try to revers it but really no idea this look so stupid this format anyone can have a look please ?
## Post #28
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-05-11T08:32:28+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

Please someone help us!
## Post #29
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2013-09-21T09:45:16+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

thanks to all

I need 

 dialog_recording_list.7z
(103.84 KiB) Downloaded 73 times

 file convert to Excel readable xml file

that is in DLC and different from original file
## Post #30
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-06-10T17:59:34+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

Any news on this? Still no hope for translating the game?
## Post #31
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2014-06-18T13:50:56+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from lostprophet
>
> Any news on this? Still no hope for translating the game?

Is this enough proof?:



Dialogs are translatable too, of course - and they working.
The DLC maybe could be problem, I think, 'cause I didn't get to those texts in mean time [I'm playing and translating it simultaneously, when I have mood for this]
## Post #32
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-06-18T17:31:32+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

proof of what ??? We knot this works on PC for years.... but not on consoles
## Post #33
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2014-06-22T14:21:59+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from michalss
>
> proof of what ??? We knot this works on PC for years.... but not on consoles

He asked about translation - not console versions.
## Post #34
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-06-22T14:59:12+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from terminator
>
> michalss wrote:proof of what ??? We knot this works on PC for years.... but not on consoles

He asked about translation - not console versions.

Hmm sorry where is different exactly? I dont care about PC for example at all
## Post #35
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2014-06-22T16:02:32+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

Is translation possible ? @michalss
## Post #36
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-06-22T17:09:01+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from turkgamer
>
> Is translation possible ? @michalss

PC version i guess so, Consoles nope
## Post #37
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2014-06-23T11:34:11+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from michalss
>
> turkgamer wrote:Is translation possible ? @michalss

PC version i guess so, Consoles nope

"I guess so?"   Would u help me to localizate SGW2? (In PC)
## Post #38
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-06-23T13:52:41+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from turkgamer
>
> michalss wrote:turkgamer wrote:Is translation possible ? @michalss

PC version i guess so, Consoles nope 

"I guess so?"   Would u help me to localizate SGW2? (In PC)

Im sorry i do not work with PC versions to be hones, but someone in here did it better to ask them mate..
## Post #39
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2014-06-29T07:44:41+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

Sniper Ghost Warrior 2 localization - PC

0. Download the attachment!
1. Extract anywhere, localize what you need (with Notepad++ with UCS-2 Little Endian or what you need for turkish) and place them here (make "languages" directory!):



2. Done. Test it out!
[Sniper Ghost Warrior 2 English.7z](https://xentaxbackup.github.io/file/7530_Sniper Ghost Warrior 2 English.7z)
## Post #40
- Username: kamuline
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Sep 02, 2009 2:11 am
- Post datetime: 2014-06-29T10:11:13+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from terminator
>
> Sniper Ghost Warrior 2 localization - PC

0. Download the attachment!
1. Extract anywhere, localize what you need (with Notepad++ with UCS-2 Little Endian or what you need for turkish) and place them here (make "languages" directory!):



2. Done. Test it out!
[viewtopic.php?f=35&t=10227&start=20](http://forum.xentax.com/viewtopic.php?f=35&t=10227&start=20) ???
## Post #41
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2014-06-29T12:18:33+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

Did I mentioned somewhere that I found the solution?
## Post #42
- Username: kamuline
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Sep 02, 2009 2:11 am
- Post datetime: 2014-06-29T13:08:53+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from terminator
>
> Did I mentioned somewhere that I found the solution?
Files are available, reupload is unnecessary.
Far enough to point to the post, as i did...

And you didn't even mention the original uploader of the files.
It's not nice, if you post the package as yours...
## Post #43
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2014-06-29T14:01:25+00:00
- Post Title: Re: Sniper Ghost Warrior 2 .xml files

> Reply from kamuline
>
> terminator wrote:Did I mentioned somewhere that I found the solution?
Files are available, reupload is unnecessary.
Far enough to point to the post, as i did...

Thanks, but you're overreacting this one. Bye.
