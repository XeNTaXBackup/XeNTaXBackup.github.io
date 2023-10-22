## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-05-23T15:50:00+00:00
- Post Title: State of Decay Text Repacker

Can anyone please have a look on this files :

```
http://warimagehost.net/files/LANGUA~1.RAR
```


Thx
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-06-16T20:16:15+00:00
- Post Title: State of Decay Text Repacker

noone pls ?


This is what i have so far

```
//--- 010 Editor v4.0.3 Binary Template
//
// File:TXDB
// Author: michalss
// Revision: 1.0
// Purpose: pretty clear
//--------------------------------------
local int x,pos,oof,head,total,leng;
local string text;

BigEndian();

head=16;
char TXDB[4];
uint ver;
uint GUID;
uint records;
total = records*4+head;

//1 - 55344 - real offset where the text starts 
//2 - 55359 - this is 2 text
//3 - 55434 - this is 3 text

for(x=0;x<records;x++) {
    
    struct TEXT {
    
    uint offset; //??? no idea what this is, looks like id or some kind of CRC???
    pos=FTell();
      
    FSeek(total);    
    text = ReadString(total);
    leng = Strlen(text);
    char TEXT[leng+1];
    total+=leng+1;
    FSeek(pos);

    } DATA;
}
```
## Post #3
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-06-17T07:54:56+00:00
- Post Title: State of Decay Text Repacker

If you compare 2 langs ( except english ), you see the whole table thing is almost the same. So i think there are only ids, no offset or length datas.
So try to edit the lines in hex editor, adding new characters, and see if its working in game.
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-06-17T14:36:27+00:00
- Post Title: State of Decay Text Repacker

> Reply from swuforce
>
> If you compare 2 langs ( except english ), you see the whole table thing is almost the same. So i think there are only ids, no offset or length datas.
So try to edit the lines in hex editor, adding new characters, and see if its working in game.

Of course allready try this  not work and you loos all text in game and you not right coz this number is changes on the base of language
## Post #5
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2013-06-22T10:51:37+00:00
- Post Title: State of Decay Text Repacker

They are ID of strings. Look at "struct TEXT DATA[8375]"  its ID is "-1700966594". The first one in french and italian also  have same ID.  Texts have also same meaning. 
Probably, there is another file that checks overall size of file. Try to add a char to one string and delete one char from another string. Therefore overall size remains the same.
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-06-22T12:40:50+00:00
- Post Title: State of Decay Text Repacker

> Reply from rengareng
>
> They are ID of strings. Look at "struct TEXT DATA[8375]"  its ID is "-1700966594". The first one in french and italian also  have same ID.  Texts have also same meaning. 
Probably, there is another file that checks overall size of file. Try to add a char to one string and delete one char from another string. Therefore overall size remains the same.

well i was thinking about it allready, i probably know where to look, but that file with sizes looks compressed
## Post #7
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2013-06-22T13:34:18+00:00
- Post Title: State of Decay Text Repacker

> Reply from michalss
>
> 
well i was thinking about it allready, i probably know where to look, but that file with sizes looks compressed
I cant help without seeing files.
## Post #8
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-06-22T17:39:43+00:00
- Post Title: State of Decay Text Repacker

> Reply from rengareng
>
> michalss wrote:
well i was thinking about it allready, i probably know where to look, but that file with sizes looks compressed
I cant help without seeing files.
Sent to your PM  Thx
## Post #9
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2013-06-27T21:39:46+00:00
- Post Title: State of Decay Text Repacker

I think files in 

```
http://warimagehost.net/files/LANGUA~1.RAR
```

is  extracted wrongly from iso files. Please extract using another tool.
## Post #10
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-06-28T05:57:57+00:00
- Post Title: State of Decay Text Repacker

Files are extracted correctly ofcourse

```
https://dl.dropboxusercontent.com/u/38234344/languages.rar
```
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-06T20:33:06+00:00
- Post Title: State of Decay Text Repacker

does anyone know where are fonts ? There is 1 folder with 1 font in it but i think not taking it from there??
## Post #12
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-09-22T22:27:20+00:00
- Post Title: State of Decay Text Repacker

State of Decay is in Early Access on Steam, here are some .pak files from the game. The dialog.pak contains the texts files of the game, but I couldn't upload that, since it is 140MB.
[http://rghost.net/48916916](http://rghost.net/48916916)
## Post #13
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2013-09-23T20:27:12+00:00
- Post Title: State of Decay Text Repacker

> michalss
I searching everywhere in PAK files and nothing to found  I am really confused. Maybe in some GFX files, but I am not sure.
## Post #14
- Username: QueenSasha24
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 05, 2013 12:16 am
- Post datetime: 2013-09-24T19:30:53+00:00
- Post Title: State of Decay Text Repacker

> Reply from lostprophet
>
> State of Decay is in Early Access on Steam, here are some .pak files from the game. The dialog.pak contains the texts files of the game, but I couldn't upload that, since it is 140MB.
http://rghost.net/48916916

Are you certain about that? I've extracted dialog.pak and it seems to only contain .mp3 files.

It looks like the text files of the game are located inside of the language folder, with "english.win.btxt" being for the English text. (Though not in an editable form at this point)
## Post #15
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-09-25T06:45:36+00:00
- Post Title: State of Decay Text Repacker

> Reply from QueenSasha24
>
> lostprophet wrote:State of Decay is in Early Access on Steam, here are some .pak files from the game. The dialog.pak contains the texts files of the game, but I couldn't upload that, since it is 140MB.
http://rghost.net/48916916

Are you certain about that? I've extracted dialog.pak and it seems to only contain .mp3 files.

It looks like the text files of the game are located inside of the language folder, with "english.win.btxt" being for the English text. (Though not in an editable form at this point)
Yeah, you're right, I made a mistake, they are in the gamedata.pak in the .btxt files and possibly the .drl file? Hopefully someone can crack it open.
## Post #16
- Username: QueenSasha24
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 05, 2013 12:16 am
- Post datetime: 2013-09-26T02:18:55+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from lostprophet
>
> QueenSasha24 wrote:lostprophet wrote:State of Decay is in Early Access on Steam, here are some .pak files from the game. The dialog.pak contains the texts files of the game, but I couldn't upload that, since it is 140MB.
http://rghost.net/48916916

Are you certain about that? I've extracted dialog.pak and it seems to only contain .mp3 files.

It looks like the text files of the game are located inside of the language folder, with "english.win.btxt" being for the English text. (Though not in an editable form at this point)
Yeah, you're right, I made a mistake, they are in the gamedata.pak in the .btxt files and possibly the .drl file? Hopefully someone can crack it open.

Here's hoping, it's pretty much beyond me.
## Post #17
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-09-26T08:28:38+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from michalss
>
> does anyone know where are fonts ? There is 1 folder with 1 font in it but i think not taking it from there??

Fonts are in gamedata\libs\ui\*.gfx, in Compacted format. Like in GTA 5.
## Post #18
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-26T09:53:56+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from merlinsvk
>
> michalss wrote:does anyone know where are fonts ? There is 1 folder with 1 font in it but i think not taking it from there??

Fonts are in gamedata\libs\ui\*.gfx, in Compacted format. Like in GTA 5.

Thx for notice gonna have a look on this.. 
EDIT : Perfect im done  thx for it mate
## Post #19
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-09-26T12:27:11+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from merlinsvk
>
> michalss wrote:does anyone know where are fonts ? There is 1 folder with 1 font in it but i think not taking it from there??

Fonts are in gamedata\libs\ui\*.gfx, in Compacted format. Like in GTA 5.
Which GFXes are you referring to? The ones that start with CFX?
## Post #20
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2013-09-26T12:36:04+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from lostprophet
>
> Which GFXes are you referring to? The ones that start with CFX?
I think they yes. Its a standard GFX but compressed with ZLIB.
## Post #21
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-09-26T12:37:19+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from GRiNDERKILLER
>
> lostprophet wrote:Which GFXes are you referring to? The ones that start with CFX? 
I think they yes. Its a standard GFX but compressed with ZLIB.
Hm, I checked these GFXes with the CFX headers with TRILLIX, found 3 of them, but they only contained animations from the main menu and stuff.
## Post #22
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-26T12:54:42+00:00
- Post Title: Re: State of Decay Text Repacker

class3hud.gfx
class3_centerprompts.gfx
class3_frontend.gfx
class3_journal.gfx
class3_notifications.gfx
class3_pause.gfx
class3_radar.gfx

here are fonts
## Post #23
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-26T13:07:26+00:00
- Post Title: Re: State of Decay Text Repacker

Fonts are Autodesk Scaleform GFX, very non standard, exact same as GTA V
## Post #24
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2013-09-26T13:14:42+00:00
- Post Title: Re: State of Decay Text Repacker

good to know michalss and you able to edit them?
## Post #25
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-09-26T13:16:26+00:00
- Post Title: Re: State of Decay Text Repacker

What did you use to edit them? I'm guessing standard "renaming GFX to FWS -> SWiX -> TRILLIX -> Hex editing" combo doesn't work.
## Post #26
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-09-26T15:50:05+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from michalss
>
> class3hud.gfx
class3_centerprompts.gfx
class3_frontend.gfx
class3_journal.gfx
class3_notifications.gfx
class3_pause.gfx
class3_radar.gfx

here are fonts

And what about these?

class3_banners.gfx
class3_survey.gfx
class3_stats.gfx

Is it also necessary to edit fonts in them?
## Post #27
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-09-26T15:55:45+00:00
- Post Title: Re: State of Decay Text Repacker

Maybe this can work with the GFX font files:
[viewtopic.php?f=10&t=10095&hilit=scaleform&start=15](http://forum.xentax.com/viewtopic.php?f=10&t=10095&hilit=scaleform&start=15)
## Post #28
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-09-26T16:36:27+00:00
- Post Title: Re: State of Decay Text Repacker

These fonts are in different form. They were compacted during swf->gfx conversion. So the "classical" way of editing embedded fonts is not valid in this case.
## Post #29
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-09-26T16:38:59+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from merlinsvk
>
> These fonts are in different form. They were compacted during swf->gfx conversion. So the "classical" way of editing embedded fonts is not valid in this case.
Hm, so it's not that easy. I'll wait too, then.
## Post #30
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-26T18:05:50+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from merlinsvk
>
> michalss wrote:class3hud.gfx
class3_centerprompts.gfx
class3_frontend.gfx
class3_journal.gfx
class3_notifications.gfx
class3_pause.gfx
class3_radar.gfx

here are fonts

And what about these?

class3_banners.gfx
class3_survey.gfx
class3_stats.gfx

Is it also necessary to edit fonts in them?

Yeah sorry i forget about this, yes each font need to be edited, coz each font represent specific functionality in game, even some of the fonts are the same and multiple times in files. 
BTW : CZ will be done by me and my team, and even for PC, however just after GTA 5, but we have about 35% game translated allready
## Post #31
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-09-26T18:29:27+00:00
- Post Title: Re: State of Decay Text Repacker

Now we just need some means to edit these GFX files. I hate it when they don't use conventional ones.
## Post #32
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-26T18:35:18+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from lostprophet
>
> Now we just need some means to edit these GFX files. I hate it when they don't use conventional ones.

Autodesk GFx format its actually used in almost every AAA game engine. Problem is that they using different tagging than normal swf files.
## Post #33
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-09-26T18:36:28+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from michalss
>
> lostprophet wrote:Now we just need some means to edit these GFX files. I hate it when they don't use conventional ones.

Autodesk GFx format its actually used in almost every AAA game engine. Problem is that they using different tagging than normal swf files.
I think I'll hold off with the translation, until a method is figured out for the fonts.
## Post #34
- Username: momo
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Nov 28, 2010 10:13 am
- Post datetime: 2013-09-27T17:21:58+00:00
- Post Title: Re: State of Decay Text Repacker

You can replace DefineCompactedFont tag to DefineFont3 tag which is created with same object id, font name and language id of Compacted Font. This game loads both font tags properly.
## Post #35
- Username: kamuline
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Sep 02, 2009 2:11 am
- Post datetime: 2013-09-28T12:21:02+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from momo
>
> You can replace DefineCompactedFont tag to DefineFont3 tag which is created with same object id, font name and language id of Compacted Font. This game loads both font tags properly.
Can you make us a tutorial how to do that?
## Post #36
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-09-28T16:28:41+00:00
- Post Title: Re: State of Decay Text Repacker

Ehm guys, who knows how to correct that misaligned "selected" white bar?
(I replaced compacted fonts)

[](http://www.ulozisko.sk/obrazky/638414/StateOfDecay_2013-09-28_18-09-33-55.jpg)



EDIT: Ok, I fixed that
## Post #37
- Username: kamuline
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Sep 02, 2009 2:11 am
- Post datetime: 2013-09-30T10:20:34+00:00
- Post Title: Re: State of Decay Text Repacker

Everybody is talking about editing the text files and fonts, but noone want to share a tool, info or anything how to do that.
Nice...
## Post #38
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-09-30T14:35:04+00:00
- Post Title: Re: State of Decay Text Repacker

Hex editor of your choice,
SWIX (or swfmill, or maybe both),
Adobe Flash (CS3, CS4, CS5, CS6, doesn't matter),
Scaleform SDK (I've used SDK 3.0, which was included in Unreal Development Kit, probably from year 2012),
some text editor (Notepad++, PSPad, Akellpad...)

...and installed fonts that you want to put in the game.
## Post #39
- Username: momo
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Nov 28, 2010 10:13 am
- Post datetime: 2013-10-01T10:20:48+00:00
- Post Title: Re: State of Decay Text Repacker

Here is my basic procedure for replace font.

Required tools:
 - swfmill
 - hex editor
 - base64 decode tool

Required skill:
 - How to compile/decompile swf and create a new swf by swfmill.

1. Convert gfx to swf.
   Change gfx 3bytes header to swf by hex editor.

2. Decompile it.
   Decompile swf file(converted from gfx) using swfmill.
   
```
> swfill swf2xml [swf file] [xml file]
```

3. Find DefineCompactedFont tag and decode the font data to get font information.
   In decompiled xml file at step2, DefineCompactedFont is found as unknown tag which id is 0x3ED(1005) like this.
   
```
<UnknownTag id="0x3ED">....</UnknownTag>
```

   Font data is encoded with BASE64. You need to decode font data to get id and name using hex editor.
   First 2 bytes(unsigned short) of decoded data is id and following ascii characters are name.

4. Create a new swf file.
   Create a new swf file with the font which you want to replace by swfmill.
   Please check [http://swfmill.org/doc/using-swfmill.html](http://swfmill.org/doc/using-swfmill.html) for how to create new swf file.
   
```
> swfmill simple [xml for simple option] [swf file]
```

5. Change some attributes to replace.
   Decompile swf file created at step4.
   
```
> swfmil swf2xml [swf file] [xml file]
```

   In decompiled xml file, you can find DefineFont3 tag for the font you selected.
   If you choose "this tutorial font", DefineFont3 tag for it is like this.
   
```
   ...
</DefineFont3>
```

   You need to change the following attributes for replacing font.

   - objectID: change to id you found at step3.
   - language: change 0 to 1.
   - name: change to name you found at step3.

6. Replace font tag
   Replace DefineCompactedFont tag which you found at step3 to DefineFont3 tag which you edited at step5
   using text editor.

7. Compile it
   Compile modified xml file at step6 using swfmill again.
   
```
> swfmill xml2swf [xml file] [new swf file]
```
 
8. Convert swf to gfx.
   Change swf 3bytes header to gfx by hex editor.

9. Copy it to proper path in the folder which game is installed.
   This game can load unpacked files directly. you just place modified files as same as unpacked path in "Game"
   subfolder of the folder which game is installed.

   i.e. gfx files are unpacked to "libs\ui". you need to create "libs\ui" folder in "Game" subfolder and copy modified files in it.

Each gfx has several fonts in it, so that you have to do this for each font.

About btxt file, here is my tool.
[http://www.mediafire.com/download/j6a7p ... XTTool.zip](http://www.mediafire.com/download/j6a7p0lchahobnz/BTXTTool.zip)

- Unpack: BTXTTool -u <btxt file> <extracted csv file>
- Pack:  BTXTTool -p <modfied csv file> <new btxt file>
*)Character code of csv file is utf-8.

Hope this helps you who want to translate and sorry for my bad english .
## Post #40
- Username: BrucieK
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 25, 2012 3:10 am
- Post datetime: 2013-10-05T18:00:35+00:00
- Post Title: Re: State of Decay Text Repacker

What fonts do you use instead of original ones?

> Reply from merlinsvk
>
> Ehm guys, who knows how to correct that misaligned "selected" white bar?
(I replaced compacted fonts)





EDIT: Ok, I fixed that

How did you fix that?
## Post #41
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-10-05T18:24:01+00:00
- Post Title: Re: State of Decay Text Repacker

I used original fonts. Except Cloudsplitter UC BB, which I didn't found, so I used Blambot Casual Regular.

And I fixed that by changing Ascender and Descender values to original one's in FontLab Studio.
## Post #42
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2013-10-05T20:30:18+00:00
- Post Title: Re: State of Decay Text Repacker

@merlin, try this?

```
http://www.myfonts.com/fonts/blambot/cloudsplitter-bb/uc/glyphs.html
```

Just click on image with glyph and save like PNG, then use HiLogic Font Creator and load images end edit.

In which file you find this font? I found only this three: Decaying Kuntry; Expletive Deleted; VTCSuperMarketSaleSC.
## Post #43
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-10-05T21:28:24+00:00
- Post Title: Re: State of Decay Text Repacker

Thanks for the tip 

Cloudsplitter, Komika Parch and Arial are in class3hud.gfx
## Post #44
- Username: QueenSasha24
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 05, 2013 12:16 am
- Post datetime: 2013-12-03T01:12:58+00:00
- Post Title: Re: State of Decay Text Repacker

So do we have anything yet for editing the strings themselves? It would be really useful to be able to edit them now that the full game is out and it's not early access anymore.

(Apologies for the bump)
## Post #45
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-12-03T14:11:57+00:00
- Post Title: Re: State of Decay Text Repacker

If I remember correctly, there is no need to some special text tool. Just any hex editor.

[](http://postimg.org/image/c0zlwjyp3/)

That red part of .BTXT file is the same for all languages. Cut off the rest (text part) of .btxt, save it as .txt and translate it as usual. After translation, simply join cutted "header" part + text part together.

I hope nothing changed since Early Access, because I haven't the full version.
## Post #46
- Username: QueenSasha24
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 05, 2013 12:16 am
- Post datetime: 2013-12-03T14:14:45+00:00
- Post Title: Re: State of Decay Text Repacker

Actually, I just tested it and at least for the firearm names in the game, you can now modify them as you please, so seems you were correct, a tool isn't needed.
## Post #47
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-01-30T19:12:04+00:00
- Post Title: Re: State of Decay Text Repacker

Hi guys.I can't open gamedata.pak anyone help me?
## Post #48
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-01-30T19:20:04+00:00
- Post Title: Re: State of Decay Text Repacker

It's modified zip file. Use Aluigi's [BMS script](http://aluigi.altervista.org/bms/zip2.bms) for ZIP files.
## Post #49
- Username: MitiSen
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Sep 13, 2014 2:42 pm
- Post datetime: 2016-01-30T19:30:22+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from merlinsvk
>
> It's modified zip file. Use Aluigi's BMS script for ZIP files.

Thx man.You're awesome
## Post #50
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-02T12:22:54+00:00
- Post Title: Re: State of Decay Text Repacker

Oh no:(

I have a State Of Decay- Year One
And I can't open the gamedata.pak :S

Help me please,
File is right here: [http://www.mediafire.com/download/1gr44 ... medata.rar](http://www.mediafire.com/download/1gr44m9lzc5d12k/gamedata.rar)




---------------------------------------------------

I use the BMS script:
But I can't open again
## Post #51
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-03T01:11:59+00:00
- Post Title: Re: State of Decay Text Repacker

Up..
## Post #52
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2016-02-03T17:00:28+00:00
- Post Title: Re: State of Decay Text Repacker

7zip (15.14) opens it flawlessly, I think they just got back to simple zip files for the Year One release.
## Post #53
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2016-02-03T22:25:29+00:00
- Post Title: Re: State of Decay Text Repacker

> Reply from Vash
>
> 7zip (15.14) opens it flawlessly, I think they just got back to simple zip files for the Year One release.

Edit: does not work :S
