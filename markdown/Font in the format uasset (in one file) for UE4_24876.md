## Post #1
- Username: KASaLEX
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 13, 2017 10:05 pm
- Post datetime: 2021-12-22T11:10:23+00:00
- Post Title: Font in the format uasset (in one file) for UE4

Hey guys. I need your help in editing fonts in uasset. I would be glad for any information and advice on this subject. I need to change the kerning for Cyrillic in the font, and in general I want to understand how to work with this type of fonts. The game is Hidden Dragon Legend. Engine version 4.14.

Gaming Fonts
[https://mega.nz/file/lrozwYZT#asUJV0Xa3 ... 2rj0lWrAnk](https://mega.nz/file/lrozwYZT#asUJV0Xa3aoXtPeOXSfo3nhw8oxpgMM1h2rj0lWrAnk)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-22T11:41:52+00:00
- Post Title: Font in the format uasset (in one file) for UE4

I have solved similar issue lately on discord regarding "State of Decay 2" fonts.

Basically you can use offzip to extract zlib data [https://aluigi.altervista.org/mytoolz/offzip.zip](https://aluigi.altervista.org/mytoolz/offzip.zip)
using this command:

```
offzip.exe -a FontBlack.uasset
```


If the font is small enough you should get valid TTF/OTF file from uasset or ubulk files
[http://wiki.xentax.com/index.php/OpenType_Font_TTF_OTF](http://wiki.xentax.com/index.php/OpenType_Font_TTF_OTF)

Is a font is big (more than 75000 bytes in total size), then uasset/ubulk will contain multiple zlib streams and after extracting with offzip
you'll get one cutted TTF/OTF file and multiple DAT file with it.
You can join those files manually in hex editor and after that you will be able to edit font in some tool
like for example High-Logic FontCreator.


The real issue here in my opinion is automation of this joining process and being able to reimport data after editing.
In State of Decay 2 most fonts were compressed in the single zlib stream so it was easy to edit them and import back with offzip,
but in your case you have 20+ DAT files to join for each font...
## Post #3
- Username: KASaLEX
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 13, 2017 10:05 pm
- Post datetime: 2021-12-22T11:55:56+00:00
- Post Title: Font in the format uasset (in one file) for UE4

So it's not a raster font and it has no texture?
And how import back with offzip?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-22T14:38:12+00:00
- Post Title: Font in the format uasset (in one file) for UE4

> So it's not a raster font and it has no texture?
No, they are OpenType TTF fonts.

> And how import back with offzip?

You can use "-r" option for reimport (works exactly like in quickbms).



By the way, I think I have found a solution for merging/joining issue.
You could just use "-1" option while extracting:

```
offzip.exe -a -1 FontBlack.uasset
```
