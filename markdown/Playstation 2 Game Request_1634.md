## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-12-22T21:17:52+00:00
- Post Title: Playstation 2 Game Request

hello

i have request ps2 game
[Dead to rights 2.zip](https://xentaxbackup.github.io/file/500_Dead to rights 2.zip)
## Post #2
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-12-22T21:30:02+00:00
- Post Title: Playstation 2 Game Request

second request

MotoGp 3
[motogp3.zip](https://xentaxbackup.github.io/file/501_motogp3.zip)
## Post #3
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-12-22T21:43:47+00:00
- Post Title: Playstation 2 Game Request

third request

DarkWatch
[darkwatch.zip](https://xentaxbackup.github.io/file/502_darkwatch.zip)
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-23T02:01:30+00:00
- Post Title: Playstation 2 Game Request

OK, I have downloaded these (and the Obscure files too) and will look as soon as I can (may be a bit of a delay due to Christmas)

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-31T09:26:46+00:00
- Post Title: Playstation 2 Game Request

> Reply from sajad
>
> third request

DarkWatch

```
GoTo EOF 0 ;
SavePos END 0 ;
Math END -= 7 ;
GoTo END 0 ;
SavePos TailOffOff 0 ;
Get TailOffSet Long 0 ;
GoTo TailOffSet 0 ;
Get DIREntries Long 0 ;
Get FileNum Long 0 ;
Get U1 Long 0 ;
Get U2 Long 0 ;
SavePos FNOffset 0 ;
Math DIREntries *= 16 ;
Math FNOffset += DIREntries ;
Set C Long 0 ;
Do ;
Get U4 Long 0 ;
Get U5 Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos FP 0 ;
If U5 <> 0 ;
GoTo FNOffset 0 ;
Get U6 Long 0 ;
Get NameSize Long 0 ;
GetDString FName NameSize 0 ;
SavePos FNOffset 0 ;
Math C += 1 ;
Log FName FO FS FOO FSO ;
GoTo FP 0 ;
EndIf ;
While C < FileNum ;


```

[pck.zip](https://xentaxbackup.github.io/file/526_pck.zip)
## Post #6
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-12-31T10:03:35+00:00
- Post Title: Playstation 2 Game Request

hello mr mouse

thank you for script but when open package show error 
"process listfile failed : 6-overflow"
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-31T12:04:02+00:00
- Post Title: Playstation 2 Game Request

Woops! Small bug in the script ... fixed...scroll above for new version.
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-31T12:21:23+00:00
- Post Title: Playstation 2 Game Request

> Reply from sajad
>
> hello

i have request ps2 game

```
Get U1 Long 0 ;
Get U2 Long 0 ;
Get U3 Long 0 ;
Get FileNum Long 0 ;
For T = 1 To FileNum ;
GetCT FName String 10 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get U3 Long 0 ;
Log FName FO FS FOO FSO ;
Next T ;

```

[pak.zip](https://xentaxbackup.github.io/file/527_pak.zip)
## Post #9
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-12-31T20:36:32+00:00
- Post Title: Playstation 2 Game Request

mr mouse thank you again for scripts 

scripts "dead to right 2" work prefect 

but script darkwatch show error again (error above)
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-31T20:49:26+00:00
- Post Title: Playstation 2 Game Request

Could you attach the MultiEx Process log after the error? 

Options->View MultiEx Progress log

(I tested the script on the piece you sent me, and it worked.., the log may help).
## Post #11
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2006-01-01T19:31:44+00:00
- Post Title: Playstation 2 Game Request

hello mr mouse

excellent

work prefect third game request script 

darkwatch script work

thank you

but motogp 3 ?
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-01T20:20:40+00:00
- Post Title: Playstation 2 Game Request

I have failed to decipher the MotoGP format, it looks like the header is compressed/encrypted in some way. Sorry.   

How is it possible that the Darkwatch script now works? I thought you said it didn't?
## Post #13
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-02T13:38:11+00:00
- Post Title: Playstation 2 Game Request

Hi guys,

1. Darkwatch support is in the latest Game Extractor.
2. MotoGP 3 support (including decompression and repacking) will be in the next Game Extractor update.

MotoGP 3 (i had someone else ask about this one a few days ago) uses LZSS compression, which proved to be the main hinderence - I don't think I updated the wiki with the new specs yet but I will soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-02T16:25:47+00:00
- Post Title: Playstation 2 Game Request

Watto, the file Sajad gave us does not match the specs, because sajad gave a DAT file, not an ARK file.
## Post #15
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-02T20:31:53+00:00
- Post Title: Playstation 2 Game Request

Ah ok, I didn't realise that - I just assumed that he had sent the *.ark files, which are the main game archives. In that case, never mind 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #16
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2006-01-02T20:36:15+00:00
- Post Title: ps2

The contents of this post was deleted because of possible forum rules violation.
## Post #17
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-03T00:28:06+00:00
- Post Title: ps2

Hi mate,

I looked at the Indiana Jones archive - and it definately is an archive (I can see text files and DDS images in it), but there is no directory.

Are there any small files with the same name as the archive, but a different extension? For example, maybe there is a file called INDY.dir or INDY.idx?

If so, can you please send this to us, otherwise we cannot get the files out of this archive.

Thanks mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #18
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T06:43:48+00:00
- Post Title: ps2

I cannot see any DDS images in it, i can though see something with
a "MULTITEX" header, and the data stored there seems to be 8bit
indexed textured with sizes of 128x128 and 256x256 (etc etc).
(read raw successfully in photoshop with some artefacts)

by googling there seems to be something about Playstation 2 and
the multitex graphics format. didnt find much though.
## Post #19
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-03T12:18:19+00:00
- Post Title: ps2

Sorry, for clarification, I didn't find any complete DDS images, but I did find a lot of data that looked very similar to the image data of a DDS image. Many game archives with DDS images in them tend to strip them of their headers, so this is a possibility.

I think you can see some DDS-like bytes towards the end of the archive. Please feel free to correct me though 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #20
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T17:16:12+00:00
- Post Title: ps2

if you mean Back-indy.pk2 , then the structure looks like
some sample data ive found in either Silent Hill 3 or 4
from an ASF archive. it could be ADX sound.

=o
## Post #21
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2006-01-03T19:45:18+00:00
- Post Title: ps2

yes mr watto

iam find new file
[INDY.zip](https://xentaxbackup.github.io/file/548_INDY.zip)
## Post #22
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T19:57:59+00:00
- Post Title: ps2

Its the first hash index ive seen that 
actually stored everything in ASCII.

the structure is as follows.

String + Number + Number
(Filename+ Length of file + Start of file in archive)

example: GameInfo/Objectives.txt 6694 24576
file Objectives.txt is at position 24576 in archive and is 6694 bytes in size.

MIB files seems to be audio files.
MT2 files seems to be regular uncompressed texture data.
(containing multiple textures though, not just one per file)

PAK files seems to be map data and other config files.
STR files contains string files.
CFG files are...well..config files.
RPE files are speech files (possible RPE-LPT Speech codec)
SCC seems to be video files.

Converter for all files to standard formats should be possible. atleast what i think.
## Post #23
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2006-01-04T12:48:37+00:00
- Post Title: ps2

Crime Life Archive
[crime life.zip](https://xentaxbackup.github.io/file/555_crime life.zip)
## Post #24
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-04T15:29:29+00:00
- Post Title: ps2

So far only one value distinguished.
the 32 bit value before the entry names is the Length of the entry name.

=o
## Post #25
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2006-01-05T23:53:44+00:00
- Post Title: ps2

The contents of this post was deleted because of possible forum rules violation.
## Post #26
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-06T05:36:26+00:00
- Post Title: ps2

Hi mate,

Could you please make a larger File Cutter for the following games (maybe 1MB or 2MB or larger)...

- Crime Life: Gang Wars (PS2) *.dat
- True Crime 2 (PS2) *.pak

Thanks mate. Most of the other games you requested will be in the next update.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #27
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2006-01-06T09:22:53+00:00
- Post Title: ps2

The contents of this post was deleted because of possible forum rules violation.
## Post #28
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2006-01-06T18:24:53+00:00
- Post Title: ps2

The contents of this post was deleted because of possible forum rules violation.
## Post #29
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2006-01-13T15:15:20+00:00
- Post Title: ps2

The contents of this post was deleted because of possible forum rules violation.
## Post #30
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2008-05-30T14:42:12+00:00
- Post Title: ps2

The contents of this post was deleted because of possible forum rules violation.
[data.rar](https://xentaxbackup.github.io/file/1530_data.rar)
## Post #31
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-10T11:25:50+00:00
- Post Title: Re: Playstation 2 Game Request

Sorry for my extremely late response, but I have been busy... 

I will check the file out.
