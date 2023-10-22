## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-16T20:04:31+00:00
- Post Title: dark siders 2

hey guys iv been looking around here about this game i see people talking about the pc version and using offzip to unzip the files i wanted to know if this will work for the xbox verison? and if so what do i have to type in to extract the files if offzip doesnt work  can some one help make a script to unpack the core.pck file im willing to upload it it's 1.1gb big and the header is akpk i cant find any info on how to extract it
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-16T21:48:45+00:00
- Post Title: dark siders 2

its the same.
offzip -a c:\file c:\export 0
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-16T23:44:28+00:00
- Post Title: dark siders 2

im working to extract data with filenames (pc.mnfst)
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-17T06:06:09+00:00
- Post Title: dark siders 2

Try [this](http://forum.xentax.com/viewtopic.php?p=38696#p38696)
## Post #5
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-17T12:22:49+00:00
- Post Title: dark siders 2

> Reply from Ekey
>
> Try this
hey ekey that didnt work i will post a screen shot later
## Post #6
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-17T14:31:32+00:00
- Post Title: dark siders 2

> Reply from chrrox
>
> its the same.
offzip -a c:\file c:\export 0
hey chrrox it didnt work this is what i got 




(im uploading the file as we speak its going to take 3 hrs since its 1.1 gbs but i will be able to send it to anyone that willing to make a script and a unpacker)
## Post #7
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-08-17T18:52:29+00:00
- Post Title: dark siders 2

lllccc
For core.pck use Dragon Unpacker
And

```
FOR %%a in (*.wav) do ww2ogg.exe --pcb packed_codebooks_aoTuV_603.bin "%%a"
```
## Post #8
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-17T18:58:27+00:00
- Post Title: dark siders 2

> Reply from Haoose
>
> lllccc
For core.pck use Dragon Unpacker
And
Code: Select allFOR %%a in (*.wav) do ww2ogg.exe --pcb packed_codebooks_aoTuV_603.bin "%%a"
just one question does it repack files? 


*edit* so you now im not after the sound files i just want a stright extract off all the files in the .pck
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-17T19:01:32+00:00
- Post Title: dark siders 2

what's the exact situation of this game?
I mean if there is an unique file extension because I have seen various posts talking about archives or files having completelye different names and extensions like upks, bin, pck, mnfst and others.

what a chaos :)
## Post #10
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-17T19:04:47+00:00
- Post Title: dark siders 2

> Reply from aluigi
>
> what's the exact situation of this game?
I mean if there is an unique file extension because I have seen various posts talking about archives or files having completelye different names and extensions like upks, bin, pck, mnfst and others.

what a chaos

hey aluigi the headers are AKPK   and the extension  is pck  if you like i can upload the file so you can give it a look over
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-17T19:12:08+00:00
- Post Title: dark siders 2

ok hope it's not too big (more than 500mb), in which case just split it.

and what are all the other extensions?
where are they used?
## Post #12
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-17T19:16:16+00:00
- Post Title: dark siders 2

> Reply from aluigi
>
> ok hope it's not too big (more than 500mb), in which case just split it.

and what are all the other extensions?
where are they used?

its 1.1 gbs but im spliting them into 95 mbs each 
the only other header i see is sfx under hexeditor  and its one of main files for the game  if thats what you mean
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-17T20:05:56+00:00
- Post Title: dark siders 2

regarding the AKPK header I have 3 scripts that match it:
[http://aluigi.org/papers/bms/apb_pck.bms](http://aluigi.org/papers/bms/apb_pck.bms)
[http://aluigi.org/papers/bms/others/dea ... undpck.bms](http://aluigi.org/papers/bms/others/dead_nations_soundpck.bms)
[http://aluigi.org/papers/bms/others/ufc ... undpck.bms](http://aluigi.org/papers/bms/others/ufc2010_soundpck.bms)

maybe try them first.

then about the archive I prefer the first and last 10 megabytes if you can do it.
## Post #14
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-17T21:04:27+00:00
- Post Title: dark siders 2

> Reply from aluigi
>
> regarding the AKPK header I have 3 scripts that match it:
http://aluigi.org/papers/bms/apb_pck.bms
http://aluigi.org/papers/bms/others/dea ... undpck.bms
http://aluigi.org/papers/bms/others/ufc ... undpck.bms

maybe try them first.

then about the archive I prefer the first and last 10 megabytes if you can do it.

hey  first link didnt do anything  2ed link extracted 3 .dat files and 3rd did the same
but they all had errors 
for archive  i cant make them smaller then 95 mbs each  but its half way done now so it wont be longer
## Post #15
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-17T23:46:36+00:00
- Post Title: dark siders 2

> Reply from aluigi
>
> regarding the AKPK header I have 3 scripts that match it:
http://aluigi.org/papers/bms/apb_pck.bms
http://aluigi.org/papers/bms/others/dea ... undpck.bms
http://aluigi.org/papers/bms/others/ufc ... undpck.bms

maybe try them first.

then about the archive I prefer the first and last 10 megabytes if you can do it.
hey aluigi the files are in your inbox now ^_^
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-18T10:54:25+00:00
- Post Title: Re: dark siders 2

core.pck uses a format close to the one used in the sound archives of deadnation and ufc2010 games (the last 2 scripts posted before) but it's not the same.
the following is the correct script:

```
# script for QuickBMS http://quickbms.aluigi.org

endian big
idstring "AKPK"
goto 0x20
get DUMMYSZ long
getdstring DUMMY DUMMYSZ
get FILES long
for i = 0 < FILES
    get NAME_CRC long
    get ALIGNSZ long
    get SIZE long
    get OFFSET long
    get DUMMY long
    math OFFSET *= ALIGNSZ
    log "" OFFSET SIZE
next i
```

while for media.upak the situation is different and more chaotic because I don't see the filenames that probably are encrypted/obfuscated and I don't see the compressed size values so I suggest offzip for this archive.
## Post #17
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-08-18T11:38:41+00:00
- Post Title: Re: dark siders 2

> Reply from aluigi
>
> 
while for media.upak the situation is different and more chaotic because I don't see the filenames that probably are encrypted/obfuscated and I don't see the compressed size values so I suggest offzip for this archive.
It seems filenames and sizes for media.upak are stored in pc.mnfst.
## Post #18
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-08-18T13:35:28+00:00
- Post Title: Re: dark siders 2

Mh the script doesn't work on the core.pck and the en.pck for me.
## Post #19
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-18T14:44:59+00:00
- Post Title: Re: dark siders 2

> Reply from aluigi
>
> core.pck uses a format close to the one used in the sound archives of deadnation and ufc2010 games (the last 2 scripts posted before) but it's not the same.
the following is the correct script:
Code: Select all# DarkSiders II PCK archives
# script for QuickBMS http://quickbms.aluigi.org

endian big
idstring "AKPK"
goto 0x20
get DUMMYSZ long
getdstring DUMMY DUMMYSZ
get FILES long
for i = 0 < FILES
    get NAME_CRC long
    get ALIGNSZ long
    get SIZE long
    get OFFSET long
    get DUMMY long
    math OFFSET *= ALIGNSZ
    log "" OFFSET SIZE
next i
while for media.upak the situation is different and more chaotic because I don't see the filenames that probably are encrypted/obfuscated and I don't see the compressed size values so I suggest offzip for this archive.

iv tryied offzip and i  got and error 
chrrox wrote:
its the same.
offzip -a c:\file c:\export 0
i used that code and it didn't work unlesss you know an other code and that code extracted 1.12 gbs

and i didnt get the file you guy are talkng about (media.upak)
## Post #20
- Username: leoaires
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 06, 2012 9:06 am
- Post datetime: 2012-09-13T12:55:49+00:00
- Post Title: Re: dark siders 2

Anyone know a way to edit the files. .mnfst?
