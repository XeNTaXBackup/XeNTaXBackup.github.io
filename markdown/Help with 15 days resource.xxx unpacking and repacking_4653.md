## Post #1
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-06-24T13:09:54+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-24T18:50:58+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

I's possible, that the game uses the same method, just like the other games from that company.
(Mistery of the Druids, The Moment of Silence, Overclocked)
Here is a XeNTaXviki link: [http://wiki.xentax.com/index.php/The_Moment_Of_Silence](http://wiki.xentax.com/index.php/The_Moment_Of_Silence)
So, there must be a descriptor file, named RESOURCE.MAP
## Post #3
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-06-24T21:51:20+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

But no this kind of resource.map in game.
[15.JPG](https://xentaxbackup.github.io/file/3163_15.JPG)
## Post #4
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-26T22:21:21+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

I managed to create a simple unpacker. Works with resource.000 and resource.907. Tested with the german version of the game.
Important #1: The resoure.000 file also contains the file informations of these files:
resource.100; resource.101 and resource.200, so if  you want to unpack, you need more than 3,5 GigaBytes of free disk space.
Important #2: The resource.907 is a standalone archive, contains only its own information.
Important #3: There are no file extensions in the file information tables, so I gave the '.dat' extension to most of the files, except some '.wav'; '.dds' and '.tga' files.

Updated! Now I see, that you don't have the resource.907 file!!! You have resource.909!
Could you send me a little piece of that file? The important part is about the last 256 kilobyte of the file.
Here is a file cutter tool:[http://www.xentax.com/downloads/tools/filecutter.zip](http://www.xentax.com/downloads/tools/filecutter.zip)
## Post #5
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-06-27T00:17:40+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-27T05:50:18+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

No luck.
Could you give me one more information? What is the exact size (in bytes) of that resource.909 file?
## Post #7
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-06-27T08:31:57+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-27T13:27:40+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

O.K. I successfully updated the extractor!
Now it supports these languages: german (resource.907), english (resource.909) and french (resource.912).
(And of course also supports the general, resource.000 file.)
Little modification: The unknown extensions are marked with _01, _02 ... instead of .dat extension.

[The atteched file deleted. Please check my latest post for the most recent version.]
## Post #9
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-06-27T15:22:56+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

> Reply from bacter
>
> O.K. The extractor program now handles the resource.909 file too!
Little modification: The unknown extensions are marked with _01, _02 ... instead of .dat extension

Wow, thanks very much for your good work!
And can you post a file format of resource.000 and resource.90X here?
May be useful later.
## Post #10
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-27T18:00:09+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

Here is some pseudo-code of those files:

```
-> Seek to FILE_END - 4
-> Read: int32, this is the DATASTARTPOS
-> Seek to DATASTARTPOS
-> The DATA_size = RESOURCEFILE_SIZE - DATASTARTPOS - 4
-> Read the DATA (DATA_size)

-> Now we have the DATA, which is a zlib compressed block, with a little trick: it contains 4+4=8 plus bytes,
   in the middle of the DATA, so first we have to remove these bytes.
   So this is the structure of the DATA:
     First part: SOME_AMOUNT of bytes
     Number1 : 4 bytes
     Second part: SOME_AMOUNT of bytes
     Number2 : 4 bytes
     Last part : the rest of the bytes (DATA_size - 2 * SOME_AMOUNT - 8)
   The value of SOME_AMOUNT is: "resource.000" = 100 "resource.907" = 14
   (The formula for "resource.9XX" files: SOME_AMOUNT = XX * 2)
-> If we deleted the Number1 and Number2, we can decompress the ZLIB_compressed DATA
-> No we have the decompressed directory data, so let's go on.

-> the next step is only for the "resource.000":
   - There is an information table of the resource.xxx files:
      REPEAT
        Read RESOURCE_FILE_INFO: (112 bytes)
               ExtensionNumber : Int32 // 0=resource.000 100=resource.100 200=resource.200 201=resource.201
               UnknownNumber : Int32
               Dummy : Array[0..103] Of Byte // zero bytes
        IF (ExtensionNumber==0) AND (UnknownNumber==0) THEN THIS_IS_THE_END
      UNTIL THIS_IS_THE_END

-> now comes the information of the stored files:
      REPEAT
        Read EXT_id : Int32 // this means the extensions of the following files. 5=.tga 11=.wav 13=.dds and so on.
        Read NrOfFiles : Int32
        IF (EXT_id==0) AND (NrOfFiles==0) THEN THIS_IS_THE_END

        IF NOT THIS_IS_THE_END THEN:
            FOR 1 TO NrOfFiles
              Read FILE_INFO (76 bytes for each file)
                      FileName : Array[0..62] Of Char // with padding zero chars
                      FlagByte : Byte // this means the containing resource.XXX file -> see note #1
                      StartPos : Int32
                      OriginalSize : Int32
                      ZlibCompressedSize : Int32 // 0, if not compressed
        ENDIF
      UNTIL THIS_IS_THE_END
-> the next step is only for the "resource.907":
        Read RESOURCE_FILE_INFO: (112 bytes)
               ExtensionNumber : Int32 // 907=resource.907
               UnknownNumber : Int32
               Dummy : Array[0..103] Of Byte // zero bytes

-> the next step is only for the "resource.000":
   There are some unkown bytes at the end, maybe some useless, unimportant junk.

note #1:
The FlagByte: If we have the "resource.907" then this is 0, so no problem.
but if have the "resource.000" then this is 1,2,3 or 4, see the previously read RESOURCE_FILE_INFO blocks,
take the appropriate ExtensionNumber, and that means the correct resource.XXX file.
```
## Post #11
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-06-28T14:41:33+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

Very very thanks!
Can you figure out which file is the dialog subtitle file in these files?
## Post #12
- Username: emirdar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 14, 2010 6:20 am
- Post datetime: 2010-07-14T07:20:34+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

thank you
## Post #13
- Username: duktom
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 24, 2010 11:29 am
- Post datetime: 2010-07-24T17:00:17+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

thanks ....
## Post #14
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-09-07T09:44:05+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

Hi bacter, I need your help.

I have this game in two languages: English and spanish, but spanish language is blocked into resource.910 I guess.

Can you help me to get the spanish subtitles from .910? Your actually extractor works wonderful with all files less with 910 one, of course.

This is the head and tail of that file. If you need the full file tell me and I'll upload this one to megaupload or hotfile.

[resource.910](http://www.megaupload.com/?d=Q7CTL6J6)

Thanks a lot in advance.

Regards.
## Post #15
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-09-07T10:40:52+00:00
- Post Title: Help with 15 days resource.xxx unpacking and repacking

I updated my tool. Please check if it works.
Theoretically it has to work, but if not, then first I need one more information to test your file: the exact size of
the pak file, in bytes. (So I can make a fake file and try to load the file information table)
## Post #16
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-09-07T11:00:55+00:00
- Post Title: Re: Help with 15 days resource.xxx unpacking and repacking

It doesn't work bacter.   

Your new version give a "Range check error". Here is the information you need:

resource.910 - 102.400 Kbs (104.857.600 bytes)

I hope this information can help you.

Regards.
## Post #17
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-09-07T14:24:41+00:00
- Post Title: Re: Help with 15 days resource.xxx unpacking and repacking

Is that a real, working spanish language file? Is that work with the game?
## Post #18
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-09-07T15:07:28+00:00
- Post Title: Re: Help with 15 days resource.xxx unpacking and repacking

When I run the instalation, the game let me choose between English and spanish. It doesn't matter I chose the game always appear in english. More than that, I unpacked 909 and only include one subtitle folder with one file which contains 3 lines, ONLY three lines in English. For my experience translating videogames, i bet than in 910 file are the rest of english texts and spanish ones.

This version is multi 2 English-Spanish, with spanish blocked for any user cannot choose this language and futhermore, i cannot translate the game from english to spanish due the 909 only include a file (fmv_fluchtanimatic.subtitle) of 1 kb with three lines:

180-224, Quick! He's following us!
250-286, Are you all ok? - Sure
300-328, Let's go!.
0

I unpacked all the files with your tool and there is only a subtitle folder (in 909). The rests of the files must be in 910 file. It's the only versión that include a 910 file.

Do you remember the tool you make for Simon the Sorcerer and the  .dxxx files? It's the same, like a rar file. Well, you know more than me in this subject. 

Are you having any problem with 910 file?

Regards.

PD: My idea is unpack 910 and change the folders to make the program read the english folder and show the spanish texts.
## Post #19
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-09-08T04:17:41+00:00
- Post Title: Re: Help with 15 days resource.xxx unpacking and repacking

Forget your "resource.910" file! You won't find anything there, because it's just a crap. That's just a fake file, with useless, garbage data!!!

Bad news. There's not a special file with the game texts. The creators mixed the game texts into the other game data files.

Yes, the only clear text is in the "fmv_fluchtanimatic.subtitle" file.
The rest is digged inside these file types: "_01" (607 files!) "_03" (511 files!) and "_18" (3 files).
## Post #20
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-09-08T05:27:55+00:00
- Post Title: Re: Help with 15 days resource.xxx unpacking and repacking

Damn! What a crap! 

Well, thanks for your help my friend, and sorry for the lost of time.

Best regards.
## Post #21
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2011-01-02T16:59:14+00:00
- Post Title: Re: Help with 15 days resource.xxx unpacking and repacking

bacter, excellent job with your tool   

As well as good & concise format-specifications for these [pretty abominable] resource-files   

Top work m8
## Post #22
- Username: MiLOxentax
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 26, 2010 10:39 am
- Post datetime: 2011-12-10T03:50:21+00:00
- Post Title: Re: Help with 15 days resource.xxx unpacking and repacking

Sorry but where is the actual unpacker/extractor that we're talking about here? If it's Watoo Game Extractor than it doesn't open the recource files.
## Post #23
- Username: SashHD
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 18, 2012 4:31 am
- Post datetime: 2013-05-11T09:58:02+00:00
- Post Title: Re: Help with 15 days resource.xxx unpacking and repacking

Download the extractor for .909 again, please.
## Post #24
- Username: SergBrNord
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Feb 11, 2016 4:56 am
- Post datetime: 2016-02-23T11:40:10+00:00
- Post Title: Re: Help with 15 days resource.xxx unpacking and repacking

[http://aluigi.altervista.org/bms/15days.bms](http://aluigi.altervista.org/bms/15days.bms)
