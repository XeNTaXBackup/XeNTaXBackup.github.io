## Post #1
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-01-21T15:29:37+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

How to open a big file BigFile_0001.big? wants to translate demo tnx
## Post #2
- Username: joqqy
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-21T17:37:14+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

well you should post samples but this is a quickbms script for extraction only.

```
get version long
get one byte
get nsize long
getdstring copyright nsize
get start long
get files long

get size long
get zsize long
get offset long
get unk01 long
get unk02 long
getdstring null 0x28
savepos tbl
goto offset
getdstring null 0xB
for i = 0 < files
get nsize long
math nsize - 2
get null short
getdstring name nsize
putarray 0 i name
next i
math files - 3
for i = 0 < files
goto tbl
get size long
get zsize long
get offset long
get unk01 long
get unk02 long
savepos tbl
goto offset
get tsize long
get null long
get size long
get zsize long
savepos offset
set j i
math j + 3
getarray name 0 j
if size == zsize
log name offset size
else
clog name offset zsize size
endif
next i
```
## Post #3
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-01-21T18:01:23+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from chrrox
>
> well you should post samples but this is a quickbms script for extraction only.
Code: Select allget idstring long
get version long
get one byte
get nsize long
getdstring copyright nsize
get start long
get files long

get size long
get zsize long
get offset long

I have problems with unpacking if you could upload these files?
 I was grateful 
get unk01 long
get unk02 long
getdstring null 0x28
savepos tbl
goto offset
getdstring null 0xB
for i = 0 < files
get nsize long
math nsize - 2
get null short
getdstring name nsize
putarray 0 i name
next i
math files - 3
for i = 0 < files
goto tbl
get size long
get zsize long
get offset long
get unk01 long
get unk02 long
savepos tbl
goto offset
get tsize long
get null long
get size long
get zsize long
savepos offset
set j i
math j + 3
getarray name 0 j
if size == zsize
log name offset size
else
clog name offset zsize size
endif
next i

I have a problem with this is unpacked file BigFile_0001.big
 could you upload me these files big unpack
 Thanks in advance
## Post #4
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-01-22T10:41:46+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

if I only use the Quick BMS Editor GUI ? HELP
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-01-22T11:34:29+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from quattro65
>
> if I only use the Quick BMS Editor GUI ? HELP

So ? Game is not even out yet i guess
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-22T11:45:05+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

and in any case no file was uploaded (even after the request of chrrox) so he will receive no help
## Post #7
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-01-22T12:13:12+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-01-28T16:14:04+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

I managed to unpack BMS BigFile_0001.big - [http://rghost.ru/36086116](http://rghost.ru/36086116)   , but still have a problem as it is referred back packer?
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-28T17:41:24+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

why don't you simply use the reimport feature of quickbms?
the script is fully compatible so there are no excuses.

read section 3 of quickbms.txt:
[http://aluigi.org/papers/quickbms.txt](http://aluigi.org/papers/quickbms.txt)
read it with attention for real because everything you need to know is already written there

and remember to use at least quickbms 0.5.6c because it has a better compression level with these files
## Post #10
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-01-28T23:31:39+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from aluigi
>
> why don't you simply use the reimport feature of quickbms?
the script is fully compatible so there are no excuses.

read section 3 of quickbms.txt:
http://aluigi.org/papers/quickbms.txt
read it with attention for real because everything you need to know is already written there

and remember to use at least quickbms 0.5.6c because it has a better compression level with these files
tnx aluigi     
click reimport
select kingdoms.bms code skript
select input archives BigFile_0001.big orginal?
error help can not restore BigFile_0001.big
## Post #11
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-01-30T16:15:24+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

click reimport
select kingdoms.bms code skript
select input archives BigFile_0001.big orginal?
error help can not restore BigFile_0001.big
[kingdoms revrse.jpg](https://xentaxbackup.github.io/file/5018_kingdoms revrse.jpg)
## Post #12
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-01-30T16:37:39+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

@quattro65
The edited file should be smaller or same size as the original.
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-30T16:38:36+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

as written by the tool the size of the file when compressed is bigger than the original and so it cannot be reimported.
remember that the size of the file after your modification MUST be ever smaller or equal than the original.
additionally when a file is archived in compressed mode (like this case) there is also the fact that the compressed size must be smaller/equal than the one of the compressed original file.

in this case even the kzip compression wasn't enough so if the size of the modified file is the same of the original one try to save some space removing unneeded chars.

these are the rules for reimporting via quickbms, follow them and it will work.
## Post #14
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-01-30T16:59:17+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from delutto
>
> @quattro65
The edited file should be smaller or same size as the original.
tnx
## Post #15
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-11T09:24:47+00:00
- Post Title: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Examples : 

```
http://dl.dropbox.com/u/38234344/Reckoning_Strings.rar
```


It is from X360 version of game...

PLease anyone have a look
## Post #16
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-11T13:19:09+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

PLease that script does not work for X360 version
## Post #17
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-12T09:41:08+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

please anyone help?
## Post #18
- Username: docc
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 14, 2012 7:53 am
- Post datetime: 2012-02-14T00:02:19+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Hey gays how pack files in BIG ?????
## Post #19
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-02-19T14:27:52+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

after editing and re-import dialog I have a problem, the game does not see this file localization table not loaded  , you surely must be the same size but how?
 use a file size change? I greet
## Post #20
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-02-20T00:25:32+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from michalss
>
> PLease that script does not work for X360 version
Try [this.](http://mod.gib.me/amalur/unpack.zip)
## Post #21
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-02-22T19:12:13+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from swuforce
>
> michalss wrote:PLease that script does not work for X360 version 
Try this.
[http://narod.ru/disk/40424431001/KOAR_Tools.rar.html](http://narod.ru/disk/40424431001/KOAR_Tools.rar.html)   txt converter 
txt to localization_ table does not work?
## Post #22
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-04T16:33:34+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Just finished my tools for localization and repacking big archives. Just wait to release  I have to test them little bit.
## Post #23
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-05T20:18:45+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Kingdoms of Amalur: Reckoning BIG Files Extractor
Tool to extract and repack BIG files.

```
http://raptor.cestiny.cz/download/kingdoms-of-amalur-reckoning-big-files-extractor.html
```

Kingdoms of Amalur: Reckoning Localization Table Translator
Tool to export *.localization_table to xml and back. Use your favorite xml editor (or notepad). 
Translation proces creates *.tran files (you have to select folder with original *.localization_table because of some data are copied). So don't forget to rename files back to original name. I'll put this into next version (maybe).

```
http://raptor.cestiny.cz/download/kingdoms-of-amalur-reckoning-localization-table-translator.html
```


Well it is tested, but you know, nothing is perfect 
Tools are PC only. Not working for XBox files, yet.
## Post #24
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-03-05T21:52:19+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from XRaptor
>
> Kingdoms of Amalur: Reckoning BIG Files Extractor
Tool to extract and repack BIG files.
Code: Select allhttp://raptor.cestiny.cz/download/kingdoms-of-amalur-reckoning-big-files-extractor.html
Kingdoms of Amalur: Reckoning Localization Table Translator
Tool to export *.localization_table to xml and back. Use your favorite xml editor (or notepad). 
Translation proces creates *.tran files (you have to select folder with original *.localization_table because of some data are copied). So don't forget to rename files back to original name. I'll put this into next version (maybe).
Code: Select allhttp://raptor.cestiny.cz/download/kingdoms-of-amalur-reckoning-localization-table-translator.html

Well it is tested, but you know, nothing is perfect 

Tools are PC only. Not working for XBox files, yet.
tnx 
tnx XRaptorThe requested URL /download/files/utils/AmalurTranslator100.rar was not found on this server.?
## Post #25
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-06T08:17:42+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

ups, fixed, it is AmalurTextTranslator100.rar
## Post #26
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-03-06T11:03:04+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from XRaptor
>
> ups, fixed, it is AmalurTextTranslator100.rar
Kingdoms of Amalur: Reckoning Localization Table Translator 
works great
but I have a problem with reimport back repack to bigFile_0001.big
open file/patch/save/folder Search/001 ?
BigFile_0001_NEW.big nothing has changed
greetings
## Post #27
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-03-06T12:58:43+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Great work XRaptor again.
Just a question: when I import the translated xml back, it gives me this warning:

```
>> Unexpected EOF. I = 6648 instead of 9824
```
## Post #28
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-03-06T13:12:23+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Working PS3 version?

Tks.
## Post #29
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-06T14:17:36+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from lostprophet
>
> Just a question: when I import the translated xml back, it gives me this warning:
Code: Select all001\content\assets\localizationtable\main_table.localization_table
>> Unexpected EOF. I = 6648 instead of 9824
Well you can just ignore it, it is just internal warning. It seems that this one file "main_table.localization_table" is corrupted or truncated in game, because there should be more entries. If you check this file in any editor, you will se theat last string ends with "It was created" and nothing more. Header in file says there should be 9824 strings, but only 6648 is inside. Maybe there will be patch or something.

> Reply from quattro65
>
> XRaptor wrote:ups, fixed, it is AmalurTextTranslator100.rar 
Kingdoms of Amalur: Reckoning Localization Table Translator 
works great
but I have a problem with reimport back repack to bigFile_0001.big
open file/patch/save/folder Search/001 ?
BigFile_0001_NEW.big nothing has changed
greetings
Well, how to do it:
1) Extract files to any folder (like c:\export)
2) Use translator on this folder (it is recursive tool and checks for all files)
3) When translated, use tool to generate trans files
4) Rename *.trans files to original ones (I know, it is boring for now, but use any script or bat file)
5) Use extractor, open original BIG file, click to Patch button a select this extracted folder (like c:\export), not subfolders!!! Tool looks for files based on original structure. So if exists file "c:\export\001\content\assets\localizationtable\main_table.localization_table" etc. it is inserted to new big file. Otherwise original file is streamed.

> Reply from timartinelli
>
> Working PS3 version?
Tks.
If PS3 files are the same like PC, then yes. I will create XBox version of tool later, but I have no idea what is in PS3 version.
## Post #30
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-03-06T17:09:59+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from XRaptor
>
> lostprophet wrote:Just a question: when I import the translated xml back, it gives me this warning:
Code: Select all001\content\assets\localizationtable\main_table.localization_table
>> Unexpected EOF. I = 6648 instead of 9824
Well you can just ignore it, it is just internal warning. It seems that this one file "main_table.localization_table" is corrupted or truncated in game, because there should be more entries. If you check this file in any editor, you will se theat last string ends with "It was created" and nothing more. Header in file says there should be 9824 strings, but only 6648 is inside. Maybe there will be patch or something.
quattro65 wrote:XRaptor wrote:ups, fixed, it is AmalurTextTranslator100.rar 
Kingdoms of Amalur: Reckoning Localization Table Translator 
works great
but I have a problem with reimport back repack to bigFile_0001.big
open file/patch/save/folder Search/001 ?
BigFile_0001_NEW.big nothing has changed
greetings
Well, how to do it:
1) Extract files to any folder (like c:\export)
2) Use translator on this folder (it is recursive tool and checks for all files)
3) When translated, use tool to generate trans files
4) Rename *.trans files to original ones (I know, it is boring for now, but use any script or bat file)
5) Use extractor, open original BIG file, click to Patch button a select this extracted folder (like c:\export), not subfolders!!! Tool looks for files based on original structure. So if exists file "c:\export\001\content\assets\localizationtable\main_table.localization_table" etc. it is inserted to new big file. Otherwise original file is streamed.
timartinelli wrote:Working PS3 version?
Tks.
If PS3 files are the same like PC, then yes. I will create XBox version of tool later, but I have no idea what is in PS3 version.

ok tnx everything works great but is difficult to edit the xml
 need to wait for conventer xml to txt
i great
## Post #31
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-06T17:48:21+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from quattro65
>
> 
ok tnx everything works great but is difficult to edit the xml
 need to wait for conventer xml to txt
i great
LOL, really? You can open xml in excel (or open office variant) and edit everything, then export back to xml data  xml is the best way how to transfer data to any editor you want  Translating in txt? Funny
## Post #32
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-03-06T18:05:47+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> ok tnx everything works great but is difficult to edit the xml
>
>  need to wait for conventer xml to txt
>
> i great
Use Notepad++ or as XRaptor said, Excel or OpenOffice. XML is better since the translatable strings can be clearly seen.
## Post #33
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-03-07T17:11:17+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Friend, I'm posting here XRaptor the file from the PS3, you will be able to see if the tool can work with the file from the PS3?

please.

[http://www.mediafire.com/?w4epr4e37lp63ym](http://www.mediafire.com/?w4epr4e37lp63ym)

Hug.
## Post #34
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-07T17:58:13+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Ok, just added XBox + PS3 versions of tools. Seems that PS3 files are almost the same like XBox. Just older then XBox and PC. So check them 

Kingdoms of Amalur: Reckoning BIG Files Extractor (PC + XBox + PS3)

```
http://raptor.cestiny.cz/download/kingdoms-of-amalur-reckoning-big-files-extractor.html
```

Kingdoms of Amalur: Reckoning Localization Table Translator (PC + XBox + PS3)

```
http://raptor.cestiny.cz/download/kingdoms-of-amalur-reckoning-localization-table-translator.html
```


If any problems, let me know. 

And just about slow export/import xml - I hate this shity MS XML things Tried to do this different way, but there were sometimes problems with data validity. So simply make some coffee and ignore this, maybe I will fix it somehow
## Post #35
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-03-07T18:09:41+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

friend, I downloaded the program again it still does not open the BigFile_0001.big, I mean the AmalurExtractor.exe.

the message
Unknom file type.

PS:I just saw the new tool, I'll download and test.
## Post #36
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-07T18:13:19+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from timartinelli
>
> Girlfriend, I downloaded the program again it still does not open the BigFile_0001.big, I mean the AmalurExtractor.exe.

the message
Unknom file type.

PS:I just saw the new tool, I'll download and test.
Download XBox+PS3 version  There are 2 files now to download.
## Post #37
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-03-07T18:18:26+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

I'm sorry for Girlfriend, I'm using a translator, lol

draws all, only one question.
I extract the. big files to a folder.
Then I used the translation tool and I put this folder files, and it converts all teh it is in, is that right?

inside that folder is the

001 - folder
content
bigvalidationfile.bin
bundle_mount_info.bin
lookup_names_as_strings.bin

I'm doing right? or should I use some other folder?
## Post #38
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-07T18:28:20+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Translation tool parses all language files then saves export.xml file. You can translate this file, then use again translation tool for this directory structure. It agains looks for translation tables and translate all. Then new files are saved as ORIG_NAME. tran (I can't rewrite original, some datas are streamed to new files). So rename *.trans to *.localization_table and use extractor to repack files back. And again, leave in this folder only modified files. There is no need to have everything. 

Well and tool is not tested if 3 internal files are presents:
-bigvalidationfile.bin
-bundle_mount_info.bin
-lookup_names_as_strings.bin

Simply delete them. There is nothing you have to modify.
## Post #39
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-03-07T18:33:23+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

I think I understand, I'll do a translation test to check everything.
no doubt I come here.

Hug.
## Post #40
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-03-08T13:09:36+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from XRaptor
>
> timartinelli wrote:Girlfriend, I downloaded the program again it still does not open the BigFile_0001.big, I mean the AmalurExtractor.exe.

the message
Unknom file type.

PS:I just saw the new tool, I'll download and test.
Download XBox+PS3 version  There are 2 files now to download.
is a small problem main_table.localization_table file,
 is incomplete 346kb
 complete  740kb
i great
## Post #41
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-08T13:21:13+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

That's why warning is thrown.

```
>> Unexpected EOF. I = 6648 instead of 9824

```


What I know, there is incomplete file in big archive. If you know where and how to get full version, let me know, or send me whole file and I'll try to find the problem.
## Post #42
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-03-08T14:53:31+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from XRaptor
>
> That's why warning is thrown.
Code: Select all001\content\assets\localizationtable\main_table.localization_table
>> Unexpected EOF. I = 6648 instead of 9824


What I know, there is incomplete file in big archive. If you know where and how to get full version, let me know, or send me whole file and I'll try to find the problem.

there is complete localizationtable
[http://www.mediafire.com/?nzqh8cazcb5kcsw](http://www.mediafire.com/?nzqh8cazcb5kcsw)
## Post #43
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-08T19:42:21+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Well, quattro65 is right. Some files (don't know how many yet) are splitted to more compressed parts. So I have to find out how to detect those files and how to repack them back to more parts 

EDIT: Ok, found the problem. I will release fixed tools soon.

EDIT 2: Blah, have some problems. Now I'm able to extract all files and not truncated blocks. But repack is not working. It seems that larger files must be splitted like originals and I can't find the best algorithm to split input file to more zlib streams
## Post #44
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-03-10T10:49:42+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from XRaptor
>
> Well, quattro65 is right. Some files (don't know how many yet) are splitted to more compressed parts. So I have to find out how to detect those files and how to repack them back to more parts 

EDIT: Ok, found the problem. I will release fixed tools soon.

EDIT 2: Blah, have some problems. Now I'm able to extract all files and not truncated blocks. But repack is not working. It seems that larger files must be splitted like originals and I can't find the best algorithm to split input file to more zlib streams

so agree repack is not working main_table.localization_table 765kb
at the start of the game, shows up 
[table.localization no table} missing subtitles
i great
## Post #45
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-11T16:49:12+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Ok, fixed tools uploaded. Extracting is fixed now. There will be later new version of extractor with optimised comression algorithm. It is little slow now. But if you don't try to repack whole gig archive, it is ok  Simply add to patch process only modified files. Not everything. Otherwise - you have been warned 

Text tool now exports and replaces original files, so there is no need to rename *.tran files after process.

If any problems, let me know. 

Kingdoms of Amalur: Reckoning BIG Files Extractor (PC + XBox + PS3)
[http://raptor.cestiny.cz/download/kingd ... actor.html](http://raptor.cestiny.cz/download/kingdoms-of-amalur-reckoning-big-files-extractor.html)

Kingdoms of Amalur: Reckoning Localization Table Translator (PC + XBox + PS3)
[http://raptor.cestiny.cz/download/kingd ... lator.html](http://raptor.cestiny.cz/download/kingdoms-of-amalur-reckoning-localization-table-translator.html)
## Post #46
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-03-11T18:39:26+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Awesome work XRaptor, thank you very much!
## Post #47
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-03-11T19:51:46+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

The final program works very well
 main_table complete 100%
 well done Awesome work XRaptor, thank you very much! 
i great
## Post #48
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-03-12T21:53:14+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Sorry for being an ungrateful b*tch, but can the .big extractor/repacker be made into a commandline tool also? The fonts are in a 900 megabyte .big file and I wouldn't like that packed into the installer
## Post #49
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2012-03-13T11:11:09+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from lostprophet
>
> Sorry for being an ungrateful b*tch, but can the .big extractor/repacker be made into a commandline tool also? The fonts are in a 900 megabyte .big file and I wouldn't like that packed into the installer

Have you tried out this?:

Place everything in a "Patch_0099.big" file, and this archive copy to every "Patches" directory in ...Kingdoms of Amalur Reckoning|bigs|006, "007", "008...

I think it might works.
## Post #50
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-03-13T13:31:56+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from terminator
>
> lostprophet wrote:Sorry for being an ungrateful b*tch, but can the .big extractor/repacker be made into a commandline tool also? The fonts are in a 900 megabyte .big file and I wouldn't like that packed into the installer 

Have you tried out this?:

Place everything in a "Patch_0099.big" file, and this archive copy to every "Patches" directory in ...Kingdoms of Amalur Reckoning|bigs|006, "007", "008...

I think it might works.
It would, if the "lookup_names_as_strings.bin" didn't contain the files to extract/repack from the archive. Can't add new ones to an existing archive, that's why a commandline tool would be great.
## Post #51
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-13T13:36:23+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Isn't better way to simply make some differential patch?
## Post #52
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-03-13T13:40:51+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from XRaptor
>
> Isn't better way to simply make some differential patch?
What do you have in mind? A friend of mine mentioned XDelta, would that work?
## Post #53
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-13T13:43:48+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

NSIS+VPatch, ClickTeam PatchMaker, ... whatever. I think there are many free differential patch programs.
## Post #54
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-03-14T07:37:56+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Thanks, PatchMaker didn't work for me and I use InnoSetup instead of NSIS, but XDelta ( [http://xdelta.org/](http://xdelta.org/) ) did the trick.
And thank you again, XRaptor!
## Post #55
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2012-03-17T07:12:48+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Sorry but does anyone know where is the model location and which 3d program can open it?
## Post #56
- Username: arlega02
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 25, 2012 3:21 am
- Post datetime: 2012-03-24T20:08:59+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Hello.First, thanks to xRaptor. I  using the xRaptor's "Kingdoms of Amalur: Reckoning BIG Files Extractor" and unpack "BigFile_0001.big". (for translation english to other language). After, repatching this unpacked file with same program. But ı have a problem, the orginal "BigFile_0001.big" is 1.802 KB, but when I translate any word and repatch the unpacked "BigFile_0001.big", this file turn 1.788 KB and game don't open. How can I convert the same form as before?
## Post #57
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-24T20:34:36+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Can you extract your modified file succesfully? If yes, then there should be no error inside. BUt if you think there is problem, send tthis file to me and I can check it
## Post #58
- Username: arlega02
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 25, 2012 3:21 am
- Post datetime: 2012-03-24T21:19:00+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

I have fixed this problem  Reason of this problem is character limitation. For example, at the beginning of the game, says "Press Any Button". It is 13 charecters. If I translate this line and use few or much 13 character, game is dont open  I must use 13 charecter. Therefore, translation of this game is very complicate and hard. If you know this problem's solution, please tell me.


And, my gift to you for your program  I use 13 charecter 

[http://imgim.com/316incis9207619.png](http://imgim.com/316incis9207619.png)
## Post #59
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-24T21:24:43+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

It is nonsense, there is no need to translate to the same length as original  As I said, you can send me your translated file and I can check it. Maybe there is some bug in editor.
## Post #60
- Username: arlega02
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 25, 2012 3:21 am
- Post datetime: 2012-03-24T21:43:44+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

It is not nonsense  I have translated many games before. And some games have character limitation, for example; Prison Break, Batman A.A. Some games doesn't have character limitation, just like Fallout 3, Torchlight, Arx Fatalis. I can send you translation files later. But i was translated only 3-4 strings.
## Post #61
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-25T10:04:40+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

If you are only hexediting without complette rebuild with length changes, then yes, you have to set the same length. But this is rebuilt with length changes  In some games there is engine text length restriction, but it is not this game.
## Post #62
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-03-25T13:33:22+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from XRaptor
>
> If you are only hexediting without complette rebuild with length changes, then yes, you have to set the same length. But this is rebuilt with length changes  In some games there is engine text length restriction, but it is not this game.
I can confirm XRaptor's statement, IT IS nonsense, KOAR doesn't have any character limitation. I translated a few thousand lines so far, and it works perfectly (just checked now). I'm using the latest 1.1.0 of XRaptor's tools.
## Post #63
- Username: arlega02
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 25, 2012 3:21 am
- Post datetime: 2012-03-25T13:41:37+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from XRaptor
>
> If you are only hexediting without complette rebuild with length changes, then yes, you have to set the same length. But this is rebuilt with length changes  In some games there is engine text length restriction, but it is not this game.

I am editing with notepad++. I am just a translator  I cant use programs such as hex editor. How can I solve characher limitation problem? 

And, writings seems so confused in notepad++. Is there any program that you would propose for edit writings? ([http://imgim.com/4286inciv6587096.jpg](http://imgim.com/4286inciv6587096.jpg))


EDİT: lostprophet, which program you use for edit writings? I used only the first program of xRaptor(for unpack) and using notepad++ for translate. I dont understand second program of xRaptor.(Kingdoms of Amalur: Reckoning Localization Table Translator) What is for this program? It says dat->xml and xml->dat, but ı cant understand.
## Post #64
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-25T13:45:53+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Now it makes sense to me. You are editing directly localization_table file?  Use my text translator 

Kingdoms of Amalur: Reckoning Localization Table Translator (PC + XBox + PS3)
[http://raptor.cestiny.cz/download/kingd ... lator.html](http://raptor.cestiny.cz/download/kingdoms-of-amalur-reckoning-localization-table-translator.html)
## Post #65
- Username: arlega02
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 25, 2012 3:21 am
- Post datetime: 2012-03-25T13:51:56+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from XRaptor
>
> Now it makes sense to me. You are editing directly localization_table file?  Use my text translator 

Kingdoms of Amalur: Reckoning Localization Table Translator (PC + XBox + PS3)
http://raptor.cestiny.cz/download/kingd ... lator.html

Hmmm  Now I understand   I will try it later, i am not in home right now
## Post #66
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-03-25T14:01:57+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from arlega02
>
> XRaptor wrote:Now it makes sense to me. You are editing directly localization_table file?  Use my text translator 

Kingdoms of Amalur: Reckoning Localization Table Translator (PC + XBox + PS3)
http://raptor.cestiny.cz/download/kingd ... lator.html

Hmmm  Now I understand   I will try it later, i am not in home right now
I use Notepad++ too.
## Post #67
- Username: arlega02
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 25, 2012 3:21 am
- Post datetime: 2012-03-25T15:28:30+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

I was solved character limitation :)There are how many lines in all this game? Or how can i know this?
## Post #68
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-25T16:20:15+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Open exported xml file in excel and simply check rows  There is no need to translate in notepad. Process xml file in any favorite editor or excel (or any OpenOffice variant).
## Post #69
- Username: arlega02
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 25, 2012 3:21 am
- Post datetime: 2012-03-25T21:11:24+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Like all the other games,  this game doesn't support Turkish characters such like şŞ üÜ ğĞ ıİ.
Normally, ı can editing font files with font editors but in this game, font files are not in font format  They are in FONT_XML format. How can i edit this files and add Turkish characters?


[http://imgim.com/8343incio7192664.jpg](http://imgim.com/8343incio7192664.jpg)

Follows the order: Yeni Oyun Iı İi Ğğ Şş Üü

Font Files: http: [http://www.2shared.com/file/YtbsKX6y/fonts.html](http://www.2shared.com/file/YtbsKX6y/fonts.html)
## Post #70
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-26T04:47:18+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from arlega02
>
> Like all the other games,  this game doesn't support Turkish characters such like şŞ üÜ ğĞ ıİ.
Normally, ı can editing font files with font editors but in this game, font files are not in font format  They are in FONT_XML format. How can i edit this files and add Turkish characters?


http://imgim.com/8343incio7192664.jpg

Follows the order: Yeni Oyun Iı İi Ğğ Şş Üü

Font Files: http: http://www.2shared.com/file/YtbsKX6y/fonts.html

Fonts are DDS not xml. Items u posted are might indexes. Not sure
## Post #71
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-03-26T07:23:59+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from arlega02
>
> Like all the other games,  this game doesn't support Turkish characters such like şŞ üÜ ğĞ ıİ.
Normally, ı can editing font files with font editors but in this game, font files are not in font format  They are in FONT_XML format. How can i edit this files and add Turkish characters?


http://imgim.com/8343incio7192664.jpg

Follows the order: Yeni Oyun Iı İi Ğğ Şş Üü

Font Files: http: http://www.2shared.com/file/YtbsKX6y/fonts.html
There are 9 .dds files, which contain the fonts for the game.
Bigfile_0000.big contains 177586.dds, 177587.dds, 177588.dds, 177620.dds, 1625778.dds, 1625779.dds, 2027703.dds, 2027704.dds
Bigfile_0005.big contains 2041094.dds

Edit these .dds files with Photoshop and use XRaptor's tools to repack them.
## Post #72
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2012-03-27T20:07:19+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Como volto o arquivo extraído xlm "export" para BigFile_0001.big?
## Post #73
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-27T20:26:55+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Next time english, please 

Simply use xml->dat function and repack archive
## Post #74
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2012-03-27T20:34:59+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Sorry, I use it, but it creates the file BigFile_0001.big. It creates new files in the folder 001. How can I transform the xml BigFile_0001.big?
## Post #75
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-03-27T21:02:20+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

I don't understand, so little overview:

1) Use extractor to extract file bigs\001\EnglishTarget\BigFile_0001.big to any folder (repeat for bigs\002 and 009)
2) Keep only *.localization_table, delete everything else
3) Use text translator to convert dat->xml (select folder from step 1)
4) Export.xml file is generated with all texts from files
5) Translate xml file
6) Use text translator to convert xml->dat (select folder from step 1)
7) New *.localization_table are generated with translated texts
 Use extractor, open original big file, select "patch" button, enter new filename (you CAN'T select original one) and select folder from step 1
9) Rename BigFile_0001_NEW.big (or file you set) to BigFile_0001.big

That's all
## Post #76
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2012-03-27T21:18:29+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Thanks, worked
## Post #77
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2012-03-29T20:51:09+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Anyone can help me with open ps3 dds of this game? PC is not problem, but I'm stuck on the PS3

[http://www.mediafire.com/?bu48eipins54pe8](http://www.mediafire.com/?bu48eipins54pe8)
[http://www.mediafire.com/?06se522718z75th](http://www.mediafire.com/?06se522718z75th)
## Post #78
- Username: Amakyusa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 09, 2012 2:11 am
- Post datetime: 2012-10-08T23:32:39+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Hello!

I'm new to the forums and I wish to contribute to translation resources for Kingdoms of Amalur we already have thanks to XRaptor.

To make easy the translation, I made an application that reads the XML exported using the XRaptor tool and I'd like to share with you guys.

You see, is a beta version. Any bugs you can just tell me and I try to resolve as quick as possible.

EDIT:
Download link: Ver. 1.5
[http://www.mediafire.com/?2mloaoq71lbzocq](http://www.mediafire.com/?2mloaoq71lbzocq)

Instructions:

Unzip it and run.

After you have already extracted de XML from the file on .BIG, just open with my application, edit and save 

Reimport the data in XML using the other XRaptor tools as mentioned in the earlier posts.


Hope this make easier for people who feels unconfortable editing XML in excel or notepad.(or whatever).


Thank you all!

=========== Ver. 1.5 Changelog ==============

*Added multiple files text replacement (EXPERIMENTAL! Make backups, please):
    Load the XML you're currently working with;
    In the "other" tab, add the files you wish the Locate and Replace feature to affect;
    Mark the checkbox "in other files as well";

*Standalone .EXE
    Please report any error while running it. May be needed more recent vcredist package from Micro$oft.
    x86 Version: [http://www.microsoft.com/en-us/download ... px?id=5555](http://www.microsoft.com/en-us/download/details.aspx?id=5555)
    x64 Version: [http://www.microsoft.com/en-us/download ... x?id=14632](http://www.microsoft.com/en-us/download/details.aspx?id=14632)



************ Future releases upgrades! **********

"Last Position" button with no backwards navegation limit.
*Fix a bug where "Translation" Tag is receiving blank data.


sorry about any grammatical errors ( english isn't my natural language)
## Post #79
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-10-09T06:01:10+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

You can simply open this xml in Excel or any Open Office alternative and edit  That's how I did it. But yes, you can use any xml tool.
## Post #80
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-10-09T17:13:12+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from Amakyusa
>
> Hello!

I'm new to the forums and I wish to contribute to translation resources for Kingdoms of Amalur we already have thanks to XRaptor.

To make easy the translation, I made an application that reads the XML exported using the XRaptor tool and I'd like to share with you guys.

You see, is a beta version. Any bugs you can just tell me and I try to resolve as quick as possible.

Download link:
http://www.mediafire.com/?9lzu8r1n99bh7hn

Instructions:

Unzip it and run Setup.exe and install.

After you have already extracted de XML from the file on .BIG, just open with my application, edit and save 

Reimport the data in XML using the other XRaptor tools as mentioned in the earlier posts.


Hope this make easier for people who feels unconfortable editing XML in excel or notepad.(or whatever).


Thank you all!
Great job, I'll check this at home with the translation files. One small thing: could you add a button for the replace tool, so it not only replaces the words/characters in the same file, but the other xml files too (I'm translating the whole game with the 2 DLCs, which are in separate xmls, but have lots of text in common).
## Post #81
- Username: Amakyusa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 09, 2012 2:11 am
- Post datetime: 2012-10-09T17:58:39+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Great job, I'll check this at home with the translation files. One small thing: could you add a button for the replace tool, so it not only replaces the words/characters in the same file, but the other xml files too (I'm translating the whole game with the 2 DLCs, which are in separate xmls, but have lots of text in common).

Good idea! I'll work on it!
## Post #82
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-10-09T21:01:04+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from Amakyusa
>
> 
Great job, I'll check this at home with the translation files. One small thing: could you add a button for the replace tool, so it not only replaces the words/characters in the same file, but the other xml files too (I'm translating the whole game with the 2 DLCs, which are in separate xmls, but have lots of text in common).

Good idea! I'll work on it!
1. Do we really need an installer? Couldn't it be a portable editor like every other stuff on this site? I like to bring everything with me on my pendrive, and dont really want to install it on every PC I use 
2. Using the Last Position button only returns to the previous string, but cannot go back any further. Is it a bug or is it just the way it is?
3. In the original xmls the <Translation></Translation> was in one line, but after using your tool, they are in separate lines. It's not a big bug, but the file is bigger with 300 kbytes and longer with 67.000 lines.

Other than that, great job  I'll be using this, as my Notepad++ is choking under the 360.000+ lines, when I use Wordwrapping.
## Post #83
- Username: Amakyusa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 09, 2012 2:11 am
- Post datetime: 2012-10-10T20:07:52+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> 1. Do we really need an installer? Couldn't it be a portable editor like every other stuff on this site? I like to bring everything with me on my pendrive, and dont really want to install it on every PC I use 
>
> 2. Using the Last Position button only returns to the previous string, but cannot go back any further. Is it a bug or is it just the way it is?
>
> 3. In the original xmls the <Translation></Translation> was in one line, but after using your tool, they are in separate lines. It's not a big bug, but the file is bigger with 300 kbytes and longer with 67.000 lines.
>
> 
>
> Other than that, great job  I'll be using this, as my Notepad++ is choking under the 360.000+ lines, when I use Wordwrapping.

Hi, Thank you!

About the "last position" button, yes, it just go back one position (has to do with the way I start dealing whith the xml in the first place). But I intend to change that! 

About the lines question and no installer, I'll check this..thx for the feedback!
## Post #84
- Username: Amakyusa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 09, 2012 2:11 am
- Post datetime: 2012-10-12T04:35:05+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Hello, everyone!

The XML Translation tool was updated!

The download link is in the original post and the changelog too.

Thx!
## Post #85
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-10-12T08:16:28+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from Amakyusa
>
> Hello, everyone!

The XML Translation tool was updated!

The download link is in the original post and the changelog too.

Thx!
Thanks for the fast update. The multiple file replace works okay, but the <Translation></Translation> tags are still in separate lines.
## Post #86
- Username: Amakyusa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 09, 2012 2:11 am
- Post datetime: 2012-10-12T15:02:10+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from lostprophet
>
> 
Thanks for the fast update. The multiple file replace works okay, but the <Translation></Translation> tags are still in separate lines.

o.Ô'

Ok, added for the issues list. Now that will be tricky...

I'll investigate.
## Post #87
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-10-21T14:13:12+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Any news on the fix?:)
## Post #88
- Username: Amakyusa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 09, 2012 2:11 am
- Post datetime: 2012-10-21T23:11:48+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from lostprophet
>
> Any news on the fix?:)

Sorry, not yet 

I was on vacation when I first released the tool, but since I'm back to work, had little time to fix it.

But I'll keep you informed
## Post #89
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-10-22T05:36:01+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from Amakyusa
>
> lostprophet wrote:Any news on the fix?:)

Sorry, not yet 

I was on vacation when I first released the tool, but since I'm back to work, had little time to fix it.

But I'll keep you informed
Thanks!
## Post #90
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-11-15T20:48:44+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Amakyusa, any updates?:)
## Post #91
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2013-04-01T07:44:42+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Hello
I have a problem opening the file w Kingdoms of Amalur
[http://www.speedyshare.com/ceXJs/loot-a ... tion-table](http://www.speedyshare.com/ceXJs/loot-affix-table.localization-table)
There are varieties of German equipment

I'll be grateful
## Post #92
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2013-04-14T11:45:41+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from quattro65
>
> Hello
I have a problem opening the file w Kingdoms of Amalur
http://www.speedyshare.com/ceXJs/loot-a ... tion-table
There are varieties of German equipment

I'll be grateful

Nobody is able to help me?
## Post #93
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-14T13:18:34+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from quattro65
>
> Hello
I have a problem opening the file w Kingdoms of AmalurAnd what is your problem with?
Have a look using a hexeditor - it's very simple.

Starting from file offset 0x001A you'll find this format:

DWORD counter
DWORD strlen
char str[strlen]
BYTE id

```

00010                                  06 00 00 00 0A 00             ......
00020   00 00 42 69 72 6B 65 6E  68 6F 6C 7A 11 0A 00 00   ..Birkenholz....
00030   00 42 69 72 6B 65 6E 68  6F 6C 7A 12               .Birkenholz.
```


So there's 6 times "Birkenholz" each with a string length of 10.
The id is 0x11, 0x12, 0x14, 0x21 I don't know what it is good for.

All strings are in german. That's all to tell about this "localization" table imho.

Did I miss something? Maybe the DWORD at offset 0x0004= 0x212 (530 dec.) is the counter for the (different) items? Didn't check that.
## Post #94
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2013-04-17T16:54:24+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Thank you for the information  

I have issues with the Hex Editor

Could I have a decrypted file in xml ?
## Post #95
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-17T23:08:18+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

> Reply from quattro65
>
> Could I have a decrypted file in xml ?There's nothing to "decrypt".
What you mean is a converted file I think.

This is a text file: [loottable.zip](http://www.uploadmb.com/dw.php?id=1366239468)
Any excel related app should be able to import it into a table.

xml? Well, there are different possibilities to create some xml structure.
For example each string surrounded by
<Component name="Idon'tknow" >
  Birkenholz
</Component>

But I'm not in the mood to think about this, sry.
## Post #96
- Username: neff10
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 18, 2012 2:17 pm
- Post datetime: 2013-06-08T19:39:20+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

great men! works!!
## Post #97
- Username: Phnx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 17, 2010 11:31 pm
- Post datetime: 2013-12-19T16:59:32+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

Hey I recently got back to playing KoAR. I'd like to do a little modding. I know how to hex-edit dds file to be able to edit them. Just correct the header, edit, paste the edited code back into backup of original file. Does anyone know how to edit "bin" and "bxml" files? Thx! 

So, "bxml" could be this

[http://en.wikipedia.org/wiki/Binary_XML](http://en.wikipedia.org/wiki/Binary_XML)

and "bin" one of these (or anything)?

[http://bin.fileextensionguide.com](http://bin.fileextensionguide.com)
## Post #98
- Username: stefan7202
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 15, 2010 6:10 pm
- Post datetime: 2014-09-21T16:56:25+00:00
- Post Title: Re: Kingdoms of Amalur: Reckoning unpacker BigFile_0001.big

why me out of characters? only changed the text to see if it goes to Bulgarian. Text edited with notepad program ++
