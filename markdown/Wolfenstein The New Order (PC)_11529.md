## Post #1
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2014-05-21T15:32:50+00:00
- Post Title: Wolfenstein: The New Order (PC)

Hi there, 

does anyone know about any tools for extracting text from this game? There are arhive files called "resources" which should contain all ingame text.
## Post #2
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-22T08:02:01+00:00
- Post Title: Wolfenstein: The New Order (PC)

> Reply from phill05
>
> Hi there, 

does anyone know about any tools for extracting text from this game? There are arhive files called "resources" which should contain all ingame text.

There is no bms script yet. Waiting for someone who can afford it. [viewtopic.php?f=10&t=11509](http://forum.xentax.com/viewtopic.php?f=10&t=11509)
## Post #3
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-05-22T21:57:10+00:00
- Post Title: Wolfenstein: The New Order (PC)

script for .resources

```
open FDDE resources 1
comtype unzip_dynamic

endian big
goto 0x24
get files long
get unk long
math TMP = files
math TMP - 1
for i = 0 < files
endian little
get FNsize1 long
getdstring FN1 FNsize1
get FNsize2 long
getdstring FN2 FNsize2
get namesize long
getdstring name namesize
endian big
get offset long
get size long
get zsize long
get unksize long
math unksize * 0x18
math unksize + 5
getdstring unkdata unksize

if size = zsize
log name offset size 1
else 
clog name offset zsize size 1
endif
if i != TMP
get filenumber long
endif
next i
```
## Post #4
- Username: folkemon1977
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Aug 19, 2013 3:57 pm
- Post datetime: 2014-05-23T15:16:52+00:00
- Post Title: Wolfenstein: The New Order (PC)

Thief1987 - many thanks...

Please, can you write script for .streamed files?
It looks there is text for transalation...
## Post #5
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-23T17:45:16+00:00
- Post Title: Wolfenstein: The New Order (PC)

> Reply from folkemon1977
>
> Thief1987 - many thanks...

Please, can you write script for .streamed files?
It looks there is text for transalation...

No. I think .streamed file contaings audio files. Look at chunk0.resources.

In the chunk0\generated\textures\borderclamp_alpha_fonts\arial_black folder,
there are 64_df.bimage.



And the main story script is at chunk0\strings Folder.
## Post #6
- Username: folkemon1977
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Aug 19, 2013 3:57 pm
- Post datetime: 2014-05-23T20:31:51+00:00
- Post Title: Wolfenstein: The New Order (PC)

albert1905: Many thanks.... please, what program are using for open font files?

And is there some way how put edited files back to .resource file?
## Post #7
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-24T04:46:58+00:00
- Post Title: Wolfenstein: The New Order (PC)

> Reply from folkemon1977
>
> albert1905: Many thanks.... please, what program are using for open font files?

And is there some way how put edited files back to .resource file?

I used Photoshop CS5. Open it as raw file.


<Unpack>

First, make a new foleder in quickbms folder. Name it chunk0_unpacked.
Second, double click quickbms.exe and select bms script.
Third, select both chunk0.index, chunk0.resources files.
Fourth, unpack it in the chunk0_unpacked folder.

When you unpack the .resource file, be sure to use option 'r' in order to rename duplicated files.

Type 'r' and enter.
After unpack and when you edit it, you should edit both english.lang and english_00000001.lang.


<Reimport>
To put it back, try to use reimport.bat. You can find it quickbms folder.

First, select bms script.
Second, select Original file. For example, chunk0.resources.
Third, select unpacked folder. For example, chunk0_unpacked.
Fourth, copy chunk0.resources and paste it to Wolfenstein The New Order\base folder.

<result>
## Post #8
- Username: Lib87
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Mar 22, 2013 2:44 am
- Post datetime: 2014-05-24T13:58:32+00:00
- Post Title: Wolfenstein: The New Order (PC)

> Reply from albert1905
>
> folkemon1977 wrote:albert1905: Many thanks.... please, what program are using for open font files?

And is there some way how put edited files back to .resource file?

I used Photoshop CS5. Open it as raw file.


<Unpack>

First, make a new foleder in quickbms folder. Name it chunk0_unpacked.
Second, double click quickbms.exe and select bms script.
Third, select both chunk0.index, chunk0.resources files.
Fourth, unpack it in the chunk0_unpacked folder.

When you unpack the .resource file, be sure to use option 'r' in order to rename duplicated files.

Type 'r' and enter.
After unpack and when you edit it, you should edit both english.lang and english_00000001.lang.


<Reimport>
To put it back, try to use reimport.bat. You can find it quickbms folder.

First, select bms script.
Second, select Original file. For example, chunk0.resources.
Third, select unpacked folder. For example, chunk0_unpacked.
Fourth, copy chunk0.resources and paste it to Wolfenstein The New Order\base folder.

<result>


reimport problem  

First, select bms script.
Second, select Original file. For example, chunk0.resources.
Third, select unpacked folder. For example, chunk0_unpacked.
Fourth, copy chunk0.resources and paste it to Wolfenstein The New Order\base folder.


reimport.bat open..

select chunk0.resources

select chunk0_unpacked..  but not selected.. folder opens?

Where is the error I'm doing?

sorry for my bad english

ich bin deutsche
## Post #9
- Username: folkemon1977
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Aug 19, 2013 3:57 pm
- Post datetime: 2014-05-24T15:28:58+00:00
- Post Title: Wolfenstein: The New Order (PC)

Lib87:

First, select bms script - use same script as for unpack

Second, select Original file - find this original file: chunk0.resources.

Third, select unpacked folder - go into the folder with this name = chunk0_unpacked a click on path in window (see screen) and click on button below. In this folder you must have only folder strings and inside file english.lang (nothing more).


You must received following message from BMS:



But there is a problem. Your translated file must be same or smaller as original file recources.

Hope it helps.
## Post #10
- Username: Lib87
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Mar 22, 2013 2:44 am
- Post datetime: 2014-05-24T17:15:22+00:00
- Post Title: Wolfenstein: The New Order (PC)

> Reply from folkemon1977
>
> Lib87:

First, select bms script - use same script as for unpack

Second, select Original file - find this original file: chunk0.resources.

Third, select unpacked folder - go into the folder with this name = chunk0_unpacked a click on path in window (see screen) and click on button below. In this folder you must have only folder strings and inside file english.lang (nothing more).


You must received following message from BMS:



But there is a problem. Your translated file must be same or smaller as original file recources.

Hope it helps.

Vielen dank! It's working... Thank you very much indeed!

Und for pm It is very kind of you..
## Post #11
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2014-05-24T19:00:14+00:00
- Post Title: Wolfenstein: The New Order (PC)

Thanks for useful infos but how about this file?
\fonts\arial_black\64_df.dat.

Second thing is that texts can be imported manually in HEX editor, texts in chunk0.resources aren't compressed.
## Post #12
- Username: nurullah390
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 27, 2014 2:23 am
- Post datetime: 2014-05-24T21:51:16+00:00
- Post Title: Wolfenstein: The New Order (PC)

thanks for code
## Post #13
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-05-24T22:12:02+00:00
- Post Title: Wolfenstein: The New Order (PC)

> Reply from GRiNDERKILLER
>
> Thanks for useful infos but how about this file?
\fonts\arial_black\64_df.dat.

I don't fully research format, need test, but i don't have game. This is what i know about it:
0x0A - 2 bytes in BE number of glyphs
from offset 0x0C start description of each glyph on font textures, each glyph described by 12 bytes


1 byte - width
1 byte - height
4 bytes - unknown(need test, maybe yadvance, yoffset, xadvance, xoffset)
2 bytes - x (little endian)
2 bytes - y (little endian)
2 bytes - unknown

After glyph table, going symbols id 4 bytes for each, and then kerning pairs, i think.
## Post #14
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2014-05-24T22:34:02+00:00
- Post Title: Wolfenstein: The New Order (PC)

Thanks Thief1987 for your quick research. Just keep going in peace.
## Post #15
- Username: BioLife
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-05-24T22:48:42+00:00
- Post Title: Wolfenstein: The New Order (PC)

Here is complete template for index file :

```
//--- 010 Editor v4.0.3 Binary Template
//
// File:
// Author: michalss
// Revision:
// Purpose:
//--------------------------------------
BigEndian();

local int i,charC,isIt;
local string text;
local int offsetF,sizeC,sizeU,zaloha;

FSeek(36);
int files;

for (i=0;i<files;i++) {
    LittleEndian();
  
         struct Files {
           struct FileNames { 
            int FileNum; '<hidden=true>';
            int charCount;
            char textentry0[charCount];
            int charCount1;
            char textentry1[charCount1];
            text=textentry1;
            int charCount2;
            if (charCount2!=0) char textdata1[charCount2];

            BigEndian();

            int offset;
            offsetF=offset;
            int fsize;
            sizeU=fsize;
            int csize;
            sizeC=csize;
            int extra; //some junk
            byte unkJunk[5];
            
           if (extra!=0)  char dummms[extra*24];
    
          } FILENAMES;
 
        } FILES;

}

```


With this you can simple found out data like offset of lang or fonts, if reimport failed for qbms, you can replace any other lang file with bigger size and simple change offset/size or add to end of the archive  Simple as that and no repack is needed...
## Post #16
- Username: BioLife
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Oct 24, 2012 2:54 am
- Post datetime: 2014-05-24T23:05:19+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from michalss
>
> Here is complete template for index file :


With this you can simple found out data like offset of lang or fonts, if reimport failed for qbms, you can replace any other lang file with bigger size and simple change offset/size or add to end of the archive  Simple as that and no repack is needed...

Hello,

Can you write a little "how to" to do that?

Thank you


EDIT: OK, I did it. I was able to change the language of the text with this method. I'm gonna to write a "how to" to do that, allow me few hours..
## Post #17
- Username: BioLife
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Oct 24, 2012 2:54 am
- Post datetime: 2014-05-25T00:25:16+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

How to change language text

In this HOWTO we'll change all texts from english to french (for example).

Requirements

QuickBMS
010 Editor v4.0.3
Unpack, change language, resize index and reimport

Unpack and change language

Download and extract the little attached package
Copy chunk0.index and chunk0.resources from your Wolfenstein/base install directory to orig directory
Open QuickBMS
Select the script __extract_resources.bms
Select orig/chunk0.resources
Select chunk0_unpacked directory
Wait a moment during extract and reply r when prompted
After all has been extracted, delete all but strings directory
In the strings directory: delete all but french.lang
Rename french.lang to english.lang
Resize index

Do a copy of chunk0.index and chunk0.resources to a modded directory for example
Open 010 Editor Hex
Open file binary_template.bt
Open file modded/chunk0.index
Right under the oppened tab file chunk0.index: click on Run Template and select binary_template.bt in Open Templates
A new tab open right under the tab of chunk0.index: this is a list of all indexed files in chunk0.resources
In here, press CTRL+F to start a search
Select value, type french.lang and press Enter
Once search result appeared, you'll find a lot of data.. just look at fsize and csize datas
Copy value of this data (928775 in my case)
Then do a search again and type english.lang
Again, in the search results, look at fsize and csize datas (868082 in my case)
Now just paste previously copied value on these two data fsize and csize
Finally, save and exit 010 Editor
Reimport

Now launch the reimport.bat from QuickBMS
Select the script __extract_resources.bms again
Select modded/chunk0.resources
Select chunk0_unpacked directory
Reimport shouldn't ask you to force reimport, if so, you may have do wrong a step...
And voilà

Copy/paste the new modded chunk0.index and chunk0.resources to your Wolfenstein install directory and let's kick some a** !!


Thanks

Thief1987: for his BMS script
albert1905: for his howto
 michalss: for his binary template script
[Wolfeinstein.rar](https://xentaxbackup.github.io/file/7372_Wolfeinstein.rar)
## Post #18
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-05-25T07:50:17+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

Here is better template with english and russian lang + binary...  You can apply this on index and also on archive 

If you need more offsets or languages data, let me know ill add them or i can write extractor and importer for language(no size limit) for X360 resources ONLY!!!!

```
//--- 010 Editor v5.0 Binary Template
//
// File:
// Author: michalss
// Revision:
// Purpose:
//--------------------------------------
BigEndian();


uint64 GUID;

if (GUID==239611423670403072) { //This is index
//LittleEndian();
FSeek(1228838832);
byte English[867085];
byte spolitter1[1];

FSeek(1232395040);
byte Russian[1178381];
byte spolitter2[1];

}else if (GUID==239611423685125549) { //this is data

struct ENGLISH {
LittleEndian();
FSeek(14692911);
uint textS;
BigEndian();
char russian[textS];
uint offset;
uint fsize;
uint csize;
}Lang;


struct RUSSIAN {
LittleEndian();
FSeek(14693231);
uint textS;
BigEndian();
char russian[textS];
uint offset;
uint fsize;
uint csize;
}Lang;



}
```
## Post #19
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-27T02:10:29+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

However, there are dubed movies on the game with no subtitles. How to solve this problems for those who want to insert a subtitles..?
## Post #20
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-05-27T04:54:53+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from albert1905
>
> However, there are dubed movies on the game with no subtitles. How to solve this problems for those who want to insert a subtitles..?

Not sure what is the format, but most likely BIK, you have to convert the into AVI or MPEG then make subtitles and then encode them together, last part is back to BIK. There is very long process behind it, dont really have time to explain into details, so from me it is just a hint.

Tools :
RAD Tools - [http://www.radgametools.com/bnkdown.htm](http://www.radgametools.com/bnkdown.htm)
Video Encoder (tEncoder, visrtualDub,etc... many of them) - [http://www.wikihow.com/Add-Subtitles-to ... aded-Video](http://www.wikihow.com/Add-Subtitles-to-a-Downloaded-Video)
SubtitleWorkshop - to make subtitle and timing

Hope it helps
## Post #21
- Username: HAIDER6222354
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Jul 04, 2012 12:19 pm
- Post datetime: 2014-05-27T06:21:09+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

can anyone help me with edit font in game ?
## Post #22
- Username: albert1905
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-05-27T07:15:41+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from HAIDER6222354
>
> can anyone help me with edit font in game ?

Font is RAW format, editable in PS, dat files is indexes for chars.
## Post #23
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-27T07:24:41+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from michalss
>
> albert1905 wrote:However, there are dubed movies on the game with no subtitles. How to solve this problems for those who want to insert a subtitles..?

Not sure what is the format, but most likely BIK, you have to convert the into AVI or MPEG then make subtitles and then encode them together, last part is back to BIK. There is very long process behind it, dont really have time to explain into details, so from me it is just a hint.

Tools :
RAD Tools - http://www.radgametools.com/bnkdown.htm
Video Encoder (tEncoder, visrtualDub,etc... many of them) - http://www.wikihow.com/Add-Subtitles-to ... aded-Video
SubtitleWorkshop - to make subtitle and timing

Hope it helps

I'll try it. Thanks for your advice.
## Post #24
- Username: HAIDER6222354
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Jul 04, 2012 12:19 pm
- Post datetime: 2014-05-27T07:31:35+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from michalss
>
> HAIDER6222354 wrote:can anyone help me with edit font in game ?

Font is RAW format, editable in PS, dat files is indexes for chars.

thanks , but how i can edit dat file i am not good with hex
## Post #25
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-05-27T08:10:55+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from HAIDER6222354
>
> michalss wrote:HAIDER6222354 wrote:can anyone help me with edit font in game ?

Font is RAW format, editable in PS, dat files is indexes for chars.

thanks , but how i can edit dat file i am not good with hex

 2 options you have, no need to edit dat file, but you need to replace chars you dont need on font texture or ask someone to make binary template to 010. I never done research on this so i cannot help. if there is struct know i can do it but no time to make full research unfortunately.
## Post #26
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-28T15:45:51+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

The *.bink file only contains movie and background sounds. There are no voice files.
However, *.stream files contained a voice package, and it can be unpacked by RavioliGameTools.

[http://www.scampers.org/steve/sms/other ... i_download](http://www.scampers.org/steve/sms/other.htm#ravioli_download)

But there are some problems bacause there are no file names in *.strream, so it is hard to match the bink file and audio files.
[K-42.png](https://xentaxbackup.github.io/file/7392_K-42.png)
## Post #27
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-05-29T03:00:05+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

Same for the Streamed.resource bank. They have no index files, so therefore cant be unpacked. Is there ayway to take the harted names from the other index files and extract them with the streamed.resource file?
## Post #28
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-31T13:15:29+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from OrangeC
>
> Same for the Streamed.resource bank. They have no index files, so therefore cant be unpacked. Is there ayway to take the harted names from the other index files and extract them with the streamed.resource file?

Uhm.. I had no idea.
## Post #29
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-31T13:57:46+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

I'd success on changing the offset and the size of English.lang file to Russian.lang size but when I tried to edit English font size to that of Japanese doesn't work. What's wrong with me?

<English font information>

struct Files FILES[9459]
generated/textures/borderclamp_alpha_fonts/arial_black/64_df.bimage
offset 17490960
fsize 1179720
csize 321095

struct Files FILES[9460]
1924ABh generated/decls/material/fonts/arial_black/64_df.tga.decl
offset 17812064
fsize 617
csize 248

struct Files FILES[9461]
fonts/arial_black/64_df.dat
offset 17812320
fsize 6926
csize 3579


<Japanese font information>

struct Files FILES[9474]
generated/textures/borderclamp_alpha_fonts/japanese/futura_com_medium_jpn90/64_df.bimage
offset 19152096
fsize 12845128
csize 4043329

struct Files FILES[9475]
generated/decls/material/fonts/japanese/futura_com_medium_jpn90/64_df.tga.decl
offset 23195440
fsize 638
csize 265

struct Files FILES[9476]
fonts/japanese/futura_com_medium_jpn90/64_df.dat
offset 23195712
fsize 49918
csize 23140
## Post #30
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-06-01T12:50:47+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

Hmm.. I've tried every method that I could but it didn't work, so I decided to use CHS version for my translation patch.
I hope there are 010 templates for font files but well.. it seems difficult to handle it for me, anyway I just look forward to deal with it..
## Post #31
- Username: Killermannvs
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 07, 2013 4:57 am
- Post datetime: 2014-07-06T15:42:53+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

I think the big deal is in compression method...

A lot of files is compressed and if you try to reimport them it will fail coz the game uses some modified zlib compression.

If someone know how to get exactly the same result of compressed file as is used in the game, it will be very usefull.
Maybe we dont need to compress edited files at all, but than u need to change offsets (I didnt try this method yet).

BTW Im working on resources and index file editor...
[res edit.png](https://xentaxbackup.github.io/file/7552_res edit.png)
## Post #32
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-07-07T12:24:23+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from Killermannvs
>
> I think the big deal is in compression method...

A lot of files is compressed and if you try to reimport them it will fail coz the game uses some modified zlib compression.

If someone know how to get exactly the same result of compressed file as is used in the game, it will be very usefull.
Maybe we dont need to compress edited files at all, but than u need to change offsets (I didnt try this method yet).

BTW Im working on resources and index file editor...
Wow nice! So with this it will be easier to export and modify the fonts too?
## Post #33
- Username: Killermannvs
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 07, 2013 4:57 am
- Post datetime: 2014-07-09T09:21:09+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

Well, after some playing with zlib library I can finally to decompress all files correctly.

Now, I need to try if replaced file has to be compressed as well as original file.

After this test I will be able to release first usable version of my app.
## Post #34
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-07-09T14:58:49+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from Killermannvs
>
> Well, after some playing with zlib library I can finally to decompress all files correctly.

Now, I need to try if replaced file has to be compressed as well as original file.

After this test I will be able to release first usable version of my app.

Would this support also Big Endian pls?
## Post #35
- Username: Killermannvs
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 07, 2013 4:57 am
- Post datetime: 2014-07-10T18:06:34+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

Well guys here it is...

I have successfuly tested all fonts and english.lang file and it works great.

Quick overview:
"Load file" - accepts resources or index file, you need both of them
"Export all" - exports all files into selected folder
"Export" - exports selected file into selected folder
"Import" - imports selected file back to .resources file and re-index .index file (this function will use a lot of memory, expect this)

You need to have .Net Framework 4.0 installed.

I hope that will help you guys and looking forward for your feedback.


If some will successfuly edit and than import font file and the game will work, let me know pls!
[Release.zip](https://xentaxbackup.github.io/file/7564_Release.zip)
## Post #36
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-07-10T18:36:07+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from Killermannvs
>
> Well guys here it is...

I have successfuly tested all fonts and english.lang file and it works great.

Quick overview:
"Load file" - accepts resources or index file, you need both of them
"Export all" - exports all files into selected folder
"Export" - exports selected file into selected folder
"Import" - imports selected file back to .resources file and re-index .index file (this function will use a lot of memory, expect this)

You need to have .Net Framework 4.0 installed.

I hope that will help you guys and looking forward for your feedback.


If some will successfuly edit and than import font file and the game will work, let me know pls!

Did you also test it with different sizes i mean bigger then original ?
## Post #37
- Username: folkemon1977
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Aug 19, 2013 3:57 pm
- Post datetime: 2014-07-11T18:21:47+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

Hi there,
your tool works great. Tested for translation menu.
Great work!!

But how edit .bimage fonts? Many characters of my native language are missing  Some help??

Is there somebody, who has german.lang file? German version o Wolf isn´t avaiable in my country...

Regards



> Reply from Killermannvs
>
> Well guys here it is...

I have successfuly tested all fonts and english.lang file and it works great.

Quick overview:
"Load file" - accepts resources or index file, you need both of them
"Export all" - exports all files into selected folder
"Export" - exports selected file into selected folder
"Import" - imports selected file back to .resources file and re-index .index file (this function will use a lot of memory, expect this)

You need to have .Net Framework 4.0 installed.

I hope that will help you guys and looking forward for your feedback.


If some will successfuly edit and than import font file and the game will work, let me know pls!
## Post #38
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-07-12T11:40:16+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

In my opinion, it seems that 64_df.dat file is a dummy file and I can not change font mapping information.
Although I tried to change 64_df.dat file to another lang 64_df.dat file, it didn't change anything on the game when I used quickbms reimport option.
Is it working on that tool? Hmm.. I didn't tried it but I guess that it will not work. I mean, no change.
## Post #39
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-07-12T14:10:12+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from albert1905
>
> In my opinion, it seems that 64_df.dat file is a dummy file and I can not change font mapping information.
Although I tried to change 64_df.dat file to another lang 64_df.dat file, it didn't change anything on the game when I used quickbms reimport option.
Is it working on that tool? Hmm.. I didn't tried it but I guess that it will not work. I mean, no change.
Search is your friend: [viewtopic.php?f=10&t=11556&p=96257](http://forum.xentax.com/viewtopic.php?f=10&t=11556&p=96257)
## Post #40
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-07-12T21:16:39+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from lostprophet
>
> albert1905 wrote:In my opinion, it seems that 64_df.dat file is a dummy file and I can not change font mapping information.
Although I tried to change 64_df.dat file to another lang 64_df.dat file, it didn't change anything on the game when I used quickbms reimport option.
Is it working on that tool? Hmm.. I didn't tried it but I guess that it will not work. I mean, no change.
Search is your friend: viewtopic.php?f=10&t=11556&p=96257

You misunderstand what I said. I mean, font mapping file. Not bimage. And that thread was what I asked so I knew it.
## Post #41
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-07-13T07:19:17+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from albert1905
>
> lostprophet wrote:albert1905 wrote:In my opinion, it seems that 64_df.dat file is a dummy file and I can not change font mapping information.
Although I tried to change 64_df.dat file to another lang 64_df.dat file, it didn't change anything on the game when I used quickbms reimport option.
Is it working on that tool? Hmm.. I didn't tried it but I guess that it will not work. I mean, no change.
Search is your friend: viewtopic.php?f=10&t=11556&p=96257

You misunderstand what I said. I mean, font mapping file. Not bimage. And that thread was what I asked so I knew it.

I have never check font mapping, but im planning to i guess  not sure when
## Post #42
- Username: Killermannvs
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 07, 2013 4:57 am
- Post datetime: 2014-07-13T11:03:29+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

I hate that ads!!!








I did a little research on font mapping file "64_df.dat" and I got this.

I can partialy confirm this:

> Reply from Thief1987
>
> 
1 byte - width
1 byte - height
4 bytes - unknown(need test, maybe yadvance, yoffset, xadvance, xoffset)
2 bytes - x (little endian)
2 bytes - y (little endian)
2 bytes - unknown

I have tested that 4 bytes and...
1. y axis (yadvance)
2. yoffset? (did nothing)
3. x axis (xadvance)
4. xoffset? (did nothing)

I still dont know what 2 last bytes do.

I have successfuly edited font 64_df.bimage file and my glyphs are shown in the game, but I had to replaced some original glyphs (I have choosen which ones are not used in english.lang file)
So if I want to use my glyph, I have to type original glyph and that is ugly.

I tried to replace original glyph with my glyph by unicode table, but it doesnt work.
The game shows only "*" (unknown character).

Do you have any idea how to make this work?

EDIT:
After more digging I have idea about header bytes.
Here is my struct description of 64_df.dat.

```
4B - 0x6964662B (idf+)
  font config
1B - size
1B - scale
1B - y shift
1B - y shift
1B - multi-line, CR size
1B - multi-line, CR size
2B - number of glyphs (big endian)
  glyph description
1B - width
1B - height
1B - y axis (yadvance)
1B - yoffset? (did nothing)
1B - x axis (xadvance)
1B - xoffset? (did nothing)
2B - x (little endian)
2B - y (little endian)
2B - unknown
  glyph character (unicode)
4B - char (little endian)
  kerning pairs?
2B - number of pairs (big endian)
xB - pair struct?
```
## Post #43
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-15T18:40:57+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from Killermannvs
>
> Well guys here it is...

I have successfuly tested all fonts and english.lang file and it works great.

Quick overview:
"Load file" - accepts resources or index file, you need both of them
"Export all" - exports all files into selected folder
"Export" - exports selected file into selected folder
"Import" - imports selected file back to .resources file and re-index .index file (this function will use a lot of memory, expect this)

You need to have .Net Framework 4.0 installed.

I hope that will help you guys and looking forward for your feedback.


If some will successfuly edit and than import font file and the game will work, let me know pls!

I notice some filenames in the list are black, and some are red. what do the colors mean?
## Post #44
- Username: Killermannvs
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 07, 2013 4:57 am
- Post datetime: 2014-07-17T16:53:38+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from volfin
>
> Killermannvs wrote:Well guys here it is...

I have successfuly tested all fonts and english.lang file and it works great.

Quick overview:
"Load file" - accepts resources or index file, you need both of them
"Export all" - exports all files into selected folder
"Export" - exports selected file into selected folder
"Import" - imports selected file back to .resources file and re-index .index file (this function will use a lot of memory, expect this)

You need to have .Net Framework 4.0 installed.

I hope that will help you guys and looking forward for your feedback.


If some will successfuly edit and than import font file and the game will work, let me know pls!

I notice some filenames in the list are black, and some are red. what do the colors mean?

Red are compressed files, if you look at size and zsize is always different.
## Post #45
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-07-19T17:07:46+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

I'd tried to edit font mapping file and successfully reimported it but there are no change.
Below the image is chinese version. I mean, I can't change the position of glyphs. Was 64_df.dat  really font mapping file..?
It doesn't read on game! Even if I make it blank file and reimported it, there are no changes!
[WolfNewOrder_x64_2014-06-01_22-27-06-521.jpg](https://xentaxbackup.github.io/file/7589_WolfNewOrder_x64_2014-06-01_22-27-06-521.jpg)
## Post #46
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-07-21T09:28:30+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

Does anyone know where is the japanse script file..?
## Post #47
- Username: Killermannvs
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Nov 07, 2013 4:57 am
- Post datetime: 2014-07-22T21:15:56+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from albert1905
>
> I'd tried to edit font mapping file and successfully reimported it but there are no change.
Below the image is chinese version. I mean, I can't change the position of glyphs. Was 64_df.dat  really font mapping file..?
It doesn't read on game! Even if I make it blank file and reimported it, there are no changes!

Which file do you edit? 
Because I edited this one "\base\fonts\futura_com_medium\64_df.dat" and the game reflects changes in the file.

I guess you have to check which one (64_df.dat) is really used.
## Post #48
- Username: folkemon1977
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Aug 19, 2013 3:57 pm
- Post datetime: 2014-10-12T11:49:50+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

Hi everybody,
i already translated this game to my language (czech), all works (including changed fonts).
Gallery:
[http://www.folkemon.ic.cz/wolfensteinNO/index.html](http://www.folkemon.ic.cz/wolfensteinNO/index.html)

So, if someone needs help with translation this game, i´m more than happy to help.
## Post #49
- Username: Kernaul
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 13, 2014 12:31 am
- Post datetime: 2014-11-12T16:46:54+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

Hi, is it possible to change the texture after extracting this files?
## Post #50
- Username: folkemon1977
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Aug 19, 2013 3:57 pm
- Post datetime: 2014-11-12T17:52:51+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

Hi, i edited fonts files only.
## Post #51
- Username: maitrepoul
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 25, 2015 3:20 am
- Post datetime: 2015-06-25T23:08:00+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

Omfg ! Nice ! Thank you very much guys. I could change my subtitle language 
Quite long though
## Post #52
- Username: T0T0
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 20, 2015 10:14 pm
- Post datetime: 2015-07-24T09:01:19+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

Hi !

Many thanks for the work and sharing on this forum !

I'm trying to change the text language and I have an issue with binary_template.bt: when I try to use it with 010 Editor (V 6.02) on chunk0.index, I get an error on line 23:

> ERROR Line 23: Invalid character constant. May be multi-byte character.

Line 23 is:  
```
int FileNum; '<hidden=true>';
```
 and '<hidden=true>' is highlighted in red. 
Any advice please ?

Edit: finally managed to do it, by deleting the faulty code. 

Thanks to BioLife for his detailed "How to" !
## Post #53
- Username: fabiojuniorkm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 24, 2016 1:00 pm
- Post datetime: 2016-04-25T19:35:57+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from folkemon1977
>
> Hi everybody,
i already translated this game to my language (czech), all works (including changed fonts).
Gallery:
http://www.folkemon.ic.cz/wolfensteinNO/index.html

So, if someone needs help with translation this game, i´m more than happy to help.

You can help me translate for Xbox 360 ?
## Post #54
- Username: folkemon1977
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Aug 19, 2013 3:57 pm
- Post datetime: 2016-05-15T20:33:24+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

> Reply from fabiojuniorkm
>
> folkemon1977 wrote:Hi everybody,
i already translated this game to my language (czech), all works (including changed fonts).
Gallery:
http://www.folkemon.ic.cz/wolfensteinNO/index.html

So, if someone needs help with translation this game, i´m more than happy to help.

You can help me translate for Xbox 360 ?

Sorry, but my translation was only for PC.
## Post #55
- Username: stapheen
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 11, 2014 10:24 pm
- Post datetime: 2016-05-24T10:31:09+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

is there an easy way to edit font ?
## Post #56
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-05-26T10:17:12+00:00
- Post Title: Re: Wolfenstein: The New Order (PC)

In which language?
