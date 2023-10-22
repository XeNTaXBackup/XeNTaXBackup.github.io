## Post #1
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-12-20T14:51:26+00:00
- Post Title: [PSX] Silent Hill

Hi! I want to extract and import content of the archives from this game.

There are four files in game image:

HILL (499 MB)
SILENT (92 MB)
SLES_015.14 (82 KB)
SYSTEM.CNF (4 KB)



I upload as an attachment samples from archives SILENT and HILL. Could someone help me and write for me quick bms script or something like that?
[SILENT HILL.zip](https://xentaxbackup.github.io/file/6092_SILENT HILL.zip)
## Post #2
- Username: MiLØ
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-12-22T10:49:05+00:00
- Post Title: [PSX] Silent Hill

Thanks to Horror from consolgames.ru we have now a nice tool pack for Silent Hill. He is our Saviour. 

[DOWNLOAD SILENT HILL TOOL PACK](http://ikskoks.playloc.pl/PROGRAMY/silent_hill.zip) 
(SHFilesExtractor, SHDcdr, DListEditor, FontEditor, SOURCE FILES)



The most important utility is Files Extractor. It can extract all files from SILENT archive.
Usage is quite simple. We  have to type command like that:

C:\Users\ikskoks>"C:\Users\ikskoks\Desktop\SILENT HILL\SHFilesExtractor.exe" "C:\Users\ikskoks\Desktop\SILENT HILL\SLES_015.14" "C:\Users\ikskoks\Desktop\SILENT HILL\SILENT" C:\Users\ikskoks\Desktop\SILENT HILL

SHFilesExtractor.exe - name of the tool
SLES_015.14 - file from game image. It is from PAL version, but i think NTSC U can work too.
SILENT - file to extract
C:\Users\ikskoks\Desktop\SILENT HILL - output directory


There are also others tools (Font Editor, DList Editor, SHDcdr) but i'm not sure how to use them. ;/

And now i ask you for help. Tool pack also contains source files, so extraction method is known. Can someone write a tool or script to REIMPORT edited files back to the SILENT file? Or just improve Silent Hill Files Extractor with new reimport option?

Horror told me that SHDcdr is a tool which we can encrypt/decrypt main executable (1ST/BODYPROG.BIN). Does anybody know how can i do that?

One more thing. Me and my friend are trying to translate this game, but we have technical problems with finding and edit main menu and inventory in this game. If you have some useful informations about editing this stuff, we will be grateful for sharing your knowledge. ;p
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-12-23T16:29:13+00:00
- Post Title: [PSX] Silent Hill

Ok, I figured out how to use Silent Hill Data Decryptor/Encryptor



We just have to type simple command. Example:
C:\Users\ikskoks>"C:\Users\ikskoks\Desktop\SILENT HILL\SHDcdr.exe" C:\Users\ikskoks\Desktop\SILENT\1ST\BODYPROG.BIN

SHDcdr.exe - name of the tool
BODYPROG.BIN - file from extracted SILENT archive with all texts from game

We can see the difference:


To save the changes in game we must paste encrypted file BODYPROG.BIN manually in hex editor.
(unless someone will create working importer ^^)

With this tool we can edit main menu and inventory what wasn't earlier possible.
Now anyone can make full translation of this game to any language.
## Post #4
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-12-24T09:04:55+00:00
- Post Title: [PSX] Silent Hill

Great stuff, I haven't seen Silent Hill files being hacked before. Thank you for sharing and Horror for making the tools. 
Though it looks like this utilities can not extract the HILL archive, can they? I was hoping to get music and videos from it with proper files names.
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-12-24T09:53:21+00:00
- Post Title: [PSX] Silent Hill

> Though it looks like this utilities can not extract the HILL archive, can they?
Unfortunatelly, they can't ;/


But if you want to extract and import videos and music, you can try:
jPSXdec [http://www.romhacking.net/utilities/658/](http://www.romhacking.net/utilities/658/)
XA Audio Converter [http://www.romhacking.net/utilities/894/](http://www.romhacking.net/utilities/894/)

Both utilities can replace files in game ^^
## Post #6
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-12-24T11:55:28+00:00
- Post Title: [PSX] Silent Hill

Thank you, but I already knew about those tools. jPSXdec is essential and is the best thing out there for video/audio conversion.
After scanning the HILL archive with jPSXdec it found all videos and only 4 music tracks. No file names of course. Maybe the rest of the music is in some different format (something other than XA). It could be sequenced music + custom driver, I don't know for sure. Either way it would be easier to figure this out if all the contents were extracted. 

Do you happen to know if Horror tried working on extractor for HILL? Is that file's encryption more complex than SILENT's?
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-12-24T12:11:48+00:00
- Post Title: [PSX] Silent Hill

> Do you happen to know if Horror tried working on extractor for HILL? Is that file's encryption more complex than SILENT's?
Horror told me that creating extractor for HILL is kind a hard. The HILL file contains XA and STR media, so probably it uses sector numbers instead of files.
## Post #8
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-12-25T21:03:00+00:00
- Post Title: [PSX] Silent Hill

I see. Well maybe someday. Thanks for the info.
