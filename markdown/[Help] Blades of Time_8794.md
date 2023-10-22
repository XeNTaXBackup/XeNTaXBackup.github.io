## Post #1
- Username: Maxunit
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 28, 2010 7:49 am
- Post datetime: 2012-04-19T17:40:21+00:00
- Post Title: [Help] Blades of Time

Heyo Xentax Community,

I bought Blades of Time today and played it a bit. Later on I found out, that it is from another Developer but seems to be using the same engine as X-Blades (slightly modified tho, I think).

Now I tried to unpack the file ayumi_base.grp with offzip using the following command:

offzip.exe -a ayumi_base.grp ayumi_base 0x0

It extracted 4 files, but all 4 are numeric named .dat files, where the largest is 0004e3f0.dat with 551 kilobytes. A complete list:

000487c4.dat - 12 kilobytes
000a2c39.dat - 37 kilobytes
000018e4.dat - 441 kilobytes
0004e3f0.dat - 551 kilobytes

ayumi_base.grp - 686 kilobytes

Maybe ayumi_base.grp only contains textures or the 3d model...

I know, that it is no longer allowed to upload copyrighted content to Xentax, therefor I ask, what I can do to supply information for the more experienced people here? I would like to extract more of the game, maybe even re-do some of the textures, because there a textures, which look like... 512x512, which is rather ugly.

EDIT:

I own the game, my email is [xxdarkslayerxx@hotmail.com](mailto:xxdarkslayerxx@hotmail.com). You can either send me a PM or E-Mail me.
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-19T23:39:02+00:00
- Post Title: [Help] Blades of Time

I have the game. I was going to look at it but haven't had the chance. I haven't extracted it yet so if you want you can contact me for help. That's all offzip extracted?
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-20T05:59:11+00:00
- Post Title: [Help] Blades of Time

Please take a look at the discussion here: [viewtopic.php?f=28&t=8760&p=71355#p71355](http://forum.xentax.com/viewtopic.php?f=28&t=8760&p=71355#p71355)

The only condoned way of talking about getting into touch to discuss samples is this one as stated by Craptain:

> ""I own the game, my email is n00b@blah.com". Wait for PM or email.

I edited your original message to reflect this conduct.
## Post #4
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2012-05-01T20:00:33+00:00
- Post Title: [Help] Blades of Time

Any news on how to extract the text?
## Post #5
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-05-05T12:15:43+00:00
- Post Title: [Help] Blades of Time

X-Blades aka Oniblade, the prequel, had supposedly all texts stored in zlib-compressed ob.vromfs.bin. Blades of Time is based on the same engine, so I suppose that the file bot.vromfs.bin is responsible for all the text. It is in the main game folder.

It's a main component of the game so I reckon it IS included in the demo, but whomever wants to work on the latest version from the fill game, may PM me for the file. It's small, little more than 2 MB in size.

For some localizations, fonts must be edited. These are in ui subfolder and also have the bin extension.

I'd be happy if anyone could look into editing either. Please advise.
## Post #6
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-05-05T13:52:39+00:00
- Post Title: [Help] Blades of Time

Up!
## Post #7
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-05-06T18:05:56+00:00
- Post Title: [Help] Blades of Time

There is a method to edit the language files

Use Offzip to decompress the bot.vromfs.bin file.
offzip.exe bot.vromfs.bin bot.vromfs.bin.dec 0x10

Unpack the decompressed file with this script(bot.vromfs.bin.dec).

```
get BASE_OFF long
get FILES long
for i = 0 < FILES
get NAMEOFF long
savepos OFF
goto NAMEOFF
get NAME string
goto BASE_OFF
get OFFSET long
get SIZE long
savepos BASE_OFF
log NAME OFFSET SIZE
goto OFF
next i
```

Keep the language files and delete the others.
Edit the text, but the file size must be equal or less, so i suggest to delete some lines from other langs.
Use quickbms to reimport the edited files to bot.vromfs.bin.dec
Compress the .dec file with zlibc.
zlibc.exe -k bot.vromfs.bin.dec bot.vromfs.bin.cmp

Check the .cmp file size and convert it to hexadecimal. eg use this site
1970886 --> 1E12C6

Open the .cmp and the original .bin with hex editor.
Copy the first 16 bytes from the original file, and paste it at the beginning of the .cmp file.
Edit the compressed size 0xC position, watch the endianess.


Copy .cmp file to gamedir and rename to orig, backup original file.


You can try it if want
[http://i48.tinypic.com/2m6shlt.jpg](http://i48.tinypic.com/2m6shlt.jpg)
## Post #8
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-05-06T19:59:53+00:00
- Post Title: [Help] Blades of Time

swuforce, could you look into the fonts as well? Thank you very much in advance.
## Post #9
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-05-06T23:05:47+00:00
- Post Title: [Help] Blades of Time

> Reply from Delacroix
>
> swuforce, could you look into the fonts as well? Thank you very much in advance.
My guess would be, that the fonts are in the ui directory in BIN format, but it's not the same BIN format as bot.vromfs.bin.
## Post #10
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2012-05-07T15:02:08+00:00
- Post Title: [Help] Blades of Time

could better explain how to use the Offzip?
## Post #11
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-05-07T15:47:13+00:00
- Post Title: [Help] Blades of Time

> Reply from JonhOliver
>
> could better explain how to use the Offzip?
1. Open up the commandline (Start menu > Run > type "cmd" (without quotes) > press ENTER

2. Copy the offzip.exe to the same directory as the bot.vromfs.bin file.

3. In command line, go to the same directory, for eg. if the bin file is in C:\new, then type "cd C:\new" (without quotes)

4. Then run offzip.exe, by typing "offzip.exe bot.vromfs.bin bot.vromfs.bin.dec 0x10" (without quotes)

BTW, the translation works perfectly, if it's done as swuforce wrote, but we have to wait until someone finds a way to edit the fonts (they are in the installation directory, in the ui directory)
## Post #12
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-05-07T18:24:42+00:00
- Post Title: [Help] Blades of Time

I think the font file supports many characters, so its not necessary to edit it. [http://oi45.tinypic.com/2nvquft.jpg](http://oi45.tinypic.com/2nvquft.jpg)

Btw i cant do anything with the fonts.
## Post #13
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-05-07T19:55:17+00:00
- Post Title: [Help] Blades of Time

swuforce, I am attempting translation of the game. I'm hoping it will succeed. Thank you for all your help so far.
## Post #14
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2012-05-07T20:24:10+00:00
- Post Title: [Help] Blades of Time

Thanks, could generate bot.vromfs.bin.dec. But did not understand what I do now, excuse my ignorance, I'm still learning.
## Post #15
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-05-08T01:51:15+00:00
- Post Title: [Help] Blades of Time

> Reply from JonhOliver
>
> Thanks, could generate bot.vromfs.bin.dec. But did not understand what I do now, excuse my ignorance, I'm still learning.
When you are online on MSN, I explain in detail the process.
## Post #16
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-05-08T07:45:38+00:00
- Post Title: Re: [Help] Blades of Time

> Reply from swuforce
>
> I think the font file supports many characters, so its not necessary to edit it. http://oi45.tinypic.com/2nvquft.jpg

Btw i cant do anything with the fonts.
It's a bit weird. Last time I got * characters where the áúó and other foreign characters should be.
Well, I'll try it again, when I get home.
## Post #17
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-05-08T07:50:30+00:00
- Post Title: Re: [Help] Blades of Time

swuforce, what did you use to edit the CSV's and how did you save them? I get a feeling it's all about the coding.
## Post #18
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-05-08T08:38:21+00:00
- Post Title: Re: [Help] Blades of Time

> Reply from Delacroix
>
> swuforce, what did you use to edit the CSV's and how did you save them? I get a feeling it's all about the coding.
I tried Office 2010, but maybe that's the problem. I never use it, but it's a bit nicer, than to look on endless lines. I'll try it with Notepad++.
## Post #19
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2012-05-08T22:00:29+00:00
- Post Title: Re: [Help] Blades of Time

> Reply from swuforce
>
> There is a method to edit the language files

Use Offzip to decompress the bot.vromfs.bin file.
offzip.exe bot.vromfs.bin bot.vromfs.bin.dec 0x10

Unpack the decompressed file with this script(bot.vromfs.bin.dec).
Code: Select allgoto 0x8
get BASE_OFF long
get FILES long
for i = 0 < FILES
get NAMEOFF long
savepos OFF
goto NAMEOFF
get NAME string
goto BASE_OFF
get OFFSET long
get SIZE long
savepos BASE_OFF
log NAME OFFSET SIZE
goto OFF
next i
Keep the language files and delete the others.
Edit the text, but the file size must be equal or less, so i suggest to delete some lines from other langs.
Use quickbms to reimport the edited files to bot.vromfs.bin.dec
Compress the .dec file with zlibc.
zlibc.exe -k bot.vromfs.bin.dec bot.vromfs.bin.cmp

Check the .cmp file size and convert it to hexadecimal. eg use this site
1970886 --> 1E12C6

Open the .cmp and the original .bin with hex editor.
Copy the first 16 bytes from the original file, and paste it at the beginning of the .cmp file.
Edit the compressed size 0xC position, watch the endianess.


Copy .cmp file to gamedir and rename to orig, backup original file.


You can try it if want
http://i48.tinypic.com/2m6shlt.jpg

Script Dont work error 800A0400, help please!
## Post #20
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-05-09T07:31:21+00:00
- Post Title: Re: [Help] Blades of Time

> Reply from vitoci
>
> swuforce wrote:There is a method to edit the language files

Use Offzip to decompress the bot.vromfs.bin file.
offzip.exe bot.vromfs.bin bot.vromfs.bin.dec 0x10

Unpack the decompressed file with this script(bot.vromfs.bin.dec).
Code: Select allgoto 0x8
get BASE_OFF long
get FILES long
for i = 0 < FILES
get NAMEOFF long
savepos OFF
goto NAMEOFF
get NAME string
goto BASE_OFF
get OFFSET long
get SIZE long
savepos BASE_OFF
log NAME OFFSET SIZE
goto OFF
next i
Keep the language files and delete the others.
Edit the text, but the file size must be equal or less, so i suggest to delete some lines from other langs.
Use quickbms to reimport the edited files to bot.vromfs.bin.dec
Compress the .dec file with zlibc.
zlibc.exe -k bot.vromfs.bin.dec bot.vromfs.bin.cmp

Check the .cmp file size and convert it to hexadecimal. eg use this site
1970886 --> 1E12C6

Open the .cmp and the original .bin with hex editor.
Copy the first 16 bytes from the original file, and paste it at the beginning of the .cmp file.
Edit the compressed size 0xC position, watch the endianess.


Copy .cmp file to gamedir and rename to orig, backup original file.


You can try it if want
http://i48.tinypic.com/2m6shlt.jpg

Script Dont work error 800A0400, help please!
Script perfectly works for extract and repack too! Use the latest QuickBMS from aluigi!
## Post #21
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-05-09T17:22:03+00:00
- Post Title: Re: [Help] Blades of Time

> Reply from lostprophet
>
> Delacroix wrote:swuforce, what did you use to edit the CSV's and how did you save them? I get a feeling it's all about the coding.
I tried Office 2010, but maybe that's the problem. I never use it, but it's a bit nicer, than to look on endless lines. I'll try it with Notepad++.
Excel saves in ANSI format, original is UTF8, use only Notepad++ and the translation will work perfectly.
## Post #22
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-05-09T18:04:59+00:00
- Post Title: Re: [Help] Blades of Time

Thanks, I was afraid that other pieces of software will screw the thing up so I used Notepad++ for translating just in case. Good to know that I'm doing the right thing!
## Post #23
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2012-06-13T14:53:07+00:00
- Post Title: Re: [Help] Blades of Time

Could someone explain in detail how the translated files back to original format? I'm still learning.
## Post #24
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-06-13T22:15:18+00:00
- Post Title: Re: [Help] Blades of Time

> Reply from JonhOliver
>
> Could someone explain in detail how the translated files back to original format? I'm still learning.
Read swuforce's tutorial above.
## Post #25
- Username: akyryz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 28, 2010 10:18 am
- Post datetime: 2012-07-11T16:54:25+00:00
- Post Title: Re: [Help] Blades of Time

To help people:
1) download the programs: [offzip](http://aluigi.altervista.org/mytoolz.htm#offzip), [quickbms](http://aluigi.altervista.org/quickbms.htm), [zlibc](http://durchschuss.du.funpic.de/index.php?cat=progs&site=zlibc)

2) use the scripts in the ms-dos or make a bat file:
decompress:
offzip.exe bot.vromfs.bin bot.vromfs.bin.dec 0x10
unpack:
quickbms script.bms bot.vromfs.bin.dec bot.vromfs
pack:
quickbms -w -r script.bms bot.vromfs.bin.dec bot.vromfs
compress:
zlibc -k bot.vromfs.bin.dec bot.vromfs.bin.cmp

3) save the code below into a file called "script.bms" and put in the same folder of quickbms

```
get BASE_OFF long
get FILES long
for i = 0 < FILES
get NAMEOFF long
savepos OFF
goto NAMEOFF
get NAME string
goto BASE_OFF
get OFFSET long
get SIZE long
savepos BASE_OFF
log NAME OFFSET SIZE
goto OFF
next i
```

4) Use the attached file to make the header with command line:
header:
bot_header bot.vromfs.bin.cmp

Or with a hex editor you have to copy the signature of the binary file and the size back to bot.vromfs.bin.cmp:
a) save the file size of the bot.vromfs.bin.cmp in hex
b) opens the file bot.vromfs.bin and copy the first 16 bytes
c) insert these bytes in the file bot.vromfs.bin.cmp and override the size that you saved at position 0xC:
size of bot.vromfs.bin.cmp 1970886 -> in hex 1E12C6 -> write back C6121E00

5) rename bot.vromfs.bin.cmp -> bot.vromfs.bin and replace it in the game folder

Note: For bat file:
a_unpack.bat

```
quickbms script.bms bot.vromfs.bin.dec bot.vromfs

```

b_pack.bat

```
zlibc -k bot.vromfs.bin.dec bot.vromfs.bin.cmp
bot_header bot.vromfs.bin.cmp

```

[bot_header.rar](https://xentaxbackup.github.io/file/5569_bot_header.rar)
## Post #26
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-17T14:38:10+00:00
- Post Title: Re: [Help] Blades of Time

about audio is look fsb 4.0 i use fsbii for extract fsb from another fsb but towav not give result 
what's i missing
