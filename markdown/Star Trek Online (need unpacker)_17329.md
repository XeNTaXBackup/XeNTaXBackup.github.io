## Post #1
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2017-11-24T18:10:45+00:00
- Post Title: Star Trek Online (need unpacker)

Hi guys!! Recently I came across star trek online and models in this game are pretty good. My friend is ready to make a script to extract these models,but first you need to unpack Mset and wtex files. For those who are interested And ready to make unpacker, the samples below:) 

Mset female archives: [https://www.mediafire.com/file/a6rtlpf6tnzstxt/F.rar](https://www.mediafire.com/file/a6rtlpf6tnzstxt/F.rar)

Mset male archives:   [https://www.mediafire.com/file/hd24e905b93uthn/M.rar](https://www.mediafire.com/file/hd24e905b93uthn/M.rar)

Wtex archives:  [https://www.mediafire.com/file/67kb71he ... enbody.rar](https://www.mediafire.com/file/67kb71hes7k94h3/Femalealienbody.rar)
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-12-04T09:44:16+00:00
- Post Title: Star Trek Online (need unpacker)

Gibbed's tools: [http://svn.gib.me/builds/cryptic/](http://svn.gib.me/builds/cryptic/)
WTEX Decompiler: [viewtopic.php?f=18&t=4077](http://forum.xentax.com/viewtopic.php?f=18&t=4077)

Next time please use search button.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-04T16:01:35+00:00
- Post Title: Star Trek Online (need unpacker)

those wtex samples are crunch compressed, tools posted in that link won't work with them.
Noesis supports crunch and there is a python script here that works on some
[viewtopic.php?p=87769#p87769](http://forum.xentax.com/viewtopic.php?p=87769#p87769)

edit
ok here is modified Noesis python script to open all the wtex samples and possibly htex textures too, 
or at least the ones from this thread [viewtopic.php?f=18&t=15666&p=125609](http://forum.xentax.com/viewtopic.php?f=18&t=15666&p=125609) 
*script updated March 6, 2018*


 tex_StarTrekOnline_wtex_htex.zip
(806 Bytes) Downloaded 138 times



this might be the last update i make on this script, it is becoming more chaotic than anticipated.   
there are only a few textures i seen so far that are storing mipmaps first and i don't have enough
diverse samples to compare and confirm flags so i will give the users more control here.   
in the updated script on line 4 is where you can change to 0 or 1 (false or true),
it is set to 1 or true by default, so if you see a texture that displays with mipmaps first
you must change that line in the script and save and reload plugins, then you can export that texture
and it will look correct.   

i have also seen a htex texture that starts with a valid dds header but it stores mipmaps first and
Noesis will override any command i throw at it because it thinks the dds is normal.   
so i have made a bms script that you can run on those to get a fixed dds texture that you can open.

```

idstring "DDS "
get SIZE asize
get NAME basename
string NAME + _fixed.dds
goto 0x14
get DATASIZE long
xmath OFFSET "SIZE - DATASIZE"
append
log NAME 0x0 0x80
log NAME OFFSET DATASIZE
append

```
## Post #4
- Username: FleetAdmiral01
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 24, 2012 4:49 am
- Post datetime: 2018-02-04T05:46:30+00:00
- Post Title: Star Trek Online (need unpacker)

@lyutor1945

There was someone who made an extractor for STO's Mset files at one point. I think that project was dropped but I still have the file on hand. Shoot me a note.
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-02-12T17:23:45+00:00
- Post Title: Star Trek Online (need unpacker)

If you still have the program to unpack .mset models I'll make a maxscript for model import. So, if you have any unpacked .mset sample attach it here I will take a look. Thanks.
## Post #6
- Username: FleetAdmiral01
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 24, 2012 4:49 am
- Post datetime: 2018-03-05T07:48:33+00:00
- Post Title: Star Trek Online (need unpacker)

> Reply from zaramot
>
> If you still have the program to unpack .mset models I'll make a maxscript for model import. So, if you have any unpacked .mset sample attach it here I will take a look. Thanks.

I've still got it. 

[https://drive.google.com/file/d/0B3tos6 ... sp=sharing](https://drive.google.com/file/d/0B3tos6mChygEQ1FQVlladFBOREE/view?usp=sharing)
## Post #7
- Username: Regardie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 27, 2016 10:01 pm
- Post datetime: 2018-07-09T17:48:35+00:00
- Post Title: Star Trek Online (need unpacker)

Acewell:  if you need more textures from STO let me know as I have unpacked versions of the texture hoggs from last years version of the game sitting around and I am sure I can do the same with the current game.  A lot of work swapping textures in the game is going on at Undertow and they have been updating the hoggs toolset with each new release.
## Post #8
- Username: FriendCoder
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 02, 2018 12:21 pm
- Post datetime: 2018-11-27T03:57:50+00:00
- Post Title: Star Trek Online (need unpacker)

Hi @all.

Does anyone got the Costume<xxx>.bin Converted?

If, in xml would be awesome.

And also howto create Materials from Textures in 3d Apps (Blender would be nice, 2.8+)

Howto determin if Model needs Mirroring?

Is there something about the Skeletons as Information out there?

Wouldnt it be cool to have the Picard-Maneuver as an Animation?

@Acewell: thx for the script noesis works much better now.
## Post #9
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-02-01T14:30:07+00:00
- Post Title: Star Trek Online (need unpacker)

> Reply from Acewell ↑Tue Dec 05, 2017 12:01 am at Tue Dec 05, 2017 12:01 am
>
> 
those wtex samples are crunch compressed, tools posted in that link won't work with them.
Noesis supports crunch and there is a python script here that works on some
http://forum.xentax.com/viewtopic.php?p=87769#p87769

edit
ok here is modified Noesis python script to open all the wtex samples and possibly htex textures too, 
or at least the ones from this thread http://forum.xentax.com/viewtopic.php?f ... 6&p=125609 
*script updated March 6, 2018*
tex_StarTrekOnline_wtex_htex.zip

this might be the last update i make on this script, it is becoming more chaotic than anticipated.   
there are only a few textures i seen so far that are storing mipmaps first and i don't have enough
diverse samples to compare and confirm flags so i will give the users more control here.   
in the updated script on line 4 is where you can change to 0 or 1 (false or true),
it is set to 1 or true by default, so if you see a texture that displays with mipmaps first
you must change that line in the script and save and reload plugins, then you can export that texture
and it will look correct.   

i have also seen a htex texture that starts with a valid dds header but it stores mipmaps first and
Noesis will override any command i throw at it because it thinks the dds is normal.   
so i have made a bms script that you can run on those to get a fixed dds texture that you can open.
Code: Select all# script for QuickBMS http://aluigi.altervista.org/quickbms.htm

idstring "DDS "
get SIZE asize
get NAME basename
string NAME + _fixed.dds
goto 0x14
get DATASIZE long
xmath OFFSET "SIZE - DATASIZE"
append
log NAME 0x0 0x80
log NAME OFFSET DATASIZE
append

That Noesis script doesn't seem to work anymore for textures, I get the following error when viewing and trying to export .wtex textures:
## Post #10
- Username: DMStealth
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 22, 2018 9:49 pm
- Post datetime: 2021-07-22T07:31:05+00:00
- Post Title: Star Trek Online (need unpacker)

> Reply from Assasinge ↑Mon Feb 01, 2021 10:30 pm at Mon Feb 01, 2021 10:30 pm
>
> 
That Noesis script doesn't seem to work anymore for textures, I get the following error when viewing and trying to export .wtex textures:

Sorry for bumping old topics but I think I have the solution for those interested.

Put the crunchimage.dll found in Noesis/optionalplugins into the Noesis/plugins directory.

EDIT: This is using a more recent Noesis (mine's Noesis version 4.451).

Script has worked fine after that. There are a few that don't work but I believe they're the ones with the DDS header.
## Post #11
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2021-10-07T06:57:19+00:00
- Post Title: Star Trek Online (need unpacker)

> Reply from Acewell ↑Tue Dec 05, 2017 12:01 am at Tue Dec 05, 2017 12:01 am
>
> 
those wtex samples are crunch compressed, tools posted in that link won't work with them.
Noesis supports crunch and there is a python script here that works on some

I've tried converting these .wtex crunch files with the commandline executable crunch.exe, and they all fail.
'Error: CRN unpack failed'

v1.01 crunch
[https://code.google.com/archive/p/crunch/downloads](https://code.google.com/archive/p/crunch/downloads)

v1.04 crunch
[https://github.com/BinomialLLC/crunch](https://github.com/BinomialLLC/crunch)

I made sure the files start with the magic id 'Hx', but they still fail.  Is there anything unusual about these .wtex crunch files?  Header data looks similar to crunch files created with the commandline tool, so I don't understand why they're not getting converted.

Interestingly enough, the crunch file format stores two crc16 values, one for the header and one for the data.  I recomputed it to compare against the .wtx crunch files, and I get mixed results.  So, something is wrong.
## Post #12
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-11-15T20:45:36+00:00
- Post Title: Star Trek Online (need unpacker)

Hi,everyone!
I wanna tool for converting wtex to dds (or any other formats)

I try different methods,like Quick bms and wtex to dds tools, but it not working for many textures (created dds does'n open in photoshop, irfran,noesis or nvidia tools)

Any luck with?
I attach example
[C_Dragon_Turtle_Body_01_C.7z](https://xentaxbackup.github.io/file/23039_C_Dragon_Turtle_Body_01_C.7z)
## Post #13
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-11-15T20:48:48+00:00
- Post Title: Star Trek Online (need unpacker)

> Reply from roswell ↑Thu Oct 07, 2021 2:57 pm at Thu Oct 07, 2021 2:57 pm
>
> 
Acewell wrote: ↑Tue Dec 05, 2017 12:01 am
those wtex samples are crunch compressed, tools posted in that link won't work with them.
Noesis supports crunch and there is a python script here that works on some


I've tried converting these .wtex crunch files with the commandline executable crunch.exe, and they all fail.
'Error: CRN unpack failed'

v1.01 crunch
https://code.google.com/archive/p/crunch/downloads

v1.04 crunch
https://github.com/BinomialLLC/crunch

I made sure the files start with the magic id 'Hx', but they still fail.  Is there anything unusual about these .wtex crunch files?  Header data looks similar to crunch files created with the commandline tool, so I don't understand why they're not getting converted.

Interestingly enough, the crunch file format stores two crc16 values, one for the header and one for the data.  I recomputed it to compare against the .wtx crunch files, and I get mixed results.  So, something is wrong.

How to use this tool?
